---
title: "Guía de taxonomías y etiquetas"
description: "Normas de uso para mantener una clasificación consistente del contenido del laboratorio."
---

Esta página define cómo deben usarse las etiquetas del proyecto para mantener una navegación clara, consistente y escalable.

El objetivo no es añadir etiquetas por añadir, sino crear una estructura que permita:

- encontrar contenido rápidamente
- evitar duplicados y sinónimos innecesarios
- diferenciar claramente entre herramientas, funciones y contexto
- mantener una nomenclatura estable a medida que el laboratorio crece

---

## Principios generales

### 1. Las etiquetas no deben improvisarse

Antes de crear una nueva etiqueta, conviene comprobar si ya existe una equivalente o una suficientemente cercana.

Ejemplo:

- Usar `reverse-proxy`
- No mezclar `reverse proxy`, `rev-proxy`, `proxy-inverso`

### 2. Las etiquetas deben seguir un patrón común

Se recomienda usar siempre:

- minúsculas
- palabras separadas por guiones
- términos concretos y técnicos

Ejemplos correctos:

- `vmware-workstation`
- `ubuntu-server`
- `reverse-proxy`
- `load-balancing`

Ejemplos a evitar:

- `VMware`
- `Ubuntu Server`
- `ReverseProxy`
- `networkstuff`

### 3. Las etiquetas deben diferenciar bien herramienta y función

Esta es la norma más importante.

- **software** = producto, sistema, herramienta o plataforma concreta
- **services** = función técnica o capacidad que presta algo

Ejemplos:

- `opnsense` → software
- `routing` → service
- `firewall` → service

- `unbound` → software
- `dns` → service

- `haproxy` → software
- `reverse-proxy` → service
- `load-balancing` → service

### 4. Menos etiquetas, mejor

Es preferible usar pocas etiquetas bien mantenidas que muchas etiquetas ambiguas o solapadas.

---

## Taxonomías usadas

## 1. `software`

### Qué representa

Herramientas, sistemas operativos, productos o plataformas concretas.

### Por qué existe

Permite agrupar todo el contenido relacionado con una tecnología específica, independientemente de la fase o del tipo de documento.

Sirve para preguntas como:

- ¿Qué contenido del proyecto usa OPNsense?
- ¿Qué procedimientos están relacionados con Ubuntu?
- ¿Qué incidencias han aparecido con VMware?

### Qué debe ir aquí

- sistemas operativos
- hipervisores
- firewalls
- proxies
- herramientas de observabilidad
- plataformas cloud
- software de automatización

---

## 2. `services`

### Qué representa

Funciones técnicas o capacidades que presta una parte del laboratorio.

### Por qué existe

Permite buscar contenido según la función que se está implementando o resolviendo, sin importar qué herramienta concreta se use para ello.

Sirve para preguntas como:

- ¿Qué contenido trata sobre DNS?
- ¿Qué incidencias han afectado al firewall?
- ¿Qué procedimientos existen para proxy o balanceo?

### Qué debe ir aquí

- funciones de red
- funciones de seguridad
- funciones de publicación de servicios
- funciones de observabilidad
- funciones de continuidad y acceso remoto

---

## 3. `kind`

### Qué representa

El tipo de contenido.

### Por qué existe

Permite separar la naturaleza del documento, no su contenido técnico.

Esto ayuda a responder preguntas como:

- ¿Esto es una fase, una incidencia o un procedimiento?
- ¿Quiero ver solo decisiones técnicas?
- ¿Estoy leyendo una guía repetible o una reflexión del proyecto?

### Ejemplos de uso

- `overview`
- `phase`
- `procedure`
- `incident`
- `decision`
- `note`
- `roadmap`

> Recomendación:
>\
> Usar esta taxonomía con mucha disciplina y pocos valores.
>\
> No conviene inventar nuevos tipos si ya existe uno suficientemente claro.

---

## 4. `phase`

### Qué representa

La etapa del proyecto en la que aparece o tiene sentido ese contenido.

### Por qué existe

Permite conectar procedimientos, incidencias y decisiones con el momento del laboratorio en el que surgieron.

Sirve para preguntas como:

- ¿Qué contenido pertenece a la fase 2?
- ¿Qué incidencias aparecieron en la fase 3?
- ¿Qué procedimientos nacieron durante la fase 4?

### Recomendación de formato

Usar un formato consistente, por ejemplo: `phase-xx`

---

## 5. `network_areas`

### Qué representa

La zona o segmento de red afectado por el contenido.

### Por qué existe

Permite clasificar contenido según la parte del laboratorio a la que afecta, independientemente del software o del servicio implicado.

Sirve para preguntas como:

- ¿Qué configuración afecta a la red de clientes?
- ¿Qué incidencias ocurrieron en la DMZ?
- ¿Qué procedimientos afectan al segmento de backup?

> Recomendación:
>\
> Usar esta taxonomía cuando el contenido afecte claramente a una o varias zonas de red.
>\
> No hace falta forzarla si el contenido es completamente general.

---

## Sobre la separación por tipo de contenido

Para evitar que procedimientos e incidencias compartan páginas de taxonomía y se mezclen entre sí, el proyecto usa taxonomías separadas internamente según el tipo de contenido.

Por ejemplo:

### Procedimientos

- `p_software`
- `p_services`
- `p_phases`

### Incidencias

- `i_software`
- `i_services`
- `i_phases`
- `i_issue_types`

Esto permite que una etiqueta como `dns` siga existiendo en ambos contextos, pero no mezcle en la navegación:

- procedimientos sobre DNS
- incidencias sobre DNS

La idea es mantener los **términos** iguales, pero separar el **contexto**.

Esto se hace sin que el usuario sea consciente en ningún momento de que existe esta separación, permitiendo una navegación y búsqueda del contenido más fluida y ordenada.

---

## Lista corta de etiquetas recomendadas

Esta lista no pretende ser completa.  
Su objetivo es servir de referencia rápida para no inventar etiquetas nuevas sin necesidad.

## Software

- `vmware-workstation`
- `opnsense`
- `ubuntu`
- `ubuntu-server`
- `unbound`
- `dnsmasq`
- `squid`
- `haproxy`
- `nginx`
- `docker`
- `kubernetes`
- `grafana`
- `prometheus`
- `github-pages`
- `hugo`

## Services

- `routing`
- `dhcp`
- `dns`
- `firewall`
- `nat`
- `internet-access`
- `network-segmentation`
- `vlan`
- `web-server`
- `forward-proxy`
- `reverse-proxy`
- `load-balancing`
- `caching`
- `vpn`
- `monitoring`
- `logging`
- `dashboard`
- `backup`
- `restore`
- `load-testing`

## Kind

- `overview`
- `phase`
- `procedure`
- `incident`
- `decision`
- `roadmap`

## Phase

- `phase-xx`

## Network areas

- `management`
- `clients`
- `servers`
- `iot`
- `dmz`
- `backup`
- `offsite`
- `cloud`

---

## Ejemplos prácticos

## Ejemplo 1: procedimiento

Un procedimiento para configurar Unbound como DNS principal podría usar:

- software: `opnsense`, `unbound`
- services: `dns`
- kind: `procedure`
- phase: `phase-2`
- network_areas: `clients`, `management`

## Ejemplo 2: incidencia

Una incidencia sobre acceso a la GUI de OPNsense podría usar:

- software: `opnsense`
- services: `firewall`, `routing`
- kind: `incident`
- phase: `phase-2`
- network_areas: `management`

---

## Cuándo crear una nueva etiqueta

Solo conviene crear una etiqueta nueva si:

- describe algo que todavía no está bien cubierto
- va a reutilizarse
- no es un simple sinónimo de otra ya existente
- encaja claramente en una taxonomía concreta

Antes de crearla, conviene preguntarse:

1. ¿Esto es una herramienta concreta o una función?
2. ¿Ya existe una etiqueta equivalente?
3. ¿Voy a volver a usarla?
4. ¿Su nombre sigue el patrón del proyecto?

---

## Resumen

La clasificación del proyecto se apoya en cinco ideas principales:

- **software**: con qué herramienta
- **services**: para qué función
- **kind**: qué tipo de documento es
- **phase**: en qué etapa del proyecto encaja
- **network_areas**: a qué zona del laboratorio afecta

Mantener esta estructura desde el principio evita que la documentación se vuelva inconsistente, difícil de navegar o imposible de mantener.

La prioridad no es tener muchas etiquetas, sino tener **pocas, claras y bien usadas**.
