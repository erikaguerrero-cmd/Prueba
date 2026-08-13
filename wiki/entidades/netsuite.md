---
tipo: entidad
titulo: NetSuite (ERP)
tags: [sistema, operativo, multi-book]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# NetSuite (ERP)

**Qué es:** Sistema ERP de [[entidades/manta-seguros|Manta Seguros]]. Soporta la arquitectura
**[[conceptos/estructura-multi-book|multi-book]]** (tres libros sobre un único conjunto de transacciones) y el
plan de cuentas con la **[[conceptos/columna-contexto|columna CONTEXTO]]**.

## Rol en los procesos

- Genera los tres libros: [[conceptos/niif-17|NIIF 17]], [[conceptos/niif-4|NIIF 4]]/[[conceptos/cuif|CUIF]] y Fiscal.
- **Revenue Recognition (ARM):** devengo automático de prima en el cierre.
- **Segmentación contable:** subsidiaria, departamento, clase (SOAT), ubicación, y campos *custom* de póliza y siniestro.
- **[[funciones/segregacion-de-funciones|Segregación de funciones]]:** matriz de 7 roles; el *System Administrator*
  no tiene permisos de aprobación transaccional.

## Notas / pendientes

- La contabilización del [[conceptos/reaseguro-quota-share|reaseguro]] es **manual** (fuera del alcance de
  automatización de esta fase); se registra por reclasificación en el cierre.
- Pendiente verificar en Sandbox si la aprobación de *Vendor Payment* es nativa o vía SuiteFlow.
- Configuración e implementación de NetSuite: se capitaliza como intangible solo si cumple criterios (NIC 38).

## Referencias

- Relacionado con: [[conceptos/estructura-multi-book]] · [[conceptos/columna-contexto]] · [[funciones/cierre-contable-mensual]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]]
