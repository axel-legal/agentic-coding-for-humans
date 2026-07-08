---
name: pair-with-non-technical
description: >
  Guía cómo trabajar con git/GitHub cuando el colaborador que está del otro lado (o
  vos mismo) no tiene background técnico — es abogado, médico, u otro profesional
  sin experiencia de desarrollo. Traduce cada operación de git a lenguaje simple
  antes de ejecutarla, frena y explica antes de cualquier acción irreversible o que
  afecte a otros colaboradores, y aplica una lista viva de errores ya cometidos
  (`references/errores-conocidos.md`) para no repetirlos. Úsala cuando el usuario
  mencione que no es técnico/programador, que está aprendiendo git, cuando el repo
  tiene colaboradores no técnicos, o antes de commits/pushes/operaciones de git en
  cualquier proyecto donde esto aplique.
user-invocable: true
---

# Acompañar a un colaborador no técnico

Esta skill no enseña a programar — enseña a **no asumir** que quien está del otro
lado entiende jerga de git/GitHub, y a **frenar antes de lo irreversible** en vez
de después.

## Cuándo aplica

- El usuario dice explícitamente que no es programador/developer, o que es
  abogado/médico/otro profesional trabajando con Claude Code por primera vez.
- Hay un repo con más de un colaborador y al menos uno no es técnico.
- Cualquier momento en que estés por ejecutar una operación de git — no hace falta
  que el usuario la pida por nombre técnico ("hacé un rebase"), alcanza con que la
  intención sea esa ("que quede limpio", "sácalo de todos lados").

## Mandato central

Antes de **cualquier** acción que sea (a) difícil de revertir, (b) afecte el
repositorio compartido o a otros colaboradores, o (c) pueda exponer información
sensible: **parar, explicar en lenguaje simple qué va a pasar y por qué, y esperar
confirmación explícita** — no asumir que la opción "recomendada" ya se entendió
solo por haberla nombrado.

No hay atajos: si el colaborador no técnico dice "sí, dale" a algo que no le
explicaste en sus términos, esa confirmación no cuenta — hay que volver a explicar
hasta que la decisión sea informada, no solo autorizada.

## Cómo traducir, no solo explicar

Mal: *"¿Confirmás el `git push --force` a `origin/main`?"*
Bien: *"Esto va a reemplazar la versión del repo que está en GitHub por la tuya
—incluida toda su historia—. Si [la otra persona] tiene una copia descargada en su
computadora, la suya va a quedar desincronizada y va a tener que descargarla de
nuevo. ¿Seguimos?"*

Reglas de traducción:
- Nombrá la operación técnica una sola vez, entre paréntesis, para que quien
  aprende pueda buscarla después — pero la explicación central va en palabras
  llanas.
- Explicá el **efecto observable**, no el mecanismo interno (no hace falta explicar
  qué es un commit hash para explicar que la historia cambió).
- Si la acción afecta a otra persona (otro colaborador, un cliente, alguien que
  clonó el repo), decilo explícitamente y qué tiene que hacer esa persona después.
- Usá `references/glosario-git.md` como banco de traducciones ya probadas para los
  términos que se repiten (force-push, rebase, merge, branch, .gitignore, etc.) —
  agregale una entrada nueva cuando expliques un término que no está ahí todavía.

## Checklist de errores ya conocidos

Antes de commitear, pushear, o mover archivos, repasá
`references/errores-conocidos.md` — es una lista viva de errores reales ya
cometidos en sesiones anteriores con colaboradores no técnicos, para no repetirlos.
Si en esta sesión aparece un error nuevo que no está en la lista, agregalo ahí
(generalizado, sin nombres ni datos del caso concreto) al cerrar la sesión.

Resumen de las categorías más comunes (detalle y ejemplos en el archivo):
1. Notas de trabajo/continuidad de sesión commiteadas por accidente.
2. Datos personales o sensibles (nombres reales, rutas de máquina de otra persona,
   incidentes internos) metidos en archivos versionados sin necesidad.
3. `git add -A`/`git add .` sin revisar antes qué se está agregando.
4. Operaciones irreversibles (`push --force`, `reset --hard`, reescritura de
   historia, borrar ramas/archivos) ejecutadas sin explicar el efecto ni confirmar.
5. Mover contenido de trabajo a una carpeta que no se sincroniza (gitignorada,
   local-only) sin explicar que eso significa "no hay respaldo ni se comparte".
6. Usar un atajo destructivo para resolver un obstáculo en vez de investigar la
   causa raíz.

## Detectar el error en curso, no solo el ya cometido

Si mientras trabajás notás que se está por commitear/pushear algo que parece un
error humano — una nota personal, un dato de cliente, algo que no debería estar
ahí — **decilo antes de que se pushee**, no esperes a que pregunten. La regla dura
del guardrail de secreto/confidencialidad de cualquier proyecto (si existe un
`CLAUDE.md` propio del repo) sigue aplicando encima de esta skill, no en su lugar.

## Cuando ya se cometió el error

1. No culpar ni asumir mala intención — es normal no saber algo que nunca se
   enseñó.
2. Explicar qué pasó en términos simples, y qué tan grave es (¿solo está en el
   último commit sin pushear? ¿ya está en GitHub? ¿alguien más ya lo descargó?).
3. Proponer la opción más segura primero (ej.: sacarlo del próximo commit) antes
   de ofrecer una opción más agresiva (ej.: reescribir todo el historial) — y
   explicar el costo de cada una antes de que el colaborador elija.
4. Si la solución implica una operación irreversible (reescribir historia, forzar
   un push), aplicar el mandato central de arriba igual que para cualquier otra
   acción.

## Qué NO hace esta skill

- No reemplaza el criterio de un desarrollador cuando la decisión es genuinamente
  técnica (arquitectura, elección de librerías, etc.) — es sobre higiene de
  git/repo y comunicación, no sobre cómo programar.
- No asume que "ya se explicó una vez" alcanza para todas las sesiones futuras —
  cada sesión nueva puede ser con la misma persona pero sin memoria de la
  explicación anterior; repetila la primera vez que vuelva a aparecer el tema en
  esa sesión.
