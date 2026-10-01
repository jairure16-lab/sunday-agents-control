---
name: aprender-marketing
description: Usar cuando alguien está aprendiendo a decidir qué contenido crear y a quién le habla, no cuando ya domina el criterio y solo quiere que se aplique (para eso está el agente `marketing`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Marketing

## Cuándo se activa

Cuando alguien pide aprender a decidir qué contenido crear y para quién,
o cuando se nota que arma contenido sin un "para quién" claro (demografía
genérica en vez de un problema concreto, copia el formato de un
competidor sin preguntar si resuelve algo). No se activa si la persona
solo quiere que se le aplique el criterio a una pieza puntual — eso lo
resuelve el agente `marketing` directo.

## Por qué existe

El criterio de posicionamiento no se aprende memorizando "pilares de
contenido" — se aprende evaluando piezas concretas contra un job-to-be-done
real hasta que el chequeo se vuelve automático.

## Los checkpoints (en orden estricto)

1. **Job to be done, no demografía.** Explicás por qué "mujeres 25-40" no
   alcanza. Le pedís que tome una audiencia real o hipotética y escriba
   qué problema concreto resuelve ver la pieza. No avanzás hasta que la
   respuesta sea un problema, no un dato demográfico.
2. **El hueco real.** Explicás que se busca qué no está haciendo bien
   nadie localmente, no lo que hace el competidor grande. Le pedís que
   identifique un hueco real en su propio mercado o proyecto, con
   evidencia (no una corazonada).
3. **Prueba social como estrategia.** Explicás por qué dar crédito cuando
   alguien republica es parte del plan, no cortesía. Le pedís que diseñe
   ese paso para un caso propio.
4. **La regla de precio y la aprobación humana.** Explicás que nunca se
   publica precio en canal abierto y que toda pieza pasa por aprobación
   humana antes de salir. Le pedís que revise una pieza (propia o de
   ejemplo) y señale si rompe alguna de las dos reglas. Si no detecta una
   violación real puesta a propósito, se repite el checkpoint con otra
   pieza.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique exactamente en qué checkpoint quedó
la persona, qué caso estaba resolviendo, y qué le faltó para pasarlo — la
próxima sesión retoma ahí, no desde el checkpoint 1.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota
corta del checkpoint — sobrevive aunque se pierda el historial de chat.
