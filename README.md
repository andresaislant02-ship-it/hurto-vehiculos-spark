
# Análisis del hurto de motocicletas y automotores en Colombia (2010-2026) con Apache Spark

Trabajo individual de la Tarea 3 del curso Big Data (202016911), UNAD.

## Problema
¿Cómo ha evolucionado el hurto de motocicletas y automotores en Colombia
entre 2010 y 2026, en qué departamentos y municipios se concentra y con
qué modalidades se comete?

## Dataset
- Nombre: Reporte Hurto por Modalidades
- Fuente: Policía Nacional de Colombia (datos abiertos)
- Tamaño: 656.635 registros, 9 columnas, CSV UTF-8 (81 MB)
- Periodo: 01/01/2010 a 31/07/2026 (2026 es parcial)
- Cada fila es un hurto (CANTIDAD = 1). No se eliminan filas repetidas
  porque corresponden a eventos distintos.
- El archivo no se incluye en este repositorio por su tamaño; se descarga
  desde el portal de datos abiertos de la Policía Nacional.

## Contenido
- `analisis de hurto de vehiculos.ipynb`: cuaderno con el análisis en PySpark.
- `serie_anual.png`, `top_deptos.png`, `top_municipios.png`, `modalidades.png`: gráficos generados.

## Cómo ejecutarlo
1. Abrir el cuaderno en Google Colab.
2. Ejecutar `!pip install pyspark==3.5.3 pandas matplotlib`.
3. Subir el CSV desde el panel de archivos de Colab (icono de carpeta).
4. Ejecutar la celda de análisis. Genera cuatro gráficos PNG.

## Pasos del análisis
1. Carga del CSV con Spark y normalización de nombres de columna.
2. Limpieza: fechas (dd/MM/yyyy), nulos en género y grupo etario,
   unificación de modalidades de arma blanca, municipios sin "(CT)".
3. Transformación: año, mes y día de la semana.
4. Análisis exploratorio: por tipo, año, departamento, municipio,
   modalidad, día y género.
5. Visualización con matplotlib.

## Resultados principales
- 656.635 hurtos entre 2010 y julio de 2026: 75,8 % motocicletas y 24,2 % automotores.
- Año con más casos: 2023 (53.297). En 2020 hubo una caída del 21,2 % frente a 2019.
- Antioquia, Bogotá y Valle concentran el 55,1 % de los casos.
- Bogotá, Medellín y Cali concentran el 43,8 %.
- Modalidades principales: llave maestra (225.206), sin empleo de armas (193.700) y arma de fuego (190.560).
- En automotores predomina la llave maestra (44,1 %).
- 2026 es parcial (hasta el 31 de julio).

## Limitaciones
Son hechos reportados a la Policía, por lo que no incluyen los no denunciados,
y las cifras pueden variar.
