# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 6

## Iteration Goal

Validación, observabilidad y entrega. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-3, VIC-6, QA-4, QA-8, QA-9, CRN-5. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- M-OBS
- Contratos y herramientas de integración
- Build y perfiles de aceptación

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| Tests headless, contratos y hardware en el circuito | Verificar reglas y límites reales | Necesita banco y visor para aceptación | Solo pruebas VR manuales: no aíslan regresiones |
| Métricas agregadas y registro circular | Diagnóstico offline con memoria acotada | Muestreo puede reducir detalle | Trazas ilimitadas por frame: perturbación de rendimiento |
| Artefactos identificados y promoción por etapas | Trazabilidad y reversión | Congelar toolchain y mantener evidencias | Compilar distinto para cada entorno: dificulta reproducibilidad |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| DiagnosticsPort y métricas por ventana | Medir latencia y descartes sin bloquear render |
| Suites de contrato y pipeline propuesto | Validar documentación, dominio, paquetes y dispositivos |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.5 y 8.5 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-12, DA-13. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-3 | Satisfecho a nivel de diseño. Ver decisiones DA-12, DA-13 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| VIC-6 | Satisfecho a nivel de diseño. Ver decisiones DA-12, DA-13 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-4 | Parcialmente satisfecho. Ver decisiones DA-12, DA-13 y validación de la sección 11. QA-4, QA-8 y QA-9 requieren implementación y evidencias de pipeline; no hay ejecución del producto en esta entrega. |
| QA-8 | Parcialmente satisfecho. Ver decisiones DA-12, DA-13 y validación de la sección 11. QA-4, QA-8 y QA-9 requieren implementación y evidencias de pipeline; no hay ejecución del producto en esta entrega. |
| QA-9 | Parcialmente satisfecho. Ver decisiones DA-12, DA-13 y validación de la sección 11. QA-4, QA-8 y QA-9 requieren implementación y evidencias de pipeline; no hay ejecución del producto en esta entrega. |
| CRN-5 | Satisfecho a nivel de diseño. Ver decisiones DA-12, DA-13 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-4, QA-8 y QA-9 requieren implementación y evidencias de pipeline; no hay ejecución del producto en esta entrega.
