| **Nombre:** | **Visualizar fotos (UC-11)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente visualizar las fotos de la aplicación. De forma excepcional, durante la visualización se puede realizar una denuncia sobre la foto (punto de extensión: Denunciar foto). Es un caso de uso general, del que Consultar foto y Buscar detalles son casos particulares. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El cliente accede a la sección de fotos.<br>2.- El sistema muestra las fotos disponibles.<br>3.- El cliente selecciona una foto.<br>4.- El sistema muestra la foto seleccionada junto con su información. |
| **Flujo Alternativo:** | 2.A.- No hay fotos disponibles, por lo que el sistema muestra un mensaje indicándolo.<br>4.A.- Mientras visualiza la foto, el cliente decide denunciarla. Se ejecuta el caso de uso Denunciar foto (UC-17) a través del punto de extensión. |
| **Poscondiciones:** | Se muestra la foto en pantalla, pero no se modifica ni se borra ningún dato en el sistema (salvo que se haya realizado una denuncia). |
| **Referencias:** | UC-10 (Consultar foto) y UC-12 (Buscar detalles), que son casos particulares de este caso de uso. UC-17 (Denunciar foto), que lo extiende. |
