<!-- lang:en -->

# working-system skill

Professional working methodology with Claude.ai and Claude Code for software
projects. Defines the actors, operative vocabulary, commands, Asana task
system, task lifecycle, session management, and the Claude Code handoff
protocol.

---

## What this skill does

When installed, Claude.ai knows and applies:

- **§0 Core principle:** the non-negotiable quality standard and the
  decision criterion for every technical proposal.
- **The three actors:** Claude.ai (think and decide), Claude Code (execute),
  the user (coordinate). Each with its role and limits.
- **Operative vocabulary:** exchange, task, session — three words with
  distinct meanings the system uses precisely.
- **Departments:** what they are, when to use them vs. a single generalist
  chat, the ownership rule, the redirection rule with prompt included.
- **Context files as real memory:** why keeping them current is what makes
  the department system work across chat recycles.
- **Commands:** `[SQ]`, `[MQ]`, `recycle chat` — with their exact behaviour
  and when to use them.
- **The Asana task system:** one board per project with SideQuests and
  MainQuests sections; immediate creation via MCP when a task is noted.
- **The task lifecycle:** open → discuss → summary → OK → prompt → Code
  executes → verify → close.
- **Session management in Claude Code:** `/checkpoint`, `/session-close`,
  `/context-sync` — the three commands that handle commits, PRs, and
  mirror updates.
- **The Code handoff protocol:** fixed six-field format, summary before
  the prompt, no improvisation.
- **Internal reports:** flow, file naming, destination when closing the task.
- **Error recovery:** forgotten session, unexpected Code behaviour, blocks,
  outdated chats.

---

## What lives in this skill vs. in project instructions

| Content | Where |
|---|---|
| Core principle and quality standard | **Skill** |
| What a department is, ownership rule, redirection rule | **Skill** |
| Concrete list of departments for the project | **Project instructions** |
| Commands and their behaviour | **Skill** |
| Asana board name and ID | **Project instructions** |
| Session management commands | **Skill** (+ `~/.claude/skills/` in Code) |
| Repo path and MCP connector | **Project instructions** |
| Handoff protocol format | **Skill** |
| Project context files | **Project instructions** |

---

## Relation to other skills

This skill defines the working system. Other skills define how to do the
work within the system:

- `github-workflow` — the git flow that `/session-close` and `/checkpoint`
  follow.
- `atomic-design` — the UI component methodology that Frontend and Design
  departments apply.
- `engineering-standards` — the code standards that Claude Code applies.
- `audit-system` *(in progress)* — the audit system that the Audit
  department runs.
- `code-commands` — the three Claude Code personal skills that implement
  the session management layer (`/session-close`, `/checkpoint`,
  `/context-sync`).

---

## Installation

Save the skill from Claude.ai or package with:

```bash
python -m scripts.package_skill working-system/ /output/path/
```

Install in the Project alongside the project-specific instructions.
The skill covers the system; the instructions cover the project.

<!-- lang:es -->

# working-system skill

Metodología de trabajo profesional con Claude.ai y Claude Code para proyectos
de software. Define los actores, el vocabulario operativo, los comandos, el
sistema de tareas en Asana, el ciclo de vida de las tareas, la gestión de
sesiones y el protocolo de handoff con Claude Code.

---

## Qué hace esta skill

Una vez instalada, Claude.ai conoce y aplica:

- **§0 Principio fundamental:** el estándar de calidad innegociable y el
  criterio de decisión para toda propuesta técnica.
- **Los tres actores:** Claude.ai (pensar y decidir), Claude Code (ejecutar),
  el usuario (coordinar). Cada uno con su rol y sus límites.
- **Vocabulario operativo:** intercambio, tarea, sesión — tres palabras con
  significados distintos que el sistema usa con precisión.
- **Departamentos:** qué son, cuándo usarlos frente a un único chat
  generalista, la regla de propiedad, la regla de redirección con prompt
  incluido.
- **Los archivos de contexto como memoria real:** por qué mantenerlos al día
  es lo que hace funcionar el sistema de departamentos a través de los
  reciclajes de chat.
- **Comandos:** `[SQ]`, `[MQ]`, `recycle chat` — con su comportamiento exacto
  y cuándo usarlos.
- **El sistema de tareas en Asana:** un tablero por proyecto con secciones de
  SideQuests y MainQuests; creación inmediata vía MCP cuando se anota una
  tarea.
- **El ciclo de vida de la tarea:** abrir → discutir → resumen → OK → prompt →
  Code ejecuta → verificar → cerrar.
- **La gestión de sesiones en Claude Code:** `/checkpoint`, `/session-close`,
  `/context-sync` — los tres comandos que gestionan los commits, los PRs y las
  actualizaciones de los mirrors.
- **El protocolo de handoff con Code:** formato fijo de seis campos, resumen
  antes del prompt, sin improvisación.
- **Informes internos:** flujo, nomenclatura de archivos, destino al cerrar la
  tarea.
- **Recuperación de errores:** sesión olvidada, comportamiento inesperado de
  Code, bloqueos, chats desactualizados.

---

## Qué vive en esta skill frente a las instrucciones de proyecto

| Contenido | Dónde |
|---|---|
| Principio fundamental y estándar de calidad | **Skill** |
| Qué es un departamento, regla de propiedad, regla de redirección | **Skill** |
| Lista concreta de departamentos del proyecto | **Instrucciones de proyecto** |
| Comandos y su comportamiento | **Skill** |
| Nombre e ID del tablero de Asana | **Instrucciones de proyecto** |
| Comandos de gestión de sesiones | **Skill** (+ `~/.claude/skills/` en Code) |
| Ruta del repo y conector MCP | **Instrucciones de proyecto** |
| Formato del protocolo de handoff | **Skill** |
| Archivos de contexto del proyecto | **Instrucciones de proyecto** |

---

## Relación con otras skills

Esta skill define el sistema de trabajo. Otras skills definen cómo hacer el
trabajo dentro del sistema:

- `github-workflow` — el flujo de git que siguen `/session-close` y
  `/checkpoint`.
- `atomic-design` — la metodología de componentes de UI que aplican los
  departamentos de Frontend y Diseño.
- `engineering-standards` — los estándares de código que aplica Claude Code.
- `audit-system` *(en progreso)* — el sistema de auditoría que ejecuta el
  departamento de Auditoría.
- `code-commands` — las tres skills personales de Claude Code que implementan
  la capa de gestión de sesiones (`/session-close`, `/checkpoint`,
  `/context-sync`).

---

## Instalación

Guarda la skill desde Claude.ai o empaquétala con:

```bash
python -m scripts.package_skill working-system/ /output/path/
```

Instálala en el Proyecto junto a las instrucciones específicas del proyecto.
La skill cubre el sistema; las instrucciones cubren el proyecto.
