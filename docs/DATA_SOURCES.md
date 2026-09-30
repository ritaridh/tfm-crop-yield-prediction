# Fuentes de datos

Este documento identifica las fuentes externas utilizadas en el TFM y distingue entre los datos brutos originales y los productos procesados publicados en GitHub.

## MAPA

Fuente: Ministerio de Agricultura, Pesca y Alimentación (España), estadísticas de superficies, producciones y rendimientos de cultivos.

Portal oficial:
https://www.mapa.gob.es/es/estadistica/temas/estadisticas-agrarias/agricultura/superficies-producciones-anuales-cultivos/

Se incluyen los Excel utilizados para trigo y cebada entre 2017 y 2023, además de algunos archivos empleados durante la exploración inicial de cultivos candidatos.

## EuroCrops

Fuente utilizada: EuroCrops, registro Zenodo 14094196.

https://zenodo.org/records/14094196

Los archivos provinciales completos no se incluyen debido a su gran tamaño. Los productos provinciales derivados sí están en `02_Datos_procesados/`.

## ERA5-Land

Fuente: Copernicus Climate Change Service / Climate Data Store.

https://cds.climate.copernicus.eu/datasets/reanalysis-era5-land

Los NetCDF originales no se publican en el repositorio principal. Se incluyen las tablas provinciales definitivas utilizadas en el dataset maestro.

## SoilGrids

Fuente: ISRIC – World Soil Information, SoilGrids 2.0.

https://soilgrids.org/
https://docs.isric.org/globaldata/soilgrids/

Los GeoTIFF originales no se incluyen por tamaño. Se publican las tablas provinciales derivadas.

## Sentinel-2

Fuente: Copernicus Sentinel-2 / Copernicus Data Space Ecosystem.

https://dataspace.copernicus.eu/data-collections/copernicus-sentinel-missions/sentinel-2

Se incluyen los productos tabulares provinciales utilizados en el dataset maestro.

## Límites administrativos

La geometría provincial procesada `provincias_CNIG_50.gpkg` se utilizó en determinadas etapas geoespaciales y de control, pero no se publica en este repositorio. No es necesaria para inspeccionar el dataset maestro, las métricas finales ni los artefactos de inferencia.

## Nota

El repositorio está orientado a la trazabilidad del flujo y a la auditoría del resultado final. La reproducción íntegra desde todas las fuentes brutas requiere descargar los recursos externos indicados anteriormente.
