---
title: "Incidencia 01 - Conflicto entre VMware y características de virtualización de Windows"
summary: "test"
i_software:
    - VMware
i_services:

i_phases:
    - phase-0
issue_types:
    - virtualización
---

## Síntoma

VMware no disponía de acceso completo a las capacidades de virtualización del equipo, lo que impedía un funcionamiento correcto del entorno.

Errores presenciados:

- Virtualized AMD-V/RVI is not supported on this platform.

## Causa

Varias características de virtualización de Windows entraban en conflicto con VMware Workstation.

## Impacto

El laboratorio no podía ejecutarse con normalidad o quedaba limitado para ciertos escenarios.

## Solución aplicada

Se desactivaron las características de Windows que interferían con el acceso de VMware a la virtualización.

## Aprendizaje

Antes de montar un laboratorio serio en VMware sobre Windows, conviene validar primero la compatibilidad de la capa de virtualización del sistema anfitrión.
