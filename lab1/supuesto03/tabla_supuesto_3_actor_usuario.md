# Supuesto 3

### Opción 1: Tabla en Markdown estándar (2 columnas)

| **Actor** | **Usuario** (**ACT 001**) |
| :--- | :--- |
| **Desc** | Es el usuario general que accede a las funcionalidades comunes básicas. |
| **Caract** | Comparte funciones con los demás usuarios que heredan de él. |
| **Relaciones** | Relación de Herencia de Cliente y empleado al usuario. |
| **Referencias** | El usuario puede consultar disponibilidades que a su vez le muestra el calendario y busca elementos. |
| **Autor** | Marcos Sánchez García &nbsp;\|&nbsp; **Fecha:** 15/10/2026 &nbsp;\|&nbsp; **Versión:** 1.0 |

---

### Opción 2: Tabla con columnas divididas (Formato exacto del cuaderno)

> *Nota: Como Markdown básico no permite combinar celdas (`colspan`), esta versión utiliza etiquetas HTML estándar compatibles con GitHub y VS Code para replicar exactamente la estructura de cajas de tu dibujo.*

<table>
  <tr>
    <td><b>Actor</b></td>
    <td colspan="4">Usuario</td>
    <td><b>ACT 001</b></td>
  </tr>
  <tr>
    <td><b>Desc</b></td>
    <td colspan="5">Es el usuario general que accede a las funcionalidades comunes básicas.</td>
  </tr>
  <tr>
    <td><b>Caract</b></td>
    <td colspan="5">Comparte funciones con los demás usuarios que heredan de él.</td>
  </tr>
  <tr>
    <td><b>Relaciones</b></td>
    <td colspan="5">Relación de Herencia de Cliente y empleado al usuario.</td>
  </tr>
  <tr>
    <td><b>Referencias</b></td>
    <td colspan="5">El usuario puede consultar disponibilidades que a su vez le muestra el calendario y busca elementos.</td>
  </tr>
  <tr>
    <td><b>Autor</b></td>
    <td>Marcos Sánchez García</td>
    <td><b>Fecha</b></td>
    <td>15/10/2026</td>
    <td><b>Versión</b></td>
    <td>1.0</td>
  </tr>
</table>