# Esquema del Cerebro Digital — Área (Contable · Legal · Operativa)

Este archivo es la **configuración principal** del cerebro digital. Le dice al agente
LLM cómo está estructurado el wiki, qué convenciones seguir, y qué flujos ejecutar al
ingerir fuentes, responder preguntas o mantener el wiki.

> **Regla de oro:** El humano cura fuentes, dirige el análisis y hace preguntas.
> El LLM hace *todo lo demás*: leer, resumir, cruzar referencias, archivar y mantener
> la consistencia. El humano casi nunca escribe el wiki a mano — lo escribe el LLM.

---

## 1. Propósito

Construir y mantener un **wiki persistente y acumulativo** sobre los documentos,
funciones y alcance del área. A diferencia de un RAG (que redescubre el conocimiento en
cada consulta), aquí el conocimiento se **compila una vez y se mantiene al día**: las
referencias cruzadas ya están, las contradicciones ya están marcadas, y la síntesis ya
refleja todo lo leído.

El área es **mixta**: cubre lo **contable/financiero**, lo **legal/de cumplimiento** y
lo **operativo/de procesos**. El wiki debe reflejar esa transversalidad.

---

## 2. Arquitectura — tres capas

1. **Fuentes crudas** (`raw/`) — Documentos originales. **Inmutables.** El LLM lee de
   aquí pero *nunca* modifica ni borra estos archivos. Es la fuente de verdad.
2. **El wiki** (`wiki/`) — Markdown generado por el LLM. Resúmenes, páginas de entidades,
   conceptos, funciones, síntesis. El LLM es dueño total de esta capa.
3. **El esquema** (`CLAUDE.md`, este archivo) — Las reglas y convenciones. El humano y el
   LLM lo co-evolucionan cuando descubren qué funciona.

---

## 3. Estructura de directorios

```
raw/                    # FUENTES CRUDAS (inmutables — nunca editar/borrar)
  documentos/           #   PDFs, Word, manuales, políticas, normativa
  hojas/                #   Excel/CSV: balances, cartera, reportes
  comunicaciones/       #   Correos, hilos de Slack, actas, transcripciones
  notas/                #   Conocimiento tácito: lo que sabe el humano
  assets/               #   Imágenes descargadas de las fuentes

wiki/                   # EL WIKI (propiedad del LLM)
  index.md              #   Catálogo de todo el wiki (orientado a contenido)
  log.md                #   Registro cronológico append-only (ingestas, consultas, lint)
  overview.md           #   Visión general del área — el mapa de alto nivel
  entidades/            #   Personas, equipos, sistemas, entes externos (DIAN, bancos…)
  conceptos/            #   Conceptos, normativa, definiciones, glosario
  funciones/            #   Funciones, responsabilidades y procesos del área
  fuentes/              #   Un resumen por cada fuente ingerida
  sintesis/             #   Análisis, comparaciones, respuestas archivadas
```

---

## 4. Convenciones de páginas

- **Formato:** Markdown compatible con Obsidian.
- **Enlaces internos:** usar wikilinks `[[nombre-de-pagina]]` (estilo Obsidian). Enlazar
  generosamente — las conexiones son tan valiosas como el contenido.
- **Nombres de archivo:** `kebab-case`, en español, sin tildes ni ñ en el nombre de
  archivo (para portabilidad), pero **con** tildes correctas en el título y el cuerpo.
  Ej: archivo `liquidacion-renta-drpj.md`, título `# Liquidación de renta DRPJ`.
- **Frontmatter YAML** al inicio de cada página (permite usar Dataview en Obsidian):

```yaml
---
tipo: entidad | concepto | funcion | fuente | sintesis | overview
titulo: Título legible
tags: [contable, legal, operativo]
creado: AAAA-MM-DD
actualizado: AAAA-MM-DD
fuentes: [nombre-fuente-1, nombre-fuente-2]   # de qué fuentes proviene la info
estado: vigente | por-revisar | obsoleto
---
```

- **Citas:** al afirmar algo que viene de una fuente, referenciar la página de fuente
  correspondiente: `(ver [[fuentes/nombre-fuente]])`.
- **Contradicciones:** cuando una fuente nueva contradice una afirmación existente, **no
  borrar** la anterior en silencio. Marcar con un bloque:

```markdown
> ⚠️ **Contradicción:** [[fuentes/fuente-nueva]] (2026-08) indica X, mientras que
> [[fuentes/fuente-vieja]] (2025-11) indicaba Y. Pendiente de resolver con el humano.
```

---

## 5. Flujos de trabajo

### 5.1 Ingesta (Ingest)

Cuando el humano deja una fuente nueva en `raw/` y pide procesarla:

1. **Leer** la fuente completa. Si es una hoja de cálculo, usar las skills `xlsx`/`csv`
   apropiadas. Si es un documento con imágenes, leer el texto primero y luego revisar las
   imágenes relevantes en `raw/assets/`.
2. **Discutir** los puntos clave con el humano antes de archivar (salvo que pida
   ingesta en lote sin supervisión).
3. **Escribir** una página de resumen en `wiki/fuentes/<nombre>.md` con: qué es, fecha,
   puntos clave, datos relevantes, y enlaces a las páginas que toca.
4. **Actualizar** las páginas afectadas de `entidades/`, `conceptos/` y `funciones/`.
   Una sola fuente puede tocar 10–15 páginas. Crear páginas nuevas si aparecen entidades
   o conceptos que aún no existen.
5. **Marcar contradicciones** si la fuente nueva choca con lo existente.
6. **Actualizar `index.md`** con las páginas nuevas/modificadas.
7. **Añadir una entrada a `log.md`** (ver formato abajo).

### 5.2 Consulta (Query)

Cuando el humano hace una pregunta:

1. **Leer `index.md`** primero para ubicar las páginas relevantes; luego entrar a ellas.
   Si el wiki crece mucho, usar búsqueda (grep sobre `wiki/`) como complemento.
2. **Sintetizar** una respuesta con citas a las páginas de fuente.
3. La respuesta puede tomar distintas formas: texto, tabla comparativa, página markdown,
   diapositivas (Marp), gráfico (matplotlib), etc.
4. **Archivar respuestas valiosas:** si la respuesta es un análisis, comparación o
   conexión que vale la pena conservar, guardarla como página nueva en `wiki/sintesis/`
   y registrarla en `index.md` y `log.md`. Las exploraciones deben *acumularse*, no
   perderse en el chat.

### 5.3 Lint (Health-check)

Periódicamente, cuando el humano lo pida, revisar la salud del wiki y reportar:

- Contradicciones entre páginas.
- Afirmaciones obsoletas que fuentes nuevas ya superaron.
- Páginas huérfanas (sin enlaces entrantes).
- Conceptos importantes mencionados pero sin página propia.
- Referencias cruzadas faltantes.
- Vacíos de datos que podrían llenarse con una fuente nueva o una búsqueda web.
- Sugerir nuevas preguntas a investigar y nuevas fuentes a buscar.

Registrar cada pasada de lint en `log.md`.

---

## 6. index.md y log.md

- **`index.md`** — orientado a **contenido**. Catálogo de todo el wiki: cada página con su
  enlace, un resumen de una línea y metadatos opcionales (fecha, nº de fuentes).
  Organizado por categoría (overview, entidades, conceptos, funciones, fuentes, síntesis).
  Se actualiza en **cada** ingesta.

- **`log.md`** — orientado al **tiempo**. Registro append-only de qué pasó y cuándo. Cada
  entrada empieza con un prefijo consistente para poder filtrarlo con unix:

```markdown
## [AAAA-MM-DD] ingest | Título de la fuente
## [AAAA-MM-DD] query  | Pregunta resuelta
## [AAAA-MM-DD] lint   | Resumen de la pasada de salud
```

  Así `grep "^## \[" wiki/log.md | tail -5` da las últimas 5 entradas.

---

## 7. Estilo

- Escribir en **español**, claro y conciso. Español de Colombia cuando aplique al dominio
  (PUC, DIAN, DRPJ, cartera, etc.).
- Preferir listas y tablas sobre párrafos largos cuando aporte claridad.
- No inventar datos. Si algo no está en las fuentes, decirlo explícitamente.
- Mantener la consistencia entre páginas — es el trabajo principal del LLM.
