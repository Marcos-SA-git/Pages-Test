---
title: 'Incid. 01 - Limitaciones de red en VMware' 
summary: 'Comportamiento inesperado al modificar adaptadores VMnet reservados de VMware Workstation Pro.'
date: '2026-04-30T17:19:21+02:00'
draft: false

c_type:
    - incident

i_software:
    - vmware-workstation
i_services:
    - nat
    - segmentación de red
    - redes virtuales
i_phases:
    - fase 0
i_issue_types:
    - limitación de configuración
network_areas:
    - 
---

## Síntoma

Los adaptadores de red configurados por defecto en VMware Workstation Pro no permiten ser editados con la misma libertad que uno añadido con posterioridad. Esto se observó cuando:

- El adaptador `VMnet1` no permite cambiar su nombre.
- Al intentar mover la función NAT de `VMnet8` (configurado por defecto) a otro adaptador creado manualmente, las máquinas virtuales no obtenía salida a Internet al configurarse para usar NAT en los ajustes del adaptador de red.

## Contexto

A la hora de configurar la arquitectura de red que se usa como base de este laboratorio, se procuró que todos los adaptadores fueran en un orden predecible.

Se empezó por intentar editar el `VMnet1` que es uno de los adaptadores instalados por defecto, e ir añadiendo el resto desde ahí pasando también por el `VMnet8` para seguir este orden.

## Comportamiento esperado

Se esperaba poder editar estas interfaces incluidas como otras cualquiera, pudiendo cambiar nombre y configuración, generando un comportamiento predecible al de un adaptador nuevo añadido.

## Causa raíz

Los adaptadores configurados por defecto parecen cumplir roles concretos y reservados para el correcto funcionamiento de VMware.

## Impacto

No tiene un impacto real en el proyecto.

Obliga a aceptar cierto desorden en la configuración de los adaptadores de virtuales.

## Solución aplicada

Evitar modificar o usar los adaptadores de red de fábrica y añadir nuevos que sí permiten su personalización completa.

## Validación tras la corrección

Tras apreciar este comportamiento, se restauró la configuración por defecto del editor de redes virtuales de VMware, se crearon nuevos adaptadores personalizados con las características necesarias evitando manipular los instalados por defecto y, tras probar su uso en máquinas virtuales, estos se comportaron según lo esperado.

## Aprendizajes

VMware trae configuración por defecto con roles predeterminados que conviene dejar como están para que VMware se comporte como se espera en ciertos escenarios.

Así pues, conviene:

- No modificar ni usar los VMnet reservados salvo que haya una razón clara.
- Crear redes adicionales para el laboratorio.
