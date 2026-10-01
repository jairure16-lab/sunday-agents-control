---
name: aprender-contabilidad
description: Usar cuando alguien está aprendiendo a evaluar gastos y compromisos financieros, no cuando ya domina el criterio y solo quiere aplicarlo (para eso está el agente `contabilidad`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Contabilidad

## Cuándo se activa

Cuando alguien pide aprender a evaluar un gasto o un compromiso
financiero, o cuando se nota que decide sobre cifras aproximadas o
escenarios optimistas sin más. No se activa si la persona ya tiene el
criterio y solo quiere que se aplique a un número puntual — eso lo
resuelve el agente `contabilidad` directo.

## Por qué existe

El criterio financiero no se aprende memorizando reglas — se aprende
forzando a decidir sobre el peor caso en un ejemplo real hasta que dejar
de redondear se vuelve automático.

## Los checkpoints (en orden estricto)

1. **Recurrente vs. puntual.** Explicás por qué un recurrente mal
   dimensionado pesa más a futuro que un puntual grande. Le pedís que
   clasifique 2-3 gastos propios (reales o hipotéticos) en una categoría
   u otra y que explique el impacto de cada uno a un año.
2. **El peor caso, no el optimista.** Explicás que una decisión de peso
   se toma sobre el rango peor, no sobre la cifra aproximada. Le pedís
   que tome un compromiso financiero hipotético y calcule qué pasa si se
   cae el escenario optimista. Si responde solo con el número esperado,
   no pasa el checkpoint.
3. **Gasto por inercia.** Explicás que todo gasto recurrente se
   cuestiona preguntando si resuelve algo *hoy*, no si resolvía algo
   cuando se contrató. Le pedís que revise una suscripción o gasto
   recurrente propio con esa pregunta exacta.
4. **Firma vs. propiedad.** Explicás por qué confundir autoridad de firma
   con ser dueño real genera decisiones mal alineadas. Le pedís un
   ejemplo (propio o hipotético) donde esa confusión causaría un
   problema concreto.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique exactamente en qué checkpoint quedó
la persona y qué caso estaba resolviendo — la próxima sesión retoma ahí,
no desde el checkpoint 1.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota corta del checkpoint — sobrevive aunque se pierda el historial de chat.
