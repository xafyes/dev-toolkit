---
name: dev-agents
description: Orquesta subagentes durante un desarrollo largo, eligiendo modelo/esfuerzo según la dificultad real de cada tarea para ahorrar tokens. Úsala cuando el usuario quiera dejar agentes corriendo mientras se construye una feature/app, en vez de hacer todo con el modelo por defecto.
---

# dev-agents

No todas las tareas de un desarrollo necesitan el modelo más caro. Clasificar antes de delegar.

## Clasificación de dificultad

- **Baja** (boilerplate, CRUD simple, renombrar, mover archivos, tests triviales, formatear): modelo más barato/rápido disponible, effort bajo.
- **Media** (feature estándar, lógica de negocio típica, integración ya conocida en el proyecto): modelo por defecto de la sesión, effort medio.
- **Alta** (decisiones de arquitectura, seguridad, algoritmos no triviales, refactor que toca varias capas, nada de lo que se tenga certeza): el mejor modelo disponible, effort alto.

Si hay duda entre dos niveles, subir uno, no bajar — una tarea de seguridad mal resuelta cuesta más que el ahorro de tokens.

## Cómo delegar

Al usar el tool `Agent`:
- Fijar `model` y `effort` según la clasificación de arriba, no dejar el default sin pensarlo.
- Tareas independientes y de bajo riesgo → `run_in_background: true`, para no bloquear mientras se sigue trabajando.
- Tareas que comparten contexto pesado con el trabajo ya hecho en la sesión → `subagent_type: "fork"` en vez de un agente nuevo, para no repetir contexto (y por lo tanto tokens).
- Nunca asumir que "más modelo" es siempre mejor: una tarea de baja dificultad resuelta por el modelo grande no mejora el resultado, solo gasta más.

## Reporte

Al terminar una tanda de agentes, resumen corto: qué se hizo, con qué modelo/effort cada tarea relevante, y qué quedó pendiente. No repetir el output completo de cada agente en el chat.
