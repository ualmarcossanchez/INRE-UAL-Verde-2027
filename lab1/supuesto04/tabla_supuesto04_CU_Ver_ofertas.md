| **Nombre:** | **Ver ofertas (UC-07)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite consultar las ofertas existentes en la aplicación. Es un caso de uso general, del que Ver ofertas (cliente) es un caso particular. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El actor accede a la sección de ofertas.<br>2.- El sistema muestra un listado con las ofertas existentes.<br>3.- El actor selecciona una oferta del listado.<br>4.- El sistema muestra el detalle de la oferta seleccionada. |
| **Flujo Alternativo:** | 2.A.- No existe ninguna oferta en el sistema, por lo que el sistema muestra un mensaje indicándolo y el listado aparece vacío. |
| **Poscondiciones:** | Se muestran las ofertas en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-08 (Ver ofertas (cliente)), que es un caso particular de este caso de uso. |
