---
name: memory-vault
description: Sincroniza el vault de memoria persistente (repo dev-vault, formato Obsidian) entre sesiones y repositorios. Úsala al iniciar trabajo en un proyecto nuevo (para leer contexto previo) y al cerrar un bloque de trabajo relevante (para guardar decisiones). No es para notas efímeras de una sola sesión.
---

# memory-vault

El vault (`dev-vault`) es markdown plano + carpeta `.obsidian/`, independiente de cualquier repo de proyecto. Es la única fuente de memoria entre sesiones.

## Al empezar a trabajar en un repo

1. Adjuntar `dev-vault` con `add_repo` (access: push) si aún no está.
2. Leer `Standards/coding-standards.md`, `Standards/security-standards.md`, `Standards/viability-checklist.md`.
3. Leer `Projects/<nombre-del-repo>.md` si existe. Si no existe, no crear nada todavía (se crea al primer guardado real).
4. No repetir ese contenido en el chat salvo que sea directamente relevante a la pregunta.

## Al guardar algo

Guardar cuando: se tomó una decisión de arquitectura, se descubrió una convención específica del proyecto, se encontró un bug recurrente o su causa, o el usuario lo pide explícitamente ("guarda esto", "anota esto").

No guardar: detalles triviales, código completo, nada que cambie seguido.

Formato en `Projects/<nombre-del-repo>.md`:

```markdown
## 2026-11-20
- Decisión: ...
- Razón: ...
```

Commitear y pushear el vault sin pedir confirmación en cada escritura (es memoria privada del usuario, no un repo compartido/productivo). Avisar en una línea qué se guardó. Si algo parece sensible (credenciales, datos personales de terceros), no lo guardes y dilo.

## Nunca

- No mezclar el vault con el repo del proyecto (nunca commitear archivos del vault dentro de un repo de proyecto).
- No guardar secretos, tokens ni credenciales.
