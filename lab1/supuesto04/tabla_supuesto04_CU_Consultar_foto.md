| **Nombre:** | **Consultar foto (UC-10)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente llevar a cabo consultas sobre las fotos de la aplicación. Es un caso particular de visualizar fotos. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El cliente accede a la sección de consulta de fotos.<br>2.- El sistema muestra un formulario para introducir los criterios de consulta.<br>3.- El cliente introduce los criterios y confirma la consulta.<br>4.- El sistema muestra las fotos que cumplen los criterios.<br>5.- El cliente selecciona una foto y el sistema la muestra. |
| **Flujo Alternativo:** | 4.A.- Ninguna foto cumple los criterios de consulta, por lo que el sistema muestra un mensaje indicándolo y el listado aparece vacío. |
| **Poscondiciones:** | Se muestran las fotos consultadas en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-11 (Visualizar fotos), del que es un caso particular. |
