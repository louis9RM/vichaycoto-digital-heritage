# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 2

## Iteration Goal

Simulación y fidelidad histórica. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-2, VIC-3, QA-2, QA-8, CRN-2. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- M-DOM y M-SIM
- Modelos y catálogo de evidencias
- Escenarios de experimentación

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| Máquinas de estados y solver de paso fijo | Reglas operativas y evolución reproducible | Modelos y rangos deben calibrarse | Animación sin modelo: no permite contrastar magnitudes |
| Perfiles museo e investigación | Controlar costo móvil y precisión por finalidad | Duplicidad de validación por perfil | Una fidelidad universal: no acota costo ni error |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| M-SIM y SimulationPort | Solvers reemplazables y snapshots inmutables |
| MachineModel, Experiment y Evidence | Separar hipótesis, observación y procedencia |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.2 y 8.2 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-04, DA-05. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-2 | Satisfecho a nivel de diseño. Ver decisiones DA-04, DA-05 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| VIC-3 | Satisfecho a nivel de diseño. Ver decisiones DA-04, DA-05 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-2 | Parcialmente satisfecho. Ver decisiones DA-04, DA-05 y validación de la sección 11. QA-2 parcialmente satisfecho: faltan modelos y referencias; QA-8 requiere suite headless. |
| QA-8 | Parcialmente satisfecho. Ver decisiones DA-04, DA-05 y validación de la sección 11. QA-2 parcialmente satisfecho: faltan modelos y referencias; QA-8 requiere suite headless. |
| CRN-2 | Satisfecho a nivel de diseño. Ver decisiones DA-04, DA-05 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-2 parcialmente satisfecho: faltan modelos y referencias; QA-8 requiere suite headless.
