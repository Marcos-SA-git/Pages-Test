---
title: 'Proced. 01 - Primer acceso a OPNsense por GUI'
summary: 'Cómo configurar OPNsense la primera vez y acceder a la GUI para más configuraciones.'
date: '2026-05-27T02:42:07+02:00'
draft: true

c_type:
    - procedure

p_software:
    - opnsense
    - ubuntu
p_services:
    - dhcp
    - routing
p_phases:
    - fase 01
network_areas:
    - internet
    - administración
    - clientes
    - servers
---

## Propósito

Iniciar y configurar OPNsense por primera vez y acceder a la GUI desde un equipo conectado a la interfaz de red de administración

## Requisitos

- OPNsense instalado.
    - Interfaces de red NAT, Administracion, Clientes y Servers conectadas.
- Máquina del administrador instalada. (Ubuntu en este caso)
    - Conectado únicamente a la interfaz de Administración.

## Pasos

### 1. Iniciar OPNsense e iniciar sesión

Cuando salga la linea de "login", introducir el siguiente usuario y contraseña por defecto:

- root
- opnsense

### 2. Asignar las interfaces

La primera vez que iniciamos OPNsense, este no sabe qué interfaces son para WAN, LAN u opcionales. En un router real, podría no ser tan evidente qué cable y/o puerto de red es para internet, u otras redes.

En este caso, al ser una máquina virtual, el orden que seguirá se puede ver en la configuración de esta. Y, si hemos configurado las interfaces poniendo primero la NAT y luego el orden de la arquitectura del proyecto, estarán en orden durante el resto de la configuración, siguiendo así el orden óptimo.

Una vez iniciamos sesión, marcamos la opción "(1) Assign Interfaces":

- Configurar LAGGs ahora? -> N
- Configurar VLANs ahora? -> N
- Interfaz WAN? -> em0
- Interfaz LAN? -> em1
- Interfaz OPT1? -> em2
- Interfaz OPT2? -> em3

Una vez asignadas estas 4 interfaces de momento, sin marcar nada más, pulsamos `<Enter>` y confirmamos que esas son las interfaces que queremos configurar marcando `Y`. Así, volveremos al menú.

### 3. Configurar la red de administración

La red LAN, sería la interfaz de administración, que, por defecto, es la que permite la conexión a la GUI para administrar el router de maneras más cómodas y avanzadas.

Para ello, hay que asignar una IP y por comodidad se habilitará el DHCP en esta interfaz. Para hacer esta configuración, marcar la opción "(2) Set interface IP address".

> Inicio

- Seleccionar interfaz -> 1 (LAN)

- Configurar esta interfaz por/con DHCP? -> N

> Dirección del router

- Introducir la IPv4 del router en esta interfaz -> 10.10.10.1
- Introducir la máscara de red CIDR -> 24

>Puerta de enlace externa

- Configurar una puerta de enlace externa para la red? -> N

> IPv6

- Configurar IPv6 por/con WAN tracking? -> N
- Configurar IPv6 por/con DHCP? -> N
- Introduce la IPv6 del router en esta interfaz -> Saltar presionando `<Enter>`

> DHCP

- Configurar DHCP IPv4 en esta interfaz? -> **Y**
- IP de inicio: 10.10.10.100
- IP de fin: 10.10.10.200

> Web GUI

- Cambiar protocolo de la web de HTTPS a HTTP? -> N
- Crear un nuevo certificado para la web GUI? -> **Y**
- Restablecer los ajustes por defecto de la web GUI? -> **Y**

Esperar a que termine de configurarse la interfaz y vuelva al menú.

Si la configuración se completó correctamente, se verá en el menú que la interfaz LAN em1 tiene configurada la IPv4 previamente introducida.

### 4. Iniciar MV del administrador y conectarse a la Web GUI

Tras iniciar sesión en la máquina de administrador, en la configuración de red, debería verse que se ha conectado satisfactoriamente y habrá una IPv4 entre el rango de 10.10.10.100 y x.x.x.200.

Logrado esto, si se introduce la dirección IP de la puerta de enlace en el navegador, debería de acceder correctamente a la configuración del router, que en este caso es la 10.10.10.1.

## Validación

## Resolución de problemas

## Notas
