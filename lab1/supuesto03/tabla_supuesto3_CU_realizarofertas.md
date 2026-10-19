
| **Nombre:** | Realizar ofertas (CU-004) |
| :--- | :--- |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al empleado crear y publicar una nueva oferta o promoción en el sistema. Este proceso incluye la actualización automática de las tarifas y permite, de forma opcional, bloquear temporalmente una reserva vinculada a dicha oferta. |
| **Actores:** | Empleado (Administrador / Comercial) |
| **Precondiciones:** | El empleado debe estar autenticado en el sistema con los permisos correspondientes. |
| **Flujo Normal:** | 1.- El empleado accede a la sección de gestión de ofertas y selecciona crear una nueva.<br>2.- El sistema muestra un formulario para introducir los datos de la promoción (porcentaje de descuento, fechas de validez, etc.).<br>3.- El empleado introduce los datos requeridos y pulsa en calcular.<br>4.- El sistema realiza automáticamente el **recálculo de precios** (Include) aplicando el descuento sobre las tarifas base y muestra el resultado.<br>5.- El empleado confirma la publicación de la oferta.<br>6.- El sistema almacena la oferta y notifica que se ha creado con éxito. |
| **Flujo Alternativo:** | 4.A.- **Bloqueo temporal de reserva** (Extend): Antes de confirmar la publicación en el paso 5, el empleado decide que esta oferta va dirigida a una habitación/reserva específica que está tramitando.<br>4.A.1.- El empleado selecciona la opción de bloquear disponibilidad.<br>4.A.2.- El sistema bloquea temporalmente la reserva vinculada para que ningún otro usuario pueda ocuparla.<br>4.A.3.- El flujo retorna al paso 5 del flujo normal. |
| **Poscondiciones:** | La nueva oferta queda registrada en el sistema con los precios actualizados. Si se aplicó el flujo alternativo, la reserva asociada queda bloqueada temporalmente. |
