# Glosario de terminal/CLI en lenguaje llano

Banco de traducciones para explicar términos de terminal y Claude Code a alguien
sin background técnico. Mismo formato que `glosario-git.md`: término, traducción
simple, y cuándo importa que lo sepa. Agregar entradas nuevas cuando aparezca un
término que no está todavía.

## terminal
**Qué es en simple:** una ventana donde le escribís instrucciones a la
computadora en texto, en vez de hacer clic en botones. Todo lo que hace una app
con clics, la terminal lo hace escribiendo.
**Cuándo importa:** es el lugar donde Claude Code corre — no hay nada "misterioso"
adentro, es una forma distinta de dar la misma instrucción.

## comando
**Qué es en simple:** una instrucción escrita que la computadora entiende y
ejecuta al apretar Enter. Tiene una estructura: el nombre del comando, a veces
"opciones" (ver flag/opción) y a veces datos extra (ver argumento).
**Cuándo importa:** antes de aprobar que Claude corra un comando, vale la pena
que te digan en una frase qué hace ese comando específico — no hace falta
entender cada palabra del comando en sí.

## flag / opción
**Qué es en simple:** un modificador que cambia cómo se comporta un comando,
generalmente escrito con guiones (ej. `--force`, `-a`). Es como un "además hacé
esto" agregado al comando principal.
**Cuándo importa:** algunos flags cambian un comando normal en uno mucho más
arriesgado (ej. `--force`, `--hard`) — son justamente los que ameritan pararse a
explicar antes de correr (ver el glosario de git para casos concretos).

## argumento
**Qué es en simple:** el dato sobre el que actúa el comando — por ejemplo, en
"borrar archivo.txt", `archivo.txt` es el argumento: le dice al comando *sobre
qué* actuar.

## ruta (path)
**Qué es en simple:** la "dirección" de un archivo o carpeta dentro de la
computadora — como una dirección postal, pero de carpetas dentro de carpetas.
**Cuándo importa:** confundir la ruta (ej. correr algo en la carpeta equivocada)
es una de las formas más comunes de que un comando haga algo no deseado en el
lugar equivocado.

## directorio de trabajo (cwd)
**Qué es en simple:** la carpeta "donde estás parado" en este momento dentro de
la terminal — los comandos actúan ahí salvo que se les diga explícitamente otra
ruta.

## sesión
**Qué es en simple:** una conversación con Claude, desde que empieza hasta que
se cierra (con `/exit`, cerrando la ventana, o simplemente dejando de usarla).
**Cuándo importa:** cerrar una sesión no borra el trabajo que ya quedó guardado
en archivos — pero si algo se discutió en el chat y no se guardó en ningún
archivo, eso no persiste solo. Esa distinción vale la pena aclararla la primera
vez.

## permiso / aprobar una acción
**Qué es en simple:** el cartel que aparece antes de que Claude haga algo real
(crear, modificar o borrar un archivo, correr un comando, etc.), pidiendo tu
visto bueno antes de proceder.
**Cuándo importa:** es la red de seguridad principal para alguien que recién
empieza — nunca hay que aprobar algo "porque sí"; si no se entiende qué va a
pasar, la respuesta correcta es preguntar primero, no aprobar.

## proceso
**Qué es en simple:** un programa que está corriendo en este momento en la
computadora (puede ser algo que arrancó un comando, o algo que sigue corriendo
"en segundo plano" mientras hacés otra cosa).

## variable de entorno
**Qué es en simple:** un valor guardado que varios programas pueden leer sin que
esté escrito directamente en el comando — se usa mucho para guardar claves o
configuración sin dejarla a la vista en texto plano.
**Cuándo importa:** es una de las formas correctas de guardar una clave/token sin
exponerla — si un comando pide "pegar tu API key" directamente en la terminal o
en un archivo, vale la pena confirmar que ese es el lugar correcto antes de
hacerlo.

## script
**Qué es en simple:** un archivo con una lista de comandos guardados, para
correrlos todos juntos en vez de uno por uno.
**Cuándo importa:** correr un script de una fuente que no conocés (descargado de
internet, copiado de un lugar no verificado) es equivalente a aprobar *todos* los
comandos que tiene adentro de una sola vez — el mandato de "explicar antes de
ejecutar" aplica con más razón todavía.

## `Ctrl+C` (interrumpir)
**Qué es en simple:** la combinación de teclas que detiene lo que está corriendo
en este momento en la terminal, sin borrar nada ya guardado.
**Cuándo importa:** es la forma segura de "parar" algo que se está corriendo y
no se quiere seguir esperando — no rompe el proyecto, solo corta lo que estaba
en curso.

## `/exit` (salir de la sesión)
**Qué es en simple:** el comando para cerrar la conversación con Claude de forma
prolija.
**Cuándo importa:** el trabajo que ya se guardó en archivos permanece; lo que
solo existía en la conversación (y no se escribió a un archivo) no.
