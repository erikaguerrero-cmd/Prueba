---
tipo: fuente
titulo: Contexto del Proyecto — Manta Seguros (README)
tags: [contable, legal, operativo, proyecto, confidencial]
creado: 2026-09-15
actualizado: 2026-09-15
origen: raw/documentos/contexto-proyecto-manta.pdf
fecha_fuente: 2026
estado: vigente
---

# Contexto del Proyecto — Manta Seguros (README)

**Qué es:** Documento **maestro de contexto** del proyecto de puesta en marcha de
[[entidades/manta-seguros|Manta Seguros]] (5 páginas). Es la "fuente de verdad versionada" del proyecto,
pensada para cargarse como base de conocimiento. **Interlocutora principal:** [[entidades/erika-guerrero|Erika
Guerrero]] (Controller y PM del [[entidades/proyecto-orion|Proyecto Orión]]).

> 🔒 **Confidencial:** marcado "No publicar. No mezclar con contenido de otros clientes." Solo se procesa en este
> wiki local (repo privado). No enviar a servicios externos.

## Puntos clave

1. **Tres frentes del proyecto:** (i) constitución y autorización ante la [[entidades/superintendencia-financiera|SFC]],
   (ii) implementación del ERP [[entidades/netsuite|NetSuite]] ([[entidades/proyecto-orion|Proyecto Orión]]),
   (iii) capital, reservas y arquitectura contable NIIF 17 / NIIF 4.
2. **Producto:** [[conceptos/soat|SOAT]] (ramo 04), tarifa regulada SFC (EOSF art. 193 num. 5; Decreto 2312 de
   2023). Se acoge a la **Nota Técnica SFC SOAT v9.0** (ene 2026) — no la reproduce (instrucción del oficio SFC).
3. **[[conceptos/nota-tecnica-soat|Nota Técnica propia]]** MANTA-NT-SOAT, **versión 14** (jul 2026), radicada en
   respuesta al oficio SFC 2026051309-026-000. No existe V13 externa (revisión interna descartada); control de
   cambios V12→V14. Elaborada por **[[entidades/juan-felipe-restrepo|Juan Felipe Restrepo O.]]** (actuario tercerizado).
4. **[[conceptos/parametros-regulados-soat|Parámetros regulados]]** (NT SFC v9.0): GA 10%, CI 8% (Sentencia
   C-395-22), T_ADRES 9,5%, T_ANSV 3%, θ (factor de seguridad) ∈ {1%, 2,5%, 5%}. **Decisiones internas:** cesión
   50%, r% ULAE 50%, **descuentos sobre tarifa = 0%** (cobra tarifa máxima SFC).
5. **Marco contable:** NIIF 17 diferida a **1-ene-2028** (Decretos 217 y 219 de 2026); marco prudencial vigente
   Decreto 2555/2010 (Libro 31, mod. 1531/2022). **Transición: enfoque retrospectivo completo** (ver ⚠️ abajo).
   **CUIF de 10 dígitos obligatorio enero 2027.**
6. **Reservas** (continuidad técnica): RPND, RIP, RSA, ULAE, RSONA (Factor 0,7175). Ver
   [[conceptos/reservas-tecnicas-soat]].
7. **[[entidades/proyecto-orion|Proyecto Orión]]:** contrato con **LatamReady terminado** por incumplimiento;
   desarrollo a cargo del equipo IT de **[[entidades/grupo-r5|Grupo R5]]**. Testing SFC 15–30 oct 2026 (corte
   30 jun 2026); ESFA de apertura 1 ene 2026.

## Base de conocimiento referenciada (fuentes por ingerir)

- **Nota Técnica SOAT** (control de cambios V12→V14) — documento central del trámite SFC.
- **Hoja de Trabajo SOAT.xlsx** — formulación de reservas y ejemplos numéricos.
- **Modelo Financiero.xlsx** — proyecciones financieras.
- **Estudio de Incidencia Administrativa, Técnica y Financiera.pdf** — soporte de constitución.
- **Manual SIAR.pdf** — marco de gobierno de reservas.

## Preferencias de trabajo (de Erika)

- Respuestas concisas y accionables; entregables inmediatamente usables.
- Preferencia por **una sola herramienta consolidada** (operativa + tablero) sobre documentos separados.
- Registro por audiencia (directivos pulido; desarrolladores limpio; junior en lenguaje llano).
- Al validar contabilidad: *"siento que está bien" ≠ implementación verificada* — actuar como contrapeso.
- Titularidad de todo proceso **permanece en el equipo de Manta** (ningún tercero es dueño de un proceso).

## Impacto en el wiki

**Entidades:** [[entidades/proyecto-orion]] · [[entidades/grupo-r5]] · [[entidades/juan-felipe-restrepo]] ·
[[entidades/dian]] (actualiza [[entidades/manta-seguros]], [[entidades/erika-guerrero]], [[entidades/netsuite]])

**Conceptos:** [[conceptos/nota-tecnica-soat]] · [[conceptos/parametros-regulados-soat]] (actualiza
[[conceptos/estructura-multi-book]], [[conceptos/columna-contexto]], [[conceptos/marco-normativo]],
[[conceptos/soat]], [[conceptos/niif-17]])

## ⚠️ Tensión con el manual (método de transición NIIF 17)

> ⚠️ **Contradicción / matiz:** El [[fuentes/manual-politicas-contables-manta|Manual de Políticas]] (§11) afirma
> que Manta, por ser **entidad de nueva constitución**, aplica NIIF 17 desde el inicio **sin recurrir a las
> disposiciones de transición** (NIIF 17.C3). Este README y la
> [[fuentes/emision-poliza-soat-desarrollo|especificación de emisión]] indican que la transición a NIIF 17 se
> hará bajo **enfoque retrospectivo completo (full retrospective)** con fecha efectiva 1-ene-2028 (de ahí que se
> capturen campos de trazabilidad desde la primera emisión). **Pendiente de aclarar** cómo se concilian ambos
> enunciados (¿aplica a la construcción del libro regulatorio de 2028?).

> **Matiz "doble libro" vs. "tres libros":** el README dice *"doble libro: NIIF 17 primario y NIIF 4/CUIF
> secundario"*; el manual lista **tres** ([[conceptos/estructura-multi-book|NIIF 17, NIIF 4/CUIF y Fiscal]]). El
> README omite el fiscal por enfocarse en lo contable/regulatorio; no es contradicción de fondo.
