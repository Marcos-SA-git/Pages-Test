---
title: "HomeLab de pruebas empresarial"
---

## Propósito del proyecto

Consiste en la creación de un laboratorio virtual realista y reproducible con tecnologías y servicios progresivamente más complejos para poner en práctica habilidades y conocimientos propios de un administrador de sistemas en un entorno empresarial.

Desde la planificación, despligue, puesta en marcha, medidas de seguridad y automatización, incluyendo documentación, toma de decisiones y resolución de problemas.

---

## Qué quiero demostrar con este proyecto

A través de este homelab quiero demostrar que soy capaz de:

- Diseñar una arquitectura técnica con intención
- Segmentar redes y pensar en seguridad desde el inicio
- Desplegar y mantener servicios de infraestructura
- Analizar problemas y resolver incidencias reales
- Documentar de forma clara y profesional
- Trabajar con repositorios, automatización y publicación técnica
- Construir un portfolio técnico basado en trabajo real, no solo teoría

---

## Documentación

La documentación del proyecto se organiza en varias capas:

- Visión general de arquitectura
- Plan de direccionamiento
- Fases del despliegue
- Decisiones técnicas importantes
- Incidencias y aprendizajes
- Procedimientos replicables

Esto me permite usar el laboratorio no solo como entorno de práctica, sino también como proyecto técnico demostrable.

---

## Filosofía del proyecto

Este repositorio sigue una idea simple:

> construir por fases, validar cada capa, documentar las decisiones importantes y dejar evidencia real del trabajo realizado.

El objetivo no es crear un laboratorio gigantesco desde el primer día, sino una base sólida sobre la que ir añadiendo complejidad de forma controlada.

---

## Planteamiento de la red

### Convención usada

Las redes siguen el siguiente esquema lógico:

- **Primer octeto**: clase / bloque privado
- **Segundo octeto**: lugar / sitio / entorno
- **Tercer octeto**: uso / segmento / propósito
- **Cuarto octeto**: IP asignada al equipo

- **Máscara de red**: 255.255.255.0 (CIDR: /24)

> Nota: se trata de una convención interna de diseño para facilitar lectura y escalabilidad, no de una regla técnica obligatoria.

### Redes definidas

| Red | Uso | Estado |
| --- | --- | ------ |
| 10.10.10.0/24 | Administración / Gestión | Activo |
| 10.10.20.0/24 | Servidores | Activo |
| 10.10.30.0/24 | Clientes | Activo |
| 10.10.40.0/24 | IoTs | - |
| 10.10.50.0/24 | DMZ | - |
| 10.10.60.0/24 | Backup | - |
| 10.20.10.0/24 | Offsite | - |
| 10.x.x.x/24 | Extra | Opcional |

### Diagrama de arquitectura general

![Diagrama del proyecto](assets/img/high-level-homelab-architecture.drawio.svg)

---

## Estado del proyecto

Actualmente el proyecto se encuentra en una fase temprana de construcción, centrada en la preparación de la base del laboratorio y en la definición de la arquitectura inicial.

La intención es evolucionarlo por fases, manteniendo siempre:

- documentación clara
- validación técnica
- evidencias del funcionamiento
- lecciones aprendidas

---

## Visión a futuro

A medio y largo plazo, este homelab se conectará con mi futura web personal y servirá como una pieza central de mi portfolio técnico.

La idea es que cada proyecto o bloque del laboratorio tenga su propia documentación pública, bien estructurada y accesible, mostrando no solo el resultado final, sino también el proceso, las decisiones y la evolución del entorno.
