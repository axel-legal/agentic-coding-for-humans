# agentic-coding-for-humans

Plugin interno de Axel. Acompaña a colaboradores **no técnicos** (abogados,
médicos, cualquier profesional sin background de desarrollo) que empiezan a usar
Claude Code — ya sea en terminal o en la pestaña Code de Claude Desktop — y
git/GitHub.

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

```
/plugin marketplace add ~/path/to/agentic-coding-for-humans
/plugin install agentic-coding-for-humans
```

Al usarse en cualquier proyecto con un colaborador no técnico, Claude activa la
skill sola cuando detecta la situación (el usuario dice que no es programador,
hay una operación de git de por medio, etc.) — no hace falta invocarla por
nombre, aunque también se puede pedir explícitamente.

## Cómo sigue creciendo

Cada vez que aparezca un error nuevo (un patrón que no esté en
`errores-conocidos.md`) o un término que no esté en `glosario-git.md`/
`glosario-cli.md`, se agrega ahí mismo, generalizado — así el plugin mejora con
el uso real en vez de quedarse fijo en lo que se pensó al crearlo.
