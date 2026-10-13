# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 1

## Iteration Goal

Estructura y despliegue offline. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-1, QA-3, QA-4, CON-1, CON-2, CRN-1. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- Sistema completo (descomposición inicial)
- Aplicación local y catálogo
- Composición de adaptadores

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| Hexagonal y monolito modular local | Dominio aislado y ejecución offline | Disciplina de dependencias | Microservicios obligatorios: agregan red al recorrido |
| Paquete instalado y composición explícita | Arranque sin servicios externos | Espacio y actualización local | Streaming obligatorio: impide uso sin internet |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| M-DOM, M-APP, M-XR y M-PKG | Núcleo, orquestación, presentación y contenido desacoplados |
| C-QUEST y C-AUTHOR | Separar reproducción y autoría |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.1 y 8.1 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-01, DA-02, DA-03. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-1 | Satisfecho a nivel de diseño. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-3 | Parcialmente satisfecho. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. QA-3 depende de ensayo offline en visor; QA-4 requiere segundo adaptador. |
| QA-4 | Parcialmente satisfecho. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. QA-3 depende de ensayo offline en visor; QA-4 requiere segundo adaptador. |
| CON-1 | Satisfecho a nivel de diseño. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| CON-2 | Satisfecho a nivel de diseño. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| CRN-1 | Satisfecho a nivel de diseño. Ver decisiones DA-01, DA-02, DA-03 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-3 depende de ensayo offline en visor; QA-4 requiere segundo adaptador.
