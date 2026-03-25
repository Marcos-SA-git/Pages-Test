# Enterprise Homelab

## Descripción

Laboratorio virtual orientado a redes, sistemas, seguridad y servicios empresariales, desplegado sobre VMware Workstation.

El objetivo es construir una infraestructura privada y segmentada que permita practicar de forma progresiva:

- routing y firewalling
- DHCP y DNS
- Active Directory / identidad
- SSO
- servidores Linux y Windows
- publicación de servicios
- observabilidad y dashboards
- backups
- conectividad remota y cloud híbrida

## Objetivo del proyecto

Diseñar y desplegar un homelab demostrable, documentado y escalable, con una arquitectura modular que pueda evolucionar hacia un entorno más cercano al mundo profesional.

## Estado actual

Fase 1 completada parcialmente:

- Redes virtuales creadas en VMware
- Esquema de direccionamiento definido
- OPNsense desplegado como router/firewall central
- Cliente Ubuntu y servidor Ubuntu creados
- DHCP de VMware desactivado en todas las redes virtuales

Pendiente dentro de esta fase:

- Activar DHCP en OPNsense
- Asignar IP a cliente y servidor
- Validar conectividad
- Publicar una web simple en el servidor
- Permitir acceso desde cliente al servidor

## Roadmap inicial

1. Configuración inicial
2. DHCP y conectividad básica
3. Publicación web simple
4. DNS interno
5. Segmentación real por roles
6. Observabilidad básica
7. Identidad y autenticación
8. Nodo remoto / offsite
9. Publicación controlada y dashboards
