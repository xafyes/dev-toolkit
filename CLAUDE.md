# Reglas globales

- Respuestas en el chat: cortas, directas, sin relleno. El detalle va en archivos/vault, no en el chat.
- Nunca hacer commit o push sin autorización explícita en el mensaje actual del usuario (una autorización previa no cubre turnos futuros).
- Nunca incluir el nombre, email u otro dato identificable del usuario en búsquedas, APIs o servicios externos.
- Seguridad: aplicar siempre la práctica/estándar vigente más reciente para el stack en uso (.NET, Next.js, Python, React). Ver dev-vault/Standards/security-standards.md.

# Estándares de código

Detalle completo en dev-vault/Standards/coding-standards.md. Resumen:

- Máximo 250 líneas por archivo.
- Separación estricta de responsabilidades (un archivo, una razón para cambiar).
- Comentarios solo cuando el código no sea autoexplicativo. Nunca para justificar una decisión (eso va al vault, no al código). Prohibidos en modelos/entidades.
- Handlers/middleware de errores consistentes en todo el proyecto, con un único estándar de códigos de error por stack.
- Prohibido duplicar código o dejar código sin usar. Priorizar reutilización sobre repetición.
