<!-- lang:en -->

# Claude Skills — by Rodri

A collection of Claude skills I use in my own development projects.
Free. No strings attached.

---

## What's a Claude skill?

A skill is a file that Claude reads automatically when the task matches.
No commands. No reminders. No "please write clean code" in every session.
You install it once and it works.

---

## engineering-standards

The default quality bar for all code I write with Claude.

Covers five stacks with language-specific rules for each:

- **Python** / FastAPI
- **JavaScript** / TypeScript / React
- **Dart** / Flutter
- **C#** / .NET
- **SQL**

Universal principles across all of them:
- Solidity over speed. No patches, no "fix it later".
- Standards over invention. If it's a solved problem, use the standard.
- Clean Architecture: business logic independent of framework, UI and I/O.
- Explicit error handling. A hidden failure is a patch by another name.
- Domain-specific naming. No `utils`, `helpers` or `common` dumping grounds.

---

## How to install

1. Download the `.skill` file from this repo.
2. Go to [claude.ai](https://claude.ai) → Settings → Skills.
3. Upload the file.

That's it. Claude will use it automatically when you're working on code.

---

## License

MIT — use it, modify it, share it.
If you adapt it to your stack, I'd be curious to know how.

<!-- lang:es -->

# Claude Skills — by Rodri

Una colección de skills de Claude que uso en mis propios proyectos de desarrollo.
Gratis. Sin condiciones.

---

## ¿Qué es una skill de Claude?

Una skill es un archivo que Claude lee automáticamente cuando la tarea encaja.
Sin comandos. Sin recordatorios. Sin "por favor escribe código limpio" en cada
sesión. La instalas una vez y funciona.

---

## engineering-standards

El listón de calidad por defecto para todo el código que escribo con Claude.

Cubre cinco stacks con reglas específicas de lenguaje para cada uno:

- **Python** / FastAPI
- **JavaScript** / TypeScript / React
- **Dart** / Flutter
- **C#** / .NET
- **SQL**

Principios universales para todos ellos:
- Solidez antes que velocidad. Sin parches, sin "ya lo arreglo luego".
- Estándares antes que invención. Si es un problema resuelto, usa el estándar.
- Clean Architecture: lógica de negocio independiente del framework, la UI y la I/O.
- Manejo de errores explícito. Un fallo oculto es un parche con otro nombre.
- Nombres específicos del dominio. Sin cajones de sastre `utils`, `helpers` o `common`.

---

## Cómo instalar

1. Descarga el archivo `.skill` de este repo.
2. Ve a [claude.ai](https://claude.ai) → Ajustes → Skills.
3. Sube el archivo.

Ya está. Claude la usará automáticamente cuando trabajes en código.

---

## Licencia

MIT — úsala, modifícala, compártela.
Si la adaptas a tu stack, me daría curiosidad saber cómo.
