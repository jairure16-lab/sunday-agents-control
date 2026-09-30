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
3. Copiá `agents/mentor.md` a `~/.claude/agents/`.
4. Abrí (o creá) `~/.claude/CLAUDE.md` y agregá estas líneas al final:

   ```
   @rules/desacuerdo-obligatorio.md
   @rules/modo-orquestador.md
   @rules/gestion-contexto-sesion.md
   ```

5. Abrí una sesión nueva de Claude Code y preguntale: *"¿qué reglas tenés
   activas ahora?"* — si te las puede explicar con sus propias palabras,
   quedó bien instalado.

## Instalación (nivel proyecto — solo para un repo puntual)

Mismo proceso, pero dentro de la carpeta del proyecto en vez de `~/.claude/`:
`<tu-proyecto>/.claude/rules/`, `<tu-proyecto>/.claude/skills/`, y un
`CLAUDE.md` en la raíz del proyecto.

## Qué hacer después

Las tres reglas y las dos skills que vienen acá salieron de casos reales
míos (bugs repetidos, trabajo que quedó a medias entre sesiones). Las tuyas
van a salir de lo mismo: la primera vez que algo te moleste de cómo trabaja
el agente, o que te encuentres explicando lo mismo dos veces, esa es la
señal de que necesitás una regla o una skill nueva — no una excepción que
recordás de memoria.
