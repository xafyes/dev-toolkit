---
name: project-kickoff
description: Arranca una aplicación o feature nueva siguiendo el estándar personal del usuario (stack .NET / Next.js / Python / React, separación de responsabilidades, handlers de error). Úsala cuando el usuario diga que quiere crear/iniciar una app, servicio o feature nueva desde cero.
---

# project-kickoff

Objetivo: reemplazar un prompt largo por un flujo corto y repetible.

## Pasos

0. Si lo que se arranca es una librería/framework propio para publicar en GitHub (no una app interna), usar `oss-publish` en vez de este flujo desde el principio.
1. Invocar `memory-vault` para cargar contexto previo (si el repo ya tiene historial en el vault).
2. Preguntar solo lo que no se pueda inferir, en una sola tanda, con `AskUserQuestion` cuando aplique:
   - Stack (.NET / Next.js / Python / React / combinación).
   - Tipo de app (API, full-stack, frontend solo, worker, etc.).
   - Nombre del proyecto/feature.
3. Invocar `viability-review` si es una app nueva (no un feature chico) antes de escribir código. Su plan de desarrollo (fases, funcionalidades núcleo primero) es el input para los pasos siguientes.
4. Infra por defecto mientras no esté publicado (ver `infra-standards.md`): free tier de AWS/Azure, Supabase como BD de dev (o la alternativa gratuita vigente si Supabase se limita).
5. Scaffolding respetando siempre:
   - Separación de responsabilidades por capa (ver `coding-standards.md`).
   - Máximo 250 líneas por archivo.
   - Un patrón único de handler/middleware de errores desde el día 1, no agregado después.
   - Sin comentarios de decisión ni comentarios en modelos/entidades.
6. Si el desarrollo es lo bastante grande para delegar en subagentes, usar `dev-agents` para elegir modelo/esfuerzo por tarea en vez de correr todo con el modelo por defecto.
7. Guardar en el vault (`Projects/<nombre>.md`) el stack elegido y las decisiones de estructura tomadas.
8. Responder en el chat de forma corta: qué se creó y qué sigue, sin repetir el detalle que ya quedó en archivos/vault.

## Nunca

- No generar scaffolding sin antes confirmar el stack si hay ambigüedad real.
- No escribir un resumen largo en el chat cuando el detalle ya está en el código o el vault.
