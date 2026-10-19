| **Nombre:** | **Verificar datos (UC-13)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite comprobar que los datos introducidos en una búsqueda de detalles son correctos antes de realizarla. Este caso de uso se ejecuta como parte de buscar detalles. |
| **Actores:** | Vendedor (a través de Buscar detalles) |
| **Precondiciones:** | El vendedor debe haber introducido los datos de la búsqueda de detalles. |
| **Flujo Normal:** | 1.- El sistema recibe los datos introducidos por el vendedor.<br>2.- El sistema comprueba que los datos tienen el formato correcto y que los obligatorios están completos.<br>3.- El sistema da los datos por válidos y devuelve el control al caso de uso Buscar detalles. |
| **Flujo Alternativo:** | 3.A.- Los datos no son correctos, por lo que el sistema informa de los errores encontrados y los devuelve al vendedor para que los corrija. |
| **Poscondiciones:** | Los datos han sido verificados, ya sea dándolos por válidos o notificando los errores al vendedor. |
| **Referencias:** | UC-12 (Buscar detalles), que lo incluye. |
