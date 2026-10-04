# Asis Marlo — contrato de logo y activos visuales para web

**Estado:** CONTRATO DE ARQUITECTURA WEB  
**Responsable:** `arquitecto-web-asis-marlo-01`  
**Autoridad de marca:** `revisor-marca-asis-marlo-01` / Asis Marlo  
**Fecha:** 2026-10-03

## Objetivo

Definir qué archivos necesita Arquitectura/Desarrollo para utilizar correctamente el logo de **Asis Marlo — Esencia, Piel y Luz** en la web y qué controles debe realizar el Editor Fotográfico Web antes de declarar un activo técnicamente utilizable.

Este documento **no autoriza rediseñar el logo**. La identidad visual vigente protege el logo actual y la fotografía debe seguir siendo protagonista.

## Ubicación canónica

Los activos aprobados o candidatos de marca destinados a la web deben vivir bajo:

```text
marca/
└── assets/
    └── logo/
```

La documentación de marca permanece en `marca/`.

Desarrollo no debe buscar el logo en chats, capturas de pantalla, WhatsApp, carpetas temporales o archivos descargados sin trazabilidad si existe una versión canónica en el repositorio.

## Formato maestro esperado

### 1. SVG — preferido para web

El formato maestro web preferido es **SVG vectorial real**.

Requisitos:

- trazos y formas limpios;
- `viewBox` correcto;
- sin fondo opaco accidental;
- proporción original preservada;
- sin imágenes raster incrustadas que aparenten ser vector;
- sin recursos externos rotos;
- sin metadatos innecesarios o contenido extraño;
- debe renderizar correctamente a tamaños pequeños y grandes;
- no debe cambiar visualmente el logo aprobado.

Convertir automáticamente un JPG/PNG a `.svg` **no lo convierte en un logo vectorial válido**. Si sólo existe una imagen raster, debe conservarse como tal hasta que una vectorización fiel sea revisada y aprobada por Marca.

Nombre recomendado:

`asis-marlo-logo.svg`

### 2. PNG transparente — respaldo obligatorio si está disponible

Debe existir una versión PNG de alta calidad cuando sea necesaria como respaldo, referencia o para contextos incompatibles con SVG.

Requisitos recomendados:

- fondo transparente real;
- sin halos blancos o negros en bordes;
- proporción original preservada;
- sin recortes accidentales;
- sin artefactos JPEG;
- espacio de color apropiado para pantalla, preferentemente sRGB;
- resolución suficientemente alta para generar derivados sin degradación.

Como fuente raster, se recomienda aproximadamente **2000–3000 px de ancho** cuando el original permita esa resolución real. No se debe ampliar artificialmente una imagen pequeña sólo para alcanzar esa cifra.

Nombre recomendado:

`asis-marlo-logo.png`

### 3. Fuente vectorial original — conservación

Si Asis dispone del original en AI, EPS o PDF vectorial, debe conservarse como fuente de marca. No es necesariamente el archivo que cargará el navegador.

No convertir, simplificar o reinterpretar esa fuente sin autorización.

## Variantes

No crear automáticamente versiones blanca, negra, clara, oscura, monocromática, isotipo, favicon o reducida.

Cada variante que cambie el tratamiento visual del logo requiere validación de Marca.

Una vez aprobadas, deben tener nombres inequívocos y quedar documentadas. Desarrollo nunca debe inferir una variante aplicando filtros CSS, inversión de color o recoloreado arbitrario al logo protegido.

## Calidad mínima del logo

Antes de entregar un logo a Desarrollo, el Editor Fotográfico Web debe comprobar:

1. **Fidelidad:** coincide visualmente con el logo aprobado por Marca.
2. **Integridad:** no faltan letras, trazos, tagline ni partes del diseño.
3. **Proporción:** no está estirado ni comprimido.
4. **Bordes:** no presenta halos, dientes o artefactos evitables.
5. **Transparencia:** cuando corresponda, el canal alfa es limpio.
6. **Resolución:** el raster tiene resolución fuente suficiente para su uso previsto.
7. **Vector real:** si se declara SVG, las formas son realmente vectoriales o se documenta cualquier excepción.
8. **Color:** no se han alterado colores respecto al activo aprobado.
9. **Encuadre:** no existe recorte accidental ni margen destructivo.
10. **Legibilidad:** debe evaluarse especialmente el tagline `Esencia, Piel y Luz` a los tamaños web previstos.
11. **Peso:** debe ser razonable para web sin degradar visualmente el activo.
12. **Trazabilidad:** se conoce qué archivo fue recibido, qué transformación técnica se realizó y cuál fue el resultado.

## Qué puede corregir técnicamente el Editor Fotográfico Web

Cuando su contrato lo autorice, puede preparar un derivado técnico para web mediante acciones no creativas como:

- eliminar fondo no deseado si el original demuestra que debe ser transparente;
- limpiar halos o artefactos de exportación;
- recortar espacio vacío técnico sin alterar composición protegida;
- convertir de manera fiel a un formato web adecuado;
- optimizar peso sin pérdida visual relevante;
- corregir perfil de color para consistencia web;
- generar dimensiones derivadas desde una fuente de mayor calidad;
- documentar que un archivo recibido no tiene calidad suficiente.

Estas acciones deben preservar la apariencia aprobada.

## Qué NO puede decidir el Editor Fotográfico Web

Sin aprobación de Marca no puede:

- redibujar el logo;
- cambiar tipografía;
- cambiar espaciado entre letras por criterio propio;
- mover o eliminar `Esencia, Piel y Luz`;
- modificar proporciones internas;
- cambiar colores;
- añadir sombras, brillos, texturas, contornos o efectos;
- crear un isotipo nuevo;
- reinterpretar el logo;
- declarar una nueva variante como oficial;
- sustituir el logo por una recreación generada por IA.

Si el original tiene una limitación que sólo puede solucionarse alterando el diseño, el estado es **BLOCKED POR MARCA**, no “corregido”.

## Entrega esperada del Editor Fotográfico Web

Para cada activo preparado debe dejar un registro equivalente a:

```text
ACTIVO: logo
FUENTE RECIBIDA:
FORMATO FUENTE:
DIMENSIONES / VIEWBOX:
TRANSFORMACIONES TÉCNICAS:
CAMBIOS CREATIVOS: NINGUNO
ARCHIVO RESULTANTE:
FORMATO:
DIMENSIONES / VIEWBOX RESULTANTE:
TRANSPARENCIA: OK / N/A / PROBLEMA
COLOR: OK / PROBLEMA
BORDES: OK / PROBLEMA
LEGIBILIDAD: OK / LIMITACIÓN
FIDELIDAD AL ORIGINAL: OK / REQUIERE MARCA
PESO:
LISTO TÉCNICAMENTE PARA WEB: SÍ / NO
APROBACIÓN DE MARCA REQUERIDA: SÍ / NO
OBSERVACIONES:
```

**“Listo técnicamente para web” no significa “aprobado por Marca”.** Son estados diferentes.

## Relación con la identidad visual vigente

El Editor debe leer antes de actuar:

1. `/AGENTS.md`
2. su contrato en `/agentes/`
3. `/marca/identidad-visual-base-v1.md`
4. este documento `/marca/LOGO-Y-ACTIVOS-WEB.md`
5. cualquier decisión de Marca posterior que afecte al logo.

Si dos documentos de Marca se contradicen, debe detener el cambio afectado y pedir resolución al `revisor-marca-asis-marlo-01`. No debe escoger silenciosamente la interpretación que resulte más cómoda.

## Handoff a Desarrollo

Desarrollo sólo debe consumir como activo canónico un logo que:

- tenga archivo exacto identificable;
- haya pasado revisión técnica para su uso previsto;
- no contenga cambios creativos no aprobados;
- tenga claro su estado de aprobación de Marca;
- esté ubicado bajo `marca/assets/logo/` o en la ubicación posterior explícitamente definida por Arquitectura.

La eventual copia/transformación hacia una carpeta pública del framework será responsabilidad de implementación. `marca/assets/logo/` conserva la fuente de verdad de marca para el proyecto.

## Estado

**CONTRATO DE ARQUITECTURA LISTO PARA CONSUMO — 2026-10-03.**

— `arquitecto-web-asis-marlo-01`
