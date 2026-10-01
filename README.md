# Sunday Agents Control (SAC)

Esto no es una teoría genérica de "cómo usar IA" — es el setup real de Jair
Ureña para trabajar con un agente: las reglas y flujos que corren todos los
días construyendo Ratio Solutions y sus proyectos. Lo armé yo, Sunday, junto
con él, y lo documento acá para que cualquiera pueda instalarlo, usarlo, y
aprender a construirse el suyo.

Este repo es el siguiente nivel después del taller `taller-web-boilerplate`:
ahí aprendiste a construir un sitio con ayuda de un agente. Acá está cómo se
ve cuando ese agente ya tiene reglas propias, memoria, y flujos que se
invocan por nombre en vez de explicarse de cero cada vez.

## Estructura

```
rules/    → reglas permanentes que el agente sigue en toda sesión
skills/   → flujos reutilizables, se activan solos cuando aplican
agents/   → subagentes especializados para una tarea puntual
```

Ver [`COMO-INSTALAR.md`](COMO-INSTALAR.md) para copiar esto a tu propio
Claude paso a paso — incluye por qué conviene sumarle un vault de Obsidian
como memoria del sistema, no solo los archivos del repo.

## Qué hay ahorita

**Agentes** (`agents/`) — aplican criterio real sobre un caso puntual:
`mentor` (entrevista antes de construir), `ventas`, `marketing`,
`contabilidad`, `admin`, `profesor`.

**Skills** (`skills/`) — `codex-handoff` y `continuidad-sesion` son de
flujo general. Por cada rol de negocio arriba hay una skill hermana con
nombre separado del agente para no pisarse (`aprender-ventas`,
`aprender-marketing`, `aprender-contabilidad`, `aprender-admin`,
`aprender-profesor`) que enseña ese mismo criterio en checkpoints en vez
de aplicarlo directo — no avanza al siguiente checkpoint hasta que
resolvés un caso propio, y usa `continuidad-sesion` para retomar exacto
donde quedaste si la sesión se corta a la mitad. `aprender-construir` es
distinto a los demás: no enseña un rol de negocio, enseña a fabricar tu
propia regla/skill/agente una vez que ya instalaste esto.

## Por qué esto y no solo "prompts sueltos"

Escribir la misma instrucción larga cada vez que abrís una sesión de IA es
perder tiempo. Una regla se escribe una vez y se aplica siempre. Una skill se
guarda una vez y se invoca cuando la necesitás. Ese es el salto real entre
"chatear con IA" y "dirigir un agente".

## Cómo se construyó

Cada archivo en `rules/` y `skills/` nace de un caso real de Jair: un error
que se repitió, una decisión que tuvo que corregirle al agente más de una
vez, un flujo que hace seguido. Nada de esto es teórico.

Dicho eso — Jair no es perfecto ni tiene todas las respuestas, y este repo
tampoco. Donde su flujo real no alcanzaba o no aplicaba a alguien más (por
ejemplo, el criterio de `contabilidad`), yo completé con buenas prácticas
externas en vez de forzar un patrón que no existía. Ver `COMO-INSTALAR.md`
para dónde queda explícito qué viene de su uso real y qué es recomendación
mía, de Sunday, por fuera de eso.
