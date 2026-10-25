## Supuesto 1: Horarios

En una universidad, el personal del PDI, el personal del PAS y los estudiantes pueden consultar horarios. Por su parte, el personal del PAS puede modificar horarios y dar de alta estudiantes. El personal de PDI puede proponer cambios en los horarios y dar de alta estudiantes. La funcionalidad de dar de alta estudiantes del PAS realiza una verificación de los datos del estudiante. Sin embargo, la funcionalidad de dar de alta estudiantes del PDI, además de verificar los datos también permite de forma excepcional realizar la búsqueda en las listas de clase de sus asignaturas.



## Supuesto 2: Sistema de Compras

En un sistema de compra, existen cuatro tipos de usuarios: comprador, vendedor, proveedor y administrador. Los compradores pueden agregar productos, consultar precios, finalizar la compra y consultar ofertas. Agregar productos implica marcar esos productos como bloqueados. Los vendedores también pueden consultar ofertas y consultar precios. Los proveedores pueden consultar precios, avisar de nuevos productos y consultar ofertas. Avisar de nuevos productos, de forma excepcional, realiza la incorporación de una oferta. Los proveedores también tienen una funcionalidad para avisar del fin de una oferta. Cuando se avisa del fin de una oferta, se ejecuta la funcionalidad de eliminar la oferta. Ambas funcionalidades de avisar del proveedor tienen en común que se encarga de enviar una notificación. Los administradores pueden consultar precios, consultar ofertas y eliminar productos. La funcionalidad de consultar precios incluye una funcionalidad de buscar productos que es similar a la funcionalidad de consultar productos de los compradores. Sin embargo, la funcionalidad de consultar productos añade una funcionalidad para verificar la disponibilidad. Para realizar una venta, un comprador y un vendedor participan de forma conjunta. En dicha operación, se lleva a cabo el acuerdo de un precio; excepcionalmente, durante la realización de la venta, se consultará el histórico de ventas.

<img width="1345" height="767" alt="image" src="https://github.com/user-attachments/assets/32c4d210-d659-4956-acae-1ecf4e1df263" />

## Descripción de los actores

## Actores del sistema

### Usuario

| **Actor** | **Usuario (ACT 001)** |
|---|---|
| **Desc** | Es el actor general que representa a cualquier persona que accede al sistema de compras. |
| **Caract** | Es un actor abstracto: sus características comunes las heredan el Comprador, el Vendedor, el Proveedor y el Administrador. Puede consultar precios y consultar ofertas. |
| **Relaciones** | Relación de herencia de Comprador, Vendedor, Proveedor y Administrador hacia Usuario. |
| **Referencias** | El usuario puede consultar precios (UC-01) y consultar ofertas (UC-02), por lo que también pueden hacerlo el Comprador, el Vendedor, el Proveedor y el Administrador. |
| **Autor** | Emilio Murillo Cortés \| **Fecha:** 24/10/2026 \| **Versión:** 1.0 |


### Comprador

| **Actor** | **Comprador (ACT 002)** |
|---|---|
| **Desc** | Representa a la persona que utiliza el sistema para seleccionar productos y efectuar una compra. |
| **Caract** | Es una especialización de Usuario. Puede consultar precios y ofertas, agregar productos, consultar productos y participar en la realización de una compraventa. |
| **Relaciones** | Hereda del actor Usuario. Se relaciona con Agregar productos, Consultar productos y Realizar compraventa. En la compraventa participa conjuntamente con el Vendedor. |
| **Referencias** | Puede consultar precios (UC-01), consultar ofertas (UC-02), agregar productos (UC-03), consultar productos (UC-05) y realizar una compraventa (UC-07). Agregar productos incluye marcar los productos como bloqueados (UC-04). Consultar productos incluye verificar su disponibilidad (UC-06). Realizar la compraventa incluye acordar el precio (UC-08) y puede extenderse excepcionalmente con la consulta del histórico de ventas (UC-09). |
| **Autor** | Emilio Murillo Cortés \| **Fecha:** 24/10/2026 \| **Versión:** 1.0 |


### Vendedor

| **Actor** | **Vendedor (ACT 003)** |
|---|---|
| **Desc** | Representa a la persona que interviene en la venta de productos dentro del sistema de compras. |
| **Caract** | Es una especialización de Usuario. Puede consultar precios y ofertas, además de participar en la realización de una compraventa. |
| **Relaciones** | Hereda del actor Usuario. Se relaciona directamente con Realizar compraventa, operación en la que participa conjuntamente con el Comprador. |
| **Referencias** | Puede consultar precios (UC-01), consultar ofertas (UC-02) y realizar una compraventa (UC-07). La compraventa incluye acordar el precio (UC-08) y puede extenderse excepcionalmente con la consulta del histórico de ventas (UC-09). |
| **Autor** | Emilio Murillo Cortés \| **Fecha:** 24/10/2026 \| **Versión:** 1.0 |


### Proveedor

| **Actor** | **Proveedor (ACT 004)** |
|---|---|
| **Desc** | Representa a la persona o entidad que suministra productos y comunica al sistema la aparición o finalización de ofertas. |
| **Caract** | Es una especialización de Usuario. Puede consultar precios y ofertas, avisar de nuevos productos y avisar del fin de una oferta. |
| **Relaciones** | Hereda del actor Usuario. Se relaciona con Avisar de nuevos productos y Avisar del fin de una oferta. Ambas funcionalidades son especializaciones de Avisar. |
| **Referencias** | Puede consultar precios (UC-01), consultar ofertas (UC-02), avisar de nuevos productos (UC-10) y avisar del fin de una oferta (UC-14). Avisar de nuevos productos puede provocar excepcionalmente la incorporación de una oferta (UC-11). Avisar del fin de una oferta incluye eliminar la oferta (UC-15). Las dos modalidades de aviso comparten la funcionalidad Avisar (UC-12), que incluye enviar una notificación (UC-13). |
| **Autor** | Emilio Murillo Cortés \| **Fecha:** 24/10/2026 \| **Versión:** 1.0 |


### Administrador

| **Actor** | **Administrador (ACT 005)** |
|---|---|
| **Desc** | Representa a la persona responsable de gestionar y eliminar productos dentro del sistema de compras. |
| **Caract** | Es una especialización de Usuario. Puede consultar precios y ofertas, además de eliminar productos. |
| **Relaciones** | Hereda del actor Usuario. Se relaciona directamente con Eliminar productos. |
| **Referencias** | Puede consultar precios (UC-01), consultar ofertas (UC-02) y eliminar productos (UC-16). La consulta de precios incluye la búsqueda de productos (UC-17). |
| **Autor** | Emilio Murillo Cortés \| **Fecha:** 24/10/2026 \| **Versión:** 1.0 |

## Descripción de los casos de uso

## Casos de uso

### UC-01 — Consultar precios

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar precios (UC-01) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite consultar el precio de los productos del sistema. |
| **Actores:** | Usuario. |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario introduce los criterios de búsqueda.<br>2. El sistema busca los productos que coinciden con los criterios.<br>3. El sistema muestra los productos encontrados.<br>4. El sistema muestra el precio de cada producto. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-02 — Consultar ofertas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar ofertas (UC-02) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite consultar las ofertas existentes en el sistema. |
| **Actores:** | Usuario. |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario solicita consultar las ofertas.<br>2. El sistema obtiene las ofertas existentes.<br>3. El sistema muestra las ofertas al usuario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-03 — Agregar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Agregar productos (UC-03) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite al comprador agregar productos al carrito. |
| **Actores:** | Comprador. |
| **Precondiciones:** | El producto debe estar disponible. |
| **Flujo normal:** | 1. El comprador selecciona un producto.<br>2. El comprador indica la cantidad deseada.<br>3. El sistema identifica el producto seleccionado.<br>4. El sistema reserva la cantidad seleccionada.<br>5. El sistema reduce la cantidad disponible del producto.<br>6. Si la cantidad disponible llega a cero, el sistema marca el producto como BLOQUEADO.<br>7. El sistema agrega el producto al carrito.<br>8. El sistema confirma que el producto ha sido agregado. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El producto queda agregado al carrito y se reduce su cantidad disponible. Si no quedan unidades disponibles, el producto queda en estado BLOQUEADO. |

### UC-04 — Marcar productos como bloqueados

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Marcar productos como bloqueados (UC-04) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite reservar las unidades de un producto y bloquearlo cuando se agotan sus existencias. |
| **Actores:** | Comprador. |
| **Precondiciones:** | El producto debe estar disponible. |
| **Flujo normal:** | 1. El sistema identifica el producto seleccionado.<br>2. El sistema reserva la cantidad seleccionada.<br>3. El sistema reduce la cantidad disponible del producto.<br>4. Si la cantidad disponible llega a cero, el sistema marca el producto como BLOQUEADO. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Se reduce la cantidad disponible del producto. Si no quedan unidades disponibles, el producto queda en estado BLOQUEADO. |

### UC-05 — Consultar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar productos (UC-05) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite al comprador consultar los productos del sistema y conocer su disponibilidad. |
| **Actores:** | Comprador. |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El comprador solicita consultar los productos.<br>2. El sistema obtiene los productos existentes.<br>3. El sistema consulta el estado de cada producto.<br>4. El sistema consulta la cantidad disponible de cada producto.<br>5. El sistema determina que un producto está disponible si se encuentra ACTIVO y su cantidad disponible es mayor que cero.<br>6. El sistema muestra el resultado al comprador.<br>7. El sistema muestra la información de los productos. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-06 — Verificar disponibilidad

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Verificar disponibilidad (UC-06) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite comprobar si un producto está disponible para su compra. |
| **Actores:** | Comprador. |
| **Precondiciones:** | El producto debe existir. |
| **Flujo normal:** | 1. El sistema consulta el estado de cada producto.<br>2. El sistema consulta la cantidad disponible de cada producto.<br>3. El sistema determina que un producto está disponible si se encuentra ACTIVO y su cantidad disponible es mayor que cero.<br>4. El sistema muestra el resultado al comprador. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-07 — Realizar compraventa

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Realizar compraventa (UC-07) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite realizar una compraventa entre un comprador y un vendedor. |
| **Actores:** | Comprador y Vendedor. |
| **Precondiciones:** | El comprador debe haber seleccionado al menos un producto. |
| **Flujo normal:** | 1. El comprador solicita realizar la compraventa.<br>2. El sistema muestra los productos incluidos en la operación.<br>3. El sistema presenta el precio de cada producto.<br>4. El comprador y el vendedor acuerdan el precio definitivo.<br>5. El sistema conserva el precio acordado para la compraventa.<br>6. El sistema calcula el importe total.<br>7. El sistema registra la compraventa y sus productos.<br>8. El sistema confirma la realización de la compraventa. |
| **Flujo alternativo:** | 4.A. Durante la realización de la compraventa se solicita consultar el histórico de ventas.<br>4.A.1. El sistema obtiene las compraventas anteriores.<br>4.A.2. El sistema muestra la información de las ventas anteriores.<br>4.A.3. La compraventa continúa en el paso 4. |
| **Poscondiciones:** | La compraventa, sus productos y los precios definitivos quedan registrados en el sistema. |

### UC-08 — Acordar precio

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Acordar precio (UC-08) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite establecer el precio definitivo de los productos de una compraventa. |
| **Actores:** | Comprador y Vendedor. |
| **Precondiciones:** | Debe estar realizándose una compraventa. |
| **Flujo normal:** | 1. El sistema presenta el precio de cada producto.<br>2. El comprador y el vendedor acuerdan el precio definitivo.<br>3. El sistema conserva el precio acordado para la compraventa. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El precio definitivo queda establecido para la compraventa. |

### UC-09 — Consultar histórico de ventas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar histórico de ventas (UC-09) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite consultar las compraventas realizadas anteriormente. |
| **Actores:** | Comprador y Vendedor. |
| **Precondiciones:** | Debe estar realizándose una compraventa. |
| **Flujo normal:** | 1. El actor solicita consultar el histórico de ventas.<br>2. El sistema obtiene las compraventas anteriores.<br>3. El sistema muestra la información de las ventas anteriores. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-10 — Avisar de nuevos productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar de nuevos productos (UC-10) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite al proveedor avisar de la existencia de nuevos productos. |
| **Actores:** | Proveedor. |
| **Precondiciones:** | El producto debe existir en el sistema. |
| **Flujo normal:** | 1. El proveedor selecciona el nuevo producto.<br>2. El proveedor introduce la información del aviso.<br>3. El sistema identifica al destinatario.<br>4. El sistema genera el título y el mensaje.<br>5. El sistema relaciona la notificación con el producto correspondiente.<br>6. El sistema registra la notificación como no leída.<br>7. El sistema pone la notificación a disposición del destinatario.<br>8. El sistema confirma la realización del aviso. |
| **Flujo alternativo:** | 2.A. El nuevo producto dispone de una oferta.<br>2.A.1. El proveedor introduce el precio y las fechas de la oferta.<br>2.A.2. El sistema asocia la oferta al producto.<br>2.A.3. El sistema registra la oferta.<br>2.A.4. El sistema confirma que la oferta ha sido incorporada.<br>2.A.5. El proceso continúa en el paso 3. |
| **Poscondiciones:** | La notificación queda registrada. Si se incorpora una oferta, la oferta también queda registrada. |

### UC-11 — Incorporar oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Incorporar oferta (UC-11) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite incorporar una oferta asociada a un nuevo producto. |
| **Actores:** | Proveedor. |
| **Precondiciones:** | El producto debe existir en el sistema. |
| **Flujo normal:** | 1. El proveedor introduce el precio y las fechas de la oferta.<br>2. El sistema asocia la oferta al producto.<br>3. El sistema registra la oferta.<br>4. El sistema confirma que la oferta ha sido incorporada. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La oferta queda registrada y asociada al producto. |

### UC-12 — Avisar

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar (UC-12) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Recoge el comportamiento común de los avisos realizados por el proveedor. |
| **Actores:** | Proveedor. |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El proveedor introduce la información del aviso.<br>2. El sistema identifica el producto o la oferta relacionados.<br>3. El sistema identifica al destinatario.<br>4. El sistema genera el título y el mensaje.<br>5. El sistema relaciona la notificación con el producto o la oferta correspondiente.<br>6. El sistema registra la notificación como no leída.<br>7. El sistema pone la notificación a disposición del destinatario.<br>8. El sistema confirma la realización del aviso. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La notificación del aviso queda registrada en el sistema. |

### UC-13 — Enviar notificación

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Enviar notificación (UC-13) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite enviar una notificación a un usuario del sistema. |
| **Actores:** | Proveedor. |
| **Precondiciones:** | Debe existir un destinatario para la notificación. |
| **Flujo normal:** | 1. El sistema identifica al destinatario.<br>2. El sistema genera el título y el mensaje.<br>3. El sistema relaciona la notificación con el producto o la oferta correspondiente.<br>4. El sistema registra la notificación como no leída.<br>5. El sistema pone la notificación a disposición del destinatario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La notificación queda registrada como no leída. |

### UC-14 — Avisar del fin de una oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar del fin de una oferta (UC-14) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite al proveedor avisar de que una oferta ha finalizado. |
| **Actores:** | Proveedor. |
| **Precondiciones:** | La oferta debe existir. |
| **Flujo normal:** | 1. El proveedor selecciona la oferta finalizada.<br>2. El sistema identifica la oferta.<br>3. El sistema cambia su estado a ELIMINADA.<br>4. El sistema confirma la eliminación de la oferta.<br>5. El proveedor introduce la información del aviso.<br>6. El sistema identifica al destinatario.<br>7. El sistema genera el título y el mensaje.<br>8. El sistema relaciona la notificación con la oferta correspondiente.<br>9. El sistema registra la notificación como no leída.<br>10. El sistema pone la notificación a disposición del destinatario.<br>11. El sistema confirma la realización del aviso. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La oferta queda registrada con estado ELIMINADA y la notificación queda registrada como no leída. |

### UC-15 — Eliminar oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Eliminar oferta (UC-15) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite eliminar una oferta que ha llegado a su fin. |
| **Actores:** | Proveedor. |
| **Precondiciones:** | La oferta debe existir. |
| **Flujo normal:** | 1. El sistema identifica la oferta.<br>2. El sistema cambia su estado a ELIMINADA.<br>3. El sistema confirma la eliminación de la oferta. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La oferta queda registrada con estado ELIMINADA. |

### UC-16 — Eliminar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Eliminar productos (UC-16) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite al administrador eliminar productos del sistema. |
| **Actores:** | Administrador. |
| **Precondiciones:** | El producto debe existir. |
| **Flujo normal:** | 1. El administrador selecciona el producto.<br>2. El sistema muestra la información del producto.<br>3. El administrador confirma la eliminación.<br>4. El sistema cambia el estado del producto a ELIMINADO.<br>5. El sistema confirma la eliminación. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El producto queda registrado con estado ELIMINADO. |

### UC-17 — Buscar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Buscar productos (UC-17) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** | Permite buscar productos en el sistema. |
| **Actores:** | Usuario. |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario introduce los criterios de búsqueda.<br>2. El sistema busca los productos que coinciden con los criterios.<br>3. El sistema muestra los productos encontrados. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

## Base de datos

<img width="1669" height="1368" alt="image" src="https://github.com/user-attachments/assets/c5d40232-3fda-4600-817f-93cbe310622b" />

## Tablas de Requisitos de información

### INF-001 — USUARIO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-001 |
| **Nombre** | USUARIO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-01 Consultar precios.<br>UC-02 Consultar ofertas.<br>UC-03 Agregar productos.<br>UC-07 Realizar compraventa.<br>UC-10 Avisar de nuevos productos.<br>UC-14 Avisar del fin de una oferta.<br>UC-16 Eliminar productos. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los usuarios del sistema de compras. |
| **Datos específicos** | - Identificador del usuario<br>- Nombre<br>- Correo electrónico<br>- Contraseña<br>- Fecha de registro<br>- Estado de actividad |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Un usuario puede tener asignados uno o varios roles. |

### INF-002 — ROL

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-002 |
| **Nombre** | ROL |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | ACT-002 Comprador.<br>ACT-003 Vendedor.<br>ACT-004 Proveedor.<br>ACT-005 Administrador. |
| **Descripción** | El sistema deberá almacenar los diferentes roles que pueden asignarse a los usuarios. |
| **Datos específicos** | - Identificador del rol<br>- Nombre |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los roles del sistema son Comprador, Vendedor, Proveedor y Administrador. |

### INF-003 — USUARIO_ROL

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-003 |
| **Nombre** | USUARIO_ROL |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | ACT-002 Comprador.<br>ACT-003 Vendedor.<br>ACT-004 Proveedor.<br>ACT-005 Administrador. |
| **Descripción** | El sistema deberá almacenar la relación entre los usuarios y los roles que tienen asignados. |
| **Datos específicos** | - Identificador del usuario<br>- Identificador del rol |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Un usuario puede tener varios roles y un mismo rol puede estar asignado a varios usuarios. |

### INF-004 — PRODUCTO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-004 |
| **Nombre** | PRODUCTO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-01 Consultar precios.<br>UC-03 Agregar productos.<br>UC-04 Marcar productos como bloqueados.<br>UC-05 Consultar productos.<br>UC-06 Verificar disponibilidad.<br>UC-10 Avisar de nuevos productos.<br>UC-16 Eliminar productos.<br>UC-17 Buscar productos. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los productos ofrecidos por los vendedores. |
| **Datos específicos** | - Identificador del producto<br>- Vendedor<br>- Nombre<br>- Descripción<br>- Precio base<br>- Cantidad disponible<br>- Estado<br>- Fecha de alta |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los estados posibles son ACTIVO, BLOQUEADO y ELIMINADO. Un producto puede comprarse cuando está ACTIVO y su cantidad disponible es mayor que cero. Cuando su cantidad disponible llega a cero, el producto queda BLOQUEADO por estar agotado. |

### INF-005 — OFERTA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-005 |
| **Nombre** | OFERTA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-02 Consultar ofertas.<br>UC-10 Avisar de nuevos productos.<br>UC-11 Incorporar oferta.<br>UC-14 Avisar del fin de una oferta.<br>UC-15 Eliminar oferta. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las ofertas asociadas a los productos. |
| **Datos específicos** | - Identificador de la oferta<br>- Producto<br>- Publicador<br>- Precio de la oferta<br>- Fecha de inicio<br>- Fecha de fin<br>- Estado |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Los estados posibles son PENDIENTE, ACTIVA, FINALIZADA, CANCELADA y ELIMINADA. Una oferta es opcional y temporal. |

### INF-006 — CARRITO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-006 |
| **Nombre** | CARRITO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-03 Agregar productos.<br>UC-04 Marcar productos como bloqueados.<br>UC-07 Realizar compraventa. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los carritos de los compradores. |
| **Datos específicos** | - Identificador del carrito<br>- Comprador<br>- Fecha de creación<br>- Estado |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los estados posibles son ACTIVO, CONFIRMADO y CANCELADO. |

### INF-007 — LINEA_CARRITO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-007 |
| **Nombre** | LINEA_CARRITO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-03 Agregar productos.<br>UC-04 Marcar productos como bloqueados.<br>UC-06 Verificar disponibilidad.<br>UC-07 Realizar compraventa. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los productos agregados a cada carrito. |
| **Datos específicos** | - Identificador de la línea<br>- Carrito<br>- Producto<br>- Oferta<br>- Cantidad<br>- Fecha de agregación |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | La oferta es opcional. Al agregar un producto al carrito se reservan las unidades correspondientes y se reduce su cantidad disponible. Si la cantidad disponible llega a cero, el producto queda BLOQUEADO. |

### INF-008 — COMPRAVENTA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-008 |
| **Nombre** | COMPRAVENTA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-07 Realizar compraventa.<br>UC-08 Acordar precio.<br>UC-09 Consultar histórico de ventas. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las operaciones de compraventa realizadas entre compradores y vendedores. |
| **Datos específicos** | - Identificador de la compraventa<br>- Comprador<br>- Vendedor<br>- Fecha<br>- Estado<br>- Importe total |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los estados posibles son PENDIENTE, ACEPTADA, RECHAZADA, CANCELADA y COMPLETADA. El comprador y el vendedor deben ser usuarios diferentes. |

### INF-009 — DETALLE_COMPRAVENTA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-009 |
| **Nombre** | DETALLE_COMPRAVENTA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-07 Realizar compraventa.<br>UC-08 Acordar precio.<br>UC-09 Consultar histórico de ventas. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los productos incluidos en cada compraventa. |
| **Datos específicos** | - Identificador del detalle<br>- Compraventa<br>- Producto<br>- Oferta<br>- Cantidad<br>- Precio unitario final |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | La oferta es opcional. El precio unitario final puede ser el precio base, el precio de una oferta u otro precio acordado. No se almacena el proceso de negociación. |

### INF-010 — NOTIFICACION

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-010 |
| **Nombre** | NOTIFICACION |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Emilio Murillo Cortés |
| **Fuentes** | Enunciado del supuesto 2 (Sistema de Compras) |
| **Referencias** | UC-10 Avisar de nuevos productos.<br>UC-12 Avisar.<br>UC-13 Enviar notificación.<br>UC-14 Avisar del fin de una oferta. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las notificaciones enviadas a los usuarios. |
| **Datos específicos** | - Identificador de la notificación<br>- Destinatario<br>- Emisor<br>- Producto<br>- Oferta<br>- Título<br>- Mensaje<br>- Tipo<br>- Fecha de creación<br>- Fecha de lectura<br>- Estado de lectura |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Los tipos posibles son NUEVO_PRODUCTO, NUEVA_OFERTA, FIN_OFERTA, OFERTA_ELIMINADA, COMPRAVENTA y SISTEMA. El emisor, el producto, la oferta y la fecha de lectura pueden ser opcionales. |






## Supuesto 3: Compañía hotelera
En una compañía hotelera, el administrador y el comercial pueden consultar reservas. 
El comercial realiza ofertas y gestiona nuevas reservas. 
El administrador gestiona nuevas peticiones y también realiza ofertas. 
La realización de ofertas por parte del comercial conlleva un recálculo de precios. 
Además, dicha realización de ofertas conlleva opcionalmente el bloqueo temporal de una reserva. 
Los clientes, los administradores y los comerciales pueden consultar disponibilidades y visualizar ofertas. 
La consulta de disponibilidades y la consulta de reservas tienen la funcionalidad común de buscar elementos. 
Por su parte, la consulta de disponibilidades conlleva una funcionalidad que muestra un calendario.



##Supuesto 4: Fotografía Online
En una aplicación de fotografía online, los clientes pueden visualizar las fotos, donde de forma excepcional se puede realizar una denuncia sobre la foto. Al denunciar una foto, se ha de introducir una explicación sobre la denuncia. Los clientes también pueden llevar a cabo consultas sobre las fotos, operación que es un caso particular de visualizar las fotos. Los controladores de fotos pueden indicar que una foto debe ser revisada. Esta funcionalidad es un caso general de la funcionalidad de denunciar foto. Además, los controladores también pueden editar la información de las fotos. En esta aplicación también participan usuarios de tipo vendedor. Los vendedores pueden escribir a los clientes para hacerles ofertas sobre los productos de la aplicación. De forma excepcional, al hacer una oferta pueden reducir el precio de un producto. Los vendedores también pueden buscar detalles en las fotos, operación que es un caso particular de visualizar fotos. Pero esa búsqueda conlleva la verificación de los datos introducidos. Por otro lado, los gestores de la aplicación pueden ver ofertas, bloquear ofertas, emitir facturas y editar facturas. La emisión de facturas requiere la participación de un software de facturación. El administrador de la tienda puede ver ofertas, emitir facturas, editar facturas, bloquear ofertas, crear usuarios y editar usuarios. Esta funcionalidad de ver ofertas también la pueden realizar los clientes. Editar usuarios tiene características en común con editar facturas. Crear usuarios conlleva el envío de un email en el que es necesario el uso de un gestor de correo.


Supuesto 5: Gestión de Incidencias
En un sistema de gestión de incidencias, los técnicos y los operadores pueden dar de alta incidencias, para lo cual, de forma excepcional se enviará un correo (en esta operación participa un sistema de gestión de correo). Los técnicos también atienden llamadas telefónicas y realizan informes sobre las incidencias. Por su parte, los operadores atienden llamadas telefónicas, marcan incidencias como duplicadas y ordenan incidencias. La forma de atender llamadas de los técnicos y los operadores no es exactamente igual, pero tiene similitudes. De forma específica, cuando los técnicos atienden llamadas, comprueban datos de la incidencia en el sistema. Cuando los operadores atienden llamadas, introducen nuevos datos de la incidencia. Los administradores del sistema gestionan categorías de incidencias, consultan incidencias y ordenan incidencias. La ordenación por parte de los administradores conlleva la adición de un comentario. Los técnicos y los operadores también pueden consultar incidencias. La consulta de incidencias por parte técnicos, operadores y administradores puede conllevar, de forma excepcional, la edición de los datos de la incidencia. Los usuarios invitados también pueden consultar incidencias, pero sin la posible edición de los datos. Además, los invitados informan sobre posibles incidencias, se pueden registrar para ver notificaciones y pueden acceder a un listado del histórico de notificaciones. El informe de posibles incidencias conlleva el dar de alta la localización en un mapa, la incorporación de una explicación completa en formato textual y la subida de una foto.



