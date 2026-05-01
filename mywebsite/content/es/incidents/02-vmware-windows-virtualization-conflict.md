---
title: "Incid. 02 - Conflicto entre VMware y características de virtualización de Windows"
summary: "Conflicto entre VMware Workstation y funciones de virtualización de Windows que impedía el acceso completo a AMD-V/RVI y podía limitar escenarios avanzados del laboratorio."
date: '2026-04-30T00:23:21+02:00'
draft: false

i_software:
    - vmware-workstation
i_services:
    - virtualización
i_phases:
    - fase 1
i_issue_types:
    - conflicto
    - seguridad
---

## Síntoma

VMware no disponía de acceso completo a las capacidades de virtualización del equipo, lo que impedía un funcionamiento correcto del entorno.

Errores presenciados:

`Virtualized AMD-V/RVI is not supported on this platform.`

## Contexto

A la hora de ejecutar una máquina virtual, en su configuración, si se aplicaba alguna de las opciones en `Procesadores -> Motor de virtualización`, al iniciar la máquina virtual daba el error comentado.

A pesar de no impedir la ejecución de la máquina virtual, para evitar futuros problemas con la virtualización, se decidió investigar y solucionar el problema.

## Causa raíz

Varias características de virtualización de Windows entraban en conflicto con VMware Workstation ya que también hacían uso de los mecanismos de virtualización del host.

## Impacto

El laboratorio podría no ejecutarse con normalidad o quedar limitado en ciertos escenarios futuros.

## Solución aplicada

Se desactivaron las características de Windows que interferían con el acceso de VMware a la virtualización. Concretamente:

- Hyper-V
- Windows Hypervisor Platform
- Virtual Machine Platform
- Memory Integrity / Core Isolation
- Credential Guard / VBS

## Validación tras la corrección

Tras desactivar las características anteriores, al ejecutarse la máquina virtual, esta ya no daba mensajes de error.

## Aprendizaje

- Windows usa virtualización para algunas funciones de seguridad y del sistema.
- Dichas funciones pueden entrar en conflicto con VMware Workstation.
- Estos conflictos son esperados y se priorizó la compativilidad con VMware por accesibilidad para las pruebas.
- En fases más avanzadas tendría sentido migrar a herramientas más dedicadas de virtualización como ESXi, Proxmox o KVM.
