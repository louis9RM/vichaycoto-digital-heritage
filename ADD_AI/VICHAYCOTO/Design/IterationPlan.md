# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Iteration Plan

## Iteration Plan Overview

| Iteration | Goal | Drivers to Address |
|---|---|---|
| 1 | Estructura y despliegue offline | VIC-1, QA-3, QA-4, CON-1, CON-2, CRN-1 |
| 2 | Simulación y fidelidad histórica | VIC-2, VIC-3, QA-2, QA-8, CRN-2 |
| 3 | Presentación VR y presupuesto temporal | VIC-1, VIC-2, QA-1, QA-10, CRN-3, CON-5 |
| 4 | Telemetría y emulación mecatrónica | VIC-4, QA-6, QA-7, CON-4, CON-6 |
| 5 | Contenido, integridad y administración | VIC-5, VIC-6, QA-2, QA-5, QA-7, CRN-4 |
| 6 | Validación, observabilidad y entrega | VIC-3, VIC-6, QA-4, QA-8, QA-9, CRN-5 |

## Detailed Iteration Goals

### Iteration 1: Estructura y despliegue offline

Refinar Sistema completo (descomposición inicial), Aplicación local y catálogo, Composición de adaptadores. Salida: decisiones DA-01, DA-02, DA-03, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-3 depende de ensayo offline en visor; QA-4 requiere segundo adaptador.

### Iteration 2: Simulación y fidelidad histórica

Refinar M-DOM y M-SIM, Modelos y catálogo de evidencias, Escenarios de experimentación. Salida: decisiones DA-04, DA-05, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-2 parcialmente satisfecho: faltan modelos y referencias; QA-8 requiere suite headless.

### Iteration 3: Presentación VR y presupuesto temporal

Refinar M-XR, Planificador M-APP, Adaptador gráfico y de entrada. Salida: decisiones DA-06, DA-07, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-1 y QA-10 parcialmente satisfechos hasta perfilado térmico, latencia instrumental y estudio de usuarios.

### Iteration 4: Telemetría y emulación mecatrónica

Refinar C-MCU y C-EDGE, M-TEL, Mapeo entre entidad medida y modelo. Salida: decisiones DA-08, DA-09, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-6 pendiente de ensayo LAN y reloj; QA-7 requiere evaluación y pruebas de permisos y red.

### Iteration 5: Contenido, integridad y administración

Refinar M-PKG y C-AUTHOR, Autorización local, Almacén y exportación. Salida: decisiones DA-10, DA-11, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-5 y QA-7 requieren cortes inducidos, paquetes corruptos y pruebas de abuso; evidencia histórica pendiente.

### Iteration 6: Validación, observabilidad y entrega

Refinar M-OBS, Contratos y herramientas de integración, Build y perfiles de aceptación. Salida: decisiones DA-12, DA-13, módulos y contratos descritos en la arquitectura. Cierre: revisar drivers y evidencias; QA-4, QA-8 y QA-9 requieren implementación y evidencias de pipeline; no hay ejecución del producto en esta entrega.

## Implementation Timeline

Secuencia propuesta por dependencias, sin fechas comprometidas: iteración 1 establece base; 2 y 3 producen una visita offline con un mecanismo; 4 integra banco o emulador; 5 entrega contenido verificable y administración; 6 consolida aceptación. El MVP requiere VIC-1, VIC-2, QA-1, QA-2 para el mecanismo elegido, QA-3 y QA-10. La emulación puede adelantar pruebas de 4 sin esperar compra de sensores.

No se hereda el plazo de seis meses de HPS. Duraciones y presupuesto quedan pendientes de inventario, equipo y prototipo.

## Alignment with Development Team

Roles propuestos: arquitectura (contratos y dependencias), XR (presentación y rendimiento), simulación (solver y validación), mecatrónica (adquisición y calibración), curaduría/3D (evidencias y contenido), QA/operación (pruebas, paquetes y despliegue). Son responsabilidades, no personas ya asignadas. El [registro de aceptación](Architecture.md#11-validacion-riesgos-y-trazabilidad) define evidencia para el cierre técnico.
