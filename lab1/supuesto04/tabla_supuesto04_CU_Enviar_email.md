| **Nombre:** | **Enviar email (UC-06)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite enviar un email al usuario recién creado. Para ello es necesario el uso de un gestor de correo. Este caso de uso se ejecuta como parte de la creación de usuarios. |
| **Actores:** | Gestor de correo (actor secundario) |
| **Precondiciones:** | El usuario debe haber sido creado y almacenado en el sistema, con una dirección de correo asociada. El gestor de correo debe estar disponible. |
| **Flujo Normal:** | 1.- El sistema genera el email dirigido al nuevo usuario.<br>2.- El sistema envía el email al gestor de correo.<br>3.- El gestor de correo entrega el email a la dirección del usuario.<br>4.- El gestor de correo confirma al sistema que el email ha sido enviado. |
| **Flujo Alternativo:** | 3.A.- El gestor de correo no puede entregar el email, ya sea porque no está disponible o porque la dirección no es válida. El gestor de correo informa del error al sistema y éste avisa de que el email no ha sido enviado. |
| **Poscondiciones:** | El email ha sido enviado al usuario a través del gestor de correo. |
| **Referencias:** | UC-05 (Crear usuarios), que lo incluye. |
