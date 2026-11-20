---
name: ux-ui-review
description: Revisión de código frontend (React / Next.js) especializada en UX/UI — separación entre presentación y lógica, accesibilidad, estados de carga/error, consistencia visual. Úsala cuando se pida revisar UI/UX, o tras implementar/modificar componentes de frontend. No reemplaza a code-review (correctness) ni a qa-bughunt (bugs funcionales).
---

# ux-ui-review

Revisar el diff o los archivos indicados contra este checklist. Reportar solo lo que falla, no una lista de "todo lo que sí cumple".

## Checklist

**Separación de responsabilidades**
- Componente no mezcla fetching/lógica de negocio con presentación (usar hooks/handlers separados).
- Sin lógica de negocio duplicada entre componentes; extraer a hook/util compartido.
- Archivo de componente dentro del límite de 250 líneas; si lo excede, es señal de que hace demasiado.

**Estados**
- Loading, error y vacío manejados explícitamente (no solo el happy path).
- Errores mostrados al usuario de forma consistente con el estándar de códigos de error del backend (ver `coding-standards.md`), no mensajes genéricos inventados por componente.

**Accesibilidad**
- HTML semántico, roles/aria donde el elemento no sea nativo.
- Navegable por teclado, foco visible.
- Contraste de color suficiente, textos alternativos en imágenes.

**Consistencia visual**
- Usa tokens/clases/componentes compartidos existentes en vez de reimplementar estilos.
- Responsive revisado en al menos mobile y desktop.

## Salida

Lista corta de hallazgos (archivo:línea, qué falla, por qué importa). Sin preámbulo largo.
