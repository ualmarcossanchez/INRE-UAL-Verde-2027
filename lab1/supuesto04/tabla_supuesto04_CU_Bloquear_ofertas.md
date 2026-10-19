| **Nombre:** | **Bloquear ofertas (UC-09)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite bloquear una oferta existente para que deje de estar activa en la aplicación. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. La oferta a bloquear debe existir en el sistema y no estar ya bloqueada. |
| **Flujo Normal:** | 1.- El actor accede a la sección de ofertas y selecciona la oferta que desea bloquear.<br>2.- El sistema muestra el detalle de la oferta y la opción de bloquearla.<br>3.- El actor selecciona bloquear la oferta y confirma la acción.<br>4.- El sistema marca la oferta como bloqueada.<br>5.- El sistema muestra un mensaje confirmando que la oferta ha sido bloqueada. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la acción, de modo que el sistema no bloquea la oferta.<br>4.A.- La oferta ya había sido bloqueada por otro actor, por lo que el sistema avisa de ello y no realiza ningún cambio. |
| **Poscondiciones:** | La oferta ha quedado marcada como bloqueada en el sistema. |
| **Referencias:** | Ninguna. |
