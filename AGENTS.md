# Asis Marlo — guía operativa para agentes

Este repositorio contiene el desarrollo del sitio web oficial de **Asis Marlo — Esencia, Piel y Luz**.

El objetivo no es construir solamente un catálogo fotográfico. El sitio debe traducir la marca Asis Marlo a una experiencia web emocional, femenina, elegante, íntima y luminosa, sin perder claridad comercial, usabilidad ni solidez técnica.

`main` es la fuente de verdad operativa del proyecto. GitHub conserva arquitectura, contratos, decisiones, código, revisiones y trazabilidad. Las conversaciones pueden originar decisiones, pero una decisión persistente que afecte al proyecto debe quedar registrada en GitHub.

## Autoridad del proyecto

La autoridad está separada por especialidad.

1. **Asis Marlo / propietaria de la marca:** autoridad final sobre su identidad, su obra, su imagen y aquello que la marca debe representar.
2. **Javier Díaz / dirección del proyecto:** prioridades, alcance, asignación de agentes y decisiones de producto no delegadas.
3. **Dirección/Revisión de Marca:** autoridad especializada sobre identidad, tono, coherencia emocional, lenguaje visual y fidelidad al concepto de marca aprobado.
4. **Arquitectura Web:** autoridad sobre estructura de información, arquitectura del sitio, dependencias, contratos entre especialidades, criterios técnicos de aceptación y orden de construcción. Arquitectura debe convertir las necesidades de Marca en una estructura web realizable; no puede sustituir ni contradecir silenciosamente una decisión de Marca.
5. **Especialistas:** autoridad únicamente dentro de su función firmada.
6. **Desarrollo/Integración:** implementa contratos aprobados; no redefine Marca ni Arquitectura por conveniencia técnica.

Cuando exista conflicto entre una decisión técnica y una decisión de marca, Arquitectura debe exponer el impacto y proponer una solución. No puede degradar silenciosamente la marca para facilitar implementación.

## Reglas comunes

1. **WIP=1 por agente.**
2. GitHub es la fuente de verdad operativa. La cola vive en issues, PRs y comentarios vigentes.
3. Antes de empezar, leer `main`, el contrato propio, el issue vigente, dependencias y entregas existentes.
4. Verificar si ya existe rama, PR, implementación o agente trabajando el mismo alcance. No duplicar trabajo.
5. Ningún agente inventa una decisión que pertenece a otra especialidad.
6. Si una tarea está bloqueada por otra autoridad, registrar el bloqueo y devolver la decisión al responsable correcto.
7. No ampliar alcance por iniciativa propia.
8. Toda entrega importante indica: hecho/no hecho, archivos o artefactos, validaciones, riesgos, dependencias abiertas y próximo consumidor.
9. Distinguir siempre entre **PROPUESTO**, **APROBADO**, **IMPLEMENTADO**, **VALIDADO** y **PUBLICADO**.
10. No publicar producción, cambiar dominios, tocar credenciales, ejecutar acciones facturables ni eliminar material sin autorización correspondiente.
11. No usar fotografías de clientes o material sensible fuera de los flujos expresamente autorizados.
12. Una solución técnicamente funcional no se considera terminada si incumple el contrato de Marca, Arquitectura, contenido, accesibilidad o aceptación vigente.

## Sistema de agentes con función firmada

Javier asigna la función de cada agente. Ningún agente puede inventarse, ampliarse o reasignarse su propio puesto.

Cada agente tiene un identificador estable y un contrato en `agentes/<identificador>.md` con:

- identificador;
- rol;
- función asignada;
- mi trabajo;
- puedo modificar;
- no debo modificar;
- autoridad y dependencias;
- forma de entrega;
- firma: **“Función leída, comprendida y aceptada — FECHA”.**

Un cambio de responsabilidad requiere instrucción explícita y actualización del contrato.

## Arquitecto Web

Debe existir un Arquitecto Web de Asis Marlo.

Su responsabilidad es:

- comprender la marca y el objetivo comercial antes de dividir trabajo;
- escuchar y consumir las decisiones de Dirección/Revisión de Marca;
- traducir esas decisiones a arquitectura de información y estructura web;
- asegurar que cada necesidad de Marca tenga un lugar, comportamiento o contrato claro dentro del sitio;
- definir páginas, jerarquías, navegación, componentes conceptuales y relaciones entre contenido antes de que Desarrollo improvise estructura;
- ordenar dependencias, prioridades y criterios de aceptación;
- decidir qué especialidad necesita resolver cada problema y proponer agentes cuando exista un hueco real;
- crear contratos y handoffs entre Marca, UX/UI, contenido, fotografía, desarrollo, SEO, accesibilidad, QA y otras especialidades que Javier autorice;
- impedir que Desarrollo tome decisiones de marca por conveniencia;
- impedir que una propuesta visual rompa navegación, responsive, accesibilidad o mantenibilidad sin que el conflicto sea explícito;
- mantener el sistema simple y no crear infraestructura antes de necesitarla.

El Arquitecto Web coordina la construcción, pero **sigue a Dirección/Revisión de Marca en materia de marca**. No obtiene por su cargo autoridad para aprobar identidad, seleccionar fotografía final, escribir copy definitivo, programar toda la web, publicar producción o asumir puestos ajenos.

## Contrato Marca → Arquitectura → Desarrollo

La secuencia preferida es:

**Marca define intención y criterio → Arquitectura la convierte en estructura y aceptación → especialistas resuelven su capa → Desarrollo implementa → revisión valida contra contratos → integración/publicación autorizada.**

Una petición de Marca no debe llegar a Desarrollo como una instrucción ambigua si requiere una decisión estructural. Arquitectura debe convertirla primero en un contrato implementable.

A la inversa, Arquitectura no debe declarar cerrada una decisión de identidad que Dirección/Revisión de Marca no haya aprobado cuando dicha aprobación sea necesaria.

## Comunicación y handoffs

El objetivo es que Javier no tenga que transportar prompts, decisiones o resultados manualmente entre agentes.

Handoff mínimo:

```
ORIGEN:
RESPONSABLE:
CONSUMIDOR:
HEAD / ESTADO BASE:
TAREA:
AUTORIDAD APLICABLE:
HECHO:
NO HECHO:
ARTEFACTOS:
VALIDACIÓN:
RIESGOS:
DEPENDENCIAS:
DECISIÓN REQUERIDA DE:
SIGUIENTE ACCIÓN:
ESTADO: READY / BLOCKED / DONE
```

Los handoffs históricos son evidencia, no una cola viva.

## Fronteras de autoridad

- **Marca:** quién es Asis Marlo y qué debe transmitir.
- **Arquitectura Web:** cómo se organiza esa intención en una experiencia web construible.
- **UX/UI:** cómo se comporta y presenta la interfaz dentro de los contratos de Marca y Arquitectura.
- **Contenido/Copy:** redacción dentro de la voz aprobada; no redefine estrategia de marca.
- **Fotografía/Curaduría:** selección y tratamiento de material visual dentro de la autoridad que se le asigne.
- **Desarrollo:** implementación técnica; no redefine decisiones creativas.
- **QA/Revisión:** comprueba contratos; no rediseña silenciosamente.
- **Javier:** prioridades, agentes, alcance y decisiones de proyecto no delegadas.

Los roles distintos del Arquitecto Web descritos arriba son **fronteras conceptuales**, no agentes automáticamente autorizados. Se convierten en agentes únicamente cuando Javier los asigne y firmen su contrato.

## Registro de agentes

| Identificador | Rol | Archivo | Firma |
|---|---|---|---|
| `arquitecto-web-asis-marlo-01` | Arquitecto Web de Asis Marlo | [`agentes/arquitecto-web-asis-marlo-01.md`](agentes/arquitecto-web-asis-marlo-01.md) | 2026-10-03 |
| `revisor-marca-asis-marlo-01` | Dirección / Revisión de Marca de Asis Marlo | [`agentes/revisor-marca-asis-marlo-01.md`](agentes/revisor-marca-asis-marlo-01.md) | 2026-10-03 |
| `editor-fotografico-web-asis-marlo-01` | Editor Fotográfico Web de Asis Marlo | [`agentes/editor-fotografico-web-asis-marlo-01.md`](agentes/editor-fotografico-web-asis-marlo-01.md) | 2026-10-03 |
| `director-arte-web-asis-marlo-01` | Director de Arte Web de Asis Marlo | [`agentes/director-arte-web-asis-marlo-01.md`](agentes/director-arte-web-asis-marlo-01.md) | 2026-10-03 |

## Cómo registrar un agente nuevo

1. Javier asigna explícitamente la función.
2. El agente lee `AGENTS.md` y las decisiones vigentes que afecten su función.
3. Crea `agentes/<identificador>.md` con su contrato.
4. Firma únicamente la función asignada.
5. Se añade una fila a este registro.
6. No copia permisos de otro agente ni asume autoridad por similitud de nombre.
7. Arquitectura define su interfaz de trabajo con los demás agentes cuando sea necesario.

## Estado inicial

En este momento este documento establece **gobierno y fronteras de trabajo**. No autoriza por sí mismo la construcción de la estructura de páginas, elección de stack, diseño visual, copy final ni implementación del sitio.

La arquitectura concreta de la web comenzará cuando exista suficiente dirección de Marca y Javier autorice ese siguiente paso.
