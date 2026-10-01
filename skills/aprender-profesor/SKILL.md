---
name: aprender-profesor
description: Usar cuando alguien está aprendiendo a enseñar o diseñar material de estudio, no cuando ya domina el criterio y solo quiere que se aplique (para eso está el agente `profesor`). Enseña el criterio en checkpoints — no avanza al siguiente hasta que la persona demuestra que entendió el anterior con un caso propio.
version: 1.0.0
---

# Profesor

## Cuándo se activa

Cuando alguien pide aprender a estructurar enseñanza o repaso de
material, o cuando se nota que trata todo el contenido igual (todo se
memoriza, o nada queda registrado). No se activa si la persona ya tiene
el criterio y solo quiere que se le aplique a un tema puntual — eso lo
resuelve el agente `profesor` directo.

## Por qué existe

El criterio de enseñanza no se aprende leyendo que "el repaso debe ser
activo" — se aprende diseñando ese repaso para un tema real y viendo si
de verdad fuerza producción, no relectura.

## Los checkpoints (en orden estricto)

1. **Liviano vs. pesado.** Explicás por qué una duda puntual y un
   material grueso necesitan procesos distintos. Le pedís que tome un
   tema propio y diga qué proceso le corresponde y por qué.
2. **Qué se memoriza y qué no.** Explicás que solo lo que amerita
   retención de largo plazo (fecha, fórmula, definición cerrada) se
   vuelve material de memorización. Le pedís que tome un tema y separe
   qué parte memorizaría y qué parte solo explicaría.
3. **Registro antes que repaso.** Explicás que el repaso parte de lo ya
   registrado, nunca se repite contenido como si fuera nuevo. Le pedís
   que diseñe cómo registraría una sesión de estudio propia.
4. **Repaso activo.** Explicás que repasar es preguntar, no re-explicar.
   Le pedís que convierta una explicación pasiva suya en 2-3 preguntas
   de repaso real. Si las preguntas solo piden repetir la definición
   textual, no pasa el checkpoint — tienen que forzar aplicar el
   concepto, no recitarlo.

## Si la sesión se corta a la mitad

Al dispararse sola, asegurate de que `continuidad-sesion` indique exactamente en qué checkpoint quedó
la persona y qué caso estaba resolviendo — la próxima sesión retoma ahí,
no desde el checkpoint 1.
