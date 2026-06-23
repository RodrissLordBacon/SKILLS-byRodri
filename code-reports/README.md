<!-- lang:en -->

# code-reports skill

Deterministic internal report system for Claude Code → Claude.ai
communication. Fixed taxonomy, deterministic naming, mandatory field
structure, and explicit archiving rules.

---

## The problem this solves

Without this skill, every report Code produces has a different name, a
different structure, and a different archiving fate decided on the spot.
The result is a `docs/code-output/` folder with files like:
- `audit-results.md`
- `BackendReview_June.md`
- `things-i-found.md`
- `diagnostico-auth-2026.md`

None of these are locatable, comparable, or consistently structured.

This skill makes every report predictable: same naming pattern, same
field structure per type, same archiving rules.

---

## Four report types

| Type | When to use |
|---|---|
| `audit` | Systematic review against a checklist or standard |
| `diagnostic` | Root cause investigation of a specific problem |
| `extract` | Factual data extraction, no judgement |
| `snapshot` | Before-state capture ahead of a significant change |

---

## File naming

`<type>-<topic>-<YYYY-MM-DD>.md`

```
audit-security-2026-05-12.md
diagnostic-session-expiry-2026-06-03.md
extract-api-endpoints-2026-04-28.md
snapshot-auth-module-2026-05-01.md
```

---

## Lifecycle

```
Code produces report
       ↓
docs/code-output/          ← temporary, gitignored
       ↓
Department chat reads it
       ↓
Decision: archive | discard | keep in outbox
       ↓
docs/code-reports/         ← permanent, committed (if archived)
```

---

## Relation to other skills

- `working-system` — defines the handoff protocol used to request reports.
- `audit-system` — A1/A2/A3/A4 audits produce `audit` type reports
  following this skill's structure.
- `code-commands` — `/context-sync` produces an implicit `extract` of
  context file drift; it does not produce a formal report file unless
  running a full A4 audit.

<!-- lang:es -->

# code-reports skill

Sistema de informes internos determinista para la comunicación Claude Code →
Claude.ai. Taxonomía fija, nomenclatura determinista, estructura de campos
obligatoria y reglas de archivado explícitas.

---

## El problema que resuelve

Sin esta skill, cada informe que Code produce tiene un nombre distinto, una
estructura distinta y un destino de archivado decidido sobre la marcha. El
resultado es una carpeta `docs/code-output/` con archivos como:
- `audit-results.md`
- `BackendReview_June.md`
- `things-i-found.md`
- `diagnostico-auth-2026.md`

Ninguno de estos es localizable, comparable ni está estructurado de forma
consistente.

Esta skill hace que cada informe sea predecible: mismo patrón de nomenclatura,
misma estructura de campos por tipo, mismas reglas de archivado.

---

## Cuatro tipos de informe

| Tipo | Cuándo usarlo |
|---|---|
| `audit` | Revisión sistemática frente a un checklist o estándar |
| `diagnostic` | Investigación de causa raíz de un problema concreto |
| `extract` | Extracción factual de datos, sin juicio |
| `snapshot` | Captura del estado previo antes de un cambio significativo |

---

## Nomenclatura de archivos

`<type>-<topic>-<YYYY-MM-DD>.md`

```
audit-security-2026-05-12.md
diagnostic-session-expiry-2026-06-03.md
extract-api-endpoints-2026-04-28.md
snapshot-auth-module-2026-05-01.md
```

---

## Ciclo de vida

```
Code produce el informe
       ↓
docs/code-output/          ← temporal, gitignored
       ↓
El chat del departamento lo lee
       ↓
Decisión: archivar | descartar | mantener en outbox
       ↓
docs/code-reports/         ← permanente, commiteado (si se archiva)
```

---

## Relación con otras skills

- `working-system` — define el protocolo de handoff usado para solicitar
  informes.
- `audit-system` — las auditorías A1/A2/A3/A4 producen informes de tipo `audit`
  siguiendo la estructura de esta skill.
- `code-commands` — `/context-sync` produce un `extract` implícito del drift de
  los archivos de contexto; no produce un archivo de informe formal salvo que se
  ejecute una auditoría A4 completa.
