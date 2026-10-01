---
name: aprender-arquitecto
description: Usar cuando alguien está aprendiendo a auditar el estado técnico real de un proyecto, no cuando ya domina el criterio y solo quiere aplicarlo (para eso está el agente `arquitecto`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Arquitecto

## Cuándo se activa

Cuando alguien pide aprender a auditar un proyecto técnico, o cuando se
nota que diagnostica sobre supuestos (sin haber leído el código/archivo),
mezcla tipos de bloqueador en una sola lista, u ordena los bloqueadores
por lo fácil de arreglar en vez de por severidad real. No se activa si la
persona solo quiere el diagnóstico de un proyecto puntual — eso lo
resuelve el agente `arquitecto` directo.

## Por qué existe

El reflejo natural es diagnosticar rápido y suavizar lo que suena mal.
El criterio real exige lo contrario: leer todo antes de opinar, y nombrar
lo grave sin filtro. Eso se aprende forzando el caso, no explicándolo.

## Los checkpoints (en orden estricto)

1. **No diagnosticar sobre supuestos.** Explicás por qué se declara
   explícito lo que no se pudo leer. Le das un caso con información
   incompleta a propósito y le pedís el diagnóstico — si lo completa con
   suposiciones en vez de marcar el vacío, no pasa el checkpoint.
2. **Clasificar la etapa antes de evaluar.** Explicás las cuatro etapas y
   por qué el estándar de "bloqueador crítico" cambia según la etapa. Le
   das una descripción de proyecto y le pedís que identifique la etapa
   antes de listar ningún problema.
3. **Separar las tres categorías de hallazgo.** Explicás plan-vs-realidad,
   necesidad externa, y bloqueador técnico/diseño como categorías
   distintas. Le das una lista de hallazgos mezclados y le pedís que los
   reclasifique en las tres categorías correctas.
4. **Severidad real, no facilidad de arreglo.** Explicás por qué el más
   grave va primero aunque el más fácil esté más a mano. Le das una lista
   de bloqueadores y le pedís que los ordene por severidad, no por
   esfuerzo.
5. **Nombrar el bloqueador #1 sin suavizarlo.** Le pedís que cierre un
   diagnóstico de ejemplo señalando un solo bloqueador como prioridad y
   el motivo técnico concreto — si la respuesta es vaga o evita nombrar
   algo grave, se repite con otro caso.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique
exactamente en qué checkpoint quedó la persona, qué caso estaba
resolviendo, y qué le faltó para pasarlo — la próxima sesión retoma ahí,
no desde el checkpoint 1.

Si la persona tiene un vault de Obsidian, guardá ahí también una nota
corta del checkpoint — sobrevive aunque se pierda el historial de chat.
