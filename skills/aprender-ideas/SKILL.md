---
name: aprender-ideas
description: Usar cuando alguien está aprendiendo a evaluar si una idea suelta vale la pena perseguirla, guardarla o descartarla, no cuando ya domina el criterio y solo quiere aplicarlo (para eso está el agente `ideas`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Ideas

## Cuándo se activa

Cuando alguien pide aprender a evaluar ideas sueltas, o cuando se nota
que trata cada ocurrencia como proyecto (sin evaluar tensión ni
viabilidad) o descarta ideas sin explicar el motivo. No se activa si la
persona solo quiere que se evalúe una idea puntual — eso lo resuelve el
agente `ideas` directo.

## Por qué existe

El criterio de "esto tiene tensión o no" no se aprende con una
definición — se aprende forzando a explicar el motivo del descarte o la
captura en un caso real, hasta que dejar de hacerlo se sienta raro.

## Los checkpoints (en orden estricto)

1. **Los tres ángulos sin preguntar.** Explicás minimal/completo/
   inesperado y por qué no se pide más información antes de dar el
   primer análisis. Le pedís que tome una idea propia (o inventada) y
   escriba los tres ángulos sin agregar preguntas de por medio. No
   avanzás si pide más contexto antes de intentarlo.
2. **Descartar con motivo, no con reflejo.** Explicás que "no tiene
   tensión" es un juicio que se explica, no un "no me convence". Le das
   una idea de ejemplo y le pedís que la descarte o la capture
   explicando el motivo concreto. Si el motivo es vago ("no me gusta"),
   se repite con otro ejemplo.
3. **Tensión alta, viabilidad baja ≠ descartar.** Explicás por qué eso se
   captura con fecha de revisión en vez de perderse. Le pedís que tome
   un caso con esas características y arme la captura correcta (no el
   descarte).
4. **Sin siguiente paso no está capturada.** Explicás que una idea sin
   acción concreta para hoy/mañana no cuenta como resuelta. Le pedís que
   revise una "idea capturada" de ejemplo sin siguiente paso y la
   complete.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique
exactamente en qué checkpoint quedó la persona, qué caso estaba
resolviendo, y qué le faltó para pasarlo — la próxima sesión retoma ahí,
no desde el checkpoint 1.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota
corta del checkpoint — sobrevive aunque se pierda el historial de chat.
