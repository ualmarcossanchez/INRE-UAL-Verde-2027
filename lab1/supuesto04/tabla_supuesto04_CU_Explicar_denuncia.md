| **Nombre:** | **Explicar denuncia (UC-19)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente introducir la explicación que acompaña a la denuncia de una foto. Es obligatorio al denunciar una foto y se ejecuta como parte de ese caso de uso. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe haber seleccionado la opción de denunciar una foto (UC-17 en ejecución). |
| **Flujo Normal:** | 1.- El sistema muestra un campo de texto para introducir la explicación de la denuncia.<br>2.- El cliente escribe la explicación y la confirma.<br>3.- El sistema comprueba que la explicación no está vacía y la asocia a la denuncia. |
| **Flujo Alternativo:** | 3.A.- La explicación está vacía, por lo que el sistema avisa al cliente de que debe introducirla y le permite que la complete. |
| **Poscondiciones:** | La explicación ha quedado asociada a la denuncia de la foto. |
| **Referencias:** | UC-17 (Denunciar foto), que lo incluye. |
