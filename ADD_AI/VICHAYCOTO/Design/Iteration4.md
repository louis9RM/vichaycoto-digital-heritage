# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 4

## Iteration Goal

Telemetría y emulación mecatrónica. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-4, QA-6, QA-7, CON-4, CON-6. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- C-MCU y C-EDGE
- M-TEL
- Mapeo entre entidad medida y modelo

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| Gateway local y puertos de muestras | Normalización fuera del bucle VR | Requiere equipo y mantenimiento local | Sensores accediendo al dominio: mezcla protocolo y física |
| Cola acotada y sustitución explícita por emulador | Resiliencia y pruebas sin hardware | Puede perder muestras; se registra pérdida | Cola ilimitada: crecimiento de memoria y latencia |
| Canal de solo lectura para VR | Aísla órdenes físicas | Limita experimentación remota | Control de actuadores desde visor: fuera del alcance |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| TelemetryPort, MqttAdapter y EmulatorAdapter | Contrato común con origen y calidad |
| Firmware de adquisición y gateway | Captura, calibración, autenticación y buffering |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.3 y 8.3 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-08, DA-09. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-4 | Satisfecho a nivel de diseño. Ver decisiones DA-08, DA-09 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-6 | Parcialmente satisfecho. Ver decisiones DA-08, DA-09 y validación de la sección 11. QA-6 pendiente de ensayo LAN y reloj; QA-7 requiere evaluación y pruebas de permisos y red. |
| QA-7 | Parcialmente satisfecho. Ver decisiones DA-08, DA-09 y validación de la sección 11. QA-6 pendiente de ensayo LAN y reloj; QA-7 requiere evaluación y pruebas de permisos y red. |
| CON-4 | Satisfecho a nivel de diseño. Ver decisiones DA-08, DA-09 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| CON-6 | Satisfecho a nivel de diseño. Ver decisiones DA-08, DA-09 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-6 pendiente de ensayo LAN y reloj; QA-7 requiere evaluación y pruebas de permisos y red.
