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
