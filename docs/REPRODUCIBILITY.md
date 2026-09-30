# Reproducibilidad

## Opción recomendada: Google Colab

Ejecutar en una celda nueva:

```python
!git clone https://github.com/ritaridh/tfm-crop-yield-prediction.git /content/TFM_Rendimiento_cultivos
%cd /content/TFM_Rendimiento_cultivos
!pip install -r requirements.txt
```

Después puede abrirse el notebook correspondiente desde la carpeta `notebooks/`.

Las copias de GitHub han sido adaptadas para utilizar `/content/TFM_Rendimiento_cultivos` y no dependen del Google Drive personal de la autora.

## Ruta reproducible principal

Para reproducir el bloque final sin descargar los datos geoespaciales brutos:

1. usar `02_Datos_procesados/dataset_maestro_TFM_2017_2023_DEFINITIVO.csv`;
2. ejecutar `notebooks/05_Analisis_Exploratorio_Preprocesado.ipynb`;
3. ejecutar `notebooks/06_Modelado_Predictivo.ipynb`;
4. ejecutar `notebooks/07_Deep_Learning_Multirrama.ipynb`.

## Notebooks de adquisición y preprocesado

Los notebooks 01–04 documentan el proceso completo, pero algunos pasos requieren datos externos que no se almacenan en GitHub por tamaño:

- EuroCrops provincial completo;
- ERA5-Land original;
- GeoTIFF originales de SoilGrids;
- determinadas operaciones de Sentinel-2 / servicios externos.

Las fuentes y rutas esperadas se describen en `DATA_SOURCES.md`.

## Versiones de entorno

Los modelos ML serializados para despliegue se generaron con las versiones fijadas en `requirements.txt`, especialmente:

- scikit-learn 1.6.1
- xgboost 3.3.0
- pandas 2.2.2
- numpy 2.0.2
- joblib 1.5.3

Usar versiones distintas de scikit-learn para cargar un archivo `.joblib` puede generar incompatibilidades.

## Test temporal

- desarrollo y validación: 2017–2022;
- test independiente: 2023;
- observaciones de desarrollo: 572;
- observaciones del test 2023: 95.

## Principio de trazabilidad

Los archivos del Google Drive original no se modifican durante la preparación de este repositorio. Las adaptaciones de rutas y ejecución se realizan únicamente en las copias publicadas en GitHub.
