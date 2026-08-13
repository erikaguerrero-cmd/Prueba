# 🧠 Cerebro Digital del Área

Base de conocimiento persistente sobre los **documentos, funciones y alcance** del área
(mixta: contable · legal · operativa), construida con el patrón **LLM Wiki**.

No es un RAG que redescubre el conocimiento en cada pregunta. Es un **wiki que se compila
una vez y se mantiene al día**: un agente LLM lee cada fuente, extrae lo clave y lo integra
en páginas interconectadas. El conocimiento se **acumula** con cada fuente y cada pregunta.

## Cómo funciona — el reparto de trabajo

- **Tú** curas fuentes, diriges el análisis y haces buenas preguntas.
- **El LLM** hace todo lo demás: leer, resumir, cruzar referencias, archivar y mantener
  la consistencia. Tú casi nunca escribes el wiki a mano.

Idealmente: el agente LLM abierto de un lado y **Obsidian** del otro, apuntando a la
carpeta `wiki/`. El LLM edita; tú navegas los enlaces y la vista de grafo en tiempo real.

## Estructura

| Carpeta        | Qué es                                                    |
|----------------|-----------------------------------------------------------|
| `raw/`         | **Fuentes crudas** (inmutables). Tu fuente de verdad.     |
| `wiki/`        | **El wiki** (lo escribe y mantiene el LLM).               |
| `CLAUDE.md`    | **El esquema**: reglas y convenciones que sigue el LLM.   |
| `plantillas/`  | Plantillas de página para ingesta consistente.            |

Dentro de `raw/`: `documentos/`, `hojas/`, `comunicaciones/`, `notas/`, `assets/`.
Dentro de `wiki/`: `entidades/`, `conceptos/`, `funciones/`, `fuentes/`, `sintesis/`,
más `index.md`, `log.md` y `overview.md`.

## Las tres operaciones

1. **Ingesta** — Dejas una fuente en `raw/` y me pides procesarla. La leo, comentamos lo
   clave, escribo un resumen, actualizo las páginas afectadas y registro en el log.
2. **Consulta** — Me preguntas algo. Busco en el índice, leo las páginas y respondo con
   citas. Las respuestas valiosas se archivan en `wiki/sintesis/`.
3. **Lint** — Me pides un health-check: contradicciones, páginas obsoletas, huérfanas,
   conceptos sin página, referencias faltantes.

## Cómo empezar

1. Deja tus primeras fuentes en la subcarpeta de `raw/` que corresponda.
2. Dime: *"ingiere esto"* (o describe la función/proceso que quieres registrar).
3. Reviso, comentamos, y yo lo integro al wiki.

> El wiki es un repo git de markdown: tienes historial, ramas y colaboración gratis.
