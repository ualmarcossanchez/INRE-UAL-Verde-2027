## Supuesto 5: Gestión de Incidencias

En un sistema de gestión de incidencias, los técnicos y los operadores pueden dar de alta incidencias, para lo cual, de forma excepcional se enviará un correo (en esta operación participa un sistema de gestión de correo). Los técnicos también atienden llamadas telefónicas y realizan informes sobre las incidencias. Por su parte, los operadores atienden llamadas telefónicas, marcan incidencias como duplicadas y ordenan incidencias. La forma de atender llamadas de los técnicos y los operadores no es exactamente igual, pero tiene similitudes. De forma específica, cuando los técnicos atienden llamadas, comprueban datos de la incidencia en el sistema. Cuando los operadores atienden llamadas, introducen nuevos datos de la incidencia. Los administradores del sistema gestionan categorías de incidencias, consultan incidencias y ordenan incidencias. La ordenación por parte de los administradores conlleva la adición de un comentario. Los técnicos y los operadores también pueden consultar incidencias. La consulta de incidencias por parte técnicos, operadores y administradores puede conllevar, de forma excepcional, la edición de los datos de la incidencia. Los usuarios invitados también pueden consultar incidencias, pero sin la posible edición de los datos. Además, los invitados informan sobre posibles incidencias, se pueden registrar para ver notificaciones y pueden acceder a un listado del histórico de notificaciones. El informe de posibles incidencias conlleva el dar de alta la localización en un mapa, la incorporación de una explicación completa en formato textual y la subida de una foto.

<img width="100%" alt="Diagrama de casos de uso" src="PEGAR_AQUI_LA_IMAGEN_Supuesto_05.png" />

## Descripción de los actores

## Actores del sistema

### Usuario Invitado

| **Actor** | **Usuario Invitado (ACT 001)** |
|---|---|
| **Desc** | Es el usuario no registrado que navega por el sistema. |
| **Caract** | Puede informar sobre posibles incidencias, lo que conlleva dar de alta la localización en un mapa, incorporar una explicación completa en formato textual y subir una foto. También puede consultar incidencias, acceder al histórico de notificaciones y ver notificaciones; esta última funcionalidad conlleva registrarse. |
| **Relaciones** | No tiene ninguna relación de herencia. Se relaciona con Informar sobre posible incidencia, Ver notificaciones, Acceder histórico de notificaciones y Consultar incidencia usuario. |
| **Referencias** | Puede informar sobre posible incidencia (UC-01), ver notificaciones (UC-02), acceder al histórico de notificaciones (UC-03) y consultar incidencia usuario (UC-04). Ver notificaciones incluye registrarse (UC-05). Informar sobre posible incidencia incluye dar de alta la localización en un mapa (UC-06), la subida de una foto (UC-07) y la explicación completa en formato textual (UC-08). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Empleado

| **Actor** | **Empleado (ACT 002)** |
|---|---|
| **Desc** | Es el actor general que representa a todos los empleados del sistema de gestión de incidencias. |
| **Caract** | Es un actor abstracto: sus características las heredan el Administrador, el Técnico y el Operador. Puede consultar incidencias y, de forma excepcional, al consultarlas puede editar los datos de la incidencia. |
| **Relaciones** | Relaciones de herencia desde Administrador, Operador y Técnico hacia Empleado. |
| **Referencias** | Puede consultar incidencia (UC-09), por lo que también pueden hacerlo el Administrador, el Técnico y el Operador. La consulta de incidencias puede extenderse de forma excepcional con la edición de los datos de la incidencia (UC-10). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Empleado Menor

| **Actor** | **Empleado Menor (ACT 003)** |
|---|---|
| **Desc** | Es el actor general que representa a los empleados de menor categoría. |
| **Caract** | Es un actor abstracto: sus características las heredan el Técnico y el Operador. Puede dar de alta una incidencia, lo que de forma excepcional puede conllevar el envío de un correo. |
| **Relaciones** | Relaciones de herencia desde Operador y Técnico hacia Empleado Menor. Se relaciona con Dar de alta incidencia. |
| **Referencias** | Puede dar de alta una incidencia (UC-11), por lo que también pueden hacerlo el Técnico y el Operador. Dar de alta incidencia puede extenderse de forma excepcional con el envío de un correo (UC-12). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Sistema de Gestión de Correo

| **Actor** | **Sistema de Gestión de Correo (ACT 004)** |
|---|---|
| **Desc** | Es el actor externo que gestiona el sistema de envío de correos. |
| **Caract** | Es un actor externo (System). Participa en el envío de correo. |
| **Relaciones** | No tiene relaciones de herencia. Se relaciona con Enviar correo. |
| **Referencias** | Participa en la funcionalidad de enviar correo (UC-12), que extiende de forma excepcional a Dar de alta incidencia (UC-11). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Técnico

| **Actor** | **Técnico (ACT 005)** |
|---|---|
| **Desc** | Es el técnico del sistema. |
| **Caract** | Es una especialización de Empleado y de Empleado Menor. Puede realizar un informe de incidencias y atender llamadas telefónicas como técnico, que es una especialización de Atender llamada telefónica y que de forma excepcional permite comprobar un dato de incidencia. |
| **Relaciones** | Relaciones de herencia desde Técnico hacia Empleado y Empleado Menor. Se relaciona con Realizar informe de incidencias y Atender llamada telefónica técnico. |
| **Referencias** | Como Empleado puede consultar incidencia (UC-09) y editar sus datos (UC-10); como Empleado Menor puede dar de alta incidencia (UC-11) y enviar correo (UC-12). Puede realizar informe de incidencias (UC-13) y atender llamada telefónica técnico (UC-14), especialización de Atender llamada telefónica (UC-18). Atender llamada telefónica técnico puede extenderse de forma excepcional con comprobar dato de incidencia (UC-15). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Operador

| **Actor** | **Operador (ACT 006)** |
|---|---|
| **Desc** | Es el operador del sistema. |
| **Caract** | Es una especialización de Empleado y de Empleado Menor. Puede ordenar incidencias, marcar incidencias como duplicadas y atender llamadas telefónicas como operador, que es una especialización de Atender llamada telefónica y que conlleva introducir un nuevo dato de incidencia. |
| **Relaciones** | Relaciones de herencia desde Operador hacia Empleado y Empleado Menor. Se relaciona con Ordenar incidencia, Marcar incidencia duplicada y Atender llamada telefónica operador. |
| **Referencias** | Como Empleado puede consultar incidencia (UC-09) y editar sus datos (UC-10); como Empleado Menor puede dar de alta incidencia (UC-11) y enviar correo (UC-12). Puede atender llamada telefónica operador (UC-16), especialización de Atender llamada telefónica (UC-18), que incluye introducir nuevo dato de incidencia (UC-17). También puede ordenar incidencia (UC-19) y marcar incidencia duplicada (UC-20). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |


### Administrador

| **Actor** | **Administrador (ACT 007)** |
|---|---|
| **Desc** | Es el administrador del sistema y el encargado de gestionarlo. |
| **Caract** | Es una especialización de Empleado. Puede gestionar la categoría de una incidencia y ordenar incidencias como administrador, que es una especialización de Ordenar incidencia y que implica añadir un comentario. |
| **Relaciones** | Relaciones de herencia desde Administrador hacia Empleado. Se relaciona con Gestionar categoría incidencia y Ordenar incidencia administrador. |
| **Referencias** | Como Empleado puede consultar incidencia (UC-09) y editar sus datos (UC-10). Puede gestionar categoría incidencia (UC-23) y ordenar incidencia administrador (UC-21), especialización de Ordenar incidencia (UC-19), que incluye la adición de un comentario (UC-22). |
| **Autor** | Fernando Sastre Guil \| **Fecha:** 25/10/2026 \| **Versión:** 1.0 |

## Descripción de los casos de uso

## Casos de uso

### UC-01 — Informar sobre posible incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Informar sobre posible incidencia (UC-01) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite informar sobre una posible incidencia en el sistema. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario accede a informar de incidencia.<br>2. El sistema solicita que se añada una localización.<br>3. El usuario da de alta la localización de la incidencia en un mapa.<br>4. El sistema solicita que se añada una foto de la incidencia.<br>5. El usuario sube una foto de la incidencia.<br>6. El sistema solicita que se añada un comentario explicativo.<br>7. El usuario añade una explicación completa de la incidencia.<br>8. La posible incidencia queda registrada en el sistema. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Queda registrada la incidencia. |

### UC-02 — Ver notificaciones

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Ver notificaciones (UC-02) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite ver todas las notificaciones pendientes. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario accede a ver notificaciones.<br>2. El sistema exige que el usuario se registre.<br>3. El usuario se registra en el sistema.<br>4. El sistema muestra todas las notificaciones pendientes del usuario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El usuario queda registrado. |

### UC-03 — Acceder histórico de notificaciones

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Acceder histórico de notificaciones (UC-03) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite ver todas las notificaciones enviadas o recibidas. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario accede a ver el histórico de notificaciones.<br>2. El sistema muestra todas las notificaciones tramitadas por el usuario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-04 — Consultar incidencia usuario

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar incidencia usuario (UC-04) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite ver todas las incidencias del usuario. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El usuario accede a consultar incidencia usuario.<br>2. El sistema muestra todas las incidencias del usuario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-05 — Registrarse

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Registrarse (UC-05) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite al usuario invitado registrarse en el sistema. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** | El usuario ha de haber accedido a ver notificaciones. |
| **Flujo normal:** | 1. El sistema exige que el usuario se registre.<br>2. El usuario se registra en el sistema. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Queda registrado el usuario. |

### UC-06 — Dar de alta localización en un mapa

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Dar de alta localización en un mapa (UC-06) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite dar de alta una localización en un mapa. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** | El usuario ha de haber entrado en Informar sobre posible incidencia. |
| **Flujo normal:** | 1. El sistema solicita que se añada una localización en un mapa.<br>2. El usuario da de alta la localización de la incidencia en un mapa. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Queda registrada la localización en el mapa. |

### UC-07 — Subida foto

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Subida foto (UC-07) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite subir una foto. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** | El usuario ha de haber entrado en Informar sobre posible incidencia. |
| **Flujo normal:** | 1. El sistema solicita que se añada una foto de la incidencia.<br>2. El usuario sube una foto de la incidencia. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | La foto queda cargada en el sistema. |

### UC-08 — Explicación completa formato textual

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Explicación completa formato textual (UC-08) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite añadir una explicación completa en formato textual a una posible incidencia. |
| **Actores:** | Usuario Invitado (ACT-001). |
| **Precondiciones:** | El usuario ha de haber entrado en Informar sobre posible incidencia. |
| **Flujo normal:** | 1. El sistema solicita que se añada un comentario explicativo.<br>2. El usuario añade una explicación completa de la incidencia. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El comentario queda guardado en el sistema. |

### UC-09 — Consultar incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Consultar incidencia (UC-09) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite ver todas las incidencias del sistema. |
| **Actores:** | Empleado (ACT-002). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El empleado accede a consultar incidencias.<br>2. El sistema muestra todas las incidencias de todos los usuarios. |
| **Flujo alternativo:** | 2.A. El empleado solicita modificar los datos de una incidencia.<br>2.A.1. El sistema muestra los datos actuales de la incidencia.<br>2.A.2. El empleado modifica los datos necesarios.<br>2.A.3. El sistema registra los datos modificados. |
| **Poscondiciones:** |  |

### UC-10 — Edición datos incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Edición datos incidencia (UC-10) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite modificar los datos de una incidencia. |
| **Actores:** | Empleado (ACT-002). |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El empleado solicita modificar los datos de una incidencia.<br>2. El sistema muestra los datos actuales de la incidencia.<br>3. El empleado modifica los datos necesarios.<br>4. El sistema registra los datos modificados. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Quedan modificados los datos de una incidencia. |

### UC-11 — Dar de alta incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Dar de alta incidencia (UC-11) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite dar de alta una incidencia emitida por un usuario. |
| **Actores:** | Empleado Menor (ACT-003). |
| **Precondiciones:** | Debe haber alguna incidencia en el sistema y además que no esté dada de alta. |
| **Flujo normal:** | 1. El empleado menor accede a alguna incidencia emitida por los usuarios.<br>2. El empleado menor revisa la incidencia.<br>3. El empleado menor da de alta la incidencia. |
| **Flujo alternativo:** | 2.A. El empleado menor solicita enviar un correo al usuario de la incidencia.<br>2.A.1. El empleado menor redacta el correo.<br>2.A.2. El empleado menor envía el correo.<br>2.A.3. El sistema de gestión de correo gestiona el envío y recibo del correo. |
| **Poscondiciones:** | La incidencia queda dada de alta. |

### UC-12 — Enviar correo

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Enviar correo (UC-12) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite enviar un correo. |
| **Actores:** | Empleado Menor (ACT-003) y Sistema de Gestión de Correo (ACT-004). |
| **Precondiciones:** | El empleado debe haber accedido a dar de alta una incidencia. |
| **Flujo normal:** | 1. El empleado menor solicita enviar un correo al usuario de la incidencia.<br>2. El empleado menor redacta el correo.<br>3. El empleado menor envía el correo.<br>4. El sistema de gestión de correo gestiona el envío y recibo del correo. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El correo queda enviado. |

### UC-13 — Realizar informe de incidencias

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Realizar informe de incidencias (UC-13) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite realizar un informe de incidencias. |
| **Actores:** | Técnico (ACT-005). |
| **Precondiciones:** | Debe haber incidencias registradas en el sistema. |
| **Flujo normal:** | 1. El técnico accede a realizar informe de incidencias.<br>2. El técnico realiza el informe.<br>3. El sistema deja guardado el informe en el sistema. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El informe queda registrado en el sistema. |

### UC-14 — Atender llamada telefónica técnico

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Atender llamada telefónica técnico (UC-14) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Es una especialización de atender llamada telefónica y permite que una llamada telefónica sea atendida por un técnico. |
| **Actores:** | Técnico (ACT-005). |
| **Precondiciones:** | Debe haber alguna llamada telefónica pendiente. |
| **Flujo normal:** | 1. El sistema registra una llamada telefónica en espera.<br>2. El técnico contesta la llamada. |
| **Flujo alternativo:** | 2.A. El técnico solicita comprobar un dato de incidencia.<br>2.A.1. El sistema muestra el dato de incidencia al técnico.<br>2.A.2. El técnico comprueba el dato de incidencia. |
| **Poscondiciones:** |  |

### UC-15 — Comprobar dato de incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Comprobar dato de incidencia (UC-15) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite comprobar un dato de incidencia. |
| **Actores:** | Técnico (ACT-005). |
| **Precondiciones:** | El técnico debe haber atendido una llamada telefónica. |
| **Flujo normal:** | 1. El técnico solicita comprobar un dato de incidencia.<br>2. El sistema muestra el dato de incidencia al técnico.<br>3. El técnico comprueba el dato de incidencia. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-16 — Atender llamada telefónica operador

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Atender llamada telefónica operador (UC-16) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Es una especialización de atender llamada telefónica y permite que una llamada telefónica sea atendida por un operador. |
| **Actores:** | Operador (ACT-006). |
| **Precondiciones:** | Debe haber alguna llamada telefónica en espera. |
| **Flujo normal:** | 1. El sistema registra una llamada telefónica en espera.<br>2. El operador contesta la llamada.<br>3. El operador introduce un nuevo dato de incidencia.<br>4. El sistema registra el nuevo dato. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El sistema registra el nuevo dato de incidencia. |

### UC-17 — Introducir nuevo dato de incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Introducir nuevo dato de incidencia (UC-17) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite introducir un nuevo dato de incidencia. |
| **Actores:** | Operador (ACT-006). |
| **Precondiciones:** | Debe haber alguna llamada atendida por el operador. |
| **Flujo normal:** | 1. El operador introduce un nuevo dato de incidencia.<br>2. El sistema registra el nuevo dato. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El sistema registra el nuevo dato de incidencia. |

### UC-18 — Atender llamada telefónica

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Atender llamada telefónica (UC-18) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Es un caso de uso abstracto que permite recibir una llamada telefónica. |
| **Actores:** |  |
| **Precondiciones:** |  |
| **Flujo normal:** | 1. El sistema registra una llamada telefónica.<br>2. La llamada queda pendiente para que sea atendida. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-19 — Ordenar incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Ordenar incidencia (UC-19) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite ordenar incidencias. |
| **Actores:** | Operador (ACT-006). |
| **Precondiciones:** | Debe haber alguna incidencia registrada en el sistema. |
| **Flujo normal:** | 1. El operador accede a ordenar incidencia.<br>2. El operador ordena una incidencia.<br>3. El sistema registra la incidencia ordenada. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-20 — Marcar incidencia duplicada

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Marcar incidencia duplicada (UC-20) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite marcar una incidencia como duplicada. |
| **Actores:** | Operador (ACT-006). |
| **Precondiciones:** | Debe haber alguna incidencia registrada en el sistema. |
| **Flujo normal:** | 1. El operador accede a marcar incidencia duplicada.<br>2. El operador marca la incidencia correspondiente como duplicada.<br>3. El sistema recoge la incidencia como incidencia duplicada. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | El sistema registra una incidencia como duplicada. |

### UC-21 — Ordenar incidencia administrador

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Ordenar incidencia administrador (UC-21) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Es una especialización de ordenar incidencia. Permite a un administrador ordenar incidencias. |
| **Actores:** | Administrador (ACT-007). |
| **Precondiciones:** | Debe haber alguna incidencia registrada en el sistema. |
| **Flujo normal:** | 1. El administrador accede a ordenar incidencia.<br>2. El administrador ordena una incidencia.<br>3. El administrador añade un comentario a la incidencia.<br>4. El sistema registra la incidencia ordenada. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** |  |

### UC-22 — Adición de comentario

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Adición de comentario (UC-22) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite añadir un comentario en una incidencia ordenada. |
| **Actores:** | Administrador (ACT-007). |
| **Precondiciones:** | El administrador debe estar ordenando una incidencia. |
| **Flujo normal:** | 1. El administrador ordena una incidencia.<br>2. El administrador añade un comentario a la incidencia.<br>3. El sistema registra el comentario. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Queda añadido un comentario a una incidencia ordenada. |

### UC-23 — Gestionar categoría incidencia

| **Campo** | **Contenido** |
|---|---|
| **Nombre:** | Gestionar categoría incidencia (UC-23) |
| **Autor:** | Fernando Sastre Guil |
| **Fecha:** | 25/10/2026 |
| **Descripción:** | Permite a un administrador gestionar las categorías de las incidencias. |
| **Actores:** | Administrador (ACT-007). |
| **Precondiciones:** | Debe haber alguna incidencia registrada en el sistema. |
| **Flujo normal:** | 1. El administrador accede a gestionar categoría incidencia.<br>2. El sistema muestra las categorías de las incidencias.<br>3. El administrador modifica las categorías de las incidencias.<br>4. El sistema registra las nuevas categorías. |
| **Flujo alternativo:** |  |
| **Poscondiciones:** | Quedan modificadas las categorías de las incidencias registradas. |

## Base de datos

<img width="100%" alt="Diagrama entidad-relación" src="PEGAR_AQUI_LA_IMAGEN_Supuesto_05_Diagrama-Entidad-Relacion.png" />

## Tablas de Requisitos de información

### INF-001 — USUARIO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-001 |
| **Nombre** | USUARIO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-001 Usuario Invitado.<br>ACT-002 Empleado.<br>ACT-003 Empleado Menor.<br>ACT-005 Técnico.<br>ACT-006 Operador.<br>ACT-007 Administrador.<br>UC-02 Ver notificaciones.<br>UC-03 Acceder histórico de notificaciones.<br>UC-04 Consultar incidencia usuario.<br>UC-05 Registrarse.<br>UC-09 Consultar incidencia. |
| **Descripción** | El sistema deberá almacenar la información correspondiente a todos los usuarios registrados en el sistema (invitados registrados, empleados, técnicos, operadores y administradores). |
| **Datos específicos** | - Identificador del usuario<br>- Nombre<br>- Apellidos<br>- Correo electrónico<br>- Teléfono<br>- Contraseña<br>- Fecha de registro<br>- Estado de actividad |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Un usuario puede tener asignados uno o varios roles dentro del sistema. Los invitados no registrados navegan de forma anónima hasta efectuar el registro (UC-05). |

### INF-002 — ROL

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-002 |
| **Nombre** | ROL |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-001 Usuario Invitado.<br>ACT-005 Técnico.<br>ACT-006 Operador.<br>ACT-007 Administrador. |
| **Descripción** | El sistema deberá almacenar los diferentes roles que pueden asignarse a los usuarios para definir sus permisos de acceso y funcionalidades. |
| **Datos específicos** | - Identificador del rol<br>- Nombre del rol<br>- Descripción |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los roles del sistema incluyen Invitado, Técnico, Operador y Administrador. |

### INF-003 — USUARIO_ROL

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-003 |
| **Nombre** | USUARIO_ROL |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-001 Usuario Invitado.<br>ACT-002 Empleado.<br>ACT-005 Técnico.<br>ACT-006 Operador.<br>ACT-007 Administrador. |
| **Descripción** | El sistema deberá almacenar la relación entre los usuarios y los roles que tienen asignados. |
| **Datos específicos** | - Identificador del usuario<br>- Identificador del rol |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Un usuario puede tener varios roles y un mismo rol puede estar asignado a varios usuarios. |

### INF-004 — CATEGORIA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-004 |
| **Nombre** | CATEGORIA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-007 Administrador.<br>UC-23 Gestionar categoría incidencia. |
| **Descripción** | El sistema deberá almacenar las categorías para la clasificación de las incidencias. |
| **Datos específicos** | - Identificador de la categoría<br>- Nombre de la categoría<br>- Descripción<br>- Estado |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Las categorías son gestionadas exclusivamente por el perfil Administrador. |

### INF-005 — INCIDENCIA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-005 |
| **Nombre** | INCIDENCIA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | UC-01 Informar sobre posible incidencia.<br>UC-04 Consultar incidencia usuario.<br>UC-06 Dar de alta localización en un mapa.<br>UC-07 Subida foto.<br>UC-08 Explicación completa formato textual.<br>UC-09 Consultar incidencia.<br>UC-10 Edición datos incidencia.<br>UC-11 Dar de alta incidencia.<br>UC-20 Marcar incidencia duplicada. |
| **Descripción** | El sistema deberá almacenar la información detallada de las incidencias y posibles incidencias registradas en la plataforma. |
| **Datos específicos** | - Identificador de la incidencia<br>- Usuario que la reporta<br>- Empleado que la da de alta<br>- Categoría<br>- Incidencia duplicada de referencia<br>- Explicación resumida<br>- Explicación completa (formato textual)<br>- URL / Ruta de la foto<br>- Latitud<br>- Longitud<br>- Localización en el mapa / Dirección<br>- Estado<br>- Orden de prioridad<br>- Fecha de reporte<br>- Fecha de alta |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Los estados posibles incluyen PENDIENTE, DADA_DE_ALTA, DUPLICADA, EN_PROCESO, RESUELTA y CERRADA. Permite la autorreferencia hacia otra incidencia en caso de marcarse como duplicada (UC-20). |

### INF-006 — ORDENACION_INCIDENCIA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-006 |
| **Nombre** | ORDENACION_INCIDENCIA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-006 Operador.<br>ACT-007 Administrador.<br>UC-19 Ordenar incidencia.<br>UC-21 Ordenar incidencia administrador.<br>UC-22 Adición de comentario. |
| **Descripción** | El sistema deberá registrar los eventos de ordenación aplicados a las incidencias por los operadores y administradores. |
| **Datos específicos** | - Identificador de la ordenación<br>- Incidencia<br>- Usuario que ordena<br>- Orden asignado<br>- Comentario del administrador<br>- Fecha de ordenación |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | La ordenación realizada por un Administrador conlleva obligatoriamente la adición de un comentario descriptivo (UC-21, UC-22). |

### INF-007 — LLAMADA_TELEFONICA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-007 |
| **Nombre** | LLAMADA_TELEFONICA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-005 Técnico.<br>ACT-006 Operador.<br>UC-14 Atender llamada telefónica técnico.<br>UC-15 Comprobar dato de incidencia.<br>UC-16 Atender llamada telefónica operador.<br>UC-17 Introducir nuevo dato de incidencia.<br>UC-18 Atender llamada telefónica. |
| **Descripción** | El sistema deberá almacenar la información de las llamadas telefónicas atendidas por el personal operativo y técnico. |
| **Datos específicos** | - Identificador de la llamada<br>- Incidencia vinculada<br>- Empleado que atiende la llamada<br>- Teléfono de origen<br>- Fecha y hora<br>- Tipo de atención (TECNICO / OPERADOR)<br>- Datos introducidos o comprobados<br>- Observaciones |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | La atención de los técnicos implica la comprobación de datos de la incidencia (UC-15), mientras que la de los operadores implica la introducción de nuevos datos (UC-17). |

### INF-008 — INFORME_INCIDENCIA

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-008 |
| **Nombre** | INFORME_INCIDENCIA |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-005 Técnico.<br>UC-13 Realizar informe de incidencias. |
| **Descripción** | El sistema deberá almacenar los informes técnicos realizados sobre las incidencias. |
| **Datos específicos** | - Identificador del informe<br>- Incidencia<br>- Técnico redactor<br>- Título del informe<br>- Contenido<br>- Fecha de elaboración |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Los informes son elaborados de forma exclusiva por los técnicos del sistema. |

### INF-009 — CORREO

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-009 |
| **Nombre** | CORREO |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-003 Empleado Menor.<br>ACT-004 Sistema de Gestión de Correo.<br>UC-11 Dar de alta incidencia.<br>UC-12 Enviar correo. |
| **Descripción** | El sistema deberá registrar los correos electrónicos enviados al dar de alta una incidencia de forma excepcional. |
| **Datos específicos** | - Identificador del correo<br>- Incidencia asociada<br>- Empleado remitente<br>- Correo del destinatario<br>- Asunto<br>- Cuerpo del mensaje<br>- Fecha de envío<br>- Estado de envío |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | En el envío y procesamiento de estos correos participa el actor externo Sistema de Gestión de Correo. |

### INF-010 — NOTIFICACION

| **Campo** | **Contenido** |
|---|---|
| **Código** | INF-010 |
| **Nombre** | NOTIFICACION |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores** | Fernando Sastre Guil |
| **Fuentes** | Enunciado del supuesto 5 (Sistema de Gestión de Incidencias) |
| **Referencias** | ACT-001 Usuario Invitado.<br>UC-02 Ver notificaciones.<br>UC-03 Acceder histórico de notificaciones.<br>UC-05 Registrarse. |
| **Descripción** | El sistema deberá almacenar las notificaciones enviadas a los usuarios de la plataforma. |
| **Datos específicos** | - Identificador de la notificación<br>- Usuario destinatario<br>- Incidencia relacionada<br>- Título<br>- Mensaje<br>- Tipo de notificación<br>- Fecha de creación<br>- Fecha de lectura<br>- Estado de lectura |
| **Importancia** | Importante |
| **Estado** | Aceptado |
| **Comentarios** | Para acceder a la consulta de notificaciones pendientes e histórico, el usuario debe haber completado el registro en el sistema (UC-05). |
