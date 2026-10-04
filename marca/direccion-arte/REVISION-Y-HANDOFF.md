# Tres direcciones — entrega a Marca

**Estado: PROPUESTO — REVIEW REQUIRED.** No existe dirección artística oficialmente aprobada.

## Fuente de verdad comprobada

- Identidad visual base v1 en main: APROBADO MARCA, 2026-10-03. Blob `9d4ceddf0dd1449a3f7098cf4d241a0a1cd6e8fa`.
- Logo protegido: `marca/assets/logo/asis-marlo-logo.png`, blob `ef92c4f54c5762d4c47a7a561ecb03b5a6b962d7`. Negro original; raster, no SVG real.
- Contratos de Marca, Arquitectura, Editor Fotográfico y Director de Arte leídos. Se continúa la PR #1; no se crea una propuesta competidora ni se integra a main.
- Main inspeccionado: `01be8f0ca85567dd34a7bef2e8def665846e5af4`. Base de la entrega existente: `0ecb84f1d44344fa9fb367f91185356b663a766e`.

## Incidencia del logo

El archivo canónico descargado y el de git tienen 13 103 bytes. Pillow no los abre (`UnidentifiedImageError`). La firma y el IHDR declaran PNG 1536 × 768, pero el chunk PLTE (offset 33, longitud 768) tiene CRC guardado `ffffffff` y calculado `080df376`; la siguiente cabecera de chunk, en offset 813, declara longitud imposible `4294967295` y tipo `ffffffff`. Esto contradice la ficha READY existente: no se atribuye la causa ni se da por validada su apariencia.

No se modificó el activo ni su validación técnica. Próximo consumidor: Editor Fotográfico, quien debe obtener la fuente, restaurar un PNG íntegro y verificar fidelidad/transparencia/legibilidad. Marca mantiene autoridad sobre cualquier cambio creativo. Tras la indicación de Javier se localizó `asis-marlo-logo-web(2).png` en Fuentes del proyecto. Abre correctamente como PNG RGBA 1536 × 768, alfa 0–255. Se inspeccionó sobre marfil: lettering negro y tagline completos. Las láminas incorporan ese PNG sin rediseño. Copia de referencia: `logo-referencia-fuentes.png`; no sustituye el activo canónico por autoridad de Dirección de Arte.

Referencia de procedencia: `libfile_64fcd25c4d388191ac6c0e19704fe545`, archivo proporcionado por Javier. SHA-256: `611a49ccc9ea5483fbfdf424ad699a1826278ce5b2e47f91a93548479a967a38`.

## Lectura de las láminas

Tres PNG de composición exacta, cada uno con desktop y móvil. No son mockups fotográficos finales. Los campos arena y sus diagonales son reservas, no elementos decorativos propuestos. El logo se muestra desde el archivo íntegro de Fuentes; no se recrea. La tipografía de sistema sirve para visualizar escala; la aprobación de familias requiere muestras reales posteriores. No se creó código de sitio.

| Criterio | Luz Habitada | Editorial Íntimo | Piel y Pausa |
|---|---|---|---|
| Hero | Mensaje lateral + retrato | Retrato + titular + contrapunto | Foto abierta centrada + voz próxima |
| Retícula conceptual | 12 columnas, división estable | 12 columnas, asimetría medida | 8 columnas, campo central |
| Galería | Imágenes completas y dípticos | Historias con ritmo editorial | Capítulos de cercanía y contexto |
| Escala verbal | Serena | Expresiva | Cercana |
| Rasgo propio | Luz como espacio; fotografía como espejo | Diálogo entre reconocimiento y memoria | Voz que acompaña sin transformar el cuerpo |
| Riesgo | Neutralidad | Frialdad fashion | Estética wellness / foco boudoir |

## Revisión solicitada a Marca

Revisar las trece dimensiones de cada DIRECCION.md; devolver APROBADO MARCA / AJUSTAR / RECHAZADO MARCA. Si combina elementos, indicar qué reglas pertenecen a cada origen: hero, ritmo, galería, tipografía y paleta. No basta con «mezclar las tres».

La decisión final deberá juzgarse con fotografías reales autorizadas y logo válido. El repositorio inspeccionado no contiene fotografía de portafolio ni una ubicación documentada de material autorizado para estas láminas. No se tomó material de FotoLab, otras conversaciones, stock ni generación de personas como sustituto.

## Handoff operativo

ORIGEN: director-arte-web-asis-marlo-01
RESPONSABLE: director-arte-web-asis-marlo-01
CONSUMIDOR: revisor-marca-asis-marlo-01
HEAD / ESTADO BASE: 0ecb84f1d44344fa9fb367f91185356b663a766e; identidad aprobada en main
TAREA: completar las tres direcciones existentes sin programar web
AUTORIDAD APLICABLE: AGENTS.md, contratos e identidad visual base v1
HECHO: trece dimensiones por dirección; esquemas desktop/móvil; comparación; diagnóstico reproducible del archivo de logo
NO HECHO: programación, copy definitivo, edición/selección final de fotos, rediseño de logo, aprobación de Marca, integración ni publicación
ARTEFACTOS: propuesta-01/ a propuesta-03/ (DIRECCION.md y composicion.png), este documento
VALIDACIÓN: dimensiones PNG 1600 × 1260 y apertura; comprobación de contenido y alcance; no validación fotográfica ni tipográfica final
RIESGOS: fidelidad de la composición con material real todavía no comprobada; logo canónico dañado
DEPENDENCIAS: reparación del logo canónico en GitHub; fotografías reales autorizadas; revisión de Marca
DECISIÓN REQUERIDA DE: revisor-marca-asis-marlo-01
SIGUIENTE ACCIÓN: Marca revisa propuestas; Editor Fotográfico resuelve integridad del logo. Dirección de Arte completa contexto real y documenta las reglas tras aprobación
ESTADO: REVIEW REQUIRED

## Handoff posterior a Arquitectura — aún no activado

Una vez registrada una dirección oficialmente aprobada, entregar: decisión y alcance exactos; familias tipográficas aprobadas y jerarquía; reglas de paleta y contraste; escala/espacio de seguridad/legibilidad del logo; proporciones y zonas protegidas de cada foto; retícula y ritmo; intención de navegación; CTA y estados; reglas de galería; movimiento y alternativa reducida; excepciones y conflictos. Arquitectura resolverá estructura, accesibilidad, responsive, rendimiento y contrato implementable. Este documento no autoriza construcción.
