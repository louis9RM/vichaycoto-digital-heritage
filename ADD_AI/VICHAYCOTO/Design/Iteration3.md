# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 3

## Iteration Goal

Presentación VR y presupuesto temporal. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-1, VIC-2, QA-1, QA-10, CRN-3, CON-5. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- M-XR
- Planificador M-APP
- Adaptador gráfico y de entrada

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| OpenXR y adaptadores de motor | Reducir dependencia del dispositivo | Extensiones y capacidades varían | SDK propietario en dominio: acopla reglas al visor |
| Snapshots, interpolación y carga acotada | Separar física y renderizado | Interpolación añade antigüedad visible | Simulación o I/O bloqueantes por frame: rompe presupuesto |
| LOD, culling y iluminación precalculada | Reducir carga gráfica | Trabajo de optimización artística | Geometría de autoría completa en visor: costo sin cota |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| XRInputAdapter y SnapshotPresenter | Entrada semántica y proyección visual |
| Governor y SafePause | Degradación visual y pausa por tracking |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.2 y 8.1 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-06, DA-07. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-1 | Satisfecho a nivel de diseño. Ver decisiones DA-06, DA-07 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| VIC-2 | Satisfecho a nivel de diseño. Ver decisiones DA-06, DA-07 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-1 | Parcialmente satisfecho. Ver decisiones DA-06, DA-07 y validación de la sección 11. QA-1 y QA-10 parcialmente satisfechos hasta perfilado térmico, latencia instrumental y estudio de usuarios. |
| QA-10 | Parcialmente satisfecho. Ver decisiones DA-06, DA-07 y validación de la sección 11. QA-1 y QA-10 parcialmente satisfechos hasta perfilado térmico, latencia instrumental y estudio de usuarios. |
| CRN-3 | Satisfecho a nivel de diseño. Ver decisiones DA-06, DA-07 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| CON-5 | Satisfecho a nivel de diseño. Ver decisiones DA-06, DA-07 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-1 y QA-10 parcialmente satisfechos hasta perfilado térmico, latencia instrumental y estudio de usuarios.
