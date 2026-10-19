| **Nombre:** | **Reducir precio (UC-15)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al vendedor reducir el precio de un producto al hacer una oferta. Se ejecuta solo de forma excepcional, como extensión de hacer oferta. |
| **Actores:** | Vendedor |
| **Precondiciones:** | El vendedor debe estar haciendo una oferta sobre un producto (UC-14 en ejecución). |
| **Flujo Normal:** | 1.- El vendedor selecciona la opción de reducir el precio durante la realización de la oferta.<br>2.- El sistema muestra el precio actual del producto y un campo para introducir el nuevo precio.<br>3.- El vendedor introduce el nuevo precio y confirma.<br>4.- El sistema comprueba que el nuevo precio es válido y lo aplica a la oferta.<br>5.- El sistema devuelve el control a Hacer oferta (UC-14). |
| **Flujo Alternativo:** | 3.A.- El vendedor cancela la reducción, de modo que la oferta mantiene el precio original.<br>4.A.- El nuevo precio no es válido (por ejemplo, no es menor que el actual), por lo que el sistema avisa al vendedor de ello permitiéndole que lo corrija. |
| **Poscondiciones:** | La oferta incluye el precio reducido del producto. |
| **Referencias:** | UC-14 (Hacer oferta), al que extiende. |
