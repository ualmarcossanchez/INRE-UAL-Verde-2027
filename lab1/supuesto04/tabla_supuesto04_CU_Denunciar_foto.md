| **Nombre:** | **Denunciar foto (UC-17)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente realizar, de forma excepcional, una denuncia sobre una foto mientras la visualiza. Al denunciar una foto se ha de introducir una explicación sobre la denuncia. Es un caso particular de indicar foto a revisar. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe estar autenticado en el sistema y estar visualizando la foto que quiere denunciar (UC-11 en ejecución). |
| **Flujo Normal:** | 1.- El cliente selecciona la opción de denunciar la foto que está visualizando.<br>2.- El sistema ejecuta el caso de uso Explicar denuncia (UC-19) para que el cliente introduzca la explicación.<br>3.- El cliente confirma la denuncia.<br>4.- El sistema registra la denuncia y marca la foto como pendiente de revisión.<br>5.- El sistema muestra un mensaje confirmando que la denuncia ha sido realizada. |
| **Flujo Alternativo:** | 3.A.- El cliente cancela la denuncia, de modo que el sistema descarta los datos y no registra ninguna denuncia. |
| **Poscondiciones:** | La denuncia ha sido registrada junto con su explicación y la foto ha quedado marcada como pendiente de revisión. |
| **Referencias:** | UC-11 (Visualizar fotos), al que extiende. UC-19 (Explicar denuncia), que se incluye en este caso de uso. UC-16 (Indicar foto a revisar), del que es un caso particular. |
