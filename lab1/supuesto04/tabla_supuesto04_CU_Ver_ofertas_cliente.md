| **Nombre:** | **Ver ofertas (cliente) (UC-08)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente consultar las ofertas que los vendedores le han hecho sobre los productos de la aplicación. Es un caso particular de ver ofertas. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El cliente accede a la sección de ofertas.<br>2.- El sistema muestra un listado con las ofertas dirigidas al cliente.<br>3.- El cliente selecciona una oferta del listado.<br>4.- El sistema muestra el detalle de la oferta seleccionada. |
| **Flujo Alternativo:** | 2.A.- El cliente no tiene ninguna oferta, por lo que el sistema muestra un mensaje indicándolo y el listado aparece vacío. |
| **Poscondiciones:** | Se muestran las ofertas del cliente en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-07 (Ver ofertas), del que es un caso particular. UC-14 (Hacer oferta), que genera las ofertas que consulta el cliente. |
