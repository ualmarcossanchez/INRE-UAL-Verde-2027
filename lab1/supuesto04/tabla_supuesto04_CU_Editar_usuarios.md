| | |
|---|---|
| **Nombre:** | **Editar usuarios (UC-02)** |
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al administrador de la tienda modificar los datos de un usuario ya registrado en la aplicación. Es un caso particular de editar datos. |
| **Actores:** | Administrador de la tienda |
| **Precondiciones:** | El administrador debe estar autenticado en el sistema. El usuario a editar debe estar registrado en la aplicación. |
| **Flujo Normal:** | 1.- El administrador accede a la gestión de usuarios y selecciona el usuario que desea editar.<br>2.- El sistema muestra los datos actuales del usuario en un formulario editable.<br>3.- El administrador modifica los datos del usuario y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que el usuario ha sido modificado. |
| **Flujo Alternativo:** | 3.A.- El administrador cancela la edición, de modo que el sistema descarta los cambios y no modifica al usuario.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al administrador de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos del usuario han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-01 (Editar datos), del que es un caso particular. |
