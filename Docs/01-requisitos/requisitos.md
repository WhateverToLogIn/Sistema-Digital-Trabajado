# Requisitos — LondX

Requisitos obtenidos de la revisión de plataformas públicas de gestión de préstamos (hallazgos H-01 a H-05). Cada uno está vinculado a un Issue.

## Requisitos funcionales

| Código | Requisito | Historia de usuario | Criterio de aceptación | Hallazgo | Issue |
|---|---|---|---|---|---|
| RF-01 | Registrar, editar y consultar clientes con nombre, cédula, teléfono y dirección. | Como prestamista, quiero registrar los datos de mis clientes para tener su información en un solo lugar. | Al guardar un cliente con los campos obligatorios, aparece en la lista y se puede abrir su ficha. | H-01 Ficha del cliente centralizada | #1 |
| RF-02 | Calcular automáticamente la cuota, el interés y la tabla de amortización al crear un préstamo. | Como prestamista, quiero que el sistema calcule cuotas e intereses para no equivocarme a mano. | Al ingresar monto, tasa y plazo se muestra la tabla de cuotas con fechas y montos. | H-02 Tabla de cuotas generada por el sistema | #2 |
| RF-03 | Registrar el pago de una cuota y actualizar el saldo del préstamo. | Como cobrador, quiero registrar el pago y que el saldo se actualice solo. | La cuota queda pagada y el saldo baja por el monto aplicado. | H-03 Pago aplicado contra la cuota | #5 |
| RF-04 | Mostrar clientes con cuotas vencidas y días de atraso. | Como prestamista, quiero ver los clientes atrasados para saber a quién cobrar primero. | Solo aparecen cuotas vencidas no pagadas, ordenadas por días de atraso. | H-04 Reportes de mora dedicados | #3 |

## Requisitos no funcionales

| Código | Requisito | Criterio de aceptación | Hallazgo | Issue |
|---|---|---|---|---|
| RNF-01 | Acceso con usuario y contraseña, con roles de administrador y cobrador. | Un cobrador no puede abrir configuración ni borrar préstamos. | H-05 Roles con permisos por pantalla | #4 |
| RNF-02 | Contraseñas guardadas cifradas en la base de datos. | Ninguna contraseña se guarda en texto plano. | H-05 | #4 |
