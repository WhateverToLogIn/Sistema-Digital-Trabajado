# Gestión del avance — LondX

Tablero: [GitHub Projects — LondX](https://github.com/users/WhateverToLogIn/projects/1)

Columnas: Backlog → Por hacer → En progreso → En revisión → Finalizado.

| Issue | Tarea | Prioridad | Columna |
|---|---|---|---|
| #8 | Levantamiento y documentación de requisitos | Alta | Finalizado |
| #7 | Diseño del diagrama de clases UML | Alta | Finalizado |
| #9 | Creación del modelo de base de datos | Alta | En revisión |
| #6 | Definición de arquitectura inicial | Alta | En progreso |
| #4 | Módulo de autenticación de usuarios | Alta | En progreso |
| #1 | Módulo de gestión de clientes | Media | En progreso |
| #2 | Módulo de préstamos y generación de cuotas | Media | Por hacer |
| #5 | Registro de pagos y actualización de saldo | Media | Por hacer |
| #3 | Dashboard y reportes | Baja | Backlog |
| — | Elaboración del plan de pruebas | Media | Backlog |

## Issues seleccionados para seguimiento técnico

| Issue | Tipo | Motivo del seguimiento |
|---|---|---|
| #9 Modelo de base de datos | Tarea pendiente | Está en revisión y bloquea la implementación de todos los módulos. |
| #4 Autenticación de usuarios | Riesgo | Un error en roles o en el cifrado de contraseñas expone datos de clientes y préstamos. |
| #2 Préstamos y generación de cuotas | Riesgo | Un error en el cálculo de intereses o amortización afecta todos los saldos. Debe validarse con el plan de pruebas. |
| #3 Dashboard y reportes | Mejora | Aporta la vista de mora para priorizar cobros; prioridad baja hasta tener pagos (#5). |
