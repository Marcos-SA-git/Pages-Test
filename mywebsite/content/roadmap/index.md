---
title: "Próximos pasos"
---

Debido a que este proyecto está actualmente en desarrollo, lo descrito  a continuación puede ir cambiando o actualizándose con el tiempo según avanza el proyecto. Sobre todo cuanto más lejanas son las fases respecto al estado actual.

## Fase 0 - Infraestructura

- Preparación del entorno para usar VMware Workstation.
- Creación de redes virtuales (VLANs) separadas por función. ([Más info](../arch/_index.md))
- Búsqueda de ISOs y asignación de recursos para las máquinas virtuales.

## Fase 1 — Configuración inicial

- Despliegue y configuración básica inicial de:
    - 1 Cliente Ubuntu
    - 1 Servidor Ubuntu
    - 1 Router OPNsense
- Configurar OPNsense como DHCP principal siguiendo la arquitectura planteada.
- Validación de conectividad básica y acceso a una web simple.

---

## Revisar a partir de aquí

---

## Fase 2 — Routing, DHCP y segmentación real

- Asignación correcta de interfaces en OPNsense
- Activación de DHCP en los segmentos necesarios
- Separación real entre cliente y servidor
- Reglas básicas de firewall
- Validación de tráfico entre redes a través del router

## Fase 3 — DNS interno y servicios base

- Resolución de nombres interna
- Primeros servicios de infraestructura
- Preparación para una administración más cómoda del entorno
- Organización inicial de hosts y roles

## Fase 4 — Publicación web y servicios internos

- Despliegue de una web simple o WordPress
- Exposición controlada de servicios internos
- Reverse proxy
- Uso de logs del tráfico para observabilidad posterior

## Fase 5 — Administración de sistemas e identidad

- Active Directory o solución equivalente
- Gestión centralizada de identidades
- Integración con servidores y clientes
- Evaluación de alternativas para entornos Linux
- Posible incorporación de SSO para aplicaciones internas

## Fase 6 — Gestión de servidores Linux

- Administración centralizada de sistemas Linux
- Estandarización de configuración
- Automatización progresiva
- Preparación para operar varios servidores de forma más profesional

## Fase 7 — Observabilidad y dashboards

- Recolección de métricas
- Centralización de logs
- Dashboards técnicos
- Monitorización del estado de servicios, hosts y tráfico
- Visualización de datos del laboratorio de forma demostrable

## Fase 8 — Bases de datos y plataforma de aplicaciones

- Despliegue de distintas bases de datos
- Persistencia y organización de servicios
- Pruebas con aplicaciones internas
- Separación por roles y necesidades

## Fase 9 — Docker y contenedores

- Despliegue de servicios contenedorizados
- Uso de Docker Compose
- Preparación de aplicaciones reproducibles
- Integración con reverse proxy, logs y monitorización

## Fase 10 — Kubernetes / K3s

- Primer clúster ligero
- Orquestación de cargas
- Servicios internos desplegados sobre Kubernetes
- Integración con observabilidad y networking

## Fase 11 — Backup y recuperación

- Estrategias de copia de seguridad
- Validación de restauraciones
- Diseño de red y almacenamiento orientado a recuperación
- Segmento específico para backup

## Fase 12 — IoT y redes especializadas

- Simulación o integración de dispositivos IoT
- Segmentación específica para este tipo de dispositivos
- Restricción de tráfico y análisis de comportamiento

## Fase 13 — Nodo remoto / offsite

- Conexión con una máquina virtual fuera del equipo principal
- Comunicación entre laboratorio principal y nodo remoto
- Gestión de tráfico entre ubicaciones
- Base para escenarios multi-sede

## Fase 14 — VPN y acceso remoto seguro

- Pruebas con tecnologías como:
    - Tailscale
    - NetBird
    - Headscale
    - Netmaker
    - ZeroTier
- Acceso seguro al laboratorio desde fuera
- Evaluación de distintos enfoques de conectividad overlay

## Fase 15 — Integración con cloud

- Pruebas de conectividad con:
    - AWS
    - Azure
    - Google Cloud
- Diseño híbrido entre laboratorio local y recursos cloud
- Validación de rutas, acceso y segmentación extendida

## Fase 16 — Publicación y portfolio técnico

- Consolidación de toda la documentación en GitHub Pages
- Integración futura con web personal y dominio propio
- Organización del proyecto como portfolio técnico público
- Presentación clara del progreso, arquitectura y aprendizajes
