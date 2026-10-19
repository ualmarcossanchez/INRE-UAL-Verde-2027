| **Nombre:** | **Emitir facturas (UC-03)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite emitir una factura desde la aplicación. La emisión requiere la participación de un software de facturación, que genera la factura a partir de los datos facilitados por el sistema. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda. Software de facturación (actor secundario) |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. Debe existir una operación sobre la que emitir la factura. El software de facturación debe estar disponible. |
| **Flujo Normal:** | 1.- El actor accede a la gestión de facturas y selecciona la opción de emitir una nueva factura.<br>2.- El sistema muestra un formulario con los datos necesarios para la factura.<br>3.- El actor completa los datos y confirma la emisión.<br>4.- El sistema comprueba la validez de los datos y los envía al software de facturación.<br>5.- El software de facturación genera la factura y la devuelve al sistema.<br>6.- El sistema almacena la factura y muestra un mensaje confirmando que ha sido emitida. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la emisión, de modo que el sistema descarta los datos y no emite la factura.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija.<br>5.A.- El software de facturación no puede generar la factura, por lo que el sistema avisa al actor del error y no almacena ninguna factura. |
| **Poscondiciones:** | La factura ha sido generada por el software de facturación y almacenada en el sistema. |
| **Referencias:** | Ninguna. |
