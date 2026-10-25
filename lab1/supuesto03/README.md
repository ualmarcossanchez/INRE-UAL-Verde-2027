## Supuesto 3: Compañía hotelera

En una compañía hotelera, el administrador y el comercial pueden consultar reservas. El comercial realiza ofertas y gestiona nuevas reservas. El administrador gestiona nuevas peticiones y también realiza ofertas. La realización de ofertas por parte del comercial conlleva un recálculo de precios. Además, dicha realización de ofertas conlleva opcionalmente el bloqueo temporal de una reserva. Los clientes, los administradores y los comerciales pueden consultar disponibilidades y visualizar ofertas. La consulta de disponibilidades y la consulta de reservas tienen la funcionalidad común de buscar elementos. Por su parte, la consulta de disponibilidades conlleva una funcionalidad que muestra un calendario.

<img width="991" height="619" alt="663018700-c817b91d-fb79-4397-a33d-c514794cba77" src="https://github.com/user-attachments/assets/00dcdd42-8471-4e04-9b42-c13f30f74c7a" />

## Descripción de los actores

## Actores del sistema

### Usuario

| **Actor** | **Usuario (ACT 001)** |
|---|---|
| **Desc** | Es el usuario general que accede a las funcionalidades comunes básicas. |
| **Caract** | Comparte funciones con los demás usuarios que heredan de él. |
| **Relaciones** | Relación de herencia de Cliente y Empleado hacia Usuario. |
| **Referencias** | El usuario puede consultar disponibilidades (CU-001), lo que a su vez le muestra el calendario (CU-008) y busca elementos (CU-007). También puede visualizar ofertas (CU-002). |
| **Autor** | Marcos Sánchez García \| **Fecha:** 15/10/2026 \| **Versión:** 1.0 |


### Cliente

| **Actor** | **Cliente (ACT 002)** |
|---|---|
| **Desc** | Es el usuario que se registra como cliente. |
| **Caract** | Tiene todas las funciones que tiene Usuario. |
| **Relaciones** | Relación que indica que hereda de Usuario. |
| **Referencias** | Puede realizar todas las funciones de Usuario: consultar disponibilidades (CU-001) y visualizar ofertas (CU-002). |
| **Autor** | Marcos Sánchez García \| **Fecha:** 15/10/2026 \| **Versión:** 1.0 |


### Empleado

| **Actor** | **Empleado (ACT 003)** |
|---|---|
| **Desc** | Es el empleado común del comercio. |
| **Caract** | Tiene todas las funciones que tiene Usuario más consultar reservas y realizar ofertas. |
| **Relaciones** | Relación que indica que hereda de Usuario, y es el actor base de Comercial y Administrador. |
| **Referencias** | Puede realizar todas las funciones de Usuario más las suyas propias: consultar reservas (CU-003) y realizar ofertas (CU-004). |
| **Autor** | Marcos Sánchez García \| **Fecha:** 15/10/2026 \| **Versión:** 1.0 |


### Administrador

| **Actor** | **Administrador (ACT 004)** |
|---|---|
| **Desc** | Es el empleado encargado de la administración. |
| **Caract** | Es un empleado con capacidad de gestionar nuevas peticiones. |
| **Relaciones** | Relación que indica que hereda de Empleado, que a su vez hereda de Usuario. |
| **Referencias** | Puede realizar todas las funciones de Usuario más las de Empleado más la suya propia: gestionar nuevas peticiones (CU-005). |
| **Autor** | Marcos Sánchez García \| **Fecha:** 15/10/2026 \| **Versión:** 1.0 |


### Comercial

| **Actor** | **Comercial (ACT 005)** |
|---|---|
| **Desc** | Es el empleado encargado de la venta y el comercio. |
| **Caract** | Es un empleado con capacidad de gestionar nuevas reservas. |
| **Relaciones** | Relación que indica que hereda de Empleado, que a su vez hereda de Usuario. |
| **Referencias** | Puede realizar todas las funciones de Usuario más las de Empleado más la suya propia: gestionar nuevas reservas (CU-006). |
| **Autor** | Marcos Sánchez García \| **Fecha:** 15/10/2026 \| **Versión:** 1.0 |


## Descripción de los casos de uso

## Casos de uso

### CU-001 — Consultar disponibilidades

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar disponibilidades (CU-001) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá permitir al usuario consultar las disponibilidades en un calendario mostrado y además incluir un buscador para encontrar cada uno de los elementos disponibles. |
| **Actores:** | Usuario (Empleado / Cliente) |
| **Precondiciones:** | Ninguna. |
| **Flujo normal:** | 1. El usuario accede al sistema para encontrar un elemento disponible.<br>2. El sistema muestra las disponibilidades a través de un calendario y deja acceso a un buscador.<br>3. El usuario introduce un elemento en el buscador.<br>4. El sistema filtra la muestra de disponibilidades hacia el elemento indicado. |
| **Flujo alternativo:** | 4.A. El elemento introducido no está disponible en las fechas indicadas. El sistema devuelve el calendario sin ninguna marca de disponibilidad y la página no muestra resultados. |
| **Poscondiciones:** | Se muestran las disponibilidades actualizadas en pantalla, pero no se actualiza ni se borra ningún dato en el sistema. |
| **Referencias:** | CU-007 (Buscar elementos) y CU-008 (Mostrar calendario), que se incluyen en este caso de uso. |

### CU-002 — Visualizar ofertas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Visualizar ofertas (CU-002) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá permitir al usuario visualizar las ofertas disponibles. |
| **Actores:** | Usuario (Empleado / Cliente) |
| **Precondiciones:** | Ninguna. |
| **Flujo normal:** | 1. El usuario accede al sistema y le da al botón de ver ofertas.<br>2. El sistema muestra las ofertas disponibles. |
| **Flujo alternativo:** | 2.A. No hay ofertas, el sistema devuelve el mensaje de que no hay ofertas disponibles. |
| **Poscondiciones:** | Se muestran las ofertas disponibles en pantalla, pero no se actualiza ni se borra ningún dato en el sistema. |
| **Referencias:** | CU-004 (Realizar ofertas), que genera las ofertas que se visualizan. |

### CU-003 — Consultar reservas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar reservas (CU-003) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá permitir al empleado consultar las reservas de los elementos. |
| **Actores:** | Empleado (Comercial / Administrador) |
| **Precondiciones:** | Ser un usuario logueado con el rol de empleado. |
| **Flujo normal:** | 1. El usuario accede al sistema logueado como empleado y le da a consultar reservas.<br>2. El sistema le muestra una lista con las reservas hechas y un buscador de elementos.<br>3. El usuario introduce un elemento en el buscador.<br>4. El sistema filtra la muestra de si hay reserva o no en el elemento indicado. |
| **Flujo alternativo:** | 4.A. El elemento introducido no está reservado en las fechas indicadas. El sistema devuelve el elemento como disponible. |
| **Poscondiciones:** | Se muestran las reservas actualizadas en pantalla, pero no se actualiza ni se borra ningún dato en el sistema. |
| **Referencias:** | CU-007 (Buscar elementos), que se incluye en este caso de uso. |

### CU-004 — Realizar ofertas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Realizar ofertas (CU-004) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | Permite al empleado crear y publicar una nueva oferta o promoción en el sistema. Este proceso incluye la actualización automática de las tarifas y permite, de forma opcional, bloquear temporalmente una reserva vinculada a dicha oferta. |
| **Actores:** | Empleado (Administrador / Comercial) |
| **Precondiciones:** | El empleado debe estar autenticado en el sistema con los permisos correspondientes. |
| **Flujo normal:** | 1. El empleado accede a la sección de gestión de ofertas y selecciona crear una nueva.<br>2. El sistema muestra un formulario para introducir los datos de la promoción (porcentaje de descuento, fechas de validez, etc.).<br>3. El empleado introduce los datos requeridos y pulsa en calcular.<br>4. El sistema realiza automáticamente el recálculo de precios (CU-009) aplicando el descuento sobre las tarifas base y muestra el resultado.<br>5. El empleado confirma la publicación de la oferta.<br>6. El sistema almacena la oferta y notifica que se ha creado con éxito. |
| **Flujo alternativo:** | 4.A. Bloqueo temporal de reserva (CU-010): antes de confirmar la publicación en el paso 5, el empleado decide que esta oferta va dirigida a una habitación/reserva específica que está tramitando.<br>4.A.1. El empleado selecciona la opción de bloquear disponibilidad.<br>4.A.2. El sistema bloquea temporalmente la reserva vinculada para que ningún otro usuario pueda ocuparla.<br>4.A.3. El flujo retorna al paso 5 del flujo normal. |
| **Poscondiciones:** | La nueva oferta queda registrada en el sistema con los precios actualizados. Si se aplicó el flujo alternativo, la reserva asociada queda bloqueada temporalmente. |
| **Referencias:** | CU-009 (Recálculo de precios), que se incluye en este caso de uso. CU-010 (Bloqueo temporal de reserva), que lo extiende. |

### CU-005 — Gestionar nuevas peticiones

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Gestionar nuevas peticiones (CU-005) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá permitir al administrador gestionar nuevas peticiones. |
| **Actores:** | Administrador |
| **Precondiciones:** | Estar logueado en el sistema como un usuario con el rol de empleado además del rol de administrador. |
| **Flujo normal:** | 1. El usuario accede al sistema como administrador y le da al botón de gestionar nuevas peticiones.<br>2. El sistema muestra un menú donde salen las peticiones.<br>3. El administrador realiza actualizaciones o borra las peticiones.<br>4. El sistema realiza las actualizaciones correspondientes o borra lo que el administrador haya gestionado. |
| **Flujo alternativo:** | 4.A. No hay ninguna petición, el sistema muestra una pantalla vacía. |
| **Poscondiciones:** | Se realizan las actualizaciones y se borran las peticiones al ya haber sido gestionadas. |
| **Referencias:** | Ninguna. |

### CU-006 — Gestionar nuevas reservas

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Gestionar nuevas reservas (CU-006) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá permitir al comercial registrar, tramitar y confirmar las nuevas reservas solicitadas por los clientes. Es un caso de uso exclusivo del departamento comercial. |
| **Actores:** | Comercial |
| **Precondiciones:** | El comercial debe estar autenticado en el sistema. La habitación solicitada debe estar disponible. |
| **Flujo normal:** | 1. El comercial accede al módulo de nuevas reservas.<br>2. Introduce los datos personales del cliente y las fechas de estancia.<br>3. El sistema verifica que haya disponibilidad en esas fechas.<br>4. El sistema calcula el importe total de la reserva.<br>5. El comercial confirma los datos con el cliente y guarda la reserva.<br>6. El sistema registra la reserva y devuelve un localizador. |
| **Flujo alternativo:** | 3.A. No hay habitaciones disponibles para las fechas/tipos indicados. El sistema avisa al comercial y el proceso se detiene o se reinicia buscando otras fechas. |
| **Poscondiciones:** | La reserva queda registrada y confirmada en el sistema, con los datos del cliente, la reserva y la asignación de la habitación. |
| **Referencias:** | CU-003 (Consultar reservas), con el que está relacionado. |

### CU-007 — Buscar elementos

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Buscar elementos (CU-007) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá proporcionar un mecanismo de filtrado (buscador) común que permita al usuario encontrar información específica tanto en las disponibilidades como en el registro de reservas. Es un caso de uso interno reutilizable, no iniciado de forma aislada por un actor. |
| **Actores:** | Usuario / Empleado (a través de Consultar disponibilidades y Consultar reservas) |
| **Precondiciones:** | El usuario debe haber invocado previamente un caso de uso que incluya esta funcionalidad. |
| **Flujo normal:** | 1. El sistema habilita la barra de búsqueda y filtros.<br>2. El usuario introduce los parámetros deseados (por ejemplo, nombre, localizador, fechas).<br>3. El sistema consulta internamente los registros.<br>4. El sistema actualiza la pantalla mostrando solo los elementos coincidentes. |
| **Flujo alternativo:** | 4.A. No hay coincidencias para el criterio introducido. El sistema muestra el mensaje "No se encontraron resultados" y deja la lista en blanco. |
| **Poscondiciones:** | Se filtra la vista actual en la pantalla del usuario. No se alteran datos. |
| **Referencias:** | CU-001 (Consultar disponibilidades) y CU-003 (Consultar reservas), que lo incluyen. |

### CU-008 — Mostrar calendario

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Mostrar calendario (CU-008) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá generar y renderizar una interfaz visual en forma de calendario interactivo para facilitar la lectura de la ocupación hotelera. Se invoca automáticamente cuando un usuario accede a consultar disponibilidades. |
| **Actores:** | Usuario (a través de Consultar disponibilidades) |
| **Precondiciones:** | Ninguna explícita, se hereda del caso base. |
| **Flujo normal:** | 1. El sistema recupera los datos de ocupación y disponibilidad para el periodo actual.<br>2. El sistema mapea estos datos sobre una cuadrícula mensual.<br>3. Se renderiza el calendario aplicando marcas de colores o iconos según el estado (libre, ocupado, bloqueado).<br>4. El sistema presenta el calendario terminado al usuario en pantalla. |
| **Flujo alternativo:** | Ninguno. |
| **Poscondiciones:** | El calendario se muestra en pantalla. No hay actualización de datos. |
| **Referencias:** | CU-001 (Consultar disponibilidades), que lo incluye. |

### CU-009 — Recálculo de precios

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Recálculo de precios (CU-009) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema deberá actualizar matemáticamente el importe final de una estancia o reserva cuando un empleado aplique una nueva oferta o descuento. Se ejecuta de forma automática en el momento en que se asocia una oferta comercial a una tarifa base. |
| **Actores:** | Empleado (a través de Realizar ofertas) |
| **Precondiciones:** | Debe existir un precio base válido y los datos del descuento de la oferta introducida. |
| **Flujo normal:** | 1. El sistema detecta la aplicación de una oferta (porcentaje o importe fijo).<br>2. El sistema toma la tarifa original de la habitación.<br>3. El sistema aplica la operación matemática correspondiente restando el descuento.<br>4. Se retornan los nuevos valores desglosados para ser mostrados o guardados. |
| **Flujo alternativo:** | 3.A. El importe del descuento es superior al precio base. El sistema detiene el cálculo y lanza un error de "Oferta no válida (importe negativo)". |
| **Poscondiciones:** | El importe total de la reserva/estancia queda modificado en memoria. |
| **Referencias:** | CU-004 (Realizar ofertas), que lo incluye. |

### CU-010 — Bloqueo temporal de reserva

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Bloqueo temporal de reserva (CU-010) |
| **Autor:** | Marcos Sánchez García |
| **Fecha:** | 19/10/2026 |
| **Descripción:** | El sistema permitirá bloquear temporalmente una disponibilidad en el calendario para evitar que otros usuarios la reserven mientras un empleado está gestionando y realizando una oferta sobre ella. Es un comportamiento opcional: si el empleado no lo solicita, la oferta se crea sin bloquear recursos. |
| **Actores:** | Empleado (Administrador / Comercial) |
| **Precondiciones:** | El elemento (habitación) sobre el que se realiza la oferta debe estar libre. |
| **Flujo normal:** | 1. El empleado solicita bloquear la disponibilidad de la habitación vinculada a la oferta.<br>2. El sistema solicita el tiempo de validez del bloqueo.<br>3. El empleado confirma los datos.<br>4. El sistema cambia el estado del elemento a "Bloqueado".<br>5. Se inicia un temporizador interno. |
| **Flujo alternativo:** | 4.A. El sistema detecta que el elemento acaba de ser reservado milisegundos antes por otro usuario. El sistema aborta el bloqueo y avisa al empleado.<br>5.A. El tiempo de bloqueo finaliza sin que la reserva se haya confirmado. El sistema libera automáticamente la habitación devolviéndola al estado "Disponible". |
| **Poscondiciones:** | El elemento cambia su estado en el sistema a "Bloqueado" de forma temporal, lo que impide la asignación de esa misma habitación a otra reserva paralela. |
| **Referencias:** | CU-004 (Realizar ofertas), al que extiende. |

## Base de datos

<img width="1125" height="621" alt="diagrama ER crow´s foot supuesto3" src="https://github.com/user-attachments/assets/052d8301-bd9d-41bf-b4ab-3eb93c86c9b3" />

## Tablas de Requisitos de información

### INF-001 — USUARIO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-001 |
| **Nombre** | USUARIO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-001 Consultar disponibilidades.<br>CU-002 Visualizar ofertas.<br>CU-003 Consultar reservas.<br>CU-004 Realizar ofertas.<br>CU-005 Gestionar nuevas peticiones.<br>CU-006 Gestionar nuevas reservas. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los usuarios del sistema hotelero. |
| **Datos específicos** | - Identificador del usuario<br>- Correo electrónico<br>- Contraseña<br>- Rol<br>- Si el usuario está activo |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Todo usuario es cliente o empleado; los datos propios de cada uno se recogen en INF-002 e INF-003. |

### INF-002 — CLIENTE

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-002 |
| **Nombre** | CLIENTE |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-001 Consultar disponibilidades.<br>CU-002 Visualizar ofertas.<br>CU-005 Gestionar nuevas peticiones.<br>CU-006 Gestionar nuevas reservas.<br>INF-001 USUARIO. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los clientes del hotel. |
| **Datos específicos** | - Identificador del cliente<br>- Usuario asociado<br>- DNI<br>- Teléfono |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Hereda los datos del usuario (INF-001). Cada cliente se corresponde con un único usuario. |

### INF-003 — EMPLEADO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-003 |
| **Nombre** | EMPLEADO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-003 Consultar reservas.<br>CU-004 Realizar ofertas.<br>CU-005 Gestionar nuevas peticiones.<br>CU-006 Gestionar nuevas reservas.<br>CU-010 Bloqueo temporal de reserva.<br>INF-001 USUARIO. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los empleados del hotel (comerciales y administradores). |
| **Datos específicos** | - Identificador del empleado<br>- Usuario asociado<br>- Número de empleado<br>- Rol (comercial o administrador) |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Hereda los datos del usuario (INF-001). Cada empleado se corresponde con un único usuario. |

### INF-004 — TIPO_HAB

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-004 |
| **Nombre** | TIPO_HAB |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-001 Consultar disponibilidades.<br>CU-006 Gestionar nuevas reservas.<br>CU-009 Recálculo de precios. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los tipos de habitación que ofrece el hotel. |
| **Datos específicos** | - Identificador del tipo<br>- Nombre<br>- Capacidad<br>- Precio base |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | El precio base del tipo de habitación es la tarifa sobre la que se aplica el recálculo de precios. |

### INF-005 — HABITACION

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-005 |
| **Nombre** | HABITACION |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-001 Consultar disponibilidades.<br>CU-006 Gestionar nuevas reservas.<br>CU-007 Buscar elementos.<br>CU-008 Mostrar calendario.<br>CU-010 Bloqueo temporal de reserva.<br>INF-004 TIPO_HAB. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las habitaciones del hotel. |
| **Datos específicos** | - Identificador de la habitación<br>- Tipo de habitación<br>- Número<br>- Estado (por ejemplo, disponible o bloqueada) |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | El estado de la habitación determina cómo se muestra en el calendario (libre, ocupado, bloqueado). |

### INF-006 — OFERTA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-006 |
| **Nombre** | OFERTA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-002 Visualizar ofertas.<br>CU-004 Realizar ofertas.<br>CU-009 Recálculo de precios.<br>INF-005 HABITACION.<br>INF-003 EMPLEADO. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las ofertas o promociones que realizan los empleados sobre las habitaciones. |
| **Datos específicos** | - Identificador de la oferta<br>- Habitación a la que se aplica<br>- Empleado que la realiza<br>- Porcentaje de descuento<br>- Fecha de inicio de validez<br>- Fecha de fin de validez |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | La oferta la realiza un comercial o un administrador y la pueden ver todos los usuarios. |

### INF-007 — BLOQUEO_TEMPORAL

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-007 |
| **Nombre** | BLOQUEO_TEMPORAL |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-004 Realizar ofertas.<br>CU-010 Bloqueo temporal de reserva.<br>INF-005 HABITACION.<br>INF-003 EMPLEADO. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a los bloqueos temporales de habitaciones que realizan los empleados al hacer una oferta. |
| **Datos específicos** | - Identificador del bloqueo<br>- Habitación bloqueada<br>- Empleado que lo realiza<br>- Fecha y hora de inicio<br>- Duración en minutos |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Es opcional: solo existe cuando el empleado solicita el bloqueo. Al terminar la duración, la habitación vuelve a estar disponible. |

### INF-008 — RESERVA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-008 |
| **Nombre** | RESERVA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-001 Consultar disponibilidades.<br>CU-003 Consultar reservas.<br>CU-006 Gestionar nuevas reservas.<br>CU-007 Buscar elementos.<br>CU-008 Mostrar calendario.<br>CU-009 Recálculo de precios.<br>INF-002 CLIENTE.<br>INF-003 EMPLEADO.<br>INF-005 HABITACION.<br>INF-006 OFERTA. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las reservas de habitaciones realizadas por los clientes. |
| **Datos específicos** | - Identificador de la reserva<br>- Cliente que la realiza<br>- Empleado que la gestiona<br>- Habitación reservada<br>- Oferta aplicada (si la hay)<br>- Fecha de entrada<br>- Fecha de salida<br>- Precio total<br>- Estado |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | El precio total se recalcula cuando se aplica una oferta. La oferta es opcional. |

### INF-009 — PETICION

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-009 |
| **Nombre** | PETICION |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Marcos Sánchez García |
| **Fuentes** | Enunciado del supuesto 3 (Compañía hotelera) |
| **Referencias** | CU-005 Gestionar nuevas peticiones.<br>INF-002 CLIENTE.<br>INF-003 EMPLEADO. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a las peticiones que realizan los clientes y que atienden los empleados. |
| **Datos específicos** | - Identificador de la petición<br>- Cliente que la solicita<br>- Empleado que la atiende<br>- Descripción<br>- Estado<br>- Fecha de solicitud |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Las peticiones las gestiona el administrador, que puede actualizarlas o borrarlas cuando ya han sido gestionadas. |
