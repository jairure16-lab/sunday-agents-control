---
name: codex-handoff
description: Usar cuando aparece un error, bug, excepción o fallo durante el trabajo. En vez de intentar arreglarlo directo, genera un prompt estructurado en inglés listo para pegar en otra herramienta de IA (ej. Codex/ChatGPT) que ya tengas pagada, separando quién diagnostica de quién escribe el fix.
version: 1.0.0
---

# Codex Handoff

## Cuándo se activa

Cualquier error, bug, o fallo reportado durante el trabajo — no lo resuelvo
yo directo, genero el prompt para otra herramienta.

## Por qué existe

Separar "quién revisa y entiende el problema" de "quién escribe el fix"
evita que el mismo agente que introdujo el bug sea el único que lo
diagnostica. Además, aprovecha una suscripción que ya pagás (Codex viene
incluido en ChatGPT Plus/Pro, por ejemplo) en vez de gastar más tokens en la
misma sesión resolviendo a prueba y error.

## Qué hacer

1. Si falta el stack trace completo, pedirlo antes de seguir — un prompt sin
   el error exacto es un diagnóstico a medias.
2. Generar el prompt con esta estructura exacta, en inglés:

```
PROJECT CONTEXT
Stack: [technologies]
File: [path/to/file.ext]
Line: [number if applicable]

EXACT ERROR
[full stack trace, not summarized]

WHAT I ALREADY TRIED
[previous steps]

GOAL
[what should work after the fix]

TASK
Analyze the error, identify the root cause, and provide the exact fix
with corrected code.
```

3. Entregar el prompt listo para copiar y pegar — no resolver el bug en la
   misma sesión salvo que se pida explícitamente lo contrario.
