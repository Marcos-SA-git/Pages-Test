---
 title: "Incidencia 02 - Limitaciones y comportamiento de VMnet en VMware Workstation"
---

## Síntoma

Durante la preparación de redes virtuales se observaron restricciones no evidentes en las interfaces VMnet predefinidas.

## Hallazgos

- VMnet0 está reservada para bridge
- VMnet1 está reservada para host-only
- VMnet8 está reservada para NAT
- VMnet1 no permite cambio de nombre
- El modo NAT solo puede existir una vez
- Configurar NAT en otra interfaz distinta puede parecer posible, pero deja de funcionar correctamente

## Impacto

Estas restricciones condicionan el diseño inicial de las redes virtuales y obligan a planificar mejor qué interfaces se usarán para qué propósito.

## Aprendizaje

No conviene asumir que todas las VMnet funcionan igual. Antes de diseñar la topología, hay que tener claro qué interfaces están reservadas y qué limitaciones reales tiene VMware Workstation.
