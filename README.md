# Predicción regional del rendimiento de cultivos mediante fusión de datos multifuente y técnicas de Machine Learning y Deep Learning

Repositorio asociado al Trabajo Fin de Máster de **Rita Isabel Duarte Henriques**, Máster Universitario en Big Data y Ciencia de Datos (curso 2025–2026).

## Resumen

El proyecto desarrolla y evalúa un sistema de predicción del rendimiento de **trigo blando** (`common_soft_wheat`) y **cebada** (`barley`) a escala provincial en España. Integra estadísticas agrícolas del MAPA con información de **EuroCrops, ERA5-Land, Sentinel-2 y SoilGrids**, y compara modelos de *Machine Learning* con arquitecturas de *Deep Learning* multirrama.

El periodo de estudio es **2017–2023**. Las campañas 2017–2022 se utilizan para desarrollo y validación temporal, mientras que **2023 se reserva como evaluación independiente**.

## Acceso rápido para revisión

Un lector puede revisar los principales elementos del TFM sin ejecutar código:

- [Dataset maestro definitivo](02_Datos_procesados/dataset_maestro_TFM_2017_2023_DEFINITIVO.csv)
- [Tablas finales](05_Resultados/Tablas_finales)
- [Comparación final ML vs DL](05_Resultados/Deep_Learning_Comparacion/Resumen_Final/comparacion_final_ML_DL.csv)
- [Figuras utilizadas en el bloque final del TFM](05_Resultados/Figuras_TFM)
- [Modelo LSTM final y artefactos de inferencia](models/DL)
- [Notebooks](notebooks)
- [Fuentes de datos](docs/DATA_SOURCES.md)
- [Notas de reproducibilidad](docs/REPRODUCIBILITY.md)

## Dataset definitivo

Archivo principal:

`02_Datos_procesados/dataset_maestro_TFM_2017_2023_DEFINITIVO.csv`

Características:

- **667 observaciones**
- **49 provincias**
- **7 campañas (2017–2023)**
- **340 observaciones de trigo blando**
- **327 observaciones de cebada**
- **48 entradas predictivas**
- **51 columnas totales**
- variable objetivo: `rendimiento_kg_ha`

## Resultados principales

Durante la validación temporal 2020–2022, los modelos de Machine Learning obtuvieron menor RMSE que las arquitecturas de Deep Learning evaluadas. Entre estas últimas, la **LSTM multirrama** presentó el mejor comportamiento y se seleccionó como arquitectura final.

En el test independiente de **2023**, la LSTM multirrama obtuvo:

- MAE: **572.012 kg/ha**
- RMSE: **714.903 kg/ha**
- R²: **0.527**
- sesgo medio predicción − observado: **195.395 kg/ha**

Como referencia, XGBoost obtuvo en 2023:

- MAE: **926.008 kg/ha**
- RMSE: **1102.817 kg/ha**
- R²: **−0.126**

Los valores completos se conservan en `05_Resultados/`.

## Notebooks

1. [01 · Exploración EuroCrops](notebooks/01_Exploracion_EuroCrops_ES.ipynb)
2. [02 · ERA5-Land](notebooks/02_ERA5_Land_Meteorologia.ipynb)
3. [03 · Propiedades edáficas](notebooks/03_Suelo_Propiedades_Edaficas.ipynb)
4. [04 · Sentinel-2 y EuroCrops](notebooks/04_Sentinel2_EuroCrops_Indices.ipynb)
5. [05 · Análisis exploratorio y preprocesado](notebooks/05_Analisis_Exploratorio_Preprocesado.ipynb)
6. [06 · Modelado predictivo](notebooks/06_Modelado_Predictivo.ipynb)
7. [07 · Deep Learning multirrama](notebooks/07_Deep_Learning_Multirrama.ipynb)
8. [Demo UI](notebooks/Demo_UI_Prediccion_Rendimiento_TFM.ipynb)

### Abrir en Google Colab

Las copias GitHub incorporan una celda inicial que clona automáticamente el repositorio si se abren directamente desde Colab.

- [Abrir notebook 05 en Colab](https://colab.research.google.com/github/ritaridh/tfm-crop-yield-prediction/blob/main/notebooks/05_Analisis_Exploratorio_Preprocesado.ipynb)
- [Abrir notebook 06 en Colab](https://colab.research.google.com/github/ritaridh/tfm-crop-yield-prediction/blob/main/notebooks/06_Modelado_Predictivo.ipynb)
- [Abrir notebook 07 en Colab](https://colab.research.google.com/github/ritaridh/tfm-crop-yield-prediction/blob/main/notebooks/07_Deep_Learning_Multirrama.ipynb)

## Reproducibilidad y trazabilidad

Los notebooks publicados son copias adaptadas para GitHub; **los originales de Google Drive no se han modificado**.

Los notebooks 01–04 documentan la adquisición y el preprocesado de fuentes originales. Parte de los datos brutos (EuroCrops provincial, GeoTIFF de SoilGrids, NetCDF de ERA5-Land y otros recursos voluminosos) no se almacena en GitHub.

Los notebooks 05 y 06 conservan también celdas históricas y de control utilizadas durante el desarrollo. Por ello, una ejecución completa de todas sus celdas puede requerir determinados archivos intermedios no incluidos en el repositorio. El **dataset maestro definitivo, los resultados finales, las figuras y los artefactos del modelo seleccionado sí están publicados** y permiten auditar el resultado final del trabajo.

La instalación completa de `requirements.txt` puede tardar varios minutos en un entorno nuevo porque incluye dependencias de ML, DL y procesamiento geoespacial.

## Estructura

```text
tfm-crop-yield-prediction/
├── README.md
├── requirements.txt
├── CITATION.cff
├── notebooks/
├── 01_Datos_originales/
│   └── MAPA/
├── 02_Datos_procesados/
├── 05_Resultados/
│   ├── Figuras_TFM/
│   ├── Tablas_finales/
│   └── Deep_Learning_Comparacion/
├── models/
│   ├── DL/
│   └── ML/
├── app/
└── docs/
```

## Aplicación demostrativa

Aplicación web:

https://tfm-rendimiento-cultivos.streamlit.app/

Repositorio de despliegue:

https://github.com/ritaridh/tfm-rendimiento-cultivos-demo

La aplicación utiliza el modelo **LSTM multirrama final** y se plantea como demostración del proceso de inferencia.

## Alcance

El modelo fue desarrollado y evaluado con rendimientos agregados a **escala provincial**. Por tanto, ni el repositorio ni la aplicación deben interpretarse como una herramienta validada para predicción a escala de parcela.
