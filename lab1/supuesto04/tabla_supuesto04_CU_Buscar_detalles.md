| **Nombre:** | **Buscar detalles (UC-12)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al vendedor buscar detalles en las fotos de la aplicación. La búsqueda conlleva la verificación de los datos introducidos. Es un caso particular de visualizar fotos. |
| **Actores:** | Vendedor |
| **Precondiciones:** | El vendedor debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El vendedor accede a la visualización de fotos y selecciona la opción de buscar detalles.<br>2.- El sistema muestra un formulario para introducir los datos de la búsqueda.<br>3.- El vendedor introduce los datos y confirma la búsqueda.<br>4.- El sistema ejecuta el caso de uso Verificar datos (UC-13) sobre los datos introducidos.<br>5.- El sistema busca los detalles en las fotos y los muestra al vendedor. |
| **Flujo Alternativo:** | 4.A.- Los datos introducidos no son válidos, por lo que el sistema avisa al vendedor de ello permitiéndole que los corrija.<br>5.A.- No se encuentra ningún detalle que cumpla la búsqueda, por lo que el sistema muestra un mensaje indicándolo. |
| **Poscondiciones:** | Se muestran los detalles encontrados en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-11 (Visualizar fotos), del que es un caso particular. UC-13 (Verificar datos), que se incluye en este caso de uso. |
