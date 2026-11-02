# Análisis de Ventas con Python y Pandas

Proyecto de portafolio: limpieza y análisis de datos de ventas con Python y pandas en Google Colab.

## Objetivo

Tomar un archivo de ventas con datos sucios y convertirlo en un resumen confiable por producto, con visualización.

## Datos

Archivo `ventas_sucias.csv`: 11 filas y 5 columnas (fecha, producto, cantidad, precio, vendedor), con filas duplicadas y valores faltantes en precio y vendedor.

## Proceso

1. Carga del archivo con `pd.read_csv`.
2. Inspección: tamaño del datos con `shape` y valores faltantes con `isna().sum()` (precio: 2 faltantes, vendedor: 4 faltantes antes de deduplicar).
3. Limpieza: `drop_duplicates()` — de 11 filas quedan 8.
4. Tratamiento de faltantes: precios con la mediana (25.5) y vendedores con "Sin asignar".
5. Nueva columna `total = cantidad * precio`.
6. Agregación con `groupby("producto")["total"].sum()`.
7. Visualización: gráfico de barras de ventas por producto.

## Resultados

| Producto | Total |
|----------|-------|
| Zapatos  | 205.5 |
| Gorra    | 135.0 |
| Pantalón | 105.5 |
| Camisa   | 76.5  |

Hallazgo principal: Zapatos fue el producto con mayores ventas (205.5), seguido por Gorra (135.0).

## Tecnologías

Python, pandas, Matplotlib, Google Colab.

## Cómo correrlo

1. Abrir el cuaderno en Google Colab.
2. Subir `ventas_sucias.csv` al panel de archivos del cuaderno.
3. Correr las celdas en orden.

## Estructura del proyecto

- Cuaderno de Colab (`.ipynb`)
- `ventas_sucias.csv`
- Este `README.md`
