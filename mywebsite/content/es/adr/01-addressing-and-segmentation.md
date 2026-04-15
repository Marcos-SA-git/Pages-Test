---
title: "01 - Esquema de direccionamiento y segmentación inicial"
summary: "Decidir cuáles serían las direcciones de red usadas y su propósito."
c_type:
    - decision

a_software:
    - opnsense
    - vmware-workstation

a_services:
    - routing
    - network-segmentation

a_phases:
    - phase-0

network_areas:
    - management
    - clients
    - servers
    - IoT
    - DMZ
    - backup
    - offsite
    - cloud
---

## Estado

Aceptado

## Contexto

El laboratorio necesita crecer de forma progresiva hacia una arquitectura con múltiples zonas:

- gestión
- servidores
- clientes
- IoT
- DMZ
- backup
- offsite
- cloud

Si el direccionamiento no se define desde el principio, el crecimiento posterior generará solapamientos, renumeración innecesaria y documentación inconsistente.

## Decisión

Se adopta un esquema basado en subredes /24 dentro del espacio privado 10.0.0.0/8, usando una convención interna donde:

- Primer octeto representa la "clase" de red. `10.x.x.x`
- Segundo octeto representa lugar o entorno. `x.10.x.x`
- Tercer octeto representa uso, función o segmento. `x.x.10.x`

Se definen inicialmente estas redes:

- `10.10.10.0/24` -> Administración / Gestión
- `10.10.20.0/24` -> Servidores
- `10.10.30.0/24` -> Clientes
- `10.10.40.0/24` -> IoTs
- `10.10.50.0/24` -> DMZ
- `10.10.60.0/24` -> Backup
- `10.20.10.0/24` -> Offsite
- `10.0.0.0/24` -> Extra
- `10.30.10.0/24` -> Cloud

## Consecuencias

### Positivas

- El direccionamiento resulta legible y escalable.
- Se facilita la segmentación por función.
- La documentación y la lectura del entorno son más claras.
- El diseño es fácilmente ampliable a nodo remoto y cloud.
- Organización y nomenclatura alineada con una posterior segmentación en VLANs.

### Negativas

- Algunas redes definidas no se utilizarán en fases tempranas.
- La convención interna debe mantenerse consistente para no perder claridad.

## Alternativas consideradas

### Usar 192.168.x.0/24

Más simple para un laboratorio pequeño, pero con menos margen visual y estructural para crecer.

### Diseñar redes solo cuando se necesiten

Más rápido al principio, pero peor para escalar y documentar.

## Justificación

Se prioriza claridad, crecimiento futuro y coherencia arquitectónica sobre la simplicidad inicial absoluta.
