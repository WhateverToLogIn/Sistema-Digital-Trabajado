# LondX — Sistema de Gestión de Préstamos y Cobros

![Estado](https://img.shields.io/badge/estado-v0.1.0%20análisis%20y%20diseño-C9A84C)
![Frontend](https://img.shields.io/badge/frontend-React-0B1F3A)
![Backend](https://img.shields.io/badge/backend-.NET%20API%20REST-0B1F3A)

Proyecto académico de la asignatura **Ingeniería de Software I** — Universidad Abierta Para Adultos (UAPA).

---

## Objetivo

Desarrollar un sistema web que permita a un prestamista registrar clientes, crear préstamos con cálculo automático de cuotas, registrar pagos y dar seguimiento a la mora desde un solo lugar.

## Problema que resuelve

El prestamista pequeño suele llevar sus clientes y préstamos en cuadernos, calcula cuotas e intereses a mano y no tiene una vista rápida de quién está atrasado. Esto provoca errores de cálculo, pagos que no quedan anotados y cobros desorganizados. LondX centraliza esa información y automatiza los cálculos.

## Funcionalidades principales

| Código | Funcionalidad | Issue |
|---|---|---|
| RF-01 | Registrar, editar y consultar clientes (nombre, cédula, teléfono, dirección) | [#1](../../issues/1) |
| RF-02 | Crear préstamos con cálculo automático de cuota, interés y tabla de amortización | [#2](../../issues/2) |
| RF-03 | Registrar el pago de una cuota y actualizar el saldo del préstamo | [#5](../../issues/5) |
| RF-04 | Listar clientes con cuotas vencidas y días de atraso | [#3](../../issues/3) |
| RNF-01 | Acceso con usuario y contraseña, roles de administrador y cobrador | [#4](../../issues/4) |
| RNF-02 | Contraseñas almacenadas cifradas en la base de datos | [#4](../../issues/4) |

## Arquitectura seleccionada

Arquitectura **en capas** (presentación, servicios, negocio y datos) sobre un modelo **cliente-servidor**. Autenticación, auditoría y notificaciones son componentes transversales. Detalle en [`docs/03-arquitectura`](docs/03-arquitectura/arquitectura.md) e issue [#6](../../issues/6).

## Organización frontend / backend

**Frontend (React)** — capa de presentación. Es responsable de:
- Pantallas de inicio de sesión, clientes, préstamos, pagos y reporte de mora.
- Validar formularios antes de enviarlos.
- Guardar el token de sesión y ocultar opciones según el rol (administrador o cobrador).
- Mostrar la tabla de cuotas y los saldos que devuelve el backend. No realiza cálculos financieros.

**Backend (.NET, API REST)** — capas de servicios, negocio y datos. Es responsable de:
- Exponer los endpoints REST que consume el frontend.
- Aplicar las reglas de negocio: cálculo de cuotas e intereses, aplicación de pagos, actualización de saldo y cálculo de días de atraso.
- Autenticar usuarios, emitir el token JWT y validar permisos por rol en cada petición.
- Guardar y consultar la información en la base de datos (contraseñas con hash).

**Comunicación entre ambas partes**

```
[ Navegador · React ]  ──HTTPS + JSON──►  [ API REST .NET ]  ──►  [ Base de datos ]
        ▲                 Authorization: Bearer <JWT>          │
        └──────────────────── respuesta JSON ◄─────────────────┘
```

1. El usuario inicia sesión; el backend valida credenciales y devuelve un JWT con su rol.
2. El frontend envía ese token en cada petición (`Authorization: Bearer`).
3. El backend valida el token y el rol, ejecuta la regla de negocio y responde en JSON.

Endpoints propuestos (por implementar):

| Método | Ruta | Uso |
|---|---|---|
| POST | `/api/auth/login` | Iniciar sesión y obtener token |
| GET / POST / PUT | `/api/clientes` | Gestión de clientes |
| POST | `/api/prestamos` | Crear préstamo y generar cuotas |
| GET | `/api/prestamos/{id}/cuotas` | Consultar tabla de cuotas |
| POST | `/api/pagos` | Registrar pago y actualizar saldo |
| GET | `/api/reportes/mora` | Clientes con cuotas vencidas |

## Herramientas utilizadas

| Herramienta | Uso |
|---|---|
| Git y GitHub | Control de versiones y repositorio |
| GitHub Issues | Requisitos, tareas e incidencias |
| GitHub Projects | Tablero Kanban del avance |
| Visual Paradigm Online | Diagramas UML |
| React | Frontend (planificado) |
| .NET (API REST) | Backend (planificado) |
| JWT sobre HTTPS | Autenticación y comunicación |

## Estado actual del proyecto

**Versión 0.1.0 — fase de análisis y diseño.** El repositorio contiene la documentación técnica; aún no hay código fuente.

| Estado | Elementos |
|---|---|
| Finalizado | Requisitos (#8), Diagrama de clases UML (#7) |
| En revisión | Modelo de base de datos (#9) |
| En progreso | Arquitectura inicial (#6), Gestión de clientes (#1), Autenticación (#4) |
| Por hacer | Préstamos y cuotas (#2), Pagos y saldo (#5) |
| Backlog | Dashboard y reportes (#3), Plan de pruebas |

Tablero: [GitHub Projects — LondX](https://github.com/users/WhateverToLogIn/projects/1)

## Estructura del repositorio

```
LondXTEst/
├── README.md
├── CHANGELOG.md
├── NOTA_VERSION.md
└── docs/
    ├── 01-requisitos/requisitos.md
    ├── 02-uml/              ← diagramas exportados de Visual Paradigm
    ├── 03-arquitectura/arquitectura.md
    └── 04-gestion/gestion-avance.md
```

## Autor

Alvaro — [@WhateverToLogIn](https://github.com/WhateverToLogIn)
