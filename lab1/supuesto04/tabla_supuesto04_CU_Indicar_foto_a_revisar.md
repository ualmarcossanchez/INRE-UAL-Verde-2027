| **Nombre:** | **Indicar foto a revisar (UC-16)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al controlador de fotos indicar que una foto debe ser revisada. Es un caso general de denunciar foto. |
| **Actores:** | Controlador de fotos |
| **Precondiciones:** | El controlador de fotos debe estar autenticado en el sistema. La foto debe existir en el sistema. |
| **Flujo Normal:** | 1.- El controlador accede a las fotos y selecciona la foto que debe revisarse.<br>2.- El sistema muestra la foto seleccionada.<br>3.- El controlador indica que la foto debe ser revisada y confirma la acción.<br>4.- El sistema marca la foto como pendiente de revisión.<br>5.- El sistema muestra un mensaje confirmando que la foto ha sido marcada. |
| **Flujo Alternativo:** | 3.A.- El controlador cancela la acción, de modo que el sistema no marca la foto.<br>4.A.- La foto ya estaba marcada como pendiente de revisión, por lo que el sistema avisa de ello y no realiza ningún cambio. |
| **Poscondiciones:** | La foto ha quedado marcada como pendiente de revisión en el sistema. |
| **Referencias:** | UC-17 (Denunciar foto), que es un caso particular de este caso de uso. |
