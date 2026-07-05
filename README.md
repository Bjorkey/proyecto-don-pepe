# 🛒 Almacén Don Pepe Argento - Análisis de Patrones de Compra

## Resumen Ejecutivo

Este proyecto utiliza el algoritmo **Apriori** para identificar patrones de compra conjunta en un supermercado de barrio. El análisis reveló **3 reglas de asociación clave** que permitirán diseñar promociones cruzadas y optimizar la disposición de productos en góndolas, con el objetivo de **aumentar el ticket promedio de los clientes en un 10-15%**.

---

## Descripción del Proyecto

Este proyecto aplica el algoritmo **Apriori** para descubrir patrones de compra conjunta en las ventas del supermercado de barrio **Almacén Don Pepe Argento**, ubicado en el oeste del Gran Buenos Aires.

El objetivo principal es identificar asociaciones entre productos para diseñar estrategias de marketing y merchandising efectivas, como promociones cruzadas y la optimización de la distribución en góndolas, con el fin último de aumentar el ticket promedio de los clientes.

---

## Metodología

El análisis se llevó a cabo siguiendo estas etapas:

1. **Carga y Exploración de Datos:** Se analizó el dataset `Groceries_dataset.csv` para comprender su estructura, volumen y características principales.
2. **Limpieza y Transformación de Datos:**
   - Eliminación de registros duplicados.
   - Conversión del campo `Date` al formato `datetime` para un posterior análisis temporal.
   - Agrupación de los datos por transacción (cliente + fecha) para crear un formato adecuado para el algoritmo Apriori.
3. **Aplicación del Algoritmo Apriori:**
   - Se utilizó la librería `mlxtend` para encontrar _itemsets_ frecuentes y generar reglas de asociación.
   - **Hiperparámetros configurados:**
     - **`min_support = 0.002 (0.2%)`**: Un umbral bajo, pero significativo, para capturar combinaciones de productos que son suficientemente frecuentes en un supermercado de barrio.
     - **`min_confidence = 0.5 (50%)`**: Se exige una alta confianza para asegurar que la regla sea comercialmente viable.
     - **`min_lift = 1.2`**: Filtro para seleccionar reglas con una asociación al menos un 20% más fuerte que el azar, garantizando un valor predictivo real.
4. **Generación y Filtrado de Reglas:** Se generaron reglas y se filtraron para destacar aquellas con mayor interés para el negocio.
5. **Visualización de Resultados:** Se crearon gráficos para comunicar de forma clara y efectiva los hallazgos.

---

## Resultados Clave y Estrategias de Negocio

De las 8 reglas generadas con un lift significativo (≥ 1.2), las tres más destacadas fueron seleccionadas para su implementación, junto con acciones comerciales concretas:

| Ranking | Regla                               | Lift | Support | Confidence | Estrategia de Negocio                                                                                               |
| :------ | :---------------------------------- | :--- | :------ | :--------- | :------------------------------------------------------------------------------------------------------------------ |
| **1**   | **{curd} → {sausage}**              | 1.45 | 0.29%   | 8.7%       | **Combo Cuajada + Salchicha** con 15% OFF. Ubicarlos juntos en la góndola de refrigerados.                          |
| **2**   | **{canned beer} → {brown bread}**   | 1.36 | 0.24%   | 6.4%       | **Pack Cerveza + Pan** con 12% OFF, enfocado en fines de semana. Reubicar el pan cerca de las cervezas.             |
| **3**   | **{sausage} → {frozen vegetables}** | 1.23 | 0.21%   | 3.4%       | **Cross-merchandising:** Ubicar las verduras congeladas cerca de las salchichas para incentivar la compra conjunta. |

---

## Estructura del Código

El proyecto está desarrollado en un notebook de Jupyter con una estructura clara:

- **1. Carga y Exploración de Datos:** Importación de librerías, carga del dataset y análisis inicial.
- **2. Tratamiento de Datos:** Limpieza, manejo de valores nulos, eliminación de duplicados y conversión de fechas.
- **3. Transformación para Apriori:** Creación de una columna de transacción y lista de productos por transacción.
- **4. Aplicación de Apriori:** Codificación de las transacciones, generación de _itemsets frecuentes_ y reglas de asociación.
- **5. Análisis y Selección de Reglas:** Filtrado y análisis de las reglas generadas para identificar las más valiosas.
- **6. Visualizaciones:** Gráficos que muestran los productos más vendidos y las reglas destacadas.
- **7. Resumen Ejecutivo:** Presentación de los resultados y estrategias de negocio en un formato claro.

---

## Archivos Generados

| Archivo                          | Descripción                                                                    |
| :------------------------------- | :----------------------------------------------------------------------------- |
| `reglas_destacadas_don_pepe.csv` | Lista completa de todas las reglas con un lift ≥ 1.2.                          |
| `top3_reglas_don_pepe.csv`       | Las tres reglas más importantes con sus acciones comerciales sugeridas.        |
| `top10_productos.png`            | Gráfico de barras con los 10 productos más vendidos.                           |
| `reglas_destacadas.png`          | Gráfico de barras horizontales que visualiza el lift de las reglas destacadas. |

---

## Cómo Ejecutar el Código

1. Clona este repositorio a tu máquina local.
2. Asegúrate de tener Python 3 y las librerías necesarias instaladas. Puedes instalar las dependencias con:
   ```bash
   pip install pandas numpy matplotlib seaborn mlxtend
   ```

👤 Autor
Tu Nombre: José Vásquez
📧 testing.it.api@gmail.com

🐙 GitHub: https://github.com/Bjorkey

📅 Fecha del Análisis
29 de Junio de 2026
