---
name: qa-bughunt
description: Caza de bugs funcionales/de comportamiento (no solo lectura estática de código) — corre la app/tests, prueba edge cases, valida manejo de errores. Úsala cuando el usuario pida "busca bugs", "revisa calidad" o después de terminar una feature, antes de darla por lista. Complementa a code-review (que es estático) y a ux-ui-review.
---

# qa-bughunt

Diferencia con `code-review`: esto es dinámico. Si se puede, correr la app o la suite de tests (usar la skill `run` si existe) en vez de solo leer el diff.

## Qué revisar

- Edge cases: valores límite, vacíos, null/undefined, listas vacías, concurrencia/condiciones de carrera en operaciones que lo permitan.
- Validación de inputs en los bordes del sistema (API, formularios) — no confiar en que el cliente ya validó.
- Consistencia del manejo de errores: todo error pasa por el handler/middleware estándar del proyecto y usa los códigos de error definidos, no excepciones silenciadas ni catches vacíos.
- Código muerto o duplicado que haya quedado de la implementación (reportar para limpieza, no solo bugs).
- Si hay tests: que cubran los edge cases de arriba, no solo el happy path. Si no hay tests para una lógica de negocio no trivial, señalarlo.

## Salida

Lista corta: bug encontrado, cómo se reproduce o por qué ocurre, severidad. Sin narrar el proceso de exploración.
