---
tipo: entidad
titulo: Proyecto Orión (implementación NetSuite)
tags: [proyecto, operativo, netsuite, erp]
creado: 2026-09-15
actualizado: 2026-09-15
fuentes: [contexto-proyecto-manta, emision-poliza-soat-desarrollo]
estado: vigente
---

# Proyecto Orión (implementación NetSuite)

**Qué es:** Proyecto de implementación del ERP [[entidades/netsuite|NetSuite]] en
[[entidades/manta-seguros|Manta Seguros]]. **PM:** [[entidades/erika-guerrero|Erika Guerrero]].

## Estado (verificar vigencia)

- Contrato con **LatamReady terminado** por incumplimiento (28% ejecución vs. 33% pagado).
- Desarrollos a cargo del equipo IT de **[[entidades/grupo-r5|Grupo R5]]**.
- **Módulos:** R2R, P2P, O2C, Localización Colombia, e integraciones con **PAS** y **motor actuarial**.
- **Testing obligatorio SFC:** previsto 15–30 oct 2026, con corte a 30 jun 2026. **ESFA de apertura:** 1 ene 2026.

## Equipo de desarrollo (roster de pendientes)

| Persona | Rol / pendientes asignados |
|---------|----------------------------|
| **Ricardo Rojas** | Destinatario de la spec de emisión; crea cuentas en Sandbox; ARM; plan de continuidad. |
| **Jefferson Paz** | Identificación de canal en PAS; bajar nº de póliza a líneas; poblar tarifa/RUNT; versiones de librerías. |
| **Daniel Iriarte** | Devengo diario; tratamiento tributario/retenciones (SuiteTax); evaluación API de FE. |
| **Khristian Robayo** | Restablecer conexión del servicio de la calculadora actuarial. |

## Relación con el área

Es el vehículo operativo que materializa la [[conceptos/estructura-multi-book|arquitectura multi-book]], la
[[funciones/emision-de-poliza-soat|emisión de póliza]] y el [[funciones/cierre-contable-mensual|cierre mensual]]
en el ERP.

## Referencias

- Relacionado con: [[entidades/netsuite]] · [[entidades/grupo-r5]] · [[funciones/emision-de-poliza-soat]]
- Aparece en: [[fuentes/contexto-proyecto-manta]] · [[fuentes/emision-poliza-soat-desarrollo]]
