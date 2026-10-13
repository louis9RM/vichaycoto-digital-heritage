# ADD_AI

## Adaptación local para AURA

En esta copia se añadió una sección de documentación propia del proyecto: [AURA](AURA/README.md). Incluye el [segundo agente, seguimiento pedagógico docente](AURA/SeguimientoDocente.md), vinculado a la iteración 9 y DA-20 de la arquitectura vigente. Esta ampliación local no forma parte de los casos publicados de Better Together. La guía ADD y los ejemplos HPS/WMS conservan su contenido original.

This repository contains files associated with the paper *"Better Together: An LLM-assisted approach to designing software architectures using Attribute-Driven Design"* by Humberto Cervantes (Universidad Autónoma Metropolitana Iztapalapa, CDMX, Mexico), Rick Kazman (University of Hawaii, HI, USA), and Yuanfang Cai (Drexel University, PA, USA).

```text
ADD_AI
├── ADD                          # ADD process definition and supporting material
│   └── ADD.md                   # Attribute-Driven Design process description
├── HPS                          # Hotel Pricing System artifacts
│   ├── ArchitecturalDrivers.md  # Architectural drivers for HPS
│   └── Design                   # Design outputs for HPS
│       ├── Architecture.md      # Architecture document
│       ├── IterationPlan.md     # Iteration plan
│       ├── Iteration1.md        # ADD iteration 1 summary
│       ├── Iteration2.md        # ADD iteration 2 summary
│       ├── Iteration3.md        # ADD iteration 3 summary
│       ├── Iteration4.md        # ADD iteration 4 summary
│       ├── Iteration5.md        # ADD iteration 5 summary
│       └── Iteration6.md        # ADD iteration 6 summary
└── WMS                          # Warehouse Management System artifacts
    ├── ArchitecturalDrivers.md  # Architectural drivers for WMS
    ├── Claude Opus 4.5 No ADD   # Design generated without explicit ADD process
    │   └── Architecture.md      # Architecture document
    ├── Claude Opus 4.5          # Design generated  with Claude Opus 4.5
    │   ├── Architecture.md      # Architecture document
    │   ├── IterationPlan.md     # Iteration plan
    │   ├── Iteration1.md        # ADD iteration 1 summary
    │   ├── Iteration2.md        # ADD iteration 2 summary
    │   ├── Iteration3.md        # ADD iteration 3 summary
    │   ├── Iteration4.md        # ADD iteration 4 summary
    │   ├── Iteration5.md        # ADD iteration 5 summary
    │   └── Iteration6.md        # ADD iteration 6 summary
    ├── GPT 5.2                  # WMS outputs generated with GPT 5.2
    │   ├── Architecture.md      # Architecture document
    │   ├── IterationPlan.md     # Iteration plan
    │   ├── Iteration1.md        # ADD iteration 1 summary
    │   ├── Iteration2.md        # ADD iteration 2 summary
    │   ├── Iteration3.md        # ADD iteration 3 summary
    │   ├── Iteration4.md        # ADD iteration 4 summary
    │   ├── Iteration5.md        # ADD iteration 5 summary
    │   ├── Iteration6.md        # ADD iteration 6 summary
    │   ├── Iteration7.md        # ADD iteration 7 summary
    │   └── Iteration8.md        # ADD iteration 8 summary
    ├── Gemini 3 Pro             # WMS outputs generated with Gemini 3 Pro
    │   ├── Architecture.md      # Architecture document
    │   ├── IterationPlan.md     # Iteration plan
    │   ├── Iteration1.md        # ADD iteration 1 summary
    │   ├── Iteration2.md        # ADD iteration 2 summary
    │   ├── Iteration3.md        # ADD iteration 3 summary
    │   ├── Iteration4.md        # ADD iteration 4 summary
    │   ├── Iteration5.md        # ADD iteration 5 summary
    │   └── Iteration6.md        # ADD iteration 6 summary
    └── Kiro                     # WMS outputs generated with Kiro
        └── Architecture.md      # Architecture document
```

## Diseño ADD para Vichaycoto

La documentación del **Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR** está en [VICHAYCOTO/README.md](VICHAYCOTO/README.md). Incluye drivers, arquitectura y seis iteraciones con los pasos ADD, interfaces y criterios de aceptación. Es una propuesta de diseño; la validación del producto está pendiente.
