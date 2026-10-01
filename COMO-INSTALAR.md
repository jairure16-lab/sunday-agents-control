# Cómo instalar esto en tu propio Claude

No hace falta entender Claude Code a fondo para instalar esto — pero de paso
vas a aprender qué es cada pieza, porque eso es lo que se usa después para
armar las tuyas.

## Los cuatro conceptos que necesitás conocer

- **`CLAUDE.md`** — el archivo que Claude Code lee siempre, en cada sesión,
  en cada proyecto. Ahí van las reglas que querés que se cumplan siempre.
  Puede vivir en `~/.claude/CLAUDE.md` (aplica a todo lo que hagas) o dentro
  de un proyecto puntual (aplica solo ahí).
- **`rules/*.md`** — reglas individuales, una por archivo. `CLAUDE.md` las
  incluye con la sintaxis `@ruta/al/archivo.md` — así no tenés un solo
  archivo gigante, sino piezas que podés prender, apagar o editar por
  separado.
- **`skills/<nombre>/SKILL.md`** — una skill es una tarea reutilizable que
  Claude invoca solo, cuando detecta que aplica (no hace falta que la
  llames por nombre cada vez). El `description` en la parte de arriba del
  archivo (el "frontmatter") es lo que Claude lee para decidir cuándo
  usarla — por eso tiene que ser específico.
- **`agents/<nombre>.md`** — un subagente: una personalidad y un set de
  herramientas separados del Claude principal, que se invoca para una tarea
  puntual (ej. "mentor" para entrevistar, "code-reviewer" para revisar
  código) y devuelve el resultado sin cargar todo ese contexto en la
  conversación principal.

## Instalación (nivel global — aplica a todo lo que hagas)

1. Copiá la carpeta `rules/` completa a `~/.claude/rules/` (si no existe
   `~/.claude/`, creala).
2. Copiá cada carpeta dentro de `skills/` a `~/.claude/skills/`.
3. Copiá cada archivo dentro de `agents/` a `~/.claude/agents/` (mentor
   para entrevistar antes de construir, y un par por rol de negocio —
   ventas, marketing, contabilidad, admin, profesor — para aplicar
   criterio real en cada área).
4. Abrí (o creá) `~/.claude/CLAUDE.md` y agregá estas líneas al final:

   ```
   @rules/desacuerdo-obligatorio.md
   @rules/modo-orquestador.md
   @rules/gestion-contexto-sesion.md
   ```

5. Abrí una sesión nueva de Claude Code y preguntale: *"¿qué reglas tenés
   activas ahora?"* — si te las puede explicar con sus propias palabras,
   quedó bien instalado.

## Importante: skills y agentes se recargan distinto

Si instalás o agregás algo a mitad de una sesión ya abierta:

- Las **skills se recargan solas** — apenas el archivo queda en
  `~/.claude/skills/`, Claude ya la puede usar en esa misma sesión.
- Los **agentes NO** — el listado de agentes disponibles se fija al abrir
  la sesión. Un agente nuevo (o uno que acabás de instalar) no va a
  responder hasta que abrís una sesión de Claude Code nueva.

Si copiaste un agente y "no aparece" o "no responde", antes de asumir que
algo está roto, confirmá que abriste una sesión nueva.

## Cómo se invoca cada cosa, en el uso diario

- **Reglas:** no se invocan, ya están siempre puestas — por eso el test
  del paso 5 es preguntar "¿qué reglas tenés activas?", no "activá tal
  regla".
- **Skills:** tampoco las invocás por nombre normalmente — Claude las
  activa solo cuando lo que estás pidiendo matchea el `description` del
  archivo. Si no se activa sola y sabés cuál querés, podés pedirla
  explícito ("usá la skill codex-handoff para esto").
- **Agentes:** se invocan para una tarea puntual, ya sea porque Claude
  decide que tu pedido coincide con la descripción de uno, o porque se lo
  pedís explícito ("aplicá el criterio del agente ventas a este lead").
  A diferencia de una skill, un agente corre aparte y te devuelve solo el
  resultado final, sin llenar la conversación principal de su proceso.

## Instalación (nivel proyecto — solo para un repo puntual)

Mismo proceso, pero dentro de la carpeta del proyecto en vez de `~/.claude/`:
`<tu-proyecto>/.claude/rules/`, `<tu-proyecto>/.claude/skills/`, y un
`CLAUDE.md` en la raíz del proyecto.

## El patrón agente + skill por rol

Para cada rol de negocio (ventas, marketing, contabilidad, admin,
profesor) hay dos piezas separadas, a propósito:

- **`agents/<rol>.md`** aplica el criterio directo — lo usás cuando ya
  sabés el criterio y solo querés que se ejecute sobre un caso puntual.
- **`skills/aprender-<rol>/SKILL.md`** enseña ese mismo criterio en
  checkpoints — no avanza al siguiente hasta que demostrás que
  entendiste el anterior con un caso propio. Si una sesión se corta a la
  mitad de un checkpoint, se apoya en la skill `continuidad-sesion` para
  retomar exacto donde quedaste, no desde el principio.

## Qué es uso real de Jair y qué es recomendación externa (mía, Sunday)

Para ser honestos con lo que hay acá: `ventas`, `marketing` y `admin`
salen de patrones reales de cómo Jair decide — los extraje de su propio
material y se los confirmé antes de escribirlos. `profesor` sale de
invertir cómo un sistema real (ADENI) ya le enseña a él. `contabilidad`
es distinto: Jair no tenía un patrón propio documentado y separable de
sus finanzas privadas, así que ese criterio lo armé yo con buenas
prácticas financieras generales — no asumas que es "cómo decide Jair" en
particular, es una base razonable que podés y deberías ajustar a tu
propio criterio.

Recomendación de Sunday que tampoco sale del flujo de Jair: considerá un
vault de Obsidian como memoria persistente de todo esto (ver más abajo).
Jair usa su propio vault para su vida entera, no como parte de SAC — la
idea de sumarlo acá como pieza recomendada del repo es mía, para que
cualquiera que instale esto tenga dónde guardar lo que los agentes y
skills generan, no solo lo que queda en el historial de chat.

## Recomendado: un vault de Obsidian como memoria

Las skills `aprender-*` y `profesor` generan algo que vale la pena
conservar: registros de sesión, checkpoints resueltos, prompts de
continuidad. Sin un lugar fijo para eso, todo vive solo en el historial
de chat — se pierde o se vuelve imposible de buscar. Un vault de Obsidian
(gratis, local, en markdown plano, sin vendor lock-in) resuelve esto
mejor que una base de datos o una nota suelta:

1. Creá una carpeta para el vault, separada del repo de SAC (no la
   mezcles con el código — una es conocimiento, el otro es config de
   agente).
2. Convención mínima de carpetas:
   ```
   00_Inbox/              → captura rápida, sin clasificar
   01_Registro_Sesiones/  → lo que `profesor` y las skills de checkpoint escriben
   02_Checkpoints/        → una nota por rol con el checkpoint donde quedaste
   ```
3. Cuando `profesor` o un `aprender-<rol>` pregunten dónde registrar la
   sesión, apuntalos a una nota dentro de `01_Registro_Sesiones/` — así
   el "Al cerrar" de cada agente tiene un destino real, no solo la
   conversación.
4. Si usás el vault entre varias máquinas, sincronizalo con una
   herramienta separada del repo de código (Git, o un servicio de sync de
   archivos) — nunca comitees el vault al mismo repo público de SAC. Si
   algún día el repo es público y el vault no lo es, mezclarlos es el
   error que más caro sale a futuro.

Esto último (separar vault de repo, nunca comitearlo junto) no es un
capricho — es una práctica de seguridad básica para cualquier repo que
vaya a ser público, no solo para este.

## Qué hacer después

Las reglas y skills que vienen acá salieron de casos reales de Jair
(bugs repetidos, trabajo que quedó a medias entre sesiones, criterio de
negocio que tuvo que explicar más de una vez). Las tuyas van a salir de
lo mismo: la primera vez que algo te moleste de cómo trabaja el agente,
o que te encuentres explicando lo mismo dos veces, esa es la señal de
que necesitás una regla, una skill, o un agente nuevo — no una excepción
que recordás de memoria. Para ese paso específico (de "me pasó una cosa"
a "archivo nuevo en el repo") está la skill `aprender-construir` — es la
única que no enseña un rol de negocio, enseña a fabricar tu propia pieza.
