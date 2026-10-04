# Subir activos binarios a GitHub desde agentes

**Estado:** GUÍA OPERATIVA  
**Repositorio:** `vaisork/Asis.Marlo`  
**Fecha:** 2026-10-04  
**Origen de la guía:** flujo validado por `editor-fotografico-web-asis-marlo-01`

## Objetivo

Documentar el procedimiento correcto para que los agentes puedan incorporar archivos binarios reales —por ejemplo PNG, JPG, WebP u otros activos— al repositorio cuando la acción normal `create_file`/`update_file` del conector de GitHub sólo admita contenido UTF-8.

Esta guía describe **transporte y escritura de archivos**. No concede autoridad para crear, modificar, aprobar o publicar activos fuera del contrato de cada agente.

## Regla fundamental: ruta temporal != ruta del repositorio

Los archivos recibidos o generados por herramientas pueden existir temporalmente en rutas como:

```text
/mnt/data/archivo.png
```

Esa ruta pertenece al entorno temporal de herramientas y **no es la ubicación permanente del proyecto**.

La ruta definitiva es la que se escribe en el árbol de GitHub, por ejemplo:

```text
marca/assets/logo/asis-marlo-logo.png
```

Cada agente debe obtener la ruta canónica de su contrato, Arquitectura o la documentación vigente. No debe inventarla por conveniencia.

## Flujo validado para archivos binarios

Cuando el conector exponga Git Data API, utilizar:

```text
archivo local real
    ↓
leer bytes
    ↓
Base64
    ↓
GitHub create_blob (encoding = base64)
    ↓
SHA del blob
    ↓
create_tree
    ↓
create_commit
    ↓
update_ref(rama autorizada)
    ↓
volver a leer/verificar en GitHub
```

### 1. Preparar el archivo local

El activo debe existir como archivo binario real en el filesystem, normalmente bajo `/mnt/data/`.

Antes de subirlo se debe comprobar, según corresponda:

- formato real;
- dimensiones;
- canal alfa/transparencia;
- perfil/color;
- calidad visual;
- peso;
- que no haya corrupción.

### 2. Codificar los bytes en Base64

Leer los **bytes** del archivo y codificarlos en Base64.

Base64 se usa únicamente como mecanismo de transporte hacia GitHub. **No se guarda el texto Base64 dentro de un archivo `.png`, `.jpg`, `.webp`, etc.**

### 3. Crear el blob

Invocar `create_blob` con:

```text
repository_full_name: <repositorio correcto>
encoding: base64
content: <Base64 de los bytes reales>
```

Guardar el SHA devuelto.

GitHub decodifica el Base64 y almacena un blob binario real.

### 4. Obtener HEAD y árbol base actuales

Antes de construir el commit, volver a comprobar el HEAD de la rama autorizada. No trabajar sobre un SHA antiguo si otro agente pudo haber actualizado la rama.

Obtener:

- SHA del commit HEAD;
- SHA de su árbol.

### 5. Crear el árbol

Usar `create_tree` con el árbol base actual y añadir cada activo mediante una entrada equivalente a:

```text
path: <ruta definitiva dentro del repositorio>
mode: 100644
type: blob
sha: <SHA devuelto por create_blob>
```

Ejemplo de Asis Marlo:

```text
path: marca/assets/logo/asis-marlo-logo.png
mode: 100644
type: blob
sha: <blob SHA>
```

El `path` del árbol es la ubicación permanente. Nunca utilizar `/mnt/data/...` como ruta de repositorio.

### 6. Crear el commit

Crear un commit cuyo:

- `tree_sha` sea el árbol recién creado;
- `parent_sha` sea el HEAD comprobado;
- mensaje explique claramente los activos incorporados.

### 7. Actualizar la rama autorizada

Mover únicamente la rama que el flujo del proyecto autorice mediante `update_ref`.

Cuando la herramienta lo permita, utilizar comprobación del SHA esperado para evitar pisar trabajo concurrente. Si HEAD cambió, no forzar silenciosamente: reconstruir el árbol/commit sobre el nuevo HEAD o seguir el flujo de integración correspondiente.

### 8. Verificación obligatoria

Después de actualizar la rama:

1. volver a consultar HEAD;
2. comprobar que apunta al commit esperado;
3. volver a leer la ruta definitiva desde GitHub;
4. comprobar que el contenido existe como binario esperado;
5. registrar ruta, commit y validaciones relevantes.

No declarar un activo “subido” sólo porque `create_blob` haya funcionado. Un blob aislado todavía no forma parte de la rama hasta completar árbol, commit y ref.

## Subida de múltiples activos

No es necesario crear un commit por imagen.

Para un lote:

1. preparar todos los archivos;
2. crear un blob por archivo;
3. conservar cada SHA;
4. incluir todos los blobs en **un único `create_tree`**;
5. crear un único commit coherente;
6. actualizar la rama una sola vez;
7. verificar el lote.

Esto reduce commits innecesarios y mantiene juntas las entregas que pertenecen a la misma unidad de trabajo.

## Qué NO hacer

- No declarar que GitHub no admite imágenes sólo porque `create_file` acepte únicamente UTF-8.
- No meter Base64 como texto dentro de un archivo con extensión de imagen.
- No renombrar un raster a `.svg`.
- No encapsular un raster en SVG y declararlo “vector real”.
- No usar `/mnt/data/...` como ruta permanente del repositorio.
- No actualizar `main` u otra rama si el agente no tiene autorización para hacerlo.
- No forzar una actualización de rama para ocultar un conflicto de concurrencia.
- No afirmar que el activo está integrado hasta verificarlo desde GitHub.

## Orden recomendado antes de declarar BLOCKED

Si una acción concreta no acepta binarios, el agente debe comprobar las capacidades reales disponibles:

1. archivo adjunto o filesystem montado;
2. Python/shell para leer y transformar bytes cuando esté permitido;
3. Git local + acceso remoto si existe;
4. GitHub `create_blob` con Base64 + `create_tree` + `create_commit` + `update_ref`;
5. cualquier acción binaria equivalente disponible en su entorno.

Sólo declarar `BLOCKED` cuando no exista una ruta correcta dentro de las herramientas disponibles. El reporte debe indicar qué capacidades se comprobaron y la limitación concreta.

## Caso validado: logo Asis Marlo

Este procedimiento se validó incorporando el PNG transparente canónico:

```text
marca/assets/logo/asis-marlo-logo.png
```

mediante:

```text
/mnt/data/... → bytes → Base64 → create_blob → create_tree → create_commit → update_ref(main)
```

El commit de validación fue:

```text
2e695ad41c358b25abb1970b9dc162576b9d9042
```

El activo fue posteriormente leído desde GitHub para confirmar su presencia en `main`.

## Autoridad

Esta guía no sustituye `AGENTS.md`, los contratos firmados ni las decisiones de Marca/Arquitectura. Antes de escribir un activo, cada agente debe verificar que:

- tiene autoridad para trabajar ese activo;
- conoce la rama autorizada;
- conoce la ruta canónica;
- respeta WIP y concurrencia;
- preserva originales cuando el contrato lo exija;
- realiza las validaciones propias de su especialidad.
