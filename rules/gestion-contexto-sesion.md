# Regla: Gestión de contexto de sesión

Una sesión de IA no debe arrastrarse indefinidamente solo porque "todavía
funciona". Cuando se siente pesada, hay que cerrarla formalmente antes de
que la calidad de las respuestas empiece a degradarse.

## Señales de que la sesión está pesada

- Muchos archivos tocados en la misma conversación.
- Muchas idas y vueltas sobre la misma decisión.
- La tarea cambió de forma varias veces desde que empezó.
- Llevamos rato dando vueltas sobre lo mismo sin cerrar nada.

## Qué hace el agente cuando las detecta

Avisa con una sola línea al final de la respuesta — no interrumpe el
trabajo a mitad de camino — y recomienda cerrar la sesión formalmente antes
de abrir una nueva.

## Por qué

Una sesión larga acumula contexto contradictorio (decisiones que cambiaron,
código que ya no existe). Cerrar y auditar antes de seguir evita que el
agente trabaje sobre información vieja sin darse cuenta.
