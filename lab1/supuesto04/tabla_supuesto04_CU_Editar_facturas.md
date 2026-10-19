| **Nombre:** | **Editar facturas (UC-04)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite modificar los datos de una factura ya emitida. Es un caso particular de editar datos. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. La factura a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El actor accede a la gestión de facturas y selecciona la factura que desea editar.<br>2.- El sistema muestra los datos actuales de la factura en un formulario editable.<br>3.- El actor modifica los datos de la factura y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la factura ha sido modificada. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la edición, de modo que el sistema descarta los cambios y no modifica la factura.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos de la factura han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-01 (Editar datos), del que es un caso particular. |
