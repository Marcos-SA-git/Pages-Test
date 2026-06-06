---
title: 'Fase 0 - Infraestructura'
summary: 'Preparación inicial del entorno de virtualización, redes base y host local del laboratorio.'
date: '2026-04-16T20:00:18+02:00'
draft: false

c_type:
    - Fases

phasesnum:
    - Fase 00
software: 
    - vmware-workstation
services:
    - virtualización
    - segmentación de red
network_areas:
---

## Objetivo

Definir la base inicial del laboratorio, incluyendo la elección de la plataforma de virtualización, la preparación del host, la planificación de redes virtuales y las primeras comprobaciones de funcionamiento.

## Punto de partida

Dado que, de manera inicial, todo se va a ejecutar de manera virtual en mi ordenador local, estas son sus características:

| Componente | Descripción |
| :--------: | ----------- |
| Sistema Operativo | Windows 11 Pro - 25H2 - Ver: 26200.8246 - x64 |
| CPU | AMD Ryzen 5 3600X - 6-Núcleos / 12-Hilos |
| RAM | 32 GB DDR4 Corsair |
| GPU | AMD Radeon RX 5700XT 8GB |
| Almacenamiento | NVMe Crucial 2TB + NVMe Sabrent 1TB + SATA HDD Seagate 2TB |
| Red | 1 Gbps Ethernet LAN Link + 800Mbps Up/Down Fibra WAN Link |

## Arquitectura en esta fase

### Plataforma de virtualización

Se ha optado por VMware Workstation Pro por su uso extendido en entornos profesionales y por las características que ofrece para crear Máquinas Virtuales (MVs), redes aisladas y escenarios de laboratorio complejos.

### Segmentación inicial de red

Dentro de la configuración de VMware, en el editor de redes virtuales de VMware, definimos los siguientes adaptadores de red con el siguiente rango de red y descripción. (Véase [ADR 01](../adr/01-addressing-and-segmentation.md))

- `10.10.10.0/24` -> Administración / Gestión
- `10.10.20.0/24` -> Servidores
- `10.10.30.0/24` -> Clientes
- `10.10.40.0/24` -> IoT
- `10.10.50.0/24` -> DMZ
- `10.10.60.0/24` -> Backup
- `10.20.10.0/24` -> Offsite
- `10.0.0.0/24` -> Extra
- `10.30.10.0/24` -> Cloud

Estos segmentos no tendrán DHCP gestionado por VMware, ya que la asignación de direcciones será responsabilidad del router/firewall desplegado en la siguiente fase.

## Cambios introducidos

- Instalación de VMware Workstation Pro.
- Habilitación de la virtualización de CPU.
- Creación de los segmentos de red según la arquitectura planteada.
- Desactivación del servicio DHCP de VMware.

## Validación

- VMware se instaló correctamente.
- Los adaptadores de red añadidos aparecen en la configuración de red del host.

Al finalizar esta fase el resultado es como se muestra a continuación:
![Diagrama Fase 0](img/phases/Fase_0.svg)

## Problemas encontrados y aprendizajes

**Problema:** Las interfaces de red instaladas por defecto de VMware están sujetas a ciertas propiedades dentro del software que limitan la personalización. (Véase [Incid. 01](../incidents/01-vmware-net-limitations.md))

**Aprendizaje:** Los adaptadores configurados por defecto de VMware poseen roles reservados y no conviene forzarlos o cambiarlos para cumplir otras funciones. Para desarrollar una arquitectura limpia y completamente personalizada se optó por crear adaptadores de red nuevos y controlados.

## Limitaciones actuales

- No se han desplegado MVs.
- No hay servicios funcionales tales como DHCP, routing, DNS, etc.
- No hay conectividad entre redes.
- La segmentación de redes solo existe a nivel de adaptadores de red en la configuración de VMware, no en un entorno de MVs reales.

## Siguiente paso

Crear el primer entorno virtual con conectividad básica:

- Desplegar varias MVs:
    - Un servidor.
    - Un cliente.
    - Un router.
- Configurar routing y firewall para permitir la conexión entre todos los elementos.
- Desplegar en el servidor una web y verificar el correcto acceso desde el cliente.

---

> *[Siguiente Fase](01-initial-setup.md)*
