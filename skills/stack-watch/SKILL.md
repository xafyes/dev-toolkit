---
name: stack-watch
description: Vigilancia de vulnerabilidades reportadas y actualizaciones relevantes para el stack personal (.NET, Next.js/Node, Python, React/npm). Solo fuentes oficiales/confiables, nunca sitios no confiables. Úsala cuando se pida revisar vulnerabilidades, novedades del stack, o antes de un kickoff para confirmar que las prácticas/versiones siguen vigentes.
---

# stack-watch

## Fuentes permitidas

Solo oficiales o de referencia reconocida: GitHub Security Advisories, NVD, release notes/changelog oficiales de .NET, Next.js, React, Python/PyPI, y los security advisories de npm/NuGet/PyPI. Nada de blogs no verificados, foros o sitios sin reputación establecida.

Preferir herramientas locales sobre navegar la web:
- .NET: `dotnet list package --vulnerable`
- Node/Next.js/React: `npm audit`
- Python: `pip-audit` (o `safety` si está instalado)

Si no hay proyecto para escanear localmente, usar `WebSearch`/`web-fetch` únicamente contra los dominios de arriba.

## Qué reportar

- Vulnerabilidad: paquete, severidad, versión afectada/corregida, acción concreta (actualizar a X).
- Actualización tecnológica relevante: solo si cambia una práctica recomendada o deprecated algo en uso (no changelog completo).

## Salida

Lista corta, priorizada por severidad/impacto. Si no hay nada relevante, decirlo en una línea, no generar un reporte vacío largo.
