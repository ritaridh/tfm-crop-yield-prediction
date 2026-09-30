# Manifiesto de archivos

## Se incluyen

### Código
- 8 notebooks del flujo del TFM, adaptados para GitHub/Colab.
- copias `.py` de los notebooks cuando aportan trazabilidad.
- configuración de dependencias.

### Datos procesados
- dataset maestro definitivo 2017–2023.
- target MAPA.
- productos provinciales de ERA5-Land.
- productos provinciales de SoilGrids.
- productos provinciales de Sentinel-2.
- productos provinciales de EuroCrops.
- geometría provincial procesada cuando resulta compatible con los límites de GitHub.

### Resultados
- tablas finales.
- figuras finales.
- comparación ML vs DL.
- resultados del test independiente 2023.
- artefactos pequeños de inferencia del modelo LSTM.

### Datos originales
- Excel de MAPA utilizados en el análisis.

## No se incluyen

- DBF/SHP provinciales completos de EuroCrops por su tamaño.
- GeoTIFF originales completos de SoilGrids.
- copias históricas redundantes de ficheros `FINAL`, `CORREGIDO` o `RECONSTRUIDO` cuando existe una versión `DEFINITIVO`.
- archivos temporales de Colab.
- credenciales o ficheros de configuración privados (por ejemplo, `.cdsapirc`).

## Fuente de verdad

La carpeta de Google Drive del TFM se conserva sin modificaciones. Este repositorio contiene únicamente copias seleccionadas y adaptadas para publicación y reproducibilidad.
