```markdown
# Especificaciones Técnicas del Módulo de Inventario

## 1. Visión General
El módulo de inventario se encarga de la sincronización en tiempo real entre las tiendas físicas y el e-commerce.

## 2. Tecnologías
* **Lenguaje:** Python 3.10
* **Base de Datos:** PostgreSQL 14
* **Cache:** Redis

## 3. Estructura de Datos: Producto

| Campo | Tipo | Descripción |
| :--- | :--- | :--- |
| `sku` | String (PK) | Identificador único (e.g., "TSHIRT-BLK-L") |
| `qty_available` | Integer | Cantidad física disponible para venta |
| `reserved` | Integer | Cantidad en carritos de compra activos |
| `last_update` | Timestamp | Última sincronización con ERP |

> **Nota:** La cantidad `reserved` se libera automáticamente después de 15 minutos de inactividad.
```