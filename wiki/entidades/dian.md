---
tipo: entidad
titulo: DIAN
tags: [regulador, fiscal, legal]
creado: 2026-09-15
actualizado: 2026-09-15
fuentes: [manual-politicas-contables-manta, emision-poliza-soat-desarrollo]
estado: vigente
---

# DIAN

**Qué es:** Dirección de Impuestos y Aduanas Nacionales. Autoridad tributaria de Colombia. Receptora del
**libro fiscal** de [[entidades/manta-seguros|Manta]] (renta, retenciones, medios magnéticos) y de la
**facturación electrónica**.

## Relación con el área

- **Libro fiscal** (tercero de la [[conceptos/estructura-multi-book|estructura multi-book]]): impuesto de renta,
  retenciones, medios magnéticos.
- **Facturación electrónica:** en la [[funciones/emision-de-poliza-soat|emisión de póliza SOAT]], el Documento 1
  (factura de venta) se transmite a la DIAN vía **Dispapeles**. La conexión fue validada contra el portal DIAN en
  la sesión E2E del 27-jul-2026.
- Requiere campos fiscales del cliente (naturaleza del tercero, régimen fiscal, código DANE del municipio,
  estado/ciudad DIAN, nombres/apellidos separados según estándar DIAN).

## Pendientes relacionados

- Definir tratamiento tributario y retenciones sobre la prima (afecta **SuiteTax** y el formulario de FE) —
  responsable Daniel Iriarte (ver [[entidades/proyecto-orion]]).

## Referencias

- Relacionado con: [[conceptos/estructura-multi-book]] · [[funciones/emision-de-poliza-soat]] · [[conceptos/transferencias-adres-ansv]]
- Aparece en: [[fuentes/emision-poliza-soat-desarrollo]] · [[fuentes/manual-politicas-contables-manta]]
