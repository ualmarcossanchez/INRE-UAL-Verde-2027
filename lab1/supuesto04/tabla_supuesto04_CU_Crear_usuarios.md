| **Nombre:** | **Crear usuarios (UC-05)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al administrador de la tienda dar de alta un nuevo usuario en la aplicación. La creación conlleva el envío de un email al nuevo usuario. |
| **Actores:** | Administrador de la tienda |
| **Precondiciones:** | El administrador debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El administrador accede a la gestión de usuarios y selecciona la opción de crear un nuevo usuario.<br>2.- El sistema muestra un formulario para introducir los datos del nuevo usuario.<br>3.- El administrador introduce los datos del usuario y confirma la creación.<br>4.- El sistema comprueba la validez de los datos y almacena al nuevo usuario.<br>5.- El sistema ejecuta el caso de uso Enviar email (UC-06) para notificar el alta al nuevo usuario.<br>6.- El sistema muestra un mensaje confirmando que el usuario ha sido creado. |
| **Flujo Alternativo:** | 3.A.- El administrador cancela la creación, de modo que el sistema descarta los datos y no crea al usuario.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos o el usuario ya existe, avisa al administrador de ello permitiéndole que los corrija.<br>5.A.- El email no ha podido enviarse, por lo que el sistema avisa al administrador de ello. El usuario queda creado igualmente. |
| **Poscondiciones:** | El nuevo usuario ha sido almacenado en el sistema y se le ha enviado un email. |
| **Referencias:** | UC-06 (Enviar email), que se incluye en este caso de uso. |
