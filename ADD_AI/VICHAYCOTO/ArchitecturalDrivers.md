# Laboratorio Histórico Vichaycoto: Gemelo Digital y Museo Interactivo en VR — Architectural Drivers

## Business Case

Rescatar y difundir el patrimonio industrial de la hacienda/fábrica Vichaycoto mediante reconstrucciones documentadas de instalaciones mecánicas y eléctricas. Turistas exploran y operan representaciones en VR; investigadores examinan hipótesis y ensayos reproducibles; técnicos aportan mediciones o emulación de banco. La conservación del patrimonio guía la experiencia y la trazabilidad del contenido.

No se dispone de inventario de máquinas, planos, mediciones, presupuesto, equipo ni calendario aprobados. Las magnitudes numéricas de esta propuesta son metas de diseño, no resultados experimentales. El gemelo inicialmente es una reconstrucción simulada; solo una instancia vinculada a una entidad instrumentada y calibrada constituye aquí un gemelo conectado. No se afirma que la maquinaria patrimonial esté operativa.

## System Requirements

### Primary functionality

| User story | Nombre | Description | Prioridad |
|---|---|---|---|
| VIC-1 | Explorar el museo offline | Turista inicia una sesión sin internet, recorre instalaciones y consulta fichas y narraciones del paquete instalado. | Alta |
| VIC-2 | Operar maquinaria virtual | Turista activa controles permitidos; el modelo reproduce mecanismos y secuencias eléctricas históricas, permite pausa y reinicio. | Alta |
| VIC-3 | Investigar y reproducir experimentos | Investigador selecciona parámetros autorizados, semilla y modelo; compara resultados y exporta series con procedencia y límites de validez. | Alta |
| VIC-4 | Adquirir o emular telemetría | Técnico conecta sensores de banco o emulador, calibra y observa variables con unidad, origen, antigüedad y calidad. | Alta |
| VIC-5 | Curar y distribuir patrimonio | Curador incorpora fuentes, modelos 3D, licencias y versiones; administrador valida e instala un paquete recuperable. | Alta |
| VIC-6 | Administrar laboratorio y diagnóstico | Administrador gestiona roles locales, configura dispositivos, inspecciona métricas y exporta diagnóstico sin datos personales de visitantes. | Media |

### Quality attribute scenarios

Cada escenario incluye fuente, estímulo, entorno, artefacto, respuesta y medida. Los percentiles se calculan sobre todas las muestras del intervalo indicado; se conservan conteos, máximos y condiciones de prueba.

| ID | Quality Attribute | Fuente | Estímulo | Entorno | Artefacto | Respuesta | Medida propuesta | Associated User story | Importancia | Dificultad |
|---|---|---|---|---|---|---|---|---|---|---|
| QA-1 | Rendimiento VR | Turista | Movimiento de cabeza e interacción | Quest objetivo, escena de referencia, 30 min tras calentamiento | Bucle de presentación | Renderizar sin bloquear por red, disco o sensores | Perfil inicial propuesto: 72 Hz; tiempo CPU y GPU p95 <= 13,89 ms por separado, frames perdidos <= 1%; movimiento a fotón p95 <= 25 ms medido con método instrumental independiente | VIC-1, VIC-2 | Alta | Alta |
| QA-2 | Fidelidad física e histórica | Investigador | Ejecutar ensayo de referencia | Modelo y parámetros dentro del rango validado | Simulación y catálogo | Comparar magnitudes y preservar evidencia | Error normalizado <= 5% en velocidad y relación de transmisión de cada mecanismo validado; 100% de afirmaciones históricas enlazadas a fuente o etiquetadas como hipótesis | VIC-2, VIC-3, VIC-5 | Alta | Alta |
| QA-3 | Disponibilidad offline | Operador | Pérdida de internet y del gateway | Paquete válido instalado; sesión de 60 min | Aplicación local | Continuar recorrido y simulación; indicar sensor no disponible | 100% de VIC-1 y VIC-2 disponibles durante prueba; arranque local <= 15 s; no exigir autenticación remota | VIC-1, VIC-2 | Alta | Media |
| QA-4 | Portabilidad y modificabilidad | Desarrollador | Añadir adaptador de visor o sensor | Nueva plataforma compatible con contratos | Núcleo y adaptadores | Integrar mediante puertos | Cero dependencias del motor, SDK XR o protocolo en dominio; cero cambios de reglas de dominio para un segundo adaptador; ejecutar suite contractual en escritorio y Quest | VIC-2, VIC-4 | Alta | Media |
| QA-5 | Integridad y recuperación | Administrador | Interrupción al instalar paquete | Almacenamiento con dos versiones y área temporal | Repositorio de contenidos | Verificar y activar atómicamente o conservar versión anterior | En 20 cortes inducidos: cero activaciones parciales, arranque con paquete válido previo; rechazar 100% de paquetes alterados de la batería | VIC-5 | Alta | Media |
| QA-6 | Temporalidad de telemetría | Sensor o emulador | Enviar muestras y desconectarse | LAN local; hasta 8 canales a 50 muestras/s cada uno | Gateway y adaptador | Validar, ordenar por dispositivo y marcar obsolescencia | Latencia recepción gateway a visualización p95 <= 100 ms; estado obsoleto <= 500 ms sin muestras; colas acotadas; pérdidas contadas | VIC-4 | Alta | Alta |
| QA-7 | Seguridad y aislamiento físico | Actor sin autorización | Modificar contenido o enviar orden física | Modo exposición; LAN compartida | Administración y banco | Verificar permisos y separar simulación de hardware | 100% de operaciones privilegiadas de la batería denegadas sin rol; cero rutas de órdenes a actuadores desde VR | VIC-4, VIC-5, VIC-6 | Alta | Alta |
| QA-8 | Testabilidad y reproducibilidad | Investigador | Repetir escenario y fallo | Misma versión de solver, plataforma, semilla, paso y entradas | Núcleo y entorno de prueba | Reproducir resultados sin visor ni sensores | 100% de reglas y contratos críticos ejercitables headless; diferencia normalizada <= 0,1% entre repeticiones del mismo perfil; tolerancias multiplataforma específicas por modelo | VIC-3, VIC-4 | Media | Media |
| QA-9 | Observabilidad y despliegue | Operador | Exportar diagnóstico y promover versión | Offline y equipos de integración | Paquetes y métricas | Registrar rendimiento y desplegar artefacto identificado | Diagnóstico con versión, percentiles, muestras descartadas y fallos; registro circular <= 50 MB; mismo artefacto promovido sin editar código | VIC-5, VIC-6 | Media | Media |
| QA-10 | Usabilidad y confort | Visitante principiante | Primera experiencia y pérdida de tracking | Exposición supervisada | Interfaz VR | Tutorial, teletransporte, giro por pasos y pausa segura | Al menos 8 de 10 participantes completan tarea guiada en <= 5 min; pérdida de tracking pausa operaciones antes del siguiente tick de simulación | VIC-1, VIC-2 | Alta | Media |

El error normalizado de QA-2 es RMSE dividido por el rango de referencia no nulo; para señales constantes se usa una escala física acordada y registrada. La validación es por mecanismo y rango de operación. El umbral no certifica fidelidad de toda la fábrica ni sustituye revisión historiográfica. Movimiento a fotón no equivale a tiempo de frame; requiere medición independiente.

### Constraints

| ID | Constraint | Estado |
|---|---|---|
| CON-1 | Experiencia inmersiva en Meta Quest con funcionamiento offline. | Confirmada por el encargo |
| CON-2 | Integrar modelado 3D, simulación, telemetría y emulación mediante arquitectura hexagonal/modular. | Confirmada por el encargo |
| CON-3 | Documentación Markdown en la estructura ADD_AI y destino lógico louis9RM/VICHAYCOTO. | Confirmada por el encargo |
| CON-4 | VR solo observa bancos físicos; no controla maquinaria patrimonial ni actuadores. | Decisión de alcance propuesta |
| CON-5 | Perfil de aceptación: Quest 3 standalone, 72 Hz, un usuario por visor y una escena con un mecanismo activo; otros modelos Quest requieren perfil propio. | Supuesto por validar |
| CON-6 | Sensores de banco de baja tensión, adquisición inicial hasta 8 canales a 50 Hz; no instrumentar instalaciones históricas sin evaluación técnica. | Supuesto por validar |

### Architectural concerns

| ID | Concern |
|---|---|
| CRN-1 | Establecer límites, dependencias y responsabilidades del sistema. |
| CRN-2 | Distinguir reconstrucción histórica, simulación validada, emulación y medición real. |
| CRN-3 | Controlar carga gráfica, térmica y concurrencia en hardware móvil. |
| CRN-4 | Versionar evidencias, contratos y contenidos sin deuda de integración. |
| CRN-5 | Definir validación y entrega reproducible con responsables por rol. |

## Priorities

Primarios: VIC-1, VIC-2, VIC-3, VIC-4 y VIC-5; QA-1, QA-2, QA-3, QA-6 y QA-7. QA-4, QA-5 y QA-10 se consideran desde la primera entrega para evitar rediseño. QA-8 y QA-9 acompañan todas las iteraciones.

| Scenario ID | Importance to the customer | Difficulty of implementation according to the architect |
|---|---|---|
| QA-1 | Alta | Alta |
| QA-2 | Alta | Alta |
| QA-3 | Alta | Media |
| QA-4 | Alta | Media |
| QA-5 | Alta | Media |
| QA-6 | Alta | Alta |
| QA-7 | Alta | Alta |
| QA-8 | Media | Media |
| QA-9 | Media | Media |
| QA-10 | Alta | Media |

## Paso 1: revisar entradas y viabilidad

Entradas revisadas: [README del marco](../README.md), [guía ADD](../ADD/ADD.md), [drivers HPS](../HPS/ArchitecturalDrivers.md), [plan HPS](../HPS/Design/IterationPlan.md) y [arquitectura HPS](../HPS/Design/Architecture.md). HPS es un ejemplo de hoteles, no requisitos aplicables a Vichaycoto. Se conserva su organización documental y se sustituyen sus drivers por los de este proyecto.

La guía comienza en Step 2; este documento explicita Step 1. En ADD, Step 2 selecciona objetivo y drivers, Step 3 selecciona elementos, Step 4 conceptos y Step 5 instancia módulos e interfaces. Esta numeración se mantiene para seguir la plantilla aunque el encargo agrupe selección de elementos y conceptos como pasos 2 y 3.

La guía ubica decisiones en sección 9; HPS usa sección 9 para eventos y 10 para decisiones. La arquitectura de Vichaycoto mantiene la sección 9 requerida por la guía y una sección 10 de eventos, con referencias explícitas en las seis iteraciones. Las revisiones intermedias se consolidan en esta entrega completa autorizada por el encargo.

## Supuestos y cuestiones pendientes

| Punto | Resolución requerida | Responsable por rol | Antes de |
|---|---|---|---|
| Inventario, derechos y fuentes históricas | Seleccionar primer mecanismo con planos o mediciones y permisos de uso | Curaduría y patrimonio | Validación QA-2 |
| Hardware y perfil VR | Confirmar Quest, runtime, motor, SDK y licencias compatibles | Líder XR | Congelar build de referencia |
| Instrumentación | Seleccionar MCU, sensores, rangos, incertidumbre y aislamiento | Ingeniería mecatrónica | Conectar banco real |
| Tolerancias físicas | Aprobar escalas, ensayos y error por magnitud | Investigación | Aceptar modelo |
| Calendario, presupuesto y personal | Estimar después del prototipo de rendimiento | Dirección | Comprometer entrega |
| Roles y retención | Aprobar credenciales locales y retención de exportaciones | Operación | Exposición |

Referencias de tecnología verificadas se encuentran en [Architecture.md](Design/Architecture.md). Estado del conjunto: diseño propuesto para revisión; implementación y aceptación pendientes.
