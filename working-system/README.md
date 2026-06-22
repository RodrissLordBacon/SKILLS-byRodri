# working-system skill

Sistema de trabajo profesional con Claude.ai y Claude Code para proyectos
de software. Define los actores, el vocabulario operativo, los comandos,
el sistema de tareas en Asana, el ciclo de vida de tareas, el cierre de
sesión y el protocolo de handoff.

---

## Qué hace esta skill

Cuando está instalada, Claude.ai conoce y aplica:

- **Los tres actores:** Claude.ai (pensar y decidir), Claude Code (ejecutar),
  el usuario (coordinar). Cada uno con su rol y sus límites.
- **El vocabulario operativo:** intercambio, tarea, sesión — tres palabras
  con significados distintos que el sistema usa con precisión.
- **Los departamentos:** qué son, la regla de pertenencia, la regla de
  redirección con prompt incluido.
- **Los comandos:** `[SQ]`, `[MQ]`, `cerrar sesión`, `reciclar chat` — con
  su comportamiento exacto y cuándo usarlos.
- **El sistema de tareas en Asana:** un tablero por proyecto con secciones
  SideQuests y MainQuests; creación inmediata vía MCP al anotar una tarea.
- **El ciclo de vida de una tarea:** apertura → discusión → resumen → OK
  → prompt → Code ejecuta → verificación → cierre.
- **El flujo de cierre de sesión:** con o sin rama según los archivos
  tocados, Conventional Commits, actualización de espejos.
- **El protocolo de handoff a Code:** formato fijo de seis campos, resumen
  antes del prompt, restricción de improvisación.
- **La generación de informes internos:** flujo, nombres de archivo,
  destino al cerrar la tarea.
- **Los mecanismos de recuperación:** sesión olvidada, comportamiento
  inesperado de Code, bloqueos, chats desactualizados.

---

## Estructura

```
working-system/
└── SKILL.md    # Sistema completo — una sola fuente de verdad
```

La skill no tiene references separados porque el sistema es metodológico,
no stack-specific. Lo que varía entre proyectos (departamentos concretos,
nombre del tablero de Asana, ruta del repo, conector MCP) vive en las
instrucciones de cada proyecto, no en la skill.

---

## Qué vive en la skill vs. qué vive en las instrucciones del proyecto

| Contenido | Dónde vive |
|---|---|
| Qué es un departamento, regla de pertenencia, regla de redirección | **Skill** |
| Lista concreta de departamentos del proyecto | **Instrucciones del proyecto** |
| Comandos y su comportamiento | **Skill** |
| Nombre del tablero de Asana | **Instrucciones del proyecto** |
| Flujo de cierre de sesión | **Skill** |
| Ruta del repo y conector MCP | **Instrucciones del proyecto** |
| Protocolo de handoff a Code (formato fijo) | **Skill** |
| Archivos de contexto del proyecto | **Instrucciones del proyecto** |

---

## Relación con otras skills

Esta skill define el sistema de trabajo. Otras skills definen cómo hacer
el trabajo dentro del sistema:

- `github-workflow` — el flujo git que se ejecuta en el cierre de sesión
  y en los prompts para Code.
- `atomic-design` — la metodología de componentes UI que los departamentos
  de Frontend y Diseño aplican.
- `audit-system` *(en construcción)* — el sistema de auditorías que el
  departamento de Auditoría ejecuta.
- `engineering-standards` — los estándares de código que Claude Code aplica.

---

## Instalación

Guardar la skill desde Claude.ai o empaquetar con:

```bash
python -m scripts.package_skill working-system/ /ruta/de/salida/
```

Instalar en el Project junto con las instrucciones del proyecto concreto.
La skill cubre el sistema; las instrucciones cubren el proyecto.
