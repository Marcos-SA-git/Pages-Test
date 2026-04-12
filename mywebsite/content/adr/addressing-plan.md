# Addressing Plan

## Convención usada

Las redes siguen el siguiente esquema lógico:

- Primer octeto: clase / bloque privado
- Segundo octeto: lugar o entorno
- Tercer octeto: uso o segmento
- Cuarto octeto: IP asignada al equipo

> Nota: se trata de una convención interna de diseño para facilitar lectura y escalabilidad, no de una regla técnica obligatoria.

## Redes definidas

| Red | Uso |
| --- | --- |
| 10.10.10.0/24 | Administración / Gestión |
| 10.10.20.0/24 | Servidores |
| 10.10.30.0/24 | Clientes |
| 10.10.40.0/24 | IoTs |
| 10.10.50.0/24 | DMZ |
| 10.10.60.0/24 | Backup |
| 10.20.10.0/24 | Offsite |
| 10.0.0.0/24 | Extra |
| 10.30.10.0/24 | Cloud |

## Objetivo del esquema

Separar el tráfico por funciones desde el inicio para facilitar:

- segmentación lógica
- crecimiento futuro
- aplicación de reglas de firewall por zona
- integración posterior con VPN, cloud y nodo remoto
