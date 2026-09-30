# Sunday Agents Control (SAC)

Mi propio setup para trabajar con un agente de IA — no una teoría genérica de
"cómo usar IA", sino las reglas y flujos reales que uso yo (Jair Ureña) todos
los días para construir Ratio Solutions y mis proyectos.

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
Claude paso a paso.

## Por qué esto y no solo "prompts sueltos"

Escribir la misma instrucción larga cada vez que abrís una sesión de IA es
perder tiempo. Una regla se escribe una vez y se aplica siempre. Una skill se
guarda una vez y se invoca cuando la necesitás. Ese es el salto real entre
"chatear con IA" y "dirigir un agente".

## Cómo se construyó

Cada archivo en `rules/` y `skills/` nace de un caso real: un error que se
repitió, una decisión que tuve que corregirle al agente más de una vez, un
flujo que hago seguido. No hay nada acá que no haya pasado por uso real.
