---
name: aprender-construir
description: Usar cuando alguien ya instaló SAC y quiere aprender a construir su propia regla, skill o agente — no uno de los roles de negocio ya incluidos, sino el meta-paso de convertir un patrón propio repetido en una pieza nueva de este repo. Enseña en checkpoints — no avanza al siguiente hasta que la persona produce su propio archivo, no un ejemplo genérico.
version: 1.0.0
---

# Aprender a construir tu propia pieza

## Cuándo se activa

Cuando alguien ya tiene SAC instalado y pregunta algo como "¿cómo hago mi
propia skill/agente/regla?" o "quiero agregar algo mío a esto". Es el
único skill de este repo que no enseña un criterio de negocio — enseña a
fabricar las piezas que enseñan criterio de negocio.

## Por qué existe

Instalar los 5 roles ya armados (ventas, marketing, contabilidad, admin,
profesor) resuelve el problema del día uno. El problema del día 30 es
distinto: la persona tiene su propio patrón repetido (un error que
corrige siempre, una decisión que explica dos veces) y no sabe
convertirlo en algo que el agente recuerde solo. Ese paso — de "me pasó
una cosa" a "archivo nuevo en `rules/`, `skills/` o `agents/`" — es lo que
enseña este skill.

## Los checkpoints (en orden estricto)

1. **Detectar la señal real.** Explicás que la señal nunca es "se me
   ocurrió una idea" sino un hecho ya ocurrido: algo que corregiste más
   de una vez, algo que explicaste dos veces, o un caso que quedó a
   medias entre sesiones. Le pedís un caso propio y real, con fecha o
   contexto — no avanzás si el ejemplo es hipotético o genérico.
2. **Clasificar dónde vive.** Explicás la diferencia real entre las tres
   piezas:
   - **Regla** (`rules/*.md`, importada desde `CLAUDE.md`) — algo que
     debe cumplirse siempre, en toda sesión, sin que nadie lo pida.
   - **Skill** (`skills/<nombre>/SKILL.md`) — una tarea reutilizable que
     se autoactiva cuando el `description` matchea la situación; no hace
     falta invocarla por nombre.
   - **Agente** (`agents/<nombre>.md`) — un criterio o personalidad
     separado, con su propio set de herramientas, que se invoca para una
     tarea puntual y devuelve un resultado sin cargar todo su contexto a
     la conversación principal.

   Le pedís que tome el caso del checkpoint 1 y diga cuál de las tres es
   y por qué las otras dos no. Si no puede justificar por qué descartó
   las otras dos, no pasa el checkpoint.
3. **Escribir el primer borrador — reusando formato, no inventando uno.**
   Según lo que clasificó en el checkpoint 2, le pedís que abra el
   archivo real más parecido que ya existe en el repo (`agents/mentor.md`
   para agente, `skills/codex-handoff/SKILL.md` para skill de flujo
   general, cualquier `skills/aprender-*/SKILL.md` para skill de
   enseñanza) y escriba su propio archivo con esa misma estructura de
   frontmatter y secciones — no un formato nuevo de su invención.
4. **Instalar y probar — con el gotcha real.** Le explicás esto, porque
   si no lo sabe va a pensar que está roto:
   - Las **skills se recargan solas**, apenas copiás el archivo a
     `~/.claude/skills/` ya aparece disponible en la misma sesión.
   - Los **agentes necesitan sesión nueva** — el listado de agentes
     disponibles queda fijo al abrir la sesión, así que un agente
     agregado a mitad de sesión no aparece hasta que abrís una sesión
     de Claude Code nueva.

   Le pedís que instale su pieza y, si es agente, que confirme
   explícitamente que abrió sesión nueva antes de reportar que "no
   funciona".

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique
exactamente en qué checkpoint quedó la persona, cuál es su caso real (no
lo inventes de nuevo la próxima sesión), y qué le faltó para pasarlo.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota corta del checkpoint — sobrevive aunque se pierda el historial de chat.
