# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration 5

## Iteration Goal

Contenido, integridad y administración. Estado: propuesta documental completa; no implica implementación.

## Drivers to Address

VIC-5, VIC-6, QA-2, QA-5, QA-7, CRN-4. Definiciones en [ArchitecturalDrivers.md](../ArchitecturalDrivers.md).

## ADD Process Steps

### Step 1: Review inputs

Revisar drivers, supuestos y decisiones de las iteraciones anteriores; para iteración 1 la entrada es el sistema descrito por el encargo. Ver [paso 1 común](../ArchitecturalDrivers.md#paso-1-revisar-entradas-y-viabilidad).

### Step 2: Establish goal for the iteration by selecting drivers

Objetivo y drivers anteriores se toman del [IterationPlan.md](IterationPlan.md). Se priorizan por impacto patrimonial, experiencia offline y riesgo técnico.

### Step 3: Choose one or more elements of the system to refine

- M-PKG y C-AUTHOR
- Autorización local
- Almacén y exportación

### Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers

| Design concept | Pros | Cons | Discarded alternatives |
|---|---|---|---|
| Paquetes inmutables firmados y activación A/B | Versiones trazables y recuperación | Espacio y gestión de claves | Sobrescribir paquete activo: deja instalación parcial |
| RBAC local y validación de entrada | Administración offline controlada | Gestión local de credenciales | Login remoto obligatorio: rompe QA-3 |

### Step 5: Instantiate Architectural Elements, Sketch Views, Allocate Responsibilities, and Define Interfaces

| Instantiation decision | Rationale |
|---|---|
| PackagePort y AuthorizationPort | Verificación, instalación y permisos por caso de uso |
| Manifest y Journal | Compatibilidad, hashes y activación recuperable |

Vistas estáticas en secciones 4–6; colaboraciones y contratos en secciones 7.4 y 8.4 de [Architecture.md](Architecture.md). La sección 6 asigna responsabilidades por módulo y la 8 define datos, errores y condiciones temporales.

### Step 6: Record Design Decisions

Registro canónico: [sección 9](Architecture.md#9-design-decisions), decisiones DA-10, DA-11. Cada fila registra drivers, decisión, justificación y alternativas descartadas; no se duplican versiones divergentes del registro.

### Step 7: Perform Analysis of Current Design and Review Iteration Goal and Achievement of Design Purpose

| Driver | Analysis result |
|---|---|
| VIC-5 | Satisfecho a nivel de diseño. Ver decisiones DA-10, DA-11 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| VIC-6 | Satisfecho a nivel de diseño. Ver decisiones DA-10, DA-11 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |
| QA-2 | Parcialmente satisfecho. Ver decisiones DA-10, DA-11 y validación de la sección 11. QA-5 y QA-7 requieren cortes inducidos, paquetes corruptos y pruebas de abuso; evidencia histórica pendiente. |
| QA-5 | Parcialmente satisfecho. Ver decisiones DA-10, DA-11 y validación de la sección 11. QA-5 y QA-7 requieren cortes inducidos, paquetes corruptos y pruebas de abuso; evidencia histórica pendiente. |
| QA-7 | Parcialmente satisfecho. Ver decisiones DA-10, DA-11 y validación de la sección 11. QA-5 y QA-7 requieren cortes inducidos, paquetes corruptos y pruebas de abuso; evidencia histórica pendiente. |
| CRN-4 | Satisfecho a nivel de diseño. Ver decisiones DA-10, DA-11 y validación de la sección 11. Alcance y responsabilidades explícitos; revisión de interesados pendiente. |

El objetivo de descomposición está cubierto documentalmente. Los atributos medibles quedan parcialmente satisfechos hasta disponer de implementación, hardware y evidencia de aceptación; no se declara verificación experimental. Acciones pendientes: QA-5 y QA-7 requieren cortes inducidos, paquetes corruptos y pruebas de abuso; evidencia histórica pendiente.
