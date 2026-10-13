# Registro de cambios — LondX

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/). Fechas tomadas del historial de Issues y del tablero de GitHub Projects.

## [0.1.0] — 2026-10-12

Primera versión controlada: documentación técnica del análisis y diseño.

### Avances registrados

| # | Fecha | Cambio | Evidencia |
|---|---|---|---|
| 1 | 2026-08-22 | Se creó el tablero de GitHub Projects con las tareas iniciales de requisitos y base de datos. | Projects #1 |
| 2 | 2026-08-27 | Se creó el repositorio y se registraron los módulos como Issues con historia de usuario, requisito (RF-01 a RF-04, RNF-01 y RNF-02), criterio de aceptación y hallazgo de origen (H-01 a H-05). | #1 – #5 |
| 3 | 2026-09-13 | Se definió la arquitectura inicial: capas sobre cliente-servidor, React + API REST .NET, HTTPS con JWT. El issue se renombró para precisar su alcance. | #6 |
| 4 | 2026-09-22 | Se cerraron el levantamiento de requisitos y el diagrama de clases UML (Usuario, Cliente, Préstamo, Cuota, Pago); ambos pasaron a Finalizado. | #7, #8 |
| 5 | 2026-09-22 | El modelo de base de datos pasó a En revisión y se registró la tarea del plan de pruebas. | #9, plan de pruebas |

### Agregado en esta versión
- `README.md` con objetivo, problema, funcionalidades, arquitectura y organización frontend/backend.
- Carpeta `docs/` con requisitos, arquitectura y gestión del avance.
- `NOTA_VERSION.md`.
