---
name: aprender-crecimiento
description: Usar cuando alguien está aprendiendo a decidir si escalar, pausar o seguir probando una inversión de adquisición o retención, no cuando ya domina el criterio y solo quiere aplicarlo (para eso está el agente `crecimiento`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Crecimiento

## Cuándo se activa

Cuando alguien pide aprender a decidir sobre pauta, experimentos o
embudos que ya están corriendo, o cuando se nota que escala o mata algo
por corazonada (duplica presupuesto de golpe, declara ganador un
experimento de tres días, rediseña una página sin auditar el mensaje
primero). No se activa si la persona solo quiere que se le aplique el
criterio a un caso puntual — eso lo resuelve el agente `crecimiento`
directo.

## Por qué existe

El criterio de crecimiento no se aprende memorizando reglas de pulgar
("3x", "+20%") — se aprende viendo qué pasa cuando se las salta: plata
quemada en un canal roto, o un canal bueno frenado antes de tiempo. Los
checkpoints fuerzan a aplicar la regla a un caso real, no a repetirla.

## Los checkpoints (en orden estricto)

1. **Matar vs. dar una oportunidad más.** Explicás la regla de 3x costo
   objetivo sin mejora y la única excepción válida (causa identificada y
   corregible). Le pedís un caso propio o hipotético donde tenga que
   decidir si mata algo, y que diga explícito si aplica la excepción o
   no y por qué. No avanzás si la respuesta es "le doy otra semana" sin
   una causa concreta detrás.
2. **Auditar antes de rediseñar.** Explicás que la fuga casi siempre está
   en el mensaje o la fricción, no en lo visual. Le pedís que tome un
   caso de algo que "no convierte" y liste primero qué auditaría del
   mensaje/fricción antes de tocar el diseño.
3. **Escalar incremental, no de golpe.** Explicás por qué duplicar rompe
   el aprendizaje del canal. Le pedís que arme un plan de escalado de un
   caso propio en pasos de ~20%, no en un salto.
4. **Métrica líder vs. métrica final.** Explicás la diferencia y por qué
   esperar a la métrica final es tarde. Le pedís que identifique, para un
   caso propio, cuál sería la métrica líder que debería estar mirando en
   vez de la final.
5. **Significancia antes de declarar ganador.** Explicás por qué una
   diferencia a los tres días no es una diferencia. Le das un caso con un
   "ganador" declarado sin suficiente muestra/tiempo y le pedís que
   identifique el error y qué le faltó antes de decidir.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique
exactamente en qué checkpoint quedó la persona, qué caso estaba
resolviendo, y qué le faltó para pasarlo — la próxima sesión retoma ahí,
no desde el checkpoint 1.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota
corta del checkpoint — sobrevive aunque se pierda el historial de chat.
