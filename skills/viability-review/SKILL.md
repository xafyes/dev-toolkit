---
name: viability-review
description: Toma una idea de app/negocio y la convierte en una evaluación objetiva (competencia, mejoras, funcionalidades, costos de infra en dev y a escala, monetización) seguida de un plan de desarrollo. Úsala cuando el usuario presente una idea nueva y quiera saber si vale la pena y qué hacer, antes de project-kickoff. Tono siempre neutral/realista, nunca optimista ni pesimista.
---

# viability-review

Dos fases: primero evaluar, después plan. No mezclar ambas en el mismo párrafo.

## Regla de tono (aplica a todo el output)

Nada de lenguaje optimista ("esto va a funcionar genial") ni pesimista ("esto no tiene futuro") sin respaldo. Cada afirmación debe apoyarse en un dato concreto: un competidor real, un costo estimado, un hueco de lógica de negocio. Si no hay dato suficiente para afirmar algo, decir que es incierto y por qué, no rellenar con opinión.

## Fase 1 — Evaluación

**Competencia**
- Quién ya resuelve este problema o algo parecido (productos reales, no genéricos).
- Qué tan saturado está el espacio.
- Diferenciación real disponible para esta idea específica (no cosmética).

**Mejoras a la idea**
- 2-4 ajustes concretos que la fortalecen, basados en huecos vistos en la competencia o en la lógica de negocio — no features inventadas sin motivo.

**Funcionalidades (para no dejar espacios vacíos en el desarrollo)**
- Lista de funcionalidades núcleo (sin esto no hay producto) vs. funcionalidades secundarias (mejoran pero no son bloqueantes) vs. futuras (post-lanzamiento).
- Objetivo: que al pasar a desarrollo no falte nada que se note después.

**Costos de infraestructura**
- Fase dev: estimar cuánto dura dentro del free tier de AWS/Azure y de la BD elegida (Supabase por defecto; si se topa con el límite, la alternativa gratuita a usar), y en qué momento se tocaría el límite según el uso esperado durante el desarrollo.
- Fase escalado (post-lanzamiento): estimar costo aproximado en AWS y en Azure por separado (el usuario trabaja con ambos), identificando los servicios concretos que generarían ese costo, no una cifra sin desglose.

**Monetización**
- Qué modelos de ingreso calzan con esta idea específica (suscripción, freemium, comisión, ads, etc.) y por qué ese y no otro.

**Veredicto**
- Viable / viable con ajustes / no viable, con las 2-3 razones de mayor peso. Corto.

## Fase 2 — Plan de desarrollo

Solo después de la evaluación, y solo si el veredicto no es "no viable" sin ajustes posibles.

- Fases de desarrollo (no todo de una vez): qué funcionalidad núcleo va primero y por qué.
- Stack sugerido (.NET/Next.js/Python/React) acorde a la idea.
- Infra: confirmar que dev se mantiene en free tier (AWS/Azure + Supabase) hasta publicar; infra de producción recién se decide al escalar.
- Entregar esto como input directo para `project-kickoff`, no repetir el detalle completo en el chat si ya quedó en el vault.

## Al terminar

Guardar la evaluación y el plan en el vault vía `memory-vault` (`Projects/<nombre>.md`). En el chat, solo el veredicto y el plan en forma resumida.
