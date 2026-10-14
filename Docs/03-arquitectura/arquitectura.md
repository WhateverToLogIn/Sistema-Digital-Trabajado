# Arquitectura — LondX

Fuente: Issue #6 "Definición de arquitectura inicial".

## Estilo
Arquitectura en capas sobre un modelo cliente-servidor.

| Capa | Ubicación | Responsabilidad |
|---|---|---|
| Presentación | Frontend React | Pantallas, formularios, manejo del token y del rol |
| Servicios | Backend .NET | Endpoints REST, validación del JWT |
| Negocio | Backend .NET | Cálculo de cuotas e intereses, aplicación de pagos, mora |
| Datos | Backend .NET + base de datos | Acceso y persistencia de la información |

**Componentes transversales:** autenticación, auditoría y notificaciones.

**Comunicación:** HTTPS con intercambio JSON; autenticación con JWT enviado en el encabezado `Authorization: Bearer`.

## Diagrama
Agregar aquí la imagen del diagrama de arquitectura publicada en el Issue #6 (`arquitectura.png`).

![Arquitectura LondX](arquitectura.png)
