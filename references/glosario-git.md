# Glosario git en lenguaje llano

Banco de traducciones para explicar términos de git/GitHub a alguien sin
background técnico. Usar como base y agregar entradas nuevas cuando aparezca un
término que no está todavía — mismo formato: término técnico, traducción
simple, y cuándo importa que lo sepa.

## commit
**Qué es en simple:** una "foto" guardada de cómo están los archivos en un
momento dado, con una nota de qué cambió y por qué.
**Cuándo importa:** cada commit queda guardado para siempre en el historial —
por eso no se debe meter ahí nada que no se quiera que quede registrado
permanentemente (ver `errores-conocidos.md`, punto 1 y 2).

## push
**Qué es en simple:** subir tus "fotos" (commits) guardadas en tu computadora al
repositorio compartido en GitHub, para que los demás las vean.
**Cuándo importa:** antes de pushear es el último momento fácil para revisar que
no se está subiendo algo indebido — después queda visible para todos los que
tengan acceso.

## pull
**Qué es en simple:** bajar a tu computadora los cambios que otros ya subieron a
GitHub.

## push --force (forzar el push)
**Qué es en simple:** reemplazar por completo la versión del repositorio que
está en GitHub por la tuya, incluso si eso significa borrar commits que otros
ya habían subido.
**Cuándo importa:** si alguien más tiene una copia descargada del repo, esa
copia queda "rota" después de un force-push — esa persona va a necesitar volver
a descargar el repo entero o hacer un paso extra para arreglarlo. Nunca se hace
sin explicar esto primero y confirmar.

## rama (branch)
**Qué es en simple:** una copia paralela del proyecto donde se puede trabajar
sin afectar la versión "oficial" (generalmente llamada `main`), hasta que esté
lista para unirse.
**Cuándo importa:** es la forma más segura de "seguir trabajando algo" sin
sacarlo del repo compartido ni arriesgar la versión que todos usan.

## merge
**Qué es en simple:** unir los cambios de una rama a otra (normalmente, traer lo
que se hizo en una rama de trabajo hacia `main`).

## reescribir el historial (rebase, filter-repo, amend, reset)
**Qué es en simple:** cambiar "fotos" (commits) que ya estaban guardadas —no
agregar una nueva, sino modificar o borrar las que ya existían.
**Cuándo importa:** es de las operaciones más delicadas que hay. Si esas fotos
ya se compartieron con alguien más (ya se pusheó), cambiarlas después
obliga a un force-push, con todo lo que eso implica (ver arriba). Siempre se
explica y se confirma antes.

## .gitignore
**Qué es en simple:** una lista de archivos o carpetas que le decís a git "nunca
los subas al repositorio compartido, ignoralos".
**Cuándo importa:** es el lugar correcto para notas personales, configuración
local de la máquina, o cualquier cosa que no deba compartirse — pero ojo: lo que
ya se había subido ANTES de agregarlo al `.gitignore` sigue estando en el
historial; agregarlo ahí no borra lo viejo (ver `errores-conocidos.md`, punto 1).

## repositorio local-only / carpeta ignorada
**Qué es en simple:** una carpeta que existe solo en tu computadora — nadie más
la ve, no se sube a ningún lado, y no hay copia de respaldo automática.
**Cuándo importa:** si la máquina falla o se borra sin querer, ese contenido se
pierde para siempre a menos que exista un respaldo aparte. No confundir "no lo
ve nadie más" con "está seguro/respaldado".

## clonar (clone)
**Qué es en simple:** descargar una copia completa del repositorio (con toda su
historia) a tu computadora por primera vez.
**Cuándo importa:** después de una reescritura de historial (ver arriba), volver
a clonar desde cero suele ser más simple y seguro que tratar de "arreglar" una
copia vieja.

## historial de git
**Qué es en simple:** el registro completo de todos los commits que existieron
alguna vez en el repositorio, en orden.
**Cuándo importa:** cualquier cosa que entre al historial (aunque sea por
accidente) queda ahí, visible, hasta que alguien la saque de forma explícita y
deliberada (una operación delicada, no un simple "borrar el archivo").
