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
    - admin
    - clientes
    - servidores
---


## PENDIENTE DE HACER EN ESTE DOCUMENTO:

- TAL VEZ SEA BUENO AÑADIR UN PROCEDIMIENTO Y HACER REFERENCIA A ÉL SOBRE CÓMO DAR ACCESO TOTAL A VMWARE SOBRE LA VIRTUALIZACIÓN.



## Objetivo

Crear un ambiente básico donde 2 equipos cliente-servidor pueden comunicarse correctamente por medio de un routing y firewall simples.

## Alcance

En esta fase se aborda:

- La instalación de máquinas virtuales iniciales.
- Configuración básica de OPNsense.
- DHCP por interfaz/subred.
- Servidor web básico.
- Reglas básicas de HTTP en el Firewall.
- Comunicación básica cliente-servidor.

No se incluye aún:

- Salida a Internet formal
- DNS
- VLANs
- Tráfico de red controlado y avanzado.

## Punto de partida

Se parte teniendo el software de virtualización, y los adaptadores virtuales de red configurados y listos para su uso.

## Arquitectura en esta fase

### Sistemas operativos

Los sistemas operativos por los que se han optado para esta fase inicial por simplicidad son:

- OPNsense como router/firewall.
- Dos instancias de Ubuntu 24.04 como cliente (GUI) y como PC del administrador
- Ubuntu mini 18.04 como servidor (CLI)

Tras previa investigación, se escogió OPNsense como la mejor alternativa de routing de código abierto y gratuita usada en ambientes profesionales. Y se incluyeron las versiones de ubuntu con y sin interfaz gráfica para practicar en ambos entornos.

### Conexiones

Para esta primera puesta en marcha, se configuran 4 interfaces de red en el router: `WAN` (VMnet8), `LAN` (Admin), `OPT1` (Servidores) y `OPT2` (Clientes).

Sin embargo, en esta fase usaremos solo las de clientes y servidores por simplicidad, deshabilitando también la interfaz WAN.



## Cambios introducidos

- Instalación de las primeras 3 MVs.
- Configuración inicial del router **OPNsense**:
    - Configuración de interfaces de red.
    - Servicio DHCP configurado para las interfaces *Servidores* y *Clientes*

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
