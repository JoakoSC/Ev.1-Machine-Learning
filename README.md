# Ev.1 Machine Learning - Predicción de Popularidad de Canciones

## 1. Descripción del problema de negocio

Una empresa dedicada a la distribución y análisis de contenido musical en plataformas digitales busca comprender qué características de las canciones pueden estar relacionadas con su nivel de popularidad.

El objetivo del proyecto es analizar un conjunto de datos de Spotify que contiene información sobre canciones, artistas, géneros y distintas características musicales, con el fin de identificar patrones relevantes y desarrollar modelos de Machine Learning capaces de estimar la variable `popularity`.

---

## 2. Objetivos del proyecto

### Objetivo general

Analizar las características musicales de canciones disponibles en Spotify para identificar su relación con la popularidad y desarrollar modelos capaces de estimar el nivel de popularidad de una canción.

### Objetivos específicos

- Explorar la estructura y características del conjunto de datos.
- Identificar valores faltantes, registros duplicados y posibles valores atípicos.
- Analizar la relación entre las características musicales y la variable `popularity`.
- Analizar diferencias de popularidad entre distintos géneros musicales.
- Preparar y transformar los datos para su utilización en modelos de Machine Learning.
- Comparar distintos algoritmos de regresión.
- Evaluar posibles sesgos, consideraciones éticas y aspectos relacionados con privacidad.

---

## 3. KPIs del proyecto

Los principales indicadores definidos para apoyar el análisis son:

| KPI | Descripción |
|---|---|
| Popularidad promedio | Permite conocer el nivel promedio de popularidad de las canciones del dataset. |
| Popularidad promedio por género | Permite comparar el comportamiento de la popularidad entre distintos géneros musicales. |
| Características relacionadas con popularidad | Permite identificar variables que presentan algún nivel de relación con `popularity`. |
| Calidad del dataset | Considera valores faltantes, duplicados y posibles anomalías. |
| Error de predicción | Permite evaluar el rendimiento de los modelos desarrollados. |

---

## 4. Fuente de datos

El proyecto utiliza el archivo:

`Spotify_Tracks_Dataset.csv`

El conjunto de datos corresponde a una fuente estructurada en formato CSV y contiene información relacionada con canciones disponibles en Spotify.

Entre sus principales variables se encuentran:

- `track_id`
- `artists`
- `album_name`
- `track_name`
- `popularity`
- `duration_ms`
- `explicit`
- `danceability`
- `energy`
- `loudness`
- `speechiness`
- `acousticness`
- `instrumentalness`
- `liveness`
- `valence`
- `tempo`
- `track_genre`

La variable objetivo utilizada para el modelamiento es `popularity`.

---

## 5. Análisis Exploratorio de Datos (EDA)

Durante el análisis exploratorio se realizaron distintas revisiones sobre el conjunto de datos:

- Dimensiones del dataset.
- Tipos de variables.
- Estadísticas descriptivas.
- Valores faltantes.
- Registros duplicados.
- Distribución de la variable `popularity`.
- Distribución de las principales características musicales.
- Identificación de posibles valores atípicos mediante el rango intercuartílico.
- Análisis de correlaciones entre variables numéricas y `popularity`.
- Análisis de popularidad según género musical.

El análisis de correlaciones mostró que las características musicales presentan relaciones lineales débiles con la popularidad de forma individual.

Por otra parte, el análisis por género mostró diferencias considerables en la popularidad promedio entre distintos géneros musicales, lo que indica que `track_genre` puede aportar información relevante al análisis.

---

## 6. Preparación de los datos

La preparación de los datos incluyó:

- Eliminación de la columna `Unnamed: 0`, correspondiente a un índice generado durante la exportación del dataset.
- Tratamiento de valores faltantes presentes en variables de texto.
- Revisión de registros duplicados.
- Análisis de canciones asociadas a más de un género musical.
- Conversión de variables necesarias para el modelamiento.
- Codificación de variables categóricas.
- Separación entre variables predictoras (`X`) y variable objetivo (`y`).
- División del conjunto de datos en entrenamiento y prueba.
- Estandarización de variables numéricas cuando fue necesario.

Durante el análisis de duplicados se detectó que una misma canción puede aparecer asociada a distintos géneros musicales. Por esta razón, los registros repetidos por `track_id` fueron analizados antes de ser tratados automáticamente como duplicados.

---

## 7. Modelos de Machine Learning

Debido a que la variable objetivo `popularity` es numérica, se utilizaron algoritmos de regresión.

Los modelos evaluados fueron:

1. Regresión Lineal.
2. Árbol de Decisión para Regresión.
3. Random Forest Regressor.

Para evaluar su desempeño se utilizaron las métricas:

- MAE
- RMSE
- R²

### Resultados

| Modelo | MAE | RMSE | R² |
|---|---:|---:|---:|
| Regresión Lineal | 12.01 | 16.85 | 0.3209 |
| Random Forest | 14.55 | 18.40 | 0.1905 |
| Árbol de Decisión | 15.24 | 19.00 | 0.1365 |

Entre los modelos evaluados, la Regresión Lineal presentó el mejor desempeño en las tres métricas utilizadas.

---

## 8. Metodología utilizada - CRISP-DM

El desarrollo del proyecto se organizó utilizando como referencia la metodología CRISP-DM.

### Comprensión del negocio

Se definió la necesidad de comprender qué características de las canciones pueden estar relacionadas con su popularidad.

### Comprensión de los datos

Se realizó un análisis exploratorio para conocer la estructura, calidad, distribuciones, anomalías y relaciones presentes en el dataset.

### Preparación de los datos

Se realizaron procesos de limpieza, tratamiento de valores faltantes, análisis de duplicados, transformación y preparación de variables.

### Modelado

Se utilizaron tres algoritmos de regresión:

- Regresión Lineal.
- Árbol de Decisión.
- Random Forest.

### Evaluación

Los modelos fueron comparados utilizando MAE, RMSE y R².

### Despliegue

El proyecto corresponde a una etapa académica y no contempla actualmente el despliegue del modelo en un entorno productivo.

---

## 9. Ética, privacidad y sesgos

El dataset utilizado contiene principalmente información relacionada con canciones, artistas y características musicales, por lo que no utiliza información personal de los oyentes.

Sin embargo, pueden existir sesgos relacionados con:

- Diferencias de representación entre géneros musicales.
- Mayor exposición de determinados artistas.
- Popularidad histórica de las canciones.
- Diferencias en la cantidad de canciones disponibles por categoría.

Por esta razón, los resultados obtenidos deben interpretarse como asociaciones presentes en el conjunto de datos y no como relaciones causales.

---

## 10. Estructura del proyecto

```text
EP1_Machine_Learning_Grupo6/
│
├── README.md
├── EP1_Machine_Learning.ipynb
│
├── data/
│   └── Spotify_Tracks_Dataset.csv
│
└── docs/
    └── EP1_Instrucciones_y_Pauta.pdf
