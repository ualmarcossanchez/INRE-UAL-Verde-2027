| **Nombre:** | **Hacer oferta (UC-14)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al vendedor escribir a un cliente para hacerle una oferta sobre un producto de la aplicación. De forma excepcional, al hacer la oferta se puede reducir el precio del producto (punto de extensión: Reducir precio). |
| **Actores:** | Vendedor |
| **Precondiciones:** | El vendedor debe estar autenticado en el sistema. Deben existir el cliente destinatario y el producto sobre el que se hace la oferta. |
| **Flujo Normal:** | 1.- El vendedor selecciona al cliente y el producto sobre el que quiere hacer la oferta.<br>2.- El sistema muestra un formulario para introducir los datos de la oferta.<br>3.- El vendedor introduce los datos de la oferta y confirma.<br>4.- El sistema comprueba la validez de los datos, registra la oferta y se la envía al cliente.<br>5.- El sistema muestra un mensaje confirmando que la oferta ha sido realizada. |
| **Flujo Alternativo:** | 3.A.- El vendedor decide reducir el precio del producto. Se ejecuta el caso de uso Reducir precio (UC-15) a través del punto de extensión.<br>3.B.- El vendedor cancela la oferta, de modo que el sistema descarta los datos y no registra ninguna oferta.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al vendedor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | La oferta ha sido registrada en el sistema y enviada al cliente. |
| **Referencias:** | UC-15 (Reducir precio), que lo extiende. UC-08 (Ver ofertas (cliente)), a través del cual el cliente consulta la oferta. |
