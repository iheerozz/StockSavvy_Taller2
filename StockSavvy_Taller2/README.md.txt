# 📦 StockSavvy – Taller 2 (POO + SQLite)

**Integrantes:**  
- Santiago Acosta  
- Santiago Arago  
- Guillaume Garey  

**Archivos principales:**  
- `Taller_2_Santiago_Acosta_Santiago_Arago_Guillaume_Garey.ipynb`  
- `inventario.db`  
- `Diseño_Arquitectura_Grupo_X.pdf`  

---

## 🧠 1. Problema que resolvemos

Pequeños importadores y negocios locales necesitan calcular el **costo real de sus productos** (costo de fábrica + envío + seguro + arancel) y definir un **precio de venta justo** con margen de ganancia.  
Además, requieren una forma fácil de **gestionar inventarios** y registrar ventas.  

**StockSavvy** automatiza estos cálculos usando Python, Programación Orientada a Objetos (POO) y una base de datos SQLite.

---

## 🧱 2. Diseño y Arquitectura

El sistema aplica **herencia** y **polimorfismo**.

### Clases principales:

| Clase | Descripción |
|--------|--------------|
| `Producto` | Clase base con atributos comunes (`nombre`, `costo_unitario`, `margen`, `cantidad`) |
| `ProductoNacional` | Hereda de `Producto`, añade el atributo `fabricante` |
| `ProductoImportado` | Hereda de `Producto`, añade `pais_origen`, `costo_envio`, `tasa_arancel` |
| `EstrategiaPrecio` | Clase con un método estático que usa polimorfismo para calcular precios según el tipo de producto |

📊 **Base de datos:**  
Tabla `productos` con columnas:  
`Nombre`, `Tipo`, `Costo Unitario`, `Cantidad`, `Margen`, `Fabricante`, `País Origen`, `Costo Envío`, `Tasa Arancel`.

> 🔁 Si se inserta un producto con el mismo nombre, el sistema **suma la cantidad existente** en lugar de duplicar el registro.

---

## ⚙️ 3. Requisitos del sistema

- Python 3.10 o superior  
- Librería estándar `sqlite3`  
- Jupyter Notebook o VS Code para ejecutar el proyecto  

---

## ▶️ 4. Cómo ejecutar el programa

### 🧩 Opción A — Desde Jupyter Notebook
1. Abre el archivo `Taller_2_Santiago_Acosta_Santiago_Arago_Guillaume_Garey.ipynb`
2. Asegúrate de que el archivo `inventario.db` está en el mismo directorio
3. Ejecuta todas las celdas (Kernel → Restart & Run All)
4. Aparecerá el menú del sistema:

