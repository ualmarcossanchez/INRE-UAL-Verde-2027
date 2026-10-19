
| **CU-004** | **Realizar ofertas** |
| :--- | :--- |
| **Versión** | 1.0 (Octubre-2026) |
| **Autores<br>Fuentes** | Marcos Sánchez García<br>Enunciado del supuesto práctico y entrevistas |
| **Referencias** | • Actor: Empleado (Comercial / Administrador)<br>• Incluye: Recálculo de precios<br>• Extendido por: Bloqueo temporal de reserva |
| **Descripción** | El sistema deberá permitir al empleado (administrador o comercial) crear y registrar nuevas ofertas promocionales, calculando automáticamente los nuevos precios. |
| **Evento activación** | El empleado inicia la funcionalidad de crear una nueva oferta en el menú principal. |
| **Pre condición** | El empleado debe estar identificado (logueado) en el sistema con su rol correspondiente. |
| **Post condición** | La nueva oferta queda registrada en el sistema y disponible para los clientes. |
| **Resultados** | Actualización del catálogo de ofertas y de las tarifas del hotel. |
| **Esc. principal** | 1. El Empleado selecciona la opción de crear nueva oferta.<br>2. El sistema solicita los datos de la promoción (fechas, porcentaje de descuento, habitaciones afectadas).<br>3. El Empleado introduce y confirma los datos de la oferta.<br>4. El sistema valida que los datos introducidos son correctos.<br>5. El sistema llama al caso de uso **Recálculo de precios** para generar las nuevas tarifas aplicables.<br>6. El sistema registra la nueva oferta.<br>7. El sistema muestra un mensaje de confirmación al Empleado. |
| **Alternativas** | **Al paso 3 (Bloqueo temporal):**<br>1. El Empleado decide que la oferta requiere bloquear unas habitaciones específicas.<br>2. Se llama al caso de uso **Bloqueo temporal de reserva**.<br>3. Se retorna al paso 4 del escenario principal. |
| **Excepciones** | **Al paso 4:**<br>1. Los datos introducidos no son válidos (ej. fechas incoherentes o descuento negativo).<br>2. El sistema muestra un mensaje de error advirtiendo del fallo.<br>3. Se retorna al paso 2 para que el Empleado corrija los datos. |
| **Importancia** | Muy importante |
| **Estado** | Aceptado |
| **Comentarios** | Es imprescindible que el recálculo de precios (`<<include>>`) no permita márgenes de beneficio negativos para la compañía. |
