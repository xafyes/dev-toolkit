---
name: oss-publish
description: Prepara y mantiene una librería/framework propio pensado para publicarse en GitHub y ser usado por terceros (no una app interna). Úsala al crear un paquete/librería nuevo, o antes de cada release. No es para contribuir a repos de otros — ahí manda el estilo del repo ajeno, no esto.
---

# oss-publish

Diferencia clave vs. una app interna: gente que no conoces va a depender de la API pública y de los edge cases que no probaste. El estándar de código personal (`coding-standards.md`) sigue aplicando — esto lo complementa.

## Setup inicial (antes del primer commit público)

- `LICENSE` — MIT por defecto salvo que se indique otra.
- `README.md`: ejemplo de uso mínimo arriba de todo, antes de cualquier explicación larga. Si alguien no puede copiar/pegar algo funcional en los primeros 30 segundos, está mal escrito.
- `CHANGELOG.md` desde el primer release (aunque sea `0.1.0`).
- CI en GitHub Actions desde el primer commit, no agregado después: build + test (+ lint) en cada push/PR. Usar el template del stack correspondiente en `templates/ci/` de este repo.
- Versionado semver estricto desde `0.1.0`. Breaking change = major, nunca "lo arreglo en el patch".

## Diseño de la API pública

- Superficie pública mínima: lo que no se expone no se puede romper. Exportar solo lo necesario.
- Nombres y shape de la API estables desde temprano; cambiarlos después cuesta un major.
- Nada de comentarios de decisión en el código (igual que siempre) — las decisiones de diseño de API van al vault (`memory-vault`, nota del proyecto), el README explica el *qué*, no el *por qué* interno.

## Antes de cada release

1. `qa-bughunt` sobre la superficie pública — foco en edge cases que un consumidor externo va a pegar sin avisar (inputs raros, versiones de Node/.NET/Python distintas a la tuya).
2. `code-review` sobre el diff del release.
3. `security-review` si la librería maneja input externo, auth, parsing o dependencias con historial de CVEs.
4. `stack-watch` para confirmar que las dependencias no tienen vulnerabilidad conocida antes de publicar.
5. Actualizar `CHANGELOG.md` y el tag de versión.

## Vault

Guardar en `Projects/<nombre-libreria>.md`: decisiones de diseño de API, por qué se eligió cierta superficie pública, breaking changes históricos y su razón.
