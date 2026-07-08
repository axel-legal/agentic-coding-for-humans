# agentic-coding-for-humans

Plugin creado por Axel Technologies. Acompaña a colaboradores **no técnicos** —
de marketing, operaciones, finanzas, legal, o cualquier otra área sin background
de desarrollo — que empiezan a usar Claude Code (ya sea en terminal o en la
pestaña Code de Claude Desktop) y git/GitHub.

No enseña a programar. Enseña a **no asumir** que quien está del otro lado
entiende jerga de terminal/git/GitHub, y a **frenar y explicar en lenguaje
simple antes** de cualquier acción irreversible o que afecte a otros
colaboradores — en vez de descubrirlo después.

## Qué incluye

- **`skills/explain-before-acting/`** — la skill principal: cubre los primeros
  pasos tanto en terminal como en Claude Desktop (pestaña Code) — qué es un
  comando, qué significa el cartel de permiso en cada entorno, cómo salir sin
  miedo — y traduce cada operación de git a lenguaje llano antes de ejecutarla,
  aplicando una lista viva de errores ya cometidos para no repetirlos.
- **`references/glosario-cli.md`** — banco de traducciones a lenguaje simple para
  los términos de terminal/Claude Code que más se repiten (comando, flag, ruta,
  sesión, permisos, proceso, etc.).
- **`references/glosario-git.md`** — lo mismo para los términos de git que más se
  repiten (push, force-push, rebase, branch, .gitignore, etc.).
- **`references/errores-conocidos.md`** — catálogo vivo de errores reales ya
  cometidos en sesiones con colaboradores no técnicos, generalizados (sin
  nombres ni datos de ningún caso concreto). Se le agrega una entrada cada vez
  que aparece un patrón nuevo.

## Instalación

Al usarse en cualquier proyecto con un colaborador no técnico, Claude activa la
skill sola cuando detecta la situación (el usuario dice que no es programador,
hay una operación de git de por medio, etc.) — no hace falta invocarla por
nombre, aunque también se puede pedir explícitamente.

### Para cualquiera (repo público, no hace falta pertenecer a Axel)

**Claude Code (CLI) — cualquier plan:**
```
/plugin marketplace add axel-legal/agentic-coding-for-humans
/plugin install agentic-coding-for-humans
```

**Claude Desktop, sin organización conectada:** panel izquierdo → **Customize**
→ **Skills** → agregar como plugin personal apuntando al repo. Esta vía funciona
de forma confiable con repos públicos como este.

**Sin pasar por "plugin" en absoluto:** cloná el repo y copiá la carpeta
`skills/explain-before-acting/` a `~/.claude/skills/` (o el equivalente de tu
agente — Codex, OpenCode, etc. leen el mismo formato `SKILL.md`). Claude la
detecta sola, sin necesidad de marketplace.

### Instalación automática para todo el equipo de Axel (Claude Desktop, plan Team/Enterprise)

Esta vía es opcional — sirve para que el plugin aparezca solo, sin que cada
persona lo instale a mano. Requiere **plan Claude Team o Enterprise** (no
Personal/Pro) y la hace un admin de la organización, una sola vez:

1. Instalar la Claude GitHub App en el repo: https://github.com/apps/claude/installations
   → seleccionar la org `axel-legal` → autorizar el repo `agentic-coding-for-humans`.
2. En Claude Desktop → **Organization settings** → pestaña **Plugins** → **Add
   plugins** → GitHub → ingresar `axel-legal/agentic-coding-for-humans`.
3. Elegir visibilidad: **"Installed by default"** (aparece solo para todo el
   equipo, recomendado para colaboradores no técnicos) o **"Available for
   install"** (cada quien lo instala si quiere — en ese caso, cada usuario lo
   activa desde Claude Desktop → **Customize** → **Skills** → "Organization
   plugins" → `+`).

Fuentes: [Manage plugins for your organization](https://support.claude.com/en/articles/13837433-manage-plugins-for-your-organization),
[Create and distribute a plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces.md),
[GitHub integration](https://support.claude.com/en/articles/10167454-use-the-github-integration).
