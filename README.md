# dev-for-non-tech

Plugin de Claude Code para acompañar a colaboradores **no técnicos** (abogados,
médicos, cualquier profesional sin background de desarrollo) que trabajan sobre
un repositorio de git con ayuda de Claude Code.

No enseña a programar. Enseña a **no asumir** que quien está del otro lado
entiende jerga de git/GitHub, y a **frenar y explicar en lenguaje simple antes**
de cualquier acción irreversible o que afecte a otros colaboradores — en vez de
descubrirlo después.

## Qué incluye

- **`skills/pair-with-non-technical/`** — la skill principal: traduce cada
  operación de git a lenguaje llano antes de ejecutarla, y aplica una lista viva
  de errores ya cometidos para no repetirlos.
- **`references/glosario-git.md`** — banco de traducciones a lenguaje simple para
  los términos de git que más se repiten (push, force-push, rebase, branch,
  .gitignore, etc.). Crece con cada término nuevo que haga falta explicar.
- **`references/errores-conocidos.md`** — catálogo vivo de errores reales ya
  cometidos en sesiones con colaboradores no técnicos, generalizados (sin
  nombres ni datos de ningún caso concreto). Se le agrega una entrada cada vez
  que aparece un patrón nuevo.

## Instalación

```
/plugin marketplace add <ruta-o-repo-de-este-plugin>
/plugin install dev-for-non-tech
```

Al usarse en cualquier proyecto con un colaborador no técnico, Claude activa la
skill sola cuando detecta la situación (el usuario dice que no es programador,
hay una operación de git de por medio, etc.) — no hace falta invocarla por
nombre, aunque también se puede pedir explícitamente.

## Cómo sigue creciendo

Cada vez que aparezca un error nuevo (un patrón que no esté en
`errores-conocidos.md`) o un término que no esté en `glosario-git.md`, se agrega
ahí mismo, generalizado — así el plugin mejora con el uso real en vez de
quedarse fijo en lo que se pensó al crearlo.
