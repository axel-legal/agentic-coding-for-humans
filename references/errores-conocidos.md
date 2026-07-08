# Errores conocidos — lista viva

Catálogo de errores reales, ya cometidos en sesiones con colaboradores no
técnicos, generalizados (sin nombres, sin datos del caso concreto) para que
sirvan de referencia en cualquier proyecto. Agregar una entrada nueva cada vez
que aparezca un patrón que no esté todavía, con la lección al final — no hace
falta el detalle completo del incidente, alcanza con el patrón y cómo evitarlo.

## 1. Notas de trabajo/continuidad de sesión commiteadas

**Qué pasó:** un archivo tipo "en qué quedamos" (estado del proyecto, notas de
sesión a sesión) terminó commiteado y pusheado al repo compartido. Con el tiempo
acumuló rutas de máquina local, nombres reales de colaboradores, y hasta la
mención de un incidente de seguridad interno — todo eso quedó en el historial de
git, visible para cualquiera con acceso al repo.

**Por qué pasa:** para alguien no técnico, un archivo `.md` en la raíz del repo no
se distingue de cualquier otro documento de trabajo — no hay una señal visual de
"esto es distinto, esto no se comparte".

**Lección:** las notas de continuidad de sesión nunca se commitean. Van a un
sistema de memoria de agente (si existe) o a una carpeta local ignorada por git
(`.local/`, o el nombre que use el proyecto) — explicar la diferencia entre "está
en mi computadora" y "está en el repo compartido" la primera vez que se cree un
archivo de este tipo.

## 2. Datos personales/sensibles en archivos versionados

**Qué pasó:** el nombre real y el estatus profesional de un colaborador (ej. si
está o no autorizado para cierta actividad) quedó escrito directamente en
archivos de referencia del repo, en vez de vivir en una configuración externa no
versionada. Además, un patrón de trabajo legítimo (dejar constancia de quién
verificó cada dato) terminó repitiendo un nombre real decenas de veces a lo largo
de varios archivos.

**Por qué pasa:** para alguien no técnico, anotar "lo verificó [nombre]" es una
forma natural y honesta de dejar trazabilidad — no hay intuición de que eso
implique un dato personal quedando en un historial de git permanente.

**Lección:** cualquier dato que identifique a una persona real (nombre completo,
estatus/credencial profesional, dato de contacto) va a una configuración externa
o se reemplaza por una referencia genérica al rol ("el responsable designado",
"verificación interna"). La trazabilidad de *qué se verificó* se puede mantener
sin atar el *quién* a un nombre propio en un archivo compartido.

## 3. `git add -A`/`git add .` sin revisar antes

**Qué pasó:** agregar todos los archivos modificados de una sola vez, sin mirar
la lista completa de `git status`, dejó pasar un archivo que no debía
commitearse.

**Lección:** antes de un `add` amplio, mostrar `git status` completo y confirmar
que cada archivo nuevo/modificado tiene sentido — en especial si alguno tiene un
nombre que suena a "notas", "borrador", "temporal" o similar.

## 4. Operaciones irreversibles ejecutadas sin explicar el efecto

**Qué pasó:** un `push --force` (tras reescribir el historial del repo para
sacar contenido sensible) se ejecutó tras una confirmación genérica de tipo
"sí, dale", sin haber explicado antes en términos simples que eso iba a
desincronizar cualquier otra copia del repo que alguien más tuviera.

**Lección:** cualquier operación que reescriba historia, fuerce un push, borre
una rama, o descarte cambios sin posibilidad de deshacer, se explica en los
términos del "Mandato central" de esta skill **antes** de pedir confirmación —
la confirmación de una acción no explicada no cuenta como consentimiento
informado.

## 5. Mover contenido de trabajo a una carpeta que no se sincroniza

**Qué pasó:** para "no publicar todavía" contenido en revisión, se movió a una
carpeta ignorada por git (existe solo en la máquina de quien la creó). Nadie más
que esa persona tiene acceso a ese contenido — no hay respaldo automático, no
viaja entre copias del repo, y si esa máquina falla, el trabajo se pierde.

**Lección:** antes de mover algo a una carpeta local-only, explicar exactamente
qué implica ("esto va a existir solo en tu computadora, nadie más lo va a ver, y
si la perdés no hay copia en ningún lado salvo que hagas un respaldo aparte") y
confirmar que la persona lo entiende — no asumir que "local" se interpreta igual
que "privado pero respaldado".

## 6. Atajo destructivo para resolver un obstáculo

**Qué pasó (patrón general, no ligado a un caso puntual):** ante un problema
(archivo bloqueado, comando que falla, conflicto), la tentación es "borrar y
volver a empezar" en vez de entender la causa. Con un colaborador no técnico de
por medio, ese atajo puede borrar trabajo que la otra persona no sabía que
estaba en riesgo.

**Lección:** investigar la causa raíz antes de proponer una solución
destructiva, y si la solución destructiva es genuinamente la única opción,
explicarlo y confirmar igual que cualquier otra acción irreversible.
