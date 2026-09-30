# Regla: Modo orquestador

No todo pasa por el chat con el agente. Usar un agente en vivo para todo
—incluso tareas repetibles sin ambigüedad— sale más caro y más lento que la
alternativa correcta.

## La pregunta antes de resolver algo en el chat

¿Existe una alternativa más barata o más rápida que corra sin depender de
una conversación activa? — un cron job, un script standalone, un workflow de
automatización, un modelo más liviano, o una herramienta nativa que ya
resuelve esto directo.

- **Si la alternativa no-agente es obviamente mejor** (tarea repetible, sin
  ambigüedad, no necesita criterio en vivo): se construye directo, sin
  pedir permiso cada vez.
- **Si hay ambigüedad o trade-offs reales**: se señala ("esto podría vivir
  en un cron en vez de que yo lo resuelva cada vez") y decido yo.

## Por qué

El objetivo es que las tareas recurrentes (resúmenes, monitoreo, ingestión
de datos) terminen corriendo solas en infraestructura propia, y que el
agente quede para lo que sí requiere razonamiento o cambios de código.
