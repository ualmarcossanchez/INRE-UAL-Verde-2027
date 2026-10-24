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
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-02 — Consultar ofertas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar ofertas (UC-02) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-03 — Agregar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Agregar productos (UC-03) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-04 — Marcar productos como bloqueados

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Marcar productos como bloqueados (UC-04) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-05 — Consultar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar productos (UC-05) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-06 — Verificar disponibilidad

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Verificar disponibilidad (UC-06) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-07 — Realizar compraventa

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Realizar compraventa (UC-07) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-08 — Acordar precio

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Acordar precio (UC-08) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-09 — Consultar histórico de ventas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar histórico de ventas (UC-09) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-10 — Avisar de nuevos productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar de nuevos productos (UC-10) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-11 — Incorporar oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Incorporar oferta (UC-11) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-12 — Avisar

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar (UC-12) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-13 — Enviar notificación

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Enviar notificación (UC-13) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-14 — Avisar del fin de una oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Avisar del fin de una oferta (UC-14) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-15 — Eliminar oferta

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Eliminar oferta (UC-15) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-16 — Eliminar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Eliminar productos (UC-16) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-17 — Buscar productos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Buscar productos (UC-17) |
| **Autor:** | Emilio Murillo Cortés |
| **Fecha:** | 24/10/2026 |
| **Descripción:** |  |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** |  |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

## Base de datos

<img width="1617" height="1409" alt="image" src="https://github.com/user-attachments/assets/1f4dbb02-2712-4ff9-95df-41d7bb98a5f1" />
