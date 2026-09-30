# Reproducibilidad

## Qué puede revisarse directamente

Sin ejecutar código, el repositorio permite auditar:

- el dataset maestro definitivo;
- las tablas y métricas finales;
- las figuras utilizadas en el bloque final del TFM;
- el modelo LSTM final;
- los scalers, imputers y configuración de inferencia;
- los notebooks que documentan el desarrollo.

## Google Colab

Los notebooks de GitHub incluyen una primera celda que clona automáticamente este repositorio en:

`/content/TFM_Rendimiento_cultivos`

Por tanto, pueden abrirse directamente desde GitHub en Google Colab.

La instalación completa de `requirements.txt` puede tardar varios minutos porque reúne dependencias de Machine Learning, Deep Learning y procesamiento geoespacial.

## Niveles de reproducibilidad

### 1. Resultado final e inferencia

Los elementos principales del resultado final están incluidos:

- `02_Datos_procesados/dataset_maestro_TFM_2017_2023_DEFINITIVO.csv`
- `models/DL/LSTM_multirrama_final.keras`
- scalers e imputers de la LSTM;
- `models/DL/config_inferencia_LSTM.json`;
- tablas y figuras finales.

### 2. Desarrollo y modelado

Los notebooks 05–07 conservan la trazabilidad del desarrollo. Los notebooks 05 y 06 incluyen también controles e iteraciones históricas, por lo que una ejecución completa de todas las celdas puede hacer referencia a archivos intermedios que no se publican cuando existe una versión definitiva o cuando se trata de datos voluminosos.

Esto no impide revisar el código, las decisiones metodológicas ni los resultados finales publicados.

### 3. Adquisición y preprocesado desde datos brutos

Los notebooks 01–04 documentan el procesamiento de las fuentes originales. Para reproducirlos íntegramente deben obtenerse algunos recursos externos:

- EuroCrops provincial completo;
- ERA5-Land original;
- GeoTIFF de SoilGrids;
- datos/servicios necesarios para Sentinel-2;
- geometría administrativa utilizada en determinados controles.

Las fuentes se describen en `DATA_SOURCES.md`.

## Entorno de los modelos serializados

Para los artefactos ML/Demo se conservaron las versiones:

- scikit-learn 1.6.1
- xgboost 3.3.0
- pandas 2.2.2
- numpy 2.0.2
- joblib 1.5.3

El repositorio de la demo fija además TensorFlow 2.21.0.

## Separación temporal

- desarrollo y validación: 2017–2022;
- test independiente: 2023;
- observaciones de desarrollo: 572;
- observaciones del test 2023: 95.

## Trazabilidad

La preparación de este repositorio se realiza sobre copias del código y de los resultados. Los archivos originales del Google Drive del proyecto no se modifican.
