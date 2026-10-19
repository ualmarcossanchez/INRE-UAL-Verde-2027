| **Nombre:** | **Editar info fotos (UC-18)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al controlador de fotos editar la información asociada a las fotos de la aplicación. |
| **Actores:** | Controlador de fotos |
| **Precondiciones:** | El controlador de fotos debe estar autenticado en el sistema. La foto a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El controlador accede a las fotos y selecciona la foto cuya información desea editar.<br>2.- El sistema muestra la información actual de la foto en un formulario editable.<br>3.- El controlador modifica la información y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la información de la foto ha sido modificada. |
| **Flujo Alternativo:** | 3.A.- El controlador cancela la edición, de modo que el sistema descarta los cambios y no modifica la foto.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al controlador de ello permitiéndole que los corrija. |
| **Poscondiciones:** | La información de la foto ha sido modificada y almacenada en el sistema. |
| **Referencias:** | Ninguna. |
