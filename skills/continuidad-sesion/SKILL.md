---
name: continuidad-sesion
description: Usar cuando durante una sesión de trabajo aparece algo que se decide diferir a otra sesión — por riesgo, alcance, tocar otro repo, o falta de tiempo. Genera automáticamente un prompt de continuidad autocontenido con pasos numerados, para que la próxima sesión no tenga que reconstruir el contexto de memoria.
version: 1.0.0
---

# Continuidad de Sesión

## Cuándo se activa

Automáticamente, sin que se pida — apenas se decide diferir trabajo a otra
sesión.

## Por qué existe

Sin esto, "lo seguimos después" significa reconstruir el contexto de
memoria la próxima vez, y la memoria falla justo en los detalles que
importan: qué endpoint ya existe, qué variable de entorno hace falta, qué
archivo se tocó a medias.

## Qué generar

Un prompt de continuidad con:

1. **Pasos numerados en orden estricto** — nunca un resumen narrativo.
2. **Rutas de archivo exactas** que hay que abrir.
3. **Qué ya existe y se debe reusar** (función, endpoint, componente) —
   para que la próxima sesión no lo reconstruya de cero.
4. **Qué falta construir**, explícito.
5. **Variables de entorno o configuración relevante.**
6. **El objetivo final, verificable** — algo que se pueda confirmar como
   "listo" sin ambigüedad, no "que funcione bien".

## Regla de fondo

No es opcional ni hay que pedirlo cada vez — se genera solo, igual que un
bug siempre dispara la skill `codex-handoff`.
