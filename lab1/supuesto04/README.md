# Supuesto 4: Fotografía Online

## Enunciado

En una aplicación de fotografía online, los clientes pueden visualizar las fotos, donde de forma excepcional se puede realizar una denuncia sobre la foto. Al denunciar una foto, se ha de introducir una explicación sobre la denuncia. Los clientes también pueden llevar a cabo consultas sobre las fotos, operación que es un caso particular de visualizar las fotos. Los controladores de fotos pueden indicar que una foto debe ser revisada. Esta funcionalidad es un caso general de la funcionalidad de denunciar foto. Además, los controladores también pueden editar la información de las fotos. En esta aplicación también participan usuarios de tipo vendedor. Los vendedores pueden escribir a los clientes para hacerles ofertas sobre los productos de la aplicación. De forma excepcional, al hacer una oferta pueden reducir el precio de un producto. Los vendedores también pueden buscar detalles en las fotos, operación que es un caso particular de visualizar fotos. Pero esa búsqueda conlleva la verificación de los datos introducidos. Por otro lado, los gestores de la aplicación pueden ver ofertas, bloquear ofertas, emitir facturas y editar facturas. La emisión de facturas requiere la participación de un software de facturación. El administrador de la tienda puede ver ofertas, emitir facturas, editar facturas, bloquear ofertas, crear usuarios y editar usuarios. Esta funcionalidad de ver ofertas también la pueden realizar los clientes. Editar usuarios tiene características en común con editar facturas. Crear usuarios conlleva el envío de un email en el que es necesario el uso de un gestor de correo.

## Diagrama de clases

![Diagrama de clases del supuesto 4](DB_supuesto04.png)

## Descripción de los actores

| **Actor** | **Gestor de la aplicación (ACT 001)** |
|---|---|
| **Desc** | Es el usuario encargado de gestionar las ofertas y las facturas de la aplicación. |
| **Caract** | Puede ver ofertas, bloquear ofertas, emitir facturas y editar facturas. Comparte estas funciones con el administrador, que hereda de él. |
| **Relaciones** | Relación de herencia del Administrador al Gestor de la aplicación. |
| **Referencias** | El gestor puede ver ofertas (UC-07), bloquear ofertas (UC-09), emitir facturas (UC-03) y editar facturas (UC-04). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Administrador (ACT 002)** |
|---|---|
| **Desc** | Es el administrador de la tienda, que gestiona las ofertas, las facturas y los usuarios de la aplicación. |
| **Caract** | Hereda todas las funciones del gestor de la aplicación y añade la gestión de usuarios: crear usuarios y editar usuarios. |
| **Relaciones** | Relación de herencia del Administrador al Gestor de la aplicación (ACT 001). |
| **Referencias** | El administrador puede crear usuarios (UC-05) y editar usuarios (UC-02). Además, por herencia, puede ver ofertas (UC-07), bloquear ofertas (UC-09), emitir facturas (UC-03) y editar facturas (UC-04). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Software de facturación (ACT 003)** |
|---|---|
| **Desc** | Es el sistema externo que genera las facturas a partir de los datos que le envía la aplicación. |
| **Caract** | Es un actor secundario: no inicia ningún caso de uso, sino que participa en la emisión de facturas. |
| **Relaciones** | No tiene relaciones de herencia. Se asocia al caso de uso Emitir facturas. |
| **Referencias** | El software de facturación participa en la emisión de facturas (UC-03). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Gestor de correo (ACT 004)** |
|---|---|
| **Desc** | Es el sistema externo que se encarga de entregar los emails que envía la aplicación. |
| **Caract** | Es un actor secundario: no inicia ningún caso de uso, sino que participa en el envío de emails. |
| **Relaciones** | No tiene relaciones de herencia. Se asocia al caso de uso Enviar email. |
| **Referencias** | El gestor de correo participa en el envío de emails (UC-06), que se ejecuta al crear usuarios (UC-05). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Cliente (ACT 005)** |
|---|---|
| **Desc** | Es el usuario que accede a la aplicación para ver las fotos y recibir ofertas de los vendedores. |
| **Caract** | Puede visualizar fotos y consultarlas. De forma excepcional, mientras visualiza una foto puede denunciarla, explicando el motivo. También puede ver las ofertas que le hacen. |
| **Relaciones** | No tiene relaciones de herencia. Los vendedores le escriben para hacerle ofertas. |
| **Referencias** | El cliente puede visualizar fotos (UC-11), consultar fotos (UC-10), denunciar fotos (UC-17), explicar la denuncia (UC-19) y ver ofertas (UC-08). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Vendedor (ACT 006)** |
|---|---|
| **Desc** | Es el usuario de tipo vendedor, que escribe a los clientes para hacerles ofertas sobre los productos de la aplicación. |
| **Caract** | Puede hacer ofertas y, de forma excepcional, reducir el precio de un producto al hacerlas. También puede buscar detalles en las fotos, lo que conlleva verificar los datos introducidos. |
| **Relaciones** | No tiene relaciones de herencia. Hace ofertas a los clientes. |
| **Referencias** | El vendedor puede hacer ofertas (UC-14), reducir precios (UC-15), buscar detalles (UC-12) y verificar datos (UC-13). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Controlador de fotos (ACT 007)** |
|---|---|
| **Desc** | Es el usuario encargado de controlar las fotos de la aplicación. |
| **Caract** | Puede indicar que una foto debe ser revisada, función de la que denunciar foto es un caso particular, y editar la información de las fotos. |
| **Relaciones** | No tiene relaciones de herencia. |
| **Referencias** | El controlador puede indicar que una foto debe ser revisada (UC-16) y editar la información de las fotos (UC-18). Indicar foto a revisar es el caso general de denunciar foto (UC-17). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 19/10/2026  \|  **Versión:** 1.0 |

## Descripción de los casos de uso

| **Nombre:** | **Editar datos (UC-01)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite modificar los datos almacenados en el sistema. Es un caso de uso general que recoge las características comunes de editar facturas y editar usuarios, que lo especializan. |
| **Actores:** | Gestor de la aplicación / Administrador (a través de sus casos de uso particulares) |
| **Precondiciones:** | El actor debe estar autenticado en el sistema y tener permisos para editar el dato. El dato a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El actor selecciona el elemento que desea editar.<br>2.- El sistema muestra los datos actuales del elemento en un formulario editable.<br>3.- El actor modifica los datos y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la edición se ha realizado. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la edición, de modo que el sistema descarta los cambios y no modifica el elemento.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos del elemento han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-02 (Editar usuarios) y UC-04 (Editar facturas), que lo especializan. |

| **Nombre:** | **Editar usuarios (UC-02)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al administrador de la tienda modificar los datos de un usuario ya registrado en la aplicación. Es un caso particular de editar datos. |
| **Actores:** | Administrador de la tienda |
| **Precondiciones:** | El administrador debe estar autenticado en el sistema. El usuario a editar debe estar registrado en la aplicación. |
| **Flujo Normal:** | 1.- El administrador accede a la gestión de usuarios y selecciona el usuario que desea editar.<br>2.- El sistema muestra los datos actuales del usuario en un formulario editable.<br>3.- El administrador modifica los datos del usuario y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que el usuario ha sido modificado. |
| **Flujo Alternativo:** | 3.A.- El administrador cancela la edición, de modo que el sistema descarta los cambios y no modifica al usuario.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al administrador de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos del usuario han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-01 (Editar datos), del que es un caso particular. |

| **Nombre:** | **Emitir facturas (UC-03)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite emitir una factura desde la aplicación. La emisión requiere la participación de un software de facturación, que genera la factura a partir de los datos facilitados por el sistema. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda. Software de facturación (actor secundario) |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. Debe existir una operación sobre la que emitir la factura. El software de facturación debe estar disponible. |
| **Flujo Normal:** | 1.- El actor accede a la gestión de facturas y selecciona la opción de emitir una nueva factura.<br>2.- El sistema muestra un formulario con los datos necesarios para la factura.<br>3.- El actor completa los datos y confirma la emisión.<br>4.- El sistema comprueba la validez de los datos y los envía al software de facturación.<br>5.- El software de facturación genera la factura y la devuelve al sistema.<br>6.- El sistema almacena la factura y muestra un mensaje confirmando que ha sido emitida. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la emisión, de modo que el sistema descarta los datos y no emite la factura.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija.<br>5.A.- El software de facturación no puede generar la factura, por lo que el sistema avisa al actor del error y no almacena ninguna factura. |
| **Poscondiciones:** | La factura ha sido generada por el software de facturación y almacenada en el sistema. |
| **Referencias:** | Ninguna. |

| **Nombre:** | **Editar facturas (UC-04)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite modificar los datos de una factura ya emitida. Es un caso particular de editar datos. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. La factura a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El actor accede a la gestión de facturas y selecciona la factura que desea editar.<br>2.- El sistema muestra los datos actuales de la factura en un formulario editable.<br>3.- El actor modifica los datos de la factura y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la factura ha sido modificada. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la edición, de modo que el sistema descarta los cambios y no modifica la factura.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al actor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | Los datos de la factura han sido modificados y almacenados en el sistema. |
| **Referencias:** | UC-01 (Editar datos), del que es un caso particular. |

| **Nombre:** | **Crear usuarios (UC-05)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al administrador de la tienda dar de alta un nuevo usuario en la aplicación. La creación conlleva el envío de un email al nuevo usuario. |
| **Actores:** | Administrador de la tienda |
| **Precondiciones:** | El administrador debe estar autenticado en el sistema. |
| **Flujo Normal:** | 1.- El administrador accede a la gestión de usuarios y selecciona la opción de crear un nuevo usuario.<br>2.- El sistema muestra un formulario para introducir los datos del nuevo usuario.<br>3.- El administrador introduce los datos del usuario y confirma la creación.<br>4.- El sistema comprueba la validez de los datos y almacena al nuevo usuario.<br>5.- El sistema ejecuta el caso de uso Enviar email (UC-06) para notificar el alta al nuevo usuario.<br>6.- El sistema muestra un mensaje confirmando que el usuario ha sido creado. |
| **Flujo Alternativo:** | 3.A.- El administrador cancela la creación, de modo que el sistema descarta los datos y no crea al usuario.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos o el usuario ya existe, avisa al administrador de ello permitiéndole que los corrija.<br>5.A.- El email no ha podido enviarse, por lo que el sistema avisa al administrador de ello. El usuario queda creado igualmente. |
| **Poscondiciones:** | El nuevo usuario ha sido almacenado en el sistema y se le ha enviado un email. |
| **Referencias:** | UC-06 (Enviar email), que se incluye en este caso de uso. |

| **Nombre:** | **Enviar email (UC-06)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite enviar un email al usuario recién creado. Para ello es necesario el uso de un gestor de correo. Este caso de uso se ejecuta como parte de la creación de usuarios. |
| **Actores:** | Gestor de correo (actor secundario) |
| **Precondiciones:** | El usuario debe haber sido creado y almacenado en el sistema, con una dirección de correo asociada. El gestor de correo debe estar disponible. |
| **Flujo Normal:** | 1.- El sistema genera el email dirigido al nuevo usuario.<br>2.- El sistema envía el email al gestor de correo.<br>3.- El gestor de correo entrega el email a la dirección del usuario.<br>4.- El gestor de correo confirma al sistema que el email ha sido enviado. |
| **Flujo Alternativo:** | 3.A.- El gestor de correo no puede entregar el email, ya sea porque no está disponible o porque la dirección no es válida. El gestor de correo informa del error al sistema y éste avisa de que el email no ha sido enviado. |
| **Poscondiciones:** | El email ha sido enviado al usuario a través del gestor de correo. |
| **Referencias:** | UC-05 (Crear usuarios), que lo incluye. |

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

| **Nombre:** | **Bloquear ofertas (UC-09)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite bloquear una oferta existente para que deje de estar activa en la aplicación. |
| **Actores:** | Gestor de la aplicación / Administrador de la tienda |
| **Precondiciones:** | El actor debe estar autenticado en el sistema. La oferta a bloquear debe existir en el sistema y no estar ya bloqueada. |
| **Flujo Normal:** | 1.- El actor accede a la sección de ofertas y selecciona la oferta que desea bloquear.<br>2.- El sistema muestra el detalle de la oferta y la opción de bloquearla.<br>3.- El actor selecciona bloquear la oferta y confirma la acción.<br>4.- El sistema marca la oferta como bloqueada.<br>5.- El sistema muestra un mensaje confirmando que la oferta ha sido bloqueada. |
| **Flujo Alternativo:** | 3.A.- El actor cancela la acción, de modo que el sistema no bloquea la oferta.<br>4.A.- La oferta ya había sido bloqueada por otro actor, por lo que el sistema avisa de ello y no realiza ningún cambio. |
| **Poscondiciones:** | La oferta ha quedado marcada como bloqueada en el sistema. |
| **Referencias:** | Ninguna. |

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

| **Nombre:** | **Hacer oferta (UC-14)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al vendedor escribir a un cliente para hacerle una oferta sobre un producto de la aplicación. De forma excepcional, al hacer la oferta se puede reducir el precio del producto (punto de extensión: Reducir precio). |
| **Actores:** | Vendedor |
| **Precondiciones:** | El vendedor debe estar autenticado en el sistema. Deben existir el cliente destinatario y el producto sobre el que se hace la oferta. |
| **Flujo Normal:** | 1.- El vendedor selecciona al cliente y el producto sobre el que quiere hacer la oferta.<br>2.- El sistema muestra un formulario para introducir los datos de la oferta.<br>3.- El vendedor introduce los datos de la oferta y confirma.<br>4.- El sistema comprueba la validez de los datos, registra la oferta y se la envía al cliente.<br>5.- El sistema muestra un mensaje confirmando que la oferta ha sido realizada. |
| **Flujo Alternativo:** | 3.A.- El vendedor decide reducir el precio del producto. Se ejecuta el caso de uso Reducir precio (UC-15) a través del punto de extensión.<br>3.B.- El vendedor cancela la oferta, de modo que el sistema descarta los datos y no registra ninguna oferta.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al vendedor de ello permitiéndole que los corrija. |
| **Poscondiciones:** | La oferta ha sido registrada en el sistema y enviada al cliente. |
| **Referencias:** | UC-15 (Reducir precio), que lo extiende. UC-08 (Ver ofertas (cliente)), a través del cual el cliente consulta la oferta. |

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

| **Nombre:** | **Indicar foto a revisar (UC-16)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al controlador de fotos indicar que una foto debe ser revisada. Es un caso general de denunciar foto. |
| **Actores:** | Controlador de fotos |
| **Precondiciones:** | El controlador de fotos debe estar autenticado en el sistema. La foto debe existir en el sistema. |
| **Flujo Normal:** | 1.- El controlador accede a las fotos y selecciona la foto que debe revisarse.<br>2.- El sistema muestra la foto seleccionada.<br>3.- El controlador indica que la foto debe ser revisada y confirma la acción.<br>4.- El sistema marca la foto como pendiente de revisión.<br>5.- El sistema muestra un mensaje confirmando que la foto ha sido marcada. |
| **Flujo Alternativo:** | 3.A.- El controlador cancela la acción, de modo que el sistema no marca la foto.<br>4.A.- La foto ya estaba marcada como pendiente de revisión, por lo que el sistema avisa de ello y no realiza ningún cambio. |
| **Poscondiciones:** | La foto ha quedado marcada como pendiente de revisión en el sistema. |
| **Referencias:** | UC-17 (Denunciar foto), que es un caso particular de este caso de uso. |

| **Nombre:** | **Denunciar foto (UC-17)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente realizar, de forma excepcional, una denuncia sobre una foto mientras la visualiza. Al denunciar una foto se ha de introducir una explicación sobre la denuncia. Es un caso particular de indicar foto a revisar. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe estar autenticado en el sistema y estar visualizando la foto que quiere denunciar (UC-11 en ejecución). |
| **Flujo Normal:** | 1.- El cliente selecciona la opción de denunciar la foto que está visualizando.<br>2.- El sistema ejecuta el caso de uso Explicar denuncia (UC-19) para que el cliente introduzca la explicación.<br>3.- El cliente confirma la denuncia.<br>4.- El sistema registra la denuncia y marca la foto como pendiente de revisión.<br>5.- El sistema muestra un mensaje confirmando que la denuncia ha sido realizada. |
| **Flujo Alternativo:** | 3.A.- El cliente cancela la denuncia, de modo que el sistema descarta los datos y no registra ninguna denuncia. |
| **Poscondiciones:** | La denuncia ha sido registrada junto con su explicación y la foto ha quedado marcada como pendiente de revisión. |
| **Referencias:** | UC-11 (Visualizar fotos), al que extiende. UC-19 (Explicar denuncia), que se incluye en este caso de uso. UC-16 (Indicar foto a revisar), del que es un caso particular. |

| **Nombre:** | **Editar info fotos (UC-18)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al controlador de fotos editar la información asociada a las fotos de la aplicación. |
| **Actores:** | Controlador de fotos |
| **Precondiciones:** | El controlador de fotos debe estar autenticado en el sistema. La foto a editar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El controlador accede a las fotos y selecciona la foto cuya información desea editar.<br>2.- El sistema muestra la información actual de la foto en un formulario editable.<br>3.- El controlador modifica la información y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos y los almacena.<br>5.- El sistema muestra un mensaje confirmando que la información de la foto ha sido modificada. |
| **Flujo Alternativo:** | 3.A.- El controlador cancela la edición, de modo que el sistema descarta los cambios y no modifica la foto.<br>4.A.- El sistema comprueba la validez de los datos; si no son correctos, avisa al controlador de ello permitiéndole que los corrija. |
| **Poscondiciones:** | La información de la foto ha sido modificada y almacenada en el sistema. |
| **Referencias:** | Ninguna. |

| **Nombre:** | **Explicar denuncia (UC-19)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al cliente introducir la explicación que acompaña a la denuncia de una foto. Es obligatorio al denunciar una foto y se ejecuta como parte de ese caso de uso. |
| **Actores:** | Cliente |
| **Precondiciones:** | El cliente debe haber seleccionado la opción de denunciar una foto (UC-17 en ejecución). |
| **Flujo Normal:** | 1.- El sistema muestra un campo de texto para introducir la explicación de la denuncia.<br>2.- El cliente escribe la explicación y la confirma.<br>3.- El sistema comprueba que la explicación no está vacía y la asocia a la denuncia. |
| **Flujo Alternativo:** | 3.A.- La explicación está vacía, por lo que el sistema avisa al cliente de que debe introducirla y le permite que la complete. |
| **Poscondiciones:** | La explicación ha quedado asociada a la denuncia de la foto. |
| **Referencias:** | UC-17 (Denunciar foto), que lo incluye. |

## Requisitos de información

| **INF-01** | **Usuario** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Crear usuarios (UC-05)<br>• Editar usuarios (UC-02) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los usuarios de la aplicación. En concreto: |
| **Datos específicos:** | • Identificador de usuario<br>• Nombre<br>• Correo electrónico<br>• Contraseña (almacenada de forma cifrada)<br>• Fecha de registro<br>• Si el usuario está activo<br>• Roles asignados (cliente, vendedor, controlador de fotos, gestor de la aplicación o administrador) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | El administrador tiene los roles del gestor más la gestión de usuarios. Todos los casos de uso requieren un usuario autenticado. |

| **INF-02** | **Foto** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Visualizar fotos (UC-11)<br>• Consultar foto (UC-10)<br>• Buscar detalles (UC-12)<br>• Indicar foto a revisar (UC-16)<br>• Denunciar foto (UC-17)<br>• Editar info fotos (UC-18) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las fotos de la aplicación. En concreto: |
| **Datos específicos:** | • Identificador de la foto<br>• Título<br>• Descripción<br>• Fecha de subida<br>• Estado (visible o pendiente de revisión) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Las consultas de los clientes y la búsqueda de detalles de los vendedores se hacen sobre estos datos y no se almacenan. |

| **INF-03** | **Denuncia** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Denunciar foto (UC-17)<br>• Explicar denuncia (UC-19)<br>• Visualizar fotos (UC-11)<br>• Foto (INF-02)<br>• Usuario (INF-01)<br>• Revisión de foto (INF-04) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las denuncias que los clientes realizan sobre las fotos. En concreto: |
| **Datos específicos:** | • Identificador de la denuncia<br>• Foto denunciada<br>• Cliente que realiza la denuncia<br>• Explicación de la denuncia<br>• Fecha de la denuncia |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | La explicación es obligatoria al denunciar una foto. Cada denuncia genera una revisión de la foto (INF-04). |

| **INF-04** | **Revisión de foto** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Indicar foto a revisar (UC-16)<br>• Denunciar foto (UC-17)<br>• Foto (INF-02)<br>• Denuncia (INF-03)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las revisiones pendientes de las fotos. En concreto: |
| **Datos específicos:** | • Identificador de la revisión<br>• Foto que debe ser revisada<br>• Controlador de fotos que la indica (si la indica un controlador)<br>• Denuncia que la origina (si nace de una denuncia)<br>• Fecha de indicación |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Denunciar una foto es un caso particular de indicar que debe ser revisada, por lo que solo se informa el controlador o la denuncia, según el origen de la revisión. |

| **INF-05** | **Producto** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Hacer oferta (UC-14)<br>• Reducir precio (UC-15) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los productos de la aplicación sobre los que los vendedores hacen ofertas. En concreto: |
| **Datos específicos:** | • Identificador del producto<br>• Nombre<br>• Descripción<br>• Precio |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | El enunciado no detalla los datos de los productos, por lo que se recogen los mínimos necesarios para hacer una oferta y reducir su precio. |

| **INF-06** | **Oferta** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Hacer oferta (UC-14)<br>• Reducir precio (UC-15)<br>• Ver ofertas (UC-07)<br>• Ver ofertas (cliente) (UC-08)<br>• Bloquear ofertas (UC-09)<br>• Producto (INF-05)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las ofertas que los vendedores hacen a los clientes sobre los productos. En concreto: |
| **Datos específicos:** | • Identificador de la oferta<br>• Producto sobre el que se hace la oferta<br>• Vendedor que la hace<br>• Cliente destinatario<br>• Mensaje dirigido al cliente<br>• Precio ofertado (que puede ser un precio reducido)<br>• Fecha de la oferta<br>• Estado (activa o bloqueada)<br>• Gestor o administrador que la bloquea y fecha de bloqueo (solo si está bloqueada) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Ver ofertas lo realizan el gestor, el administrador y, en su caso particular, el cliente, que solo ve las ofertas que se le han hecho. |

| **INF-07** | **Factura** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Emitir facturas (UC-03)<br>• Editar facturas (UC-04)<br>• Editar datos (UC-01)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las facturas emitidas por la aplicación. En concreto: |
| **Datos específicos:** | • Identificador de la factura<br>• Número de factura<br>• Usuario que la emite (gestor o administrador)<br>• Cliente facturado<br>• Fecha de emisión<br>• Importe total<br>• Datos fiscales<br>• Fecha de la última edición (solo si se ha editado) |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | El número de factura lo genera el software de facturación al emitirla. |

| **INF-08** | **Email** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 4 (Fotografía Online) |
| **Referencias:** | • Crear usuarios (UC-05)<br>• Enviar email (UC-06)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los emails que la aplicación envía a los usuarios. En concreto: |
| **Datos específicos:** | • Identificador del email<br>• Usuario destinatario<br>• Asunto<br>• Cuerpo del mensaje<br>• Fecha de envío (solo si se ha enviado)<br>• Si el email ha sido enviado |
| **Importancia:** | Poco importante |
| **Estado:** | Aceptado |
| **Comentarios:** | El envío lo realiza el gestor de correo. Si no puede entregarse, el email queda sin enviar y sin fecha de envío. |
