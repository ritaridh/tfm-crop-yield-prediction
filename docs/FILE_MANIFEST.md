# Manifiesto de archivos

## Incluidos

### Código
- 8 notebooks del flujo del TFM adaptados para GitHub/Colab.
- configuración de dependencias.
- documentación de fuentes y reproducibilidad.

Las exportaciones `.py` de Colab no se duplican para evitar mantener dos copias del mismo código.

### Datos procesados
- dataset maestro definitivo 2017–2023;
- target MAPA;
- productos provinciales de ERA5-Land;
- productos provinciales de SoilGrids;
- productos provinciales de Sentinel-2;
- productos provinciales de EuroCrops.

### Resultados
- tablas finales;
- figuras alineadas con el bloque final de la memoria en `05_Resultados/Figuras_TFM/`;
- resultados de comparación ML vs DL;
- métricas del test independiente 2023;
- artefactos de inferencia de la LSTM.

### Modelos
- modelo LSTM multirrama final;
- scalers e imputers asociados;
- configuración de inferencia;
- modelo XGBoost compacto utilizado como artefacto ML.

### Datos originales
- Excel de MAPA utilizados en el análisis.

## No incluidos

- DBF/SHP provinciales completos de EuroCrops;
- GeoTIFF originales de SoilGrids;
- NetCDF originales de ERA5-Land;
- `provincias_CNIG_50.gpkg`;
- versiones históricas redundantes cuando existe una versión definitiva;
- archivos temporales de Colab;
- credenciales o secretos.

## Fuente de verdad

Los originales del proyecto se conservan sin modificaciones. Este repositorio contiene copias seleccionadas y adaptadas para publicación, revisión y trazabilidad.
