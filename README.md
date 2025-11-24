# Spotify Churn Analysis Project

Este repositorio contiene un análisis completo de predicción de abandono (churn) para usuarios de Spotify, utilizando un dataset sintético. El proyecto abarca desde el análisis exploratorio de datos (EDA) hasta la comparación de modelos avanzados y análisis de reducción de dimensionalidad.

## Tabla de Contenidos

- [Descripción](#-descripción)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación y Configuración](#️-instalación-y-configuración)
- [Guía de Ejecución](#-guía-de-ejecución)
- [Notas Importantes](#️-notas-importantes)

## Descripción

El objetivo principal es predecir si un usuario cancelará su suscripción basándose en características como tiempo de escucha, tipo de suscripción, interacción con anuncios, etc. Se han implementado y comparado múltiples modelos de Machine Learning (XGBoost, SVM, Random Forest, etc.) y estrategias de balanceo de clases (SMOTE).

## 📂 Estructura del Proyecto

El flujo de trabajo está dividido en 5 notebooks secuenciales:

1. **`01-exploracion-eda.ipynb`**: Análisis Exploratorio de Datos (EDA). Carga de datos, análisis de distribuciones, correlaciones y detección de desbalance de clases.
2. **`02-estado-del-arte-plan.ipynb`**: Revisión del estado del arte y planificación de la estrategia de modelado.
3. **`03-preprocesamiento-fe.ipynb`**: Limpieza de datos, codificación de variables categóricas, escalado y Feature Engineering.
4. **`04-modelado-comparativo.ipynb`**: Entrenamiento y evaluación comparativa de múltiples modelos (Logistic Regression, SVM, KNN, Decision Tree, Random Forest, XGBoost) bajo diferentes estrategias (Baseline, Class Weight, SMOTE).
5. **`05-reduccion-dimension.ipynb`**: Análisis de técnicas de reducción de dimensionalidad (PCA, UMAP) y su impacto en el rendimiento de los mejores modelos.

Directorios adicionales:

- `data/`: Contiene el dataset (`spotify_churn_dataset.csv`), archivos intermedios y modelos entrenados (`.pkl`).
- `scripts/`: Scripts auxiliares de Python.

## Requisitos Previos

- **Conda** (Anaconda o Miniconda) instalado en su sistema.
- Git para clonar el repositorio.

## Instalación y Configuración

Siga estos pasos para configurar el entorno de desarrollo:

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/AndresGUIO2/Churn-analysis
   cd ChurnAnalisys
   ```

2. **Crear el entorno virtual con Conda:**

   El archivo `environment.yml` contiene todas las dependencias necesarias (Python 3.12, pandas, scikit-learn, xgboost, statsmodels, umap-learn, etc.).

   ```bash
   conda env create -f environment.yml
   ```

3. **Activar el entorno:**

   ```bash
   conda activate churn
   ```

##  Guía de Ejecución

Para reproducir los resultados, ejecute los notebooks en el siguiente orden estricto, ya que cada uno genera archivos que son consumidos por los siguientes:

1. Abra VS Code o Jupyter Lab en la raíz del proyecto.
2. Seleccione el kernel del entorno `churn` que acaba de crear.
3. Ejecute paso a paso:
   - `01-exploracion-eda.ipynb` (Descarga el dataset y genera análisis inicial)
   - `02-estado-del-arte-plan.ipynb` (Contexto teórico)
   - `03-preprocesamiento-fe.ipynb` (Genera datasets procesados en `data/`)
   - `04-modelado-comparativo.ipynb` (Entrena modelos y guarda los mejores en `data/`)
   - `05-reduccion-dimension.ipynb` (Analiza PCA/UMAP usando los modelos guardados)

## ⚠️ Notas Importantes

- **Dataset Sintético**: El dataset utilizado ([Spotify Analysis Dataset 2025](https://www.kaggle.com/datasets/nabihazahid/spotify-dataset-for-churn-analysis/data)) es generado sintéticamente. Los patrones y métricas de rendimiento (F1-Score ~0.40) no deben extrapolarse directamente a escenarios de producción con datos reales.
- **Modelos**: Los archivos de modelos entrenados (`.pkl`) se guardan en la carpeta `data/`. Si no existen, debe ejecutar el notebook `04` para generarlos.
