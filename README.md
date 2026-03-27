# Enterprise Homelab

Laboratorio virtual personal orientado a redes, sistemas, seguridad, automatización y servicios empresariales, desplegado sobre **VMware Workstation** y documentado con **Markdown + MkDocs + GitHub Actions + GitHub Pages**.

El objetivo de este proyecto es diseñar, construir, documentar y publicar una infraestructura virtual modular que me permita practicar tecnologías reales de administración de sistemas, redes y servicios, al mismo tiempo que demuestro de forma clara mis capacidades técnicas, mi criterio de diseño y mi forma de trabajar.

---

## Propósito del proyecto

Este homelab nace con una doble intención:

### 1. Desarrollo técnico

Construir un entorno progresivamente más complejo para practicar de forma demostrable:

- segmentación de red
- routing y firewalling
- DHCP y DNS
- publicación de servicios
- administración de servidores Linux
- identidad y autenticación centralizada
- SSO
- observabilidad y dashboards
- bases de datos
- contenedores y orquestación
- copias de seguridad
- conectividad híbrida con nodos remotos y cloud

### 2. Portfolio profesional

Usar este laboratorio como una forma real de mostrar mis habilidades como:

- **Administrador de sistemas**
- **Administrador de redes**
- **Perfil técnico orientado a infraestructura**
- **Profesional con capacidad de documentación, análisis y resolución de problemas**
- **Perfil con mentalidad de desarrollador**, al aplicar versionado, documentación como código, automatización y publicación estructurada del trabajo

No se trata solo de “hacer máquinas virtuales”, sino de diseñar un entorno coherente, escalable y bien documentado, parecido en filosofía a un pequeño entorno empresarial.

---

## Objetivos principales

- Diseñar una red virtual segmentada por funciones
- Centralizar el routing y el control del tráfico en un firewall/router
- Desplegar servicios de infraestructura de forma progresiva
- Practicar troubleshooting real y registrar incidencias y lecciones aprendidas
- Documentar el proceso con un enfoque claro, replicable y profesional
- Publicar el progreso y la arquitectura en GitHub Pages
- Conectar en el futuro este laboratorio con una web personal / dominio propio

---

## Filosofía del proyecto

Este repositorio sigue una idea simple:

> construir por fases, validar cada capa, documentar las decisiones importantes y dejar evidencia real del trabajo realizado.

El objetivo no es crear un laboratorio gigantesco desde el primer día, sino una base sólida sobre la que ir añadiendo complejidad de forma controlada.

---

## Arquitectura prevista a alto nivel

El laboratorio está planteado como una infraestructura virtual segmentada, con distintas redes lógicas para separar tráfico y funciones.

### Segmentos definidos actualmente

- `10.10.10.0/24` → Administración / Gestión
- `10.10.20.0/24` → Servidores
- `10.10.30.0/24` → Clientes
- `10.10.40.0/24` → IoTs
- `10.10.50.0/24` → DMZ
- `10.10.60.0/24` → Backup
- `10.20.10.0/24` → Offsite
- `10.0.0.0/24` → Extra
- `10.30.10.0/24` → Cloud

### Convención de direccionamiento

Las redes siguen una convención interna para facilitar lectura y escalabilidad:

- **Primer octeto**: bloque privado
- **Segundo octeto**: lugar / entorno
- **Tercer octeto**: uso / segmento
- **Cuarto octeto**: IP del equipo

Esta convención no responde a una obligación técnica, sino a una decisión de diseño orientada a mantener el laboratorio ordenado y preparado para crecer.

---

## Fases del proyecto

## Fase 1 — Configuración inicial

- Preparación del entorno en VMware Workstation
- Creación de redes virtuales separadas por función
- Despliegue inicial de:
    - cliente Ubuntu
    - servidor Ubuntu
    - router/firewall OPNsense
- Desactivación del DHCP integrado de VMware
- Preparación para centralizar DHCP en el router
- Validación de conectividad básica y acceso a una web simple

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

---

## Stack principal del proyecto

- **VMware Workstation**
- **OPNsense**
- **Ubuntu / Ubuntu Server**
- **GitHub**
- **GitHub Actions**
- **GitHub Pages**
- **MkDocs**
- **Markdown**

Stack previsto a medio plazo:

- Active Directory o similar
- SSO
- Docker
- Kubernetes / K3s
- WordPress
- bases de datos
- observabilidad
- VPNs overlay
- integración cloud

---

## Qué quiero demostrar con este proyecto

A través de este homelab quiero demostrar que soy capaz de:

- diseñar una arquitectura técnica con intención
- segmentar redes y pensar en seguridad desde el inicio
- desplegar y mantener servicios de infraestructura
- analizar problemas y resolver incidencias reales
- documentar de forma clara y profesional
- trabajar con repositorios, automatización y publicación técnica
- construir un portfolio técnico basado en trabajo real, no solo teoría

---

## Estado del proyecto

Actualmente el proyecto se encuentra en una fase temprana de construcción, centrada en la preparación de la base del laboratorio y en la definición de la arquitectura inicial.

La intención es evolucionarlo por fases, manteniendo siempre:

- documentación clara
- validación técnica
- evidencias del funcionamiento
- lecciones aprendidas

---

## Documentación

La documentación del proyecto se organiza en varias capas:

- visión general de arquitectura
- plan de direccionamiento
- fases del despliegue
- decisiones técnicas importantes
- incidencias y aprendizajes
- procedimientos replicables

Esto me permite usar el laboratorio no solo como entorno de práctica, sino también como proyecto técnico demostrable.

---

## Visión a futuro

A medio y largo plazo, este homelab se conectará con mi futura web personal y servirá como una pieza central de mi portfolio técnico.

La idea es que cada proyecto o bloque del laboratorio tenga su propia documentación pública, bien estructurada y accesible, mostrando no solo el resultado final, sino también el proceso, las decisiones y la evolución del entorno.

---

## Nota

Este proyecto está en evolución continua. Algunas fases están definidas a nivel de diseño pero todavía no implementadas por completo. La prioridad es avanzar de forma ordenada, entendiendo cada capa antes de añadir la siguiente.
