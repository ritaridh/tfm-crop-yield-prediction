# Fuentes de datos

Este documento identifica las fuentes externas utilizadas en el TFM y distingue entre los datos brutos originales y los productos procesados incluidos en el repositorio.

## MAPA

Fuente: Ministerio de Agricultura, Pesca y Alimentación (España), estadísticas de superficies, producciones y rendimientos de cultivos.

Portal oficial:
https://www.mapa.gob.es/es/estadistica/temas/estadisticas-agrarias/agricultura/superficies-producciones-anuales-cultivos/

En el repositorio se incluyen los ficheros Excel utilizados para trigo y cebada entre 2017 y 2023, además de algunos ficheros empleados durante la exploración inicial de cultivos candidatos.

## EuroCrops

Fuente utilizada: EuroCrops, registro Zenodo 14094196, versión que incorporó España completa.

https://zenodo.org/records/14094196

Los archivos provinciales completos no se incluyen en GitHub debido a su gran tamaño. Los productos provinciales derivados sí se incluyen en `02_Datos_procesados/`.

## ERA5-Land

Fuente: Copernicus Climate Change Service / Climate Data Store.

https://cds.climate.copernicus.eu/datasets/reanalysis-era5-land

Los NetCDF originales no son necesarios para reproducir el bloque final de modelado. Se incluyen las tablas de características meteorológicas provinciales definitivas.

## SoilGrids

Fuente: ISRIC – World Soil Information, SoilGrids 2.0.

https://soilgrids.org/
https://docs.isric.org/globaldata/soilgrids/

Los GeoTIFF originales no se incluyen debido a su tamaño. Se incluyen las tablas provinciales derivadas.

## Sentinel-2

Fuente: Copernicus Sentinel-2 / Copernicus Data Space Ecosystem.

https://dataspace.copernicus.eu/data-collections/copernicus-sentinel-missions/sentinel-2

Se incluyen los productos tabulares provinciales utilizados en el dataset maestro.

## Límites administrativos

La geometría provincial procesada empleada por los notebooks se conserva como `02_Datos_procesados/provincias_CNIG_50.gpkg` cuando el tamaño del repositorio lo permite.

## Nota de reproducibilidad

La ausencia de algunos datos brutos de gran tamaño no afecta a la reproducción de los análisis finales de los notebooks 05–07, que parten de los productos procesados y del dataset maestro definitivo.
