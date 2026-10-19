| | |
|---|---|
| **Nombre:** | **Editar datos (UC-01)** |
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite modificar los datos almacenados en el sistema. Es un caso de uso general que recoge las características comunes de editar facturas y editar usuarios, que lo especializan. |
| **Actores:** | Gestor de la aplicación / Administrador (a través de sus casos de uso particulares) |
| **Precondiciones:** | El actor debe estar autenticado en el sistema y tener permisos para editar el dato. El dato a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El actor selecciona el elemento que desea editar.<br>2.- El sistema muestra los datos actuales del elemento en un formulario editable.<br>3.- El actor modifica los datos y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la edición se ha realizado. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la edición, de modo que el sistema descarta los cambios y no modifica el elemento.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos del elemento han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-02 (Editar usuarios) y UC-04 (Editar facturas), que lo especializan. |
