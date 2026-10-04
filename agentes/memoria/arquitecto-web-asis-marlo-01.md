# Memoria persistente — arquitecto-web-asis-marlo-01

**Propósito:** permitir que una nueva sesión, ChatGPT Work u otra instancia que asuma `arquitecto-web-asis-marlo-01` recupere rápidamente el contexto operativo sin depender del historial de chat.

**Regla:** este archivo resume contexto y decisiones. No sustituye `AGENTS.md`, el contrato del agente ni las decisiones formales de `marca/`. Ante contradicción, prevalece la fuente formal correspondiente.

**Última actualización:** 2026-10-03

## Identidad y autoridad

- Proyecto: **Asis Marlo — Esencia, Piel y Luz**.
- Repositorio: `vaisork/Asis.Marlo`.
- Rama fuente de verdad: `main`.
- Agente: `arquitecto-web-asis-marlo-01`.
- Javier Díaz dirige el proyecto, asigna agentes, alcance y prioridades no delegadas.
- Arquitectura Web manda sobre estructura web.
- Dirección/Revisión de Marca manda sobre identidad y coherencia de marca.
- Arquitectura debe traducir Marca a una web construible; no sustituirla.
- WIP=1 por agente.

## Intención de marca que Arquitectura debe preservar

La experiencia debe sentirse femenina, íntima, elegante, artística, cálida, natural, contemporánea, profesional y auténtica.

La fotografía es protagonista.

Evitar especialmente:

- rosa dominante;
- romanticismo cliché;
- glamour artificial;
- dorado ostentoso;
- boudoir convencional/genérico;
- oscuridad predominante;
- frialdad clínica;
- interfaz de plantilla que compita con las fotografías.

Referencia sensorial vigente: **piel + lino + madera + luz natural entrando por una ventana + fotografía editorial**.

La identidad formal completa debe leerse en `marca/identidad-visual-base-v1.md`.

## Paleta aprobada actualmente

- Carbón / espresso: `#292522`.
- Marfil cálido: `#F5F0E9`.
- Arena / piedra: `#D8C9BA`.
- Rosa viejo / nude: `#A9827C`.
- Champagne apagado: `#B49A78`.

El logo actual está protegido; no está autorizado rediseñarlo.

## Documentos creados por Arquitectura

- `/AGENTS.md` — gobierno operativo, autoridad, fronteras y sistema de agentes.
- `/agentes/arquitecto-web-asis-marlo-01.md` — contrato firmado del Arquitecto.
- `/marca/LOGO-Y-ACTIVOS-WEB.md` — contrato técnico para logo y activos web.
- `/agentes/memoria/arquitecto-web-asis-marlo-01.md` — este archivo de continuidad.

## Logo — decisión operativa vigente

Ubicación canónica definida por Arquitectura:

`marca/assets/logo/`

Archivo previsto actualmente:

`marca/assets/logo/asis-marlo-logo.png`

Preferencia para producto final web:

1. SVG vectorial real cuando exista una fuente fiel y aprobada.
2. PNG transparente de alta calidad como respaldo/fuente raster.
3. Conservar original AI/EPS/PDF vectorial si Asis dispone de él.

No crear variantes clara/oscura/monocromática/isotipo/favicon por iniciativa propia; cambios visuales requieren Marca.

## Editor Fotográfico Web — aprendizaje operativo

El Editor reportó haber preparado un PNG real de aproximadamente `1536×768`, transparente y sin cambios creativos, pero inicialmente se declaró bloqueado para subirlo a GitHub.

Se confirmó mediante experiencia de otro agente que los binarios PNG pueden integrarse con GitHub Git Data API usando este flujo:

`archivo en /mnt/data → leer bytes → Base64 → create_blob(encoding=base64) → create_tree → create_commit → update_ref(main) → verificar`

Puntos críticos:

- `/mnt/data/...` es temporal; NO es la ruta permanente del proyecto.
- `create_file/update_file` de texto UTF-8 no es la vía para PNG.
- El Base64 se usa como transporte hacia `create_blob`; NO se guarda como texto dentro de un `.png`.
- El tree debe apuntar al SHA del blob con `mode: 100644`, `type: blob` y la ruta definitiva.
- Antes de crear commit/mover `main`, volver a consultar HEAD para evitar trabajar sobre un SHA obsoleto.
- Después de escribir, verificar que la ruta exista realmente en GitHub.
- Para lotes, pueden crearse varios blobs y añadirse todos a un único tree/commit.

Esta técnica debe reutilizarse para futuros activos binarios cuando el agente tenga las acciones Git Data necesarias.

## Criterio sobre tipos de agente

Javier preguntó qué funciones conviene ejecutar como ChatGPT Work.

Recomendación actual:

- **Arquitecto Web:** Work — recomendado por coordinación multietapa, lectura continua del repo, dependencias y contratos.
- **Director de Arte Web:** Work — recomendado cuando exista formalmente.
- **Integrador Web:** Work — recomendado cuando exista formalmente.
- **Programador/Desarrollo:** Codex para implementación fuerte.
- **Revisor de Marca:** chat normal puede ser suficiente.
- **Editor Fotográfico Web:** chat normal puede ser suficiente.
- Copy/SEO/QA pueden empezar como especialistas normales y escalar a Work cuando la carga lo justifique.

No crear estos agentes automáticamente. Javier asigna y autoriza cada función.

Javier indicó que probablemente convertirá esta misma función de Arquitecto en Work. Debe conservarse el identificador `arquitecto-web-asis-marlo-01`; no crear un segundo arquitecto sólo por cambiar de modo de ejecución.

## Estado del proyecto al cerrar esta memoria

- Gobierno del proyecto: creado.
- Arquitecto Web: registrado y firmado.
- Identidad visual base v1: aprobada por Marca y disponible en `marca/`.
- Contrato técnico del logo: creado.
- Estructura concreta de páginas: todavía no debe asumirse cerrada sólo por esta memoria.
- Stack tecnológico: no decidido por esta memoria.
- Programación del sitio: no autorizada por esta memoria.
- Logo: el Editor está intentando completar su integración binaria siguiendo el flujo Git Data API descrito arriba.

## Protocolo de recuperación para una nueva sesión / Work

Al asumir esta función:

1. Leer `/AGENTS.md` completo.
2. Leer `/agentes/arquitecto-web-asis-marlo-01.md`.
3. Leer este archivo.
4. Leer todas las decisiones vigentes en `/marca/`, no sólo las resumidas aquí.
5. Revisar HEAD de `main` y cambios posteriores a la fecha de esta memoria.
6. Revisar agentes registrados, issues/PRs/handoffs relevantes y trabajo activo antes de actuar.
7. No asumir que este archivo refleja cambios ocurridos después de su última actualización.
8. Actualizar esta memoria cuando una conversación produzca una decisión, aprendizaje operativo, cambio de autoridad o estado que sea necesario para continuidad futura y que no esté ya suficientemente registrado en otra fuente formal.

## Regla para futuras actualizaciones de memoria

No copiar conversaciones completas. Registrar sólo:

- decisiones tomadas;
- autoridad responsable;
- estado actual;
- rutas/artefactos importantes;
- bloqueos y su causa real;
- aprendizajes técnicos reutilizables;
- próximos pasos relevantes;
- cambios de rol o forma de operación.

Si una decisión merece autoridad formal propia, crear/actualizar su documento correspondiente y en esta memoria guardar únicamente el enlace/ruta y un resumen.
