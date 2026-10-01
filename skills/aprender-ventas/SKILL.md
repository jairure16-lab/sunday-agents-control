---
name: aprender-ventas
description: Usar cuando alguien está aprendiendo a evaluar leads y decidir qué vender, no cuando ya domina el criterio y solo quiere que se aplique (para eso está el agente `ventas`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Ventas

## Cuándo se activa

Cuando alguien pide aprender a evaluar leads o decidir qué ofrecer, o
cuando se nota que aplica el criterio de venta a medias (persigue leads
chicos igual que grandes, cotiza en público, compite por precio). No se
activa si la persona solo quiere que se le aplique el criterio a un caso
puntual — eso lo resuelve el agente `ventas` directo.

## Por qué existe

El criterio de venta real no se aprende leyendo una lista de reglas — se
aprende clasificando casos hasta que el patrón queda internalizado. Cada
checkpoint fuerza a la persona a aplicar el criterio a un caso concreto
antes de seguir, en vez de asentir y olvidarlo.

## Los checkpoints (en orden estricto)

1. **Tamaño manda el trato.** Explicás que el tamaño real del proyecto
   (no la simpatía del contacto) decide si es trato B2B o venta estándar.
   Le pedís un caso propio o hipotético y que lo clasifique. No avanzás
   hasta que clasifique bien y explique el por qué con sus palabras.
2. **Canal de origen.** Explicás por qué un canal que busca solo vale más
   que uno que hay que perseguir. Le pedís que ordene 2-3 leads
   hipotéticos por prioridad usando ese criterio.
3. **Qué vender.** Explicás la jerarquía (imagen de marca / argumento
   técnico / volumen) y qué se descarta aunque exista en catálogo. Le
   pedís que arme una recomendación para un caso y que justifique qué
   descartó y por qué.
4. **La objeción de precio.** Explicás que el argumento nunca es precio
   sino cumplimiento de plazo. Le pedís que responda en sus palabras a un
   "por qué ustedes y no el competidor barato" hipotético. Si responde con
   descuento o precio, no pasa el checkpoint — se repite con feedback.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique exactamente en qué checkpoint quedó
la persona, qué caso estaba resolviendo, y qué le faltó para pasarlo — la
próxima sesión retoma ahí, no desde el checkpoint 1.
