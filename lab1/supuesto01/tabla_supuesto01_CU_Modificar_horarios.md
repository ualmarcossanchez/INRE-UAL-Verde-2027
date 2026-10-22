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
