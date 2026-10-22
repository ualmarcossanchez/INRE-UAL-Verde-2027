# Supuesto 1: Horarios

## Enunciado

En una universidad, el personal del PDI, el personal del PAS y los estudiantes pueden consultar horarios. Por su parte, el personal del PAS puede modificar horarios y dar de alta estudiantes. El personal de PDI puede proponer cambios en los horarios y dar de alta estudiantes. La funcionalidad de dar de alta estudiantes del PAS realiza una verificación de los datos del estudiante. Sin embargo, la funcionalidad de dar de alta estudiantes del PDI, además de verificar los datos también permite de forma excepcional realizar la búsqueda en las listas de clase de sus asignaturas.

## Diagrama de clases

![Diagrama de clases del supuesto 1](DB_supuesto01.png)

## Descripción de los actores

| **Actor** | **Usuario (ACT 001)** |
|---|---|
| **Desc** | Es el actor general que representa a cualquier persona que accede al sistema de horarios de la universidad. |
| **Caract** | Es un actor abstracto: sus características comunes las heredan el PAS, el PDI y el Estudiante. Puede consultar horarios. |
| **Relaciones** | Relación de herencia de PAS, PDI y Estudiante hacia Usuario. |
| **Referencias** | El usuario puede consultar horarios (UC-01), por lo que también lo pueden hacer el PAS, el PDI y el Estudiante. |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 22/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **PAS (ACT 002)** |
|---|---|
| **Desc** | Es el personal de administración y servicios de la universidad. |
| **Caract** | Además de consultar horarios, puede modificar horarios y dar de alta estudiantes, operación que conlleva una verificación de los datos del estudiante. |
| **Relaciones** | Relación de herencia del PAS hacia Usuario (ACT 001). |
| **Referencias** | El PAS puede modificar horarios (UC-02), dar de alta estudiantes (UC-03) y verificar datos (UC-04). Por herencia, puede consultar horarios (UC-01). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 22/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **PDI (ACT 003)** |
|---|---|
| **Desc** | Es el personal docente e investigador de la universidad. |
| **Caract** | Además de consultar horarios, puede proponer cambios en los horarios y dar de alta estudiantes. De forma excepcional, al dar de alta estudiantes puede realizar la búsqueda en las listas de clase de sus asignaturas. |
| **Relaciones** | Relación de herencia del PDI hacia Usuario (ACT 001). |
| **Referencias** | El PDI puede proponer cambios (UC-05), dar de alta estudiantes (UC-06) y realizar búsquedas en listas de clase (UC-07). Por herencia, puede consultar horarios (UC-01). |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 22/10/2026  \|  **Versión:** 1.0 |

| **Actor** | **Estudiante (ACT 004)** |
|---|---|
| **Desc** | Es el alumno matriculado en la universidad. |
| **Caract** | Solo puede consultar horarios. No tiene casos de uso propios. |
| **Relaciones** | Relación de herencia del Estudiante hacia Usuario (ACT 001). El PAS y el PDI son quienes lo dan de alta. |
| **Referencias** | El estudiante puede consultar horarios (UC-01), heredado de Usuario. |
| **Autor** | Javier Zúñiga Carmona  \|  **Fecha:** 22/10/2026  \|  **Versión:** 1.0 |

## Descripción de los casos de uso

| **Nombre:** | **Consultar horarios (UC-01)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite consultar los horarios de la universidad. Lo pueden realizar el PDI, el PAS y los estudiantes, por ser un caso de uso del actor general Usuario. |
| **Actores:** | Usuario (PAS, PDI y Estudiante, por herencia) |
| **Precondiciones:** | El actor debe estar identificado en el sistema. |
| **Flujo Normal:** | 1.- El actor accede a la sección de horarios.<br>2.- El sistema muestra un formulario para seleccionar los criterios de consulta (asignatura, día, aula).<br>3.- El actor introduce los criterios y confirma la consulta.<br>4.- El sistema muestra los horarios que cumplen los criterios. |
| **Flujo Alternativo:** | 4.A.- Ningún horario cumple los criterios, por lo que el sistema muestra un mensaje indicándolo y el listado aparece vacío. |
| **Poscondiciones:** | Se muestran los horarios en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-02 (Modificar horarios) y UC-05 (Proponer cambios), que parten de los horarios consultados. |

| **Nombre:** | **Modificar horarios (UC-02)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite al personal del PAS modificar los horarios de las asignaturas. |
| **Actores:** | PAS |
| **Precondiciones:** | El PAS debe estar identificado en el sistema. El horario a modificar debe existir en el sistema. |
| **Flujo Normal:** | 1.- El PAS accede a la sección de horarios y selecciona el horario que desea modificar.<br>2.- El sistema muestra los datos actuales del horario en un formulario editable.<br>3.- El PAS modifica los datos (día, hora de inicio, hora de fin, aula) y confirma los cambios.<br>4.- El sistema comprueba la validez de los datos, los almacena y registra el PAS y la fecha de la modificación.<br>5.- El sistema muestra un mensaje confirmando que el horario ha sido modificado. |
| **Flujo Alternativo:** | 3.A.- El PAS cancela la modificación, de modo que el sistema descarta los cambios y no modifica el horario.<br>4.A.- Los datos no son válidos, por lo que el sistema avisa al PAS de ello permitiéndole que los corrija. |
| **Poscondiciones:** | El horario ha sido modificado y almacenado en el sistema. |
| **Referencias:** | UC-01 (Consultar horarios), desde el que se localiza el horario. UC-05 (Proponer cambios), cuyas propuestas pueden dar lugar a la modificación. |

| **Nombre:** | **Dar de alta estudiantes PAS (UC-03)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite al personal del PAS dar de alta a un estudiante en el sistema. El alta realiza una verificación de los datos del estudiante. |
| **Actores:** | PAS |
| **Precondiciones:** | El PAS debe estar identificado en el sistema. El estudiante no debe estar dado de alta previamente. |
| **Flujo Normal:** | 1.- El PAS accede a la gestión de estudiantes y selecciona la opción de dar de alta.<br>2.- El sistema muestra un formulario para introducir los datos del estudiante.<br>3.- El PAS introduce los datos y confirma el alta.<br>4.- El sistema ejecuta el caso de uso Verificar datos (UC-04) sobre los datos introducidos.<br>5.- El sistema almacena al estudiante, registrando el PAS y la fecha del alta.<br>6.- El sistema muestra un mensaje confirmando que el estudiante ha sido dado de alta. |
| **Flujo Alternativo:** | 3.A.- El PAS cancela el alta, de modo que el sistema descarta los datos y no da de alta al estudiante.<br>4.A.- Los datos no son válidos o el estudiante ya existe, por lo que el sistema avisa al PAS de ello permitiéndole que los corrija. |
| **Poscondiciones:** | El estudiante ha sido dado de alta y almacenado en el sistema con los datos verificados. |
| **Referencias:** | UC-04 (Verificar datos), que se incluye en este caso de uso. UC-06 (Dar de alta estudiantes PDI), caso equivalente del PDI. |

| **Nombre:** | **Verificar datos (UC-04)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite comprobar que los datos del estudiante introducidos en el alta son correctos. Este caso de uso se ejecuta como parte de dar de alta estudiantes del PAS. |
| **Actores:** | PAS (a través de Dar de alta estudiantes PAS) |
| **Precondiciones:** | El PAS debe haber introducido los datos del estudiante en el alta (UC-03 en ejecución). |
| **Flujo Normal:** | 1.- El sistema recibe los datos introducidos del estudiante.<br>2.- El sistema comprueba que los datos tienen el formato correcto, que los obligatorios están completos y que el DNI es válido.<br>3.- El sistema da los datos por válidos y devuelve el control a Dar de alta estudiantes PAS. |
| **Flujo Alternativo:** | 3.A.- Los datos no son correctos, por lo que el sistema informa de los errores encontrados y los devuelve al PAS para que los corrija. |
| **Poscondiciones:** | Los datos han sido verificados, ya sea dándolos por válidos o notificando los errores. |
| **Referencias:** | UC-03 (Dar de alta estudiantes PAS), que lo incluye. |

| **Nombre:** | **Proponer cambios (UC-05)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite al personal del PDI proponer cambios en los horarios de las asignaturas. |
| **Actores:** | PDI |
| **Precondiciones:** | El PDI debe estar identificado en el sistema. El horario sobre el que se propone el cambio debe existir en el sistema. |
| **Flujo Normal:** | 1.- El PDI accede a la sección de horarios y selecciona el horario sobre el que quiere proponer un cambio.<br>2.- El sistema muestra el horario y un formulario para describir el cambio propuesto.<br>3.- El PDI describe el cambio y confirma la propuesta.<br>4.- El sistema registra la propuesta como pendiente, con el PDI y la fecha.<br>5.- El sistema muestra un mensaje confirmando que la propuesta ha sido registrada. |
| **Flujo Alternativo:** | 3.A.- El PDI cancela la propuesta, de modo que el sistema descarta los datos y no registra ninguna propuesta.<br>4.A.- La descripción está vacía, por lo que el sistema avisa al PDI de que debe introducirla. |
| **Poscondiciones:** | La propuesta de cambio ha sido registrada como pendiente en el sistema. |
| **Referencias:** | UC-01 (Consultar horarios), desde el que se localiza el horario. UC-02 (Modificar horarios), que puede aplicar el cambio propuesto. |

| **Nombre:** | **Dar de alta estudiantes PDI (UC-06)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite al personal del PDI dar de alta a un estudiante en el sistema, verificando los datos introducidos. De forma excepcional, durante el alta se pueden buscar estudiantes en las listas de clase de sus asignaturas (punto de extensión: Realizar búsqueda en listas). |
| **Actores:** | PDI |
| **Precondiciones:** | El PDI debe estar identificado en el sistema. El estudiante no debe estar dado de alta previamente. |
| **Flujo Normal:** | 1.- El PDI accede a la gestión de estudiantes y selecciona la opción de dar de alta.<br>2.- El sistema muestra un formulario para introducir los datos del estudiante.<br>3.- El PDI introduce los datos y confirma el alta.<br>4.- El sistema verifica los datos introducidos.<br>5.- El sistema almacena al estudiante, registrando el PDI y la fecha del alta.<br>6.- El sistema muestra un mensaje confirmando que el estudiante ha sido dado de alta. |
| **Flujo Alternativo:** | 3.A.- El PDI necesita buscar al estudiante en las listas de clase de sus asignaturas. Se ejecuta el caso de uso Realizar búsqueda en listas (UC-07) a través del punto de extensión.<br>3.B.- El PDI cancela el alta, de modo que el sistema descarta los datos y no da de alta al estudiante.<br>4.A.- Los datos no son válidos o el estudiante ya existe, por lo que el sistema avisa al PDI de ello permitiéndole que los corrija. |
| **Poscondiciones:** | El estudiante ha sido dado de alta y almacenado en el sistema con los datos verificados. |
| **Referencias:** | UC-07 (Realizar búsqueda en listas), que lo extiende. UC-03 (Dar de alta estudiantes PAS), caso equivalente del PAS. |

| **Nombre:** | **Realizar búsqueda en listas (UC-07)** |
|---|---|
| **Autor:** | Javier Zúñiga Carmona |
| **Fecha:** | 22/10/2026 |
| **Descripción:** | Permite al PDI buscar estudiantes en las listas de clase de las asignaturas que imparte. Se ejecuta solo de forma excepcional, como extensión de dar de alta estudiantes del PDI. |
| **Actores:** | PDI |
| **Precondiciones:** | El PDI debe estar dando de alta a un estudiante (UC-06 en ejecución) y debe impartir al menos una asignatura. |
| **Flujo Normal:** | 1.- El PDI selecciona la opción de buscar en las listas de clase durante el alta.<br>2.- El sistema muestra las asignaturas que imparte el PDI y un campo de búsqueda.<br>3.- El PDI selecciona una asignatura e introduce el criterio de búsqueda (nombre o DNI).<br>4.- El sistema muestra los estudiantes de la lista de clase que cumplen el criterio.<br>5.- El sistema devuelve el control a Dar de alta estudiantes PDI (UC-06). |
| **Flujo Alternativo:** | 3.A.- El PDI cancela la búsqueda y el sistema devuelve el control al alta sin cambios.<br>4.A.- Ningún estudiante cumple el criterio, por lo que el sistema muestra un mensaje indicándolo. |
| **Poscondiciones:** | Se muestran los estudiantes encontrados en pantalla, pero no se modifica ni se borra ningún dato en el sistema. |
| **Referencias:** | UC-06 (Dar de alta estudiantes PDI), al que extiende. |

## Requisitos de información

| **INF-01** | **Usuario** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Consultar horarios (UC-01)<br>• Dar de alta estudiantes PAS (UC-03)<br>• Dar de alta estudiantes PDI (UC-06) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los usuarios de la universidad (PAS, PDI y estudiantes). En concreto: |
| **Datos específicos:** | • Identificador de usuario<br>• Nombre<br>• Correo electrónico<br>• Si el usuario está activo<br>• Tipo de usuario (PAS, PDI o estudiante) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Los datos propios de cada tipo de usuario se recogen en INF-02, INF-03 e INF-04. |

| **INF-02** | **PAS** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Modificar horarios (UC-02)<br>• Dar de alta estudiantes PAS (UC-03)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente al personal de administración y servicios. En concreto: |
| **Datos específicos:** | • Número de empleado<br>• Puesto |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Hereda los datos del usuario (INF-01). |

| **INF-03** | **PDI** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Proponer cambios (UC-05)<br>• Dar de alta estudiantes PDI (UC-06)<br>• Realizar búsqueda en listas (UC-07)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente al personal docente e investigador. En concreto: |
| **Datos específicos:** | • Número de empleado<br>• Departamento<br>• Asignaturas que imparte |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Hereda los datos del usuario (INF-01). Las asignaturas que imparte determinan en qué listas de clase puede buscar. |

| **INF-04** | **Estudiante** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Dar de alta estudiantes PAS (UC-03)<br>• Verificar datos (UC-04)<br>• Dar de alta estudiantes PDI (UC-06)<br>• Realizar búsqueda en listas (UC-07)<br>• Usuario (INF-01) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los estudiantes de la universidad. En concreto: |
| **Datos específicos:** | • DNI<br>• Fecha de alta<br>• Si sus datos han sido verificados<br>• Personal que lo ha dado de alta (PAS o PDI) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Hereda los datos del usuario (INF-01). Un estudiante es dado de alta por un PAS o por un PDI, nunca por ambos. |

| **INF-05** | **Asignatura** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Consultar horarios (UC-01)<br>• Proponer cambios (UC-05)<br>• Realizar búsqueda en listas (UC-07)<br>• PDI (INF-03) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las asignaturas de la universidad. En concreto: |
| **Datos específicos:** | • Identificador de la asignatura<br>• Código<br>• Nombre<br>• PDI que la imparte |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Una asignatura puede ser impartida por varios PDI y un PDI puede impartir varias asignaturas. |

| **INF-06** | **Lista de clase** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Realizar búsqueda en listas (UC-07)<br>• Asignatura (INF-05)<br>• Estudiante (INF-04) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las listas de clase, que relacionan a los estudiantes con las asignaturas en las que están matriculados. En concreto: |
| **Datos específicos:** | • Asignatura<br>• Estudiante<br>• Curso académico |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Es la información sobre la que el PDI realiza la búsqueda de estudiantes. |

| **INF-07** | **Horario** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Consultar horarios (UC-01)<br>• Modificar horarios (UC-02)<br>• Proponer cambios (UC-05)<br>• Asignatura (INF-05)<br>• PAS (INF-02) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a los horarios de las asignaturas. En concreto: |
| **Datos específicos:** | • Identificador del horario<br>• Asignatura<br>• Día de la semana<br>• Hora de inicio<br>• Hora de fin<br>• Aula<br>• PAS que lo modificó por última vez y fecha de la modificación (solo si se ha modificado) |
| **Importancia:** | Muy importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Solo el PAS puede modificar un horario; el PDI únicamente propone cambios. |

| **INF-08** | **Propuesta de cambio** |
|---|---|
| **Versión:** | 1.0 (Octubre-2026) |
| **Autores:** | Javier Zúñiga Carmona |
| **Fuentes:** | Enunciado del supuesto 1 (Horarios) |
| **Referencias:** | • Proponer cambios (UC-05)<br>• Horario (INF-07)<br>• PDI (INF-03) |
| **Descripción:** | El sistema deberá almacenar la información correspondiente a las propuestas de cambio de horario que realiza el PDI. En concreto: |
| **Datos específicos:** | • Identificador de la propuesta<br>• Horario sobre el que se propone el cambio<br>• PDI que la propone<br>• Descripción del cambio<br>• Fecha de la propuesta<br>• Estado (pendiente o atendida) |
| **Importancia:** | Importante |
| **Estado:** | Aceptado |
| **Comentarios:** | Una propuesta nace pendiente y pasa a atendida cuando el PAS la revisa. |
