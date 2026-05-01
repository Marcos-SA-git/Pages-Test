---
title: 'Fase 1 - Primeros entornos'
summary: 'Primer entorno funcional del laboratorio con router OPNsense, cliente, servidor web y conectividad básica entre subredes.'
date: '2026-05-01T00:42:50+02:00'
draft: true

c_type:
    - phase

phasesnum:
    - fase 01
software:
    - vmware-workstation
    - opnsense
    - ubuntu
    - ubuntu-server
    - python
services:
    - dhcp
    - firewall
    - routing
    - servidor web
    - segmentación de red
network_areas:
    - gestión
    - clientes
    - servidores
---


## PENDIENTE DE HACER EN ESTE DOCUMENTO:

- TAL VEZ SEA BUENO AÑADIR UN PROCEDIMIENTO Y HACER REFERENCIA A ÉL SOBRE CÓMO DAR ACCESO TOTAL A VMWARE SOBRE LA VIRTUALIZACIÓN.



## Objetivo

## Alcance

## Punto de partida

## Arquitectura en esta fase

## Cambios introducidos

- 

## Resumen de configuración

## Validación

## Problemas encontrados

**Problema:** Se identificó un [conflicto entre Windows 11 y VMware](../incidents/01-vmware-windows-virtualization-conflict.md), ya que algunas funciones de seguridad de Windows basadas en virtualización impedían que VMware accediera correctamente a las capacidades de virtualización del sistema.

## Aprendizajes

**Aprendizaje:** Algunas protecciones de Windows y VMware pueden competir por el control de la virtualización. Para este laboratorio, se priorizó la compatibilidad de VMware, aceptando el compromiso de reducir ciertas protecciones del host.

## Limitaciones actuales

## Siguiente paso

---

> Enlace a la siguiente fase
