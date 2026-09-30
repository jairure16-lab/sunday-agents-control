# Prompt de continuidad — Equipo completo de agentes en SAC

Pegar esto al inicio de la próxima sesión dedicada a este tema.

---

CONTEXTO DEL PROYECTO
Repo: `C:\projects\sunday-agents-control` (SAC) — ya tiene `rules/` (3
reglas), `skills/codex-handoff/` y `skills/continuidad-sesion/` (formato
real SKILL.md con frontmatter), `agents/mentor.md` (agente de prueba de
concepto), `CLAUDE.md` con los `@imports`, y `COMO-INSTALAR.md`. Repo
público en GitHub personal de Jair, ligado al taller de ADEN University
(ver [[project_sac_repo_taller]] en memoria).

OBJETIVO DE ESTA SESIÓN
Agregar a `agents/` un agente por cada rol de negocio: ventas, marketing,
contabilidad, admin, profesor — con el mismo nivel de profundidad que
`mentor.md` (instrucciones de comportamiento reales, no descripciones
genéricas de una línea).

FUENTE DE LA QUE SE EXTRAE EL CRITERIO
Vault de Obsidian de Jair: `G:\Mi unidad\[PERSONAL_LIFE]\05_SECOND_BRAIN_OBSIDIAN`
— NO copiar contenido tal cual. El objetivo es identificar **patrones de
cómo Jair evalúa/decide** en cada área (qué pregunta antes de aprobar un
gasto, cómo prioriza un lead de ventas, qué chequea antes de publicar
contenido) y generalizarlos a instrucciones de agente, sin nombres de
clientes, cifras reales de Ratio, ni datos de personas del equipo.

PASOS EN ORDEN ESTRICTO

1. Abrir `05_SECOND_BRAIN_MASTER/PROYECTOS_MAESTRO.md` dentro del vault
   para entender qué carpetas del vault corresponden a qué área (ventas,
   finanzas, contenido, etc.) antes de leer nada más.
2. Por cada rol (ventas, marketing, contabilidad, admin, profesor):
   a. Leer solo las notas relevantes a ese rol (no todo el vault de una).
   b. Extraer 3-5 patrones de decisión reales, ya generalizados y sin
      datos sensibles, ANTES de escribirlos en el agente — mostrárselos a
      Jair en el chat para que confirme cada uno antes de pasar al
      siguiente rol.
   c. Recién con la confirmación, escribir `agents/<rol>.md` siguiendo el
      formato de `agents/mentor.md` (frontmatter: name, description,
      tools, model, color + cuerpo en segunda persona).
3. Actualizar `COMO-INSTALAR.md`, sección de instalación, para listar los
   nuevos agentes en el paso de copiar `agents/`.
4. Actualizar `README.md` de SAC si la lista de ejemplos cambia.
5. Confirmar con `git status` que no se coló ningún archivo fuera de
   `agents/`, `COMO-INSTALAR.md`, `README.md` antes de proponer el commit.

RESTRICCIONES
- No leer ni copiar notas del vault que mencionen: cifras de Ratio, roster
  de personas (tabla `people` de Supabase), datos de clientes de
  Decoraciones & Cortinas, ni nada marcado como financiero/legal.
- No commitear ni pushear sin confirmación explícita de Jair en esa
  sesión — el repo ya es público, cualquier error de filtrado queda
  expuesto de inmediato.

OBJETIVO VERIFICABLE
Al cierre: 5 archivos nuevos en `agents/` (ventas, marketing, contabilidad,
admin, profesor), cada uno con instrucciones reales y específicas (no
boilerplate genérico), confirmados uno por uno con Jair antes de
escribirse, sin ningún dato privado de Ratio/Decoraciones&Cortinas/vida
personal visible en el texto final.
