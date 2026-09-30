# Predicción regional del rendimiento de cultivos mediante fusión de datos multimodales

Repositorio asociado al Trabajo Fin de Máster de **Rita Isabel Duarte Henriques**.

## Objetivo

Desarrollar y comparar modelos de *Machine Learning* y *Deep Learning* para predecir el rendimiento agrícola a escala provincial en España mediante la integración de información:

- estadística agrícola oficial de MAPA,
- coberturas de cultivo de EuroCrops,
- meteorología de ERA5-Land,
- propiedades edáficas de SoilGrids,
- índices espectrales derivados de Sentinel-2.

El estudio se centra en **trigo blando** (`common_soft_wheat`) y **cebada** (`barley`) durante el periodo **2017–2023**.

## Dataset final

El archivo principal reproducible es:

`02_Datos_procesados/dataset_maestro_TFM_2017_2023_DEFINITIVO.csv`

Características del dataset final:

- **667 observaciones**
- **51 columnas**
- **49 provincias**
- **7 campañas (2017–2023)**
- **340 observaciones de trigo blando**
- **327 observaciones de cebada**
- variable objetivo: `rendimiento_kg_ha`

## Estrategia de validación

Se separó el periodo **2017–2022** para desarrollo y validación temporal, reservando **2023** como test independiente.

### Machine Learning

En validación temporal, el ensemble RF + XGB 50/50 obtuvo:

- MAE medio: **563.744 kg/ha**
- RMSE medio: **682.161 kg/ha**
- R² medio: **0.433**

En el test independiente de 2023, XGBoost obtuvo:

- MAE: **926.008 kg/ha**
- RMSE: **1102.817 kg/ha**
- R²: **-0.126**

### Deep Learning

El modelo multirrama LSTM final, entrenado con 2017–2022 y evaluado sobre 2023, obtuvo:

- MAE: **572.012 kg/ha**
- RMSE: **714.903 kg/ha**
- R²: **0.527**
- sesgo medio predicción - observado: **195.395 kg/ha**

Los resultados completos están disponibles en `05_Resultados/`.

## Estructura del repositorio

```text
tfm-crop-yield-prediction/
├── README.md
├── requirements.txt
├── notebooks/
├── scripts/
├── 01_Datos_originales/
│   ├── MAPA/
│   └── README.md
├── 02_Datos_procesados/
├── 05_Resultados/
├── models/
└── docs/
    ├── DATA_SOURCES.md
    ├── REPRODUCIBILITY.md
    └── FILE_MANIFEST.md
```

Los datos brutos de gran tamaño (por ejemplo, EuroCrops provincial completo y los GeoTIFF originales de SoilGrids) no se incluyen en el repositorio. Se documentan sus fuentes y el procedimiento de obtención en `docs/DATA_SOURCES.md`.

## Ejecución en Google Colab

La forma recomendada es clonar el repositorio en la ruta utilizada por las copias GitHub de los notebooks:

```python
!git clone https://github.com/ritaridh/tfm-crop-yield-prediction.git /content/TFM_Rendimiento_cultivos
%cd /content/TFM_Rendimiento_cultivos
!pip install -r requirements.txt
```

Las copias de los notebooks incluidas en GitHub están adaptadas para trabajar con el repositorio y **no requieren montar Google Drive**.

## Notebooks

1. `01_Exploracion_EuroCrops_ES.ipynb`
2. `02_ERA5_Land_Meteorologia.ipynb`
3. `03_Suelo_Propiedades_Edaficas.ipynb`
4. `04_Sentinel2_EuroCrops_Indices.ipynb`
5. `05_Analisis_Exploratorio_Preprocesado.ipynb`
6. `06_Modelado_Predictivo.ipynb`
7. `07_Deep_Learning_Multirrama.ipynb`
8. `Demo_UI_Prediccion_Rendimiento_TFM.ipynb`

Los notebooks 01–04 documentan la adquisición y el preprocesado de las fuentes originales. Algunos bloques requieren descargar previamente datos externos de gran tamaño. Los notebooks 05–07 pueden partir del dataset maestro definitivo incluido en el repositorio.

## Demo

Aplicación web:

https://tfm-rendimiento-cultivos.streamlit.app/

Repositorio de despliegue:

https://github.com/ritaridh/tfm-rendimiento-cultivos-demo

## Reproducibilidad

Las instrucciones detalladas de reproducción, dependencias, datos incluidos/no incluidos y limitaciones están en:

- `docs/REPRODUCIBILITY.md`
- `docs/DATA_SOURCES.md`
- `docs/FILE_MANIFEST.md`

## Alcance

Este repositorio reproduce el flujo desarrollado en el TFM. Los datos y modelos operan a **escala provincial** y la demo tiene carácter experimental; no debe interpretarse como una herramienta operacional de predicción a escala de parcela.
