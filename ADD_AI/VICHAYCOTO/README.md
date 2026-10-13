# Laboratorio Histórico Vichaycoto

Diseño arquitectónico ADD del **Gemelo Digital y Museo Interactivo en VR**. Estado: propuesta documental completa, pendiente de validación con curaduría, prototipo XR e instrumentación. No contiene implementación del producto ni afirma resultados de rendimiento.

## Documentos

| Archivo | Contenido |
|---|---|
| [ArchitecturalDrivers.md](ArchitecturalDrivers.md) | Paso 1, casos de uso, escenarios medibles, restricciones, prioridades y supuestos |
| [Design/IterationPlan.md](Design/IterationPlan.md) | Seis iteraciones, dependencias y roles |
| [Design/Architecture.md](Design/Architecture.md) | Vistas, módulos, interfaces, decisiones, eventos y aceptación |
| [Iteración 1](Design/Iteration1.md) | Estructura y despliegue offline |
| [Iteración 2](Design/Iteration2.md) | Simulación y fidelidad |
| [Iteración 3](Design/Iteration3.md) | VR y presupuesto temporal |
| [Iteración 4](Design/Iteration4.md) | Telemetría y emulación |
| [Iteración 5](Design/Iteration5.md) | Contenido, integridad y administración |
| [Iteración 6](Design/Iteration6.md) | Validación y entrega |

Se conserva la estructura del ejemplo HPS y las tablas de la guía ADD. Paso 1 se hace explícito; pasos 2–7 aparecen en cada iteración. El registro de decisiones ocupa la sección 9 de Architecture.md conforme a la guía, y los eventos la sección 10. Las revisiones intermedias de la guía se consolidan en la entrega completa solicitada.

## Visualización y compilación

GitHub muestra Markdown y bloques Mermaid directamente. Para generar HTML con diagramas SVG se requieren Mermaid CLI (`mmdc`), su navegador compatible y Pandoc. Ejecutar desde esta carpeta:

```bash
mkdir -p /tmp/vichaycoto-docs
mmdc -i Design/Architecture.md -o /tmp/vichaycoto-docs/Architecture.md -e svg
pandoc /tmp/vichaycoto-docs/Architecture.md --standalone --metadata title="Arquitectura Vichaycoto" -o /tmp/vichaycoto-docs/Architecture.html
pandoc ArchitecturalDrivers.md --standalone --metadata title="Drivers Vichaycoto" -o /tmp/vichaycoto-docs/ArchitecturalDrivers.html
```

Para consultar el HTML conservar los SVG junto a Architecture.html. Pandoc por sí solo representa Mermaid como código; primero ejecutar mmdc para obtener los diagramas. Los enlaces a otros Markdown están orientados a navegación en GitHub; este comando genera cada documento individual y no convierte todo el conjunto en un sitio HTML.

## Repositorio de destino

Esta documentación está preparada para incorporarse a [louis9RM/VICHAYCOTO](https://github.com/louis9RM/VICHAYCOTO), conservando la ruta `ADD_AI/VICHAYCOTO`.

## Verificación de esta entrega

El 2026-10-12 se compilaron los diez documentos Markdown a HTML con Pandoc 3.1.11 en `/tmp/vichaycoto-docs`, se comprobaron destinos de enlaces locales y presencia de Steps 1–7 en las seis iteraciones. Los nueve diagramas pasaron el parser de Mermaid. Para esa comprobación gramatical se sustituyó únicamente la sanitización DOM en un proceso de prueba aislado, pues no hay DOM de navegador; no se modificó Mermaid instalado ni los documentos.

La exportación visual SVG con mmdc no pudo completarse: Chromium no inicia por restricciones del entorno (`Operation not permitted`). Por tanto, la gramática está verificada, pero el renderizado visual queda pendiente en GitHub o en un entorno con navegador habilitado. El HTML generado directamente por Pandoc contiene Mermaid como código. Ninguna de estas verificaciones documentales sustituye las pruebas de aceptación del sistema descritas en Architecture.md.
