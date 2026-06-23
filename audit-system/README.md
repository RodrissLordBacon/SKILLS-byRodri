<!-- lang:en -->

# audit-system skill

Formal audit system for software projects. Defines active and dormant audit
families, triggers, a fixed execution cycle, finding classification, and a
three-phase automation layer. Based on OWASP ASVS 5.0 and OpenSSF Scorecard.

---

## What this skill does

When installed, the Audit department chat knows and applies:

- **Four core principles** that govern all audit decisions: automation
  covers what automation can cover; the user triggers, the chat executes;
  every finding ends somewhere actionable; dormant families have written
  activation criteria.
- **Family catalogue:** A1 Security (OWASP ASVS 5.0 L2), A2 Code and
  Architecture (project's own curated principles), A3 Dependencies (OpenSSF
  Scorecard + automated Dependabot/CI), A4 Documentary Consistency
  (context files vs. repo). Plus three dormant families (D1 Data/Privacy,
  D2 Accessibility, D3 Legal) with written activation triggers.
- **Four trigger types:** roadmap phase close (primary), critical event,
  user request, explicit cadence.
- **Seven-step execution cycle:** scope confirmation → plan → Code prompt
  → Code executes → human reading → classification and derivation →
  close with archiving. Fixed for all families.
- **Three finding types:** blocking (audit stays open until resolved),
  non-blocking (SQ or MQ in Asana), observation (in report only). With
  the edge rule: when in doubt between non-blocking and observation,
  default to observation.
- **A1 quarterly lightweight review:** core subset of highest-criticality
  A1 controls reviewed every quarter regardless of phase close.
- **Three-phase automation layer:** Phase 1 (basic CI scans, any repo),
  Phase 2 (declared vs. real comparison scripts, project-specific),
  Phase 3 (semantic verification, built only if phases 1 and 2 are
  insufficient).
- **`/ultrareview`:** reserved resource for deep parallel agent audit,
  justified only before first external distribution, SaaS transition, or
  critical auth refactor.
- **System boundaries:** what audits do not cover and why.

---

## What this skill does NOT include

- **Executable checklists.** Those live in `docs/project-context/audits/`
  in each project's repo, built per-project from the standards referenced
  in the skill. The skill defines the methodology; the checklists implement
  it for a specific stack.
- **Stack-specific filtering.** ASVS items that do not apply to a given
  stack are marked inactive in the project checklist with activation
  conditions documented. The skill references the full standard; the
  checklist does the filtering.
- **Project-specific inputs.** Which files to read, which manifest files
  to check, which architectural patterns to verify — all defined in the
  project's own checklist and context files.

---

## Standards referenced

| Family | Standard |
|---|---|
| A1 — Security | OWASP ASVS 5.0 Level 2 |
| A2 — Code and Architecture | Project's own curated principles (context files) |
| A3 — Dependencies | OpenSSF Scorecard (human) + Dependabot / pip-audit / npm audit (automated) |
| A4 — Documentary Consistency | Checklist derived from the project's own context files |
| D1 — Data and Privacy | GDPR, OWASP Data Privacy Guidelines |
| D2 — Accessibility | WCAG 2.2 Level AA, platform HIG |
| D3 — Legal Compliance | Jurisdiction-specific |

---

## Relation to other skills

- `working-system` — defines how the Audit department chat operates within
  the overall project methodology (commands, prompts for Code, Asana tasks).
- `engineering-standards` — defines the code quality bar that A2 verifies
  against (alongside the project's own architecture decisions).
- `code-commands` — `/context-sync` in Claude Code is the lightweight
  ongoing complement to A4; it syncs context files but does not produce a
  formal audit report.

---

## Installation

Save the skill from Claude.ai or package with:

```bash
python -m scripts.package_skill audit-system/ /output/path/
```

After installing, create the first checklist for A1 in your project:

```
docs/project-context/audits/
└── checklist-a1-security.md   ← build this first
```

Use the Audit department chat to build it: provide the project stack and
the chat will walk OWASP ASVS 5.0 Level 2, filter by applicability, and
produce the checklist ready for the first audit.

<!-- lang:es -->

# audit-system skill

Sistema de auditoría formal para proyectos de software. Define las familias de
auditoría activas y latentes, los disparadores, un ciclo de ejecución fijo, la
clasificación de hallazgos y una capa de automatización en tres fases. Basado en
OWASP ASVS 5.0 y OpenSSF Scorecard.

---

## Qué hace esta skill

Una vez instalada, el chat del departamento de Auditoría conoce y aplica:

- **Cuatro principios fundamentales** que rigen todas las decisiones de
  auditoría: la automatización cubre lo que la automatización puede cubrir; el
  usuario dispara, el chat ejecuta; todo hallazgo termina en algún sitio
  accionable; las familias latentes tienen criterios de activación por escrito.
- **Catálogo de familias:** A1 Seguridad (OWASP ASVS 5.0 L2), A2 Código y
  Arquitectura (principios propios curados del proyecto), A3 Dependencias
  (OpenSSF Scorecard + Dependabot/CI automatizados), A4 Coherencia Documental
  (archivos de contexto frente al repo). Más tres familias latentes (D1
  Datos/Privacidad, D2 Accesibilidad, D3 Legal) con disparadores de activación
  por escrito.
- **Cuatro tipos de disparador:** cierre de fase de roadmap (primario), evento
  crítico, petición del usuario, cadencia explícita.
- **Ciclo de ejecución de siete pasos:** confirmación de alcance → plan →
  prompt para Code → Code ejecuta → lectura humana → clasificación y derivación
  → cierre con archivado. Fijo para todas las familias.
- **Tres tipos de hallazgo:** bloqueante (la auditoría sigue abierta hasta
  resolverlo), no bloqueante (SQ o MQ en Asana), observación (solo en el
  informe). Con la regla de borde: ante la duda entre no bloqueante y
  observación, por defecto observación.
- **Revisión ligera trimestral de A1:** subconjunto core de los controles A1 de
  mayor criticidad, revisado cada trimestre independientemente del cierre de
  fase.
- **Capa de automatización en tres fases:** Fase 1 (escaneos básicos de CI,
  cualquier repo), Fase 2 (scripts de comparación declarado vs. real,
  específicos del proyecto), Fase 3 (verificación semántica, construida solo si
  las fases 1 y 2 son insuficientes).
- **`/ultrareview`:** recurso reservado para auditoría profunda con agentes en
  paralelo, justificado solo antes de la primera distribución externa, la
  transición a SaaS o un refactor crítico de autenticación.
- **Límites del sistema:** qué no cubren las auditorías y por qué.

---

## Qué NO incluye esta skill

- **Checklists ejecutables.** Esos viven en `docs/project-context/audits/` en el
  repo de cada proyecto, construidos por proyecto a partir de los estándares
  referenciados en la skill. La skill define la metodología; los checklists la
  implementan para un stack concreto.
- **Filtrado específico de stack.** Los ítems de ASVS que no aplican a un stack
  dado se marcan como inactivos en el checklist del proyecto con las condiciones
  de activación documentadas. La skill referencia el estándar completo; el
  checklist hace el filtrado.
- **Inputs específicos del proyecto.** Qué archivos leer, qué archivos de
  manifiesto comprobar, qué patrones arquitectónicos verificar — todo definido
  en el propio checklist y los archivos de contexto del proyecto.

---

## Estándares referenciados

| Familia | Estándar |
|---|---|
| A1 — Seguridad | OWASP ASVS 5.0 Level 2 |
| A2 — Código y Arquitectura | Principios propios curados del proyecto (archivos de contexto) |
| A3 — Dependencias | OpenSSF Scorecard (humano) + Dependabot / pip-audit / npm audit (automatizado) |
| A4 — Coherencia Documental | Checklist derivado de los propios archivos de contexto del proyecto |
| D1 — Datos y Privacidad | GDPR, OWASP Data Privacy Guidelines |
| D2 — Accesibilidad | WCAG 2.2 Level AA, HIG de plataforma |
| D3 — Cumplimiento Legal | Específico de la jurisdicción |

---

## Relación con otras skills

- `working-system` — define cómo opera el chat del departamento de Auditoría
  dentro de la metodología general del proyecto (comandos, prompts para Code,
  tareas de Asana).
- `engineering-standards` — define el listón de calidad de código que A2
  verifica (junto a las propias decisiones de arquitectura del proyecto).
- `code-commands` — `/context-sync` en Claude Code es el complemento ligero y
  continuo de A4; sincroniza los archivos de contexto pero no produce un informe
  de auditoría formal.

---

## Instalación

Guarda la skill desde Claude.ai o empaquétala con:

```bash
python -m scripts.package_skill audit-system/ /output/path/
```

Tras instalarla, crea el primer checklist para A1 en tu proyecto:

```
docs/project-context/audits/
└── checklist-a1-security.md   ← construye este primero
```

Usa el chat del departamento de Auditoría para construirlo: proporciona el stack
del proyecto y el chat recorrerá OWASP ASVS 5.0 Level 2, filtrará por
aplicabilidad y producirá el checklist listo para la primera auditoría.
