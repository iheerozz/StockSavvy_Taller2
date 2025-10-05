📦 StockSavvy – Taller 2 (POO + SQLite)
**Integrantes:**
- Santiago Acosta
- Santiago Aragon
- Guillaume Garey

**Archivos principales:**
- Taller_2_StockSavvy_Grupo_1.ipynb
- inventario.db
- Diseño_Arquitectura_Grupo_1.pdf

🧠 1. Problema que resolvemos
Muchos pequeños importadores y negocios locales enfrentan dificultades para calcular correctamente el costo real de sus productos. A menudo subestiman gastos como el envío, el seguro o los aranceles, lo que afecta sus márgenes de ganancia. Además, no cuentan con herramientas simples para llevar un registro de inventario actualizado o registrar ventas de manera organizada.

Nuestro proyecto, **StockSavvy**, ofrece una solución práctica, automatizada y accesible. Combina los principios de la **Programación Orientada a Objetos (POO)** con una **base de datos SQLite** para crear un sistema que permite: 
- Calcular precios reales de productos nacionales e importados.
- Gestionar inventarios de forma eficiente.
- Registrar ventas y actualizar existencias automáticamente.
  
🧱 2. Diseño y Arquitectura
El sistema está diseñado bajo una arquitectura modular, aplicando los principios de **herencia** y **polimorfismo**, lo que permite extender o modificar fácilmente las funcionalidades.

A continuación, se presentan las clases principales del sistema:
- **Producto:** Clase base que contiene los atributos comunes a todos los productos: nombre, costo unitario, margen y cantidad.
- **ProductoNacional:** Hereda de Producto y añade el atributo 'fabricante'. Se usa para representar productos fabricados en el país.
- **ProductoImportado:** Hereda de Producto y añade los atributos 'país de origen', 'costo de envío' y 'tasa de arancel'. Permite calcular el costo real de importación considerando seguros y tarifas.
- **EstrategiaPrecio:** Clase auxiliar con un método estático que aplica polimorfismo para calcular precios según el tipo de producto.

📊 **Base de datos:**
El sistema utiliza SQLite como base de datos local para almacenar todos los productos. La tabla principal se llama `productos` y contiene las siguientes columnas:
`Nombre`, `Tipo`, `Costo Unitario`, `Cantidad`, `Margen`, `Fabricante`, `País Origen`, `Costo Envío`, `Tasa Arancel`.

Una de las funciones más útiles es que, si se agrega un producto con el mismo nombre, el sistema **actualiza la cantidad existente** en lugar de crear un registro duplicado.

⚙️ 3. Requisitos del sistema
- Python 3.10 o superior
- Librería estándar `sqlite3`
- Jupyter Notebook o Visual Studio Code para ejecutar el proyecto
- Archivo `inventario.db` en el mismo directorio del notebook
  
▶️ 4. Cómo ejecutar el programa
**Opción A — Desde Jupyter Notebook:**
1. Abre el archivo `Taller_2_StockSavvy_Grupo_1.ipynb`.
2. Asegúrate de que el archivo `inventario.db` está en el mismo directorio.
3. Ejecuta todas las celdas (Kernel → Restart & Run All).
4. Aparecerá un menú interactivo en la consola.
**Opción B — Desde terminal (opcional):**
Si existe una versión `.py` del proyecto, puede ejecutarse directamente desde la terminal:

`python Taller_2_StockSavvy_Grupo_1.py`

**Cálculos principales implementados:**
CIF = (costo_unitario * cantidad) + costo_envio + seguro
seguro = (mercancía + envío) * tasa_seguro%
arancel = CIF * tasa_arancel%
costo_total = CIF + arancel
precio_venta_total = costo_total * (1 + margen%)
precio_unitario = costo_unitario * (1 + margen%)
valor_inventario = precio_unitario * cantidad

🧩 5. Cómo funciona el código
El sistema está basado en una estructura de **clases y métodos** que interactúan con la base de datos. Cada producto se modela como un objeto con sus propios atributos y comportamientos, lo que permite mantener una lógica clara y escalable.
**Flujo general del programa:**
1. El usuario ejecuta el programa y accede a un menú interactivo.
2. Puede agregar productos nacionales o importados.
3. Los datos se guardan en la base de datos `inventario.db`.
4. Si se ingresa un producto repetido, el sistema suma su cantidad.
5. Es posible consultar el inventario completo o registrar ventas.
6. Al vender, se actualiza automáticamente la cantidad disponible y se calcula el valor de la venta.
   
📊 6. Interfaz de menú interactivo
El usuario puede elegir entre las siguientes opciones:
1️⃣ Agregar producto nacional
2️⃣ Agregar producto importado
3️⃣ Mostrar inventario completo
4️⃣ Ver valor total del inventario
5️⃣ Registrar una venta
6️⃣ Salir del sistema
Cada opción ejecuta funciones específicas que combinan la lógica del modelo de clases con consultas a la base de datos, mostrando resultados actualizados en tiempo real.

🎉 7. Resultados esperados
Cada vez que el usuario ejecuta una acción, el sistema muestra un resumen con el nombre del producto, su tipo, el precio unitario, la cantidad disponible y el valor total del inventario.

Esto facilita la toma de decisiones empresariales rápidas y precisas, sin necesidad de hojas de cálculo externas.
🤝 Créditos y aprendizajes del equipo
Este proyecto fue una oportunidad para poner en práctica conceptos clave de la programación moderna, combinando teoría y aplicación real.

Durante su desarrollo, el equipo aprendió a:
- Diseñar e implementar clases con **herencia y polimorfismo**.
- Conectar programas Python con una **base de datos SQLite**.
- Aplicar buenas prácticas de documentación y control de versiones en GitHub.

**StockSavvy** nos permitió comprender cómo la automatización puede optimizar la gestión de inventarios y apoyar la toma de decisiones en pequeños negocios.
