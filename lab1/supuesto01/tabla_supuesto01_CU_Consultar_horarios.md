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
