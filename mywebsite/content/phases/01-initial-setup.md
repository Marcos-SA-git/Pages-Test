---
title: "Fase 1 - Configuración inicial"
---

## Objetivo

Preparar la base del laboratorio en VMware Workstation para soportar una arquitectura segmentada, con OPNsense como router/firewall central y con el DHCP centralizado en el propio router.

El objetivo funcional inmediato de esta fase es:

1. Crear las redes virtuales que representarán los distintos segmentos del laboratorio.
2. Desplegar las máquinas virtuales base.
3. Desactivar el DHCP integrado de VMware.
4. Preparar OPNsense para asumir el rol de router y servidor DHCP.
5. Conseguir que un cliente Ubuntu pueda conectarse a un servidor Ubuntu y visualizar una web simple.

## Alcance

Esta fase se centra en la preparación inicial del entorno, no en el despliegue completo del laboratorio.

Incluye:

[hold](https://dsafa.com/)

- diseño inicial de subredes
- creación de VMs base
- conexión de interfaces virtuales
- preparación de OPNsense como punto central de red

No incluye todavía:

- DNS interno
- Active Directory
- SSO
- monitorización
- backups
- publicación externa
- conectividad offsite/cloud

## Arquitectura inicial

### Redes definidas

- 10.10.10.0/24 -> Administración / Gestión
- 10.10.20.0/24 -> Servidores
- 10.10.30.0/24 -> Clientes
- 10.10.40.0/24 -> IoTs
- 10.10.50.0/24 -> DMZ
- 10.10.60.0/24 -> Backup
- 10.20.10.0/24 -> Offsite
- 10.0.0.0/24 -> Extra
- 10.30.10.0/24 -> Cloud

### Máquinas virtuales desplegadas

- **Ubuntu Client**
    - Rol: cliente de prueba
    - Red actual: Clientes

- **Ubuntu Server**
    - Rol: servidor de prueba
    - Red actual: Clientes

- **OPNsense**
    - Rol: router/firewall central
    - Interfaces: conectado a todos los adaptadores virtuales definidos en VMware

## Estado actual de la topología

En el estado actual, tanto el cliente como el servidor se encuentran en la red de clientes.

Esto permite validar:

- obtención de IP por DHCP
- conectividad básica
- acceso a una web simple

Pero todavía no valida una segmentación real entre cliente y servidor a través del router, ya que ambos equipos comparten el mismo segmento.

## Decisiones tomadas

- Se utiliza **VMware Workstation** como plataforma de virtualización principal.
- Se desactiva el **DHCP integrado de VMware** en todos los adaptadores virtuales.
- El servicio DHCP será gestionado por **OPNsense**.
- Se define desde el inicio un esquema de direccionamiento con subredes separadas por función, aunque no todas se utilicen todavía en esta fase.
- OPNsense se despliega como punto central de interconexión entre todas las redes del laboratorio.

## Configuración realizada

### VMware Workstation

- Se han creado múltiples adaptadores virtuales para representar redes separadas.
- Cada red representa una futura VLAN lógica dentro del laboratorio.
- El DHCP de VMware ha sido desactivado en todos los adaptadores para evitar solapamiento con OPNsense.

### OPNsense

- Se ha desplegado una máquina virtual con conexión a todos los adaptadores virtuales necesarios para actuar como router/firewall central.
- Queda pendiente:
    - asignación definitiva de interfaces
    - configuración del DHCP
    - definición de reglas de firewall
    - pruebas de conectividad

### Ubuntu Client

- Máquina desplegada y conectada a la red de clientes.

### Ubuntu Server

- Máquina desplegada y conectada actualmente a la red de clientes.
- Su función en esta fase será alojar una web simple accesible desde el cliente.

## Objetivo funcional inmediato

Una vez configurado OPNsense:

1. Cliente y servidor deben obtener IP de forma controlada.
2. El cliente debe poder conectarse al servidor.
3. El servidor debe exponer una web simple.
4. El acceso a la web debe validarse desde el cliente.

## Validación prevista

Se considerará esta fase validada cuando se cumplan estas condiciones:

- OPNsense entrega IP por DHCP
- Cliente recibe IP correctamente
- Servidor recibe IP correctamente o queda configurado según la estrategia elegida
- Cliente puede resolver y alcanzar al servidor por IP
- Cliente puede visualizar una web simple servida desde Ubuntu Server

## Limitaciones actuales

- Cliente y servidor están en la misma red, por lo que aún no se está validando routing entre segmentos.
- El diseño de múltiples redes ya está preparado, pero la topología todavía no aprovecha toda la segmentación prevista.

## Siguiente paso

Mover el servidor a la red de servidores (`10.10.20.0/24`) y dejar el cliente en la red de clientes (`10.10.30.0/24`) para validar comunicación real entre segmentos a través de OPNsense.

Después:

- activar DHCP en la red de clientes
- decidir si el servidor usará DHCP o IP estática
- crear reglas mínimas de firewall
- desplegar una web simple y probar acceso desde el cliente

## Aprendizajes de esta fase

- Es preferible diseñar el esquema de direccionamiento desde el inicio, aunque no se utilicen aún todas las redes.
- Centralizar DHCP en OPNsense simplifica el control del laboratorio.
- Tener varias redes definidas desde el principio facilita la futura segmentación por roles.
- Una topología aparentemente correcta puede no estar validando routing real si varios equipos permanecen en la misma red.
