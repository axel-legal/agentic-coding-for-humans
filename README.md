# agentic-coding-for-humans

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)
[![Format: SKILL.md](https://img.shields.io/badge/format-SKILL.md-informational.svg)](https://code.claude.com/docs/en/plugins.md)

Plugin creado por Axel Technologies. Acompaña a colaboradores **no técnicos** —
de marketing, operaciones, finanzas, legal, o cualquier otra área sin background
de desarrollo — que empiezan a usar Claude Code (ya sea en terminal o en la
pestaña Code de Claude Desktop) y git/GitHub.

No enseña a programar. Enseña a **no asumir** que quien está del otro lado
entiende jerga de terminal/git/GitHub, y a **frenar y explicar en lenguaje
simple antes** de cualquier acción irreversible o que afecte a otros
colaboradores — en vez de descubrirlo después.

---

## Qué incluye

Es un plugin de una sola skill — vive entera en la raíz del repo, lista para
copiar tal cual a cualquier agente compatible con `SKILL.md`:

- **`SKILL.md`** — la lógica principal: cubre los primeros pasos tanto en
  terminal como en Claude Desktop (pestaña Code) — qué es un comando, qué
  significa el cartel de permiso en cada entorno, cómo salir sin miedo — y
  traduce cada operación de git a lenguaje llano antes de ejecutarla.
- **`references/glosario-cli.md`** — banco de traducciones a lenguaje simple para
  los términos de terminal/Claude Code que más se repiten (comando, flag, ruta,
  sesión, permisos, proceso, etc.).
- **`references/glosario-git.md`** — lo mismo para los términos de git que más se
  repiten (push, force-push, rebase, branch, .gitignore, etc.).

---

## Cómo se usa

No hace falta invocarla por nombre ni aprenderse un comando — una vez
instalada, Claude la activa sola cuando detecta la situación. Ejemplos reales
de mensajes que la disparan:

- **"No sé programar, ayudame a subir estos cambios a GitHub"** → antes de
  hacer `commit`/`push`, Claude explica en lenguaje simple qué va a pasar y
  espera confirmación, en vez de asumir que ya se entendió.
- **"Es la primera vez que uso esto"** → dispara la introducción de primeros
  pasos (qué es un comando, qué significa el cartel de permiso, cómo salir sin
  romper nada) antes de que haga falta.
- **"Borrá todo y empezá de nuevo"** o cualquier pedido que implique algo
  irreversible → la skill frena, explica el efecto real (qué se pierde, a
  quién más afecta) y pide confirmación explícita antes de ejecutar.
- **"¿Este repo está listo para hacerlo público?"** → audita lo que ya existe
  (no solo el árbol de archivos actual, también todo el historial de git en
  busca de datos que quedaron atrás) y reporta hallazgos antes de tocar nada.

También se puede pedir directo: **"actuá según la skill agentic-coding-for-humans"**
o simplemente **"explicame esto en términos simples"**.

---

## Instalación

### Individual (cualquier plan de Claude, incluido Free)

| Método | Requiere | Cómo |
|---|---|---|
| **Claude Code (CLI)** | Cualquier plan | `/plugin marketplace add axel-legal/agentic-coding-for-humans` y luego `/plugin install agentic-coding-for-humans` |
| **Claude Desktop → Skills** | Cuenta Free | Panel izquierdo → **Customize** → **Skills**. (El botón `+` de *plugins* de marketplace, con GitHub App conectada, requiere plan Pro/Team — esto no lo necesita) |
| **Manual, cualquier agente** | Ninguno | Cloná el repo y copiálo a `~/.claude/skills/agentic-coding-for-humans/` (o el equivalente en Codex, OpenCode, etc. — todos leen el mismo formato `SKILL.md`) |

```bash
/plugin marketplace add axel-legal/agentic-coding-for-humans
/plugin install agentic-coding-for-humans
```

La vía manual es la más segura si no aparece un botón directo para agregarlo
por URL — para alguien sin experiencia de terminal, puede ser más fácil
pedirle este paso puntual a alguien que sí la use, una sola vez.

### Organización (plan Claude Team o Enterprise)

Para que el plugin aparezca instalado solo, sin que cada persona lo agregue a
mano. Lo hace un admin de la organización, una sola vez, desde Claude Desktop:

1. Instalar la [Claude GitHub App](https://github.com/apps/claude/installations)
   en el repo → seleccionar la organización → autorizar el repo
   `axel-legal/agentic-coding-for-humans`.
2. Claude Desktop → **Organization settings** → pestaña **Plugins** → **Add
   plugins** → GitHub → ingresar `axel-legal/agentic-coding-for-humans`.
3. Elegir visibilidad: **"Installed by default"** (aparece solo para todo el
   equipo — recomendado para colaboradores no técnicos) o **"Available for
   install"** (cada quien lo instala si quiere — desde Claude Desktop →
   **Customize** → **Skills** → "Organization plugins" → `+`).

Fuentes: [Manage plugins for your organization](https://support.claude.com/en/articles/13837433-manage-plugins-for-your-organization),
[Create and distribute a plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces.md),
[GitHub integration](https://support.claude.com/en/articles/10167454-use-the-github-integration).

---

## Licencia

[Apache 2.0](./LICENSE).
