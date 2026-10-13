# Nota técnica de versión — LondX v0.1.0

**Fecha:** 2026-10-12  **Etiqueta:** `v0.1.0`  **Rama:** `main`

## Contenido de la versión
Versión de documentación. Incluye los requisitos funcionales y no funcionales (RF-01 a RF-04, RNF-01 y RNF-02), el diagrama de clases UML, la definición de la arquitectura en capas cliente-servidor, la organización frontend/backend, el registro de cambios y el estado del tablero. No incluye código fuente.

## Cambios controlados
- Requisitos y diagrama de clases cerrados como Issues (#8, #7).
- Arquitectura registrada y renombrada en el Issue #6.
- Modelo de base de datos enviado a revisión (#9).
- Cada módulo vinculado a su requisito y hallazgo de origen en su Issue (#1 – #5).
- Avance controlado en GitHub Projects; esta versión queda marcada con la etiqueta `v0.1.0`.

## Pendientes
- Aprobar el modelo de base de datos (#9) y definir el motor de base de datos.
- Implementar autenticación (#4), clientes (#1), préstamos y cuotas (#2), pagos (#5) y reporte de mora (#3).
- Elaborar el plan de pruebas.
- Unificar los Issues duplicados del repositorio `Sistema-Digital-Trabajado` en este repositorio.

## Próximo paso técnico
Crear la estructura base del código: proyecto React en `frontend/` y API REST .NET en `backend/`, conectar la base de datos aprobada en #9 e implementar primero la autenticación con JWT (#4), ya que los demás módulos dependen de los roles.
