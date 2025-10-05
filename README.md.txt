📦 StockSavvy – Taller 2 (POO + SQLite)

Integrantes:
- Santoiago Acosta
- Santigo Arago
- Guillaume Garey

Archivos principales:
- Taller_2_Santoiago_Acosta_Santigo_Arago_Guillaume_Garey.ipynb
- inventario.db
- Diseño_Arquitectura_Grupo_X.pdf

---

🧠 1. Problema que resolvemos
Pequeños importadores y negocios locales necesitan calcular el costo real de sus productos (costo de fábrica + envío + seguro + arancel) y definir un precio de venta justo con margen de ganancia. 
Además, requieren una forma fácil de gestionar inventarios y registrar ventas.

StockSavvy automatiza estos cálculos usando Python, Programación Orientada a Objetos (POO) y una base de datos SQLite.

---

🧱 2. Diseño y Arquitectura
El sistema aplica herencia y polimorfismo.

Clases principales:
- Producto: Clase base con atributos comunes (nombre, costo_unitario, margen, cantidad)
- ProductoNacional: Hereda de Producto, añade el atributo fabricante
- ProductoImportado: Hereda de Producto, añade pais_origen, costo_envio, tasa_arancel
- EstrategiaPrecio: Clase con un método estático que usa polimorfismo para calcular precios según el tipo de producto

Base de datos:
Tabla productos con columnas: Nombre, Tipo, Costo Unitario, Cantidad, Margen, Fabricante, País Origen, Costo Envío, Tasa Arancel.
Si se inserta un producto con el mismo nombre, el sistema suma la cantidad existente en lugar de duplicar el registro.

---

⚙️ 3. Requisitos del sistema
- Python 3.10 o superior
- Librería estándar sqlite3
- Jupyter Notebook o VS Code para ejecutar el proyecto

---

▶️ 4. Cómo ejecutar el programa
Opción A — Desde Jupyter Notebook
1. Abre el archivo Taller_2_Santoiago_Acosta_Santigo_Arago_Guillaume_Garey.ipynb
2. Asegúrate de que el archivo inventario.db está en el mismo directorio
3. Ejecuta todas las celdas (Kernel → Restart & Run All)
4. Aparecerá el menú del sistema

Opción B — Script (opcional)
Si incluyen una versión .py con el menú:
python src/app_inventario.py

Cálculos principales:
CIF = (costo_unitario * cantidad) + costo_envio + seguro
seguro = (mercancía + envío) * tasa_seguro%
arancel = CIF * tasa_arancel%
costo_total = CIF + arancel
precio_venta_total = costo_total * (1 + margen%)
precio_unitario = costo_unitario * (1 + margen%)
valor_inventario = precio_unitario * cantidad

---

⚙️ 5. ¿Cómo funciona el código?
El sistema StockSavvy combina la programación orientada a objetos (POO) con una base de datos SQLite, para crear una aplicación simple pero muy útil de gestión de inventario para productos nacionales e importados.

Estructura del código:
- Producto: Clase base. Contiene los datos comunes como el nombre, costo unitario, margen de ganancia y cantidad.
- ProductoNacional: Hereda de Producto y agrega el atributo fabricante. Representa productos hechos en el país.
- ProductoImportado: También hereda de Producto, pero incluye el país de origen, el costo de envío y el arancel.
- EstrategiaPrecio: Usa polimorfismo para calcular el precio dependiendo del tipo de producto.

Cálculos principales:
CIF = (costo_unitario * cantidad) + costo_envio + seguro
seguro = (mercancía + envío) * tasa_seguro%
arancel = CIF * tasa_arancel%
costo_total = CIF + arancel
precio_venta_total = costo_total * (1 + margen%)

Base de datos SQLite:
El archivo inventario.db guarda todos los productos en la tabla productos.
Cada vez que el usuario agrega un producto, registra una venta o consulta el inventario, el sistema interactúa directamente con la base de datos.
Si se agrega el mismo producto dos veces, no se duplica: el programa actualiza la cantidad existente.
Los datos persisten incluso después de cerrar el programa.

Interfaz por consola (menú interactivo):
1. Agregar producto nacional
2. Agregar producto importado
3. Mostrar inventario
4. Ver valor total del inventario
5. Registrar venta
6. Salir

Resultados y reportes:
Después de cada acción, el sistema muestra nombre y tipo de cada producto, precio unitario, cantidad disponible y valor total del inventario.

🎉 En resumen:
StockSavvy automatiza cálculos de importación y márgenes, guarda todo en SQLite, permite agregar, vender y consultar productos fácilmente, y aplica POO de forma clara y extensible.

🤝 Créditos y aprendizajes del equipo:
Este proyecto fue una oportunidad para aplicar de forma práctica los conceptos de POO, persistencia de datos, y estructura modular de software.
Durante el desarrollo, aprendimos a:
- Diseñar e implementar clases con herencia y polimorfismo.
- Usar bases de datos SQLite integradas en Python.
- Organizar un proyecto profesional con control de versiones y documentación.

StockSavvy nos permitió conectar la teoría de programación con un caso real de negocio, entendiendo cómo la automatización puede mejorar la gestión de inventarios.



