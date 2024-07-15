# Predicción de Accidentes Cerebrovasculares

**Autores:** Lucas Aguilera, Claudio Bórquez, Josefa Fernández.

**Curso UC:** Minería de Datos.

## Problema
El proyecto aborda la predicción de la probabilidad de que un paciente sufra un accidente cerebrovascular en función de parámetros como el sexo, la edad, diversas enfermedades y el tabaquismo. Este enfoque optimiza el proceso médico al anticipar posibles eventos cerebrovasculares.

## Estructura del Repositorio
El repositorio está organizado de la siguiente manera:

- **data/**: Conjunto de datos utilizado para entrenar y evaluar los modelos.
- **Avance Proyecto/**: Código y presentación de avance.
- **Proyecto final/**: Código y presentación final.

## Librerías Utilizadas
- TensorFlow
- Keras
- Scikit-learn
- Pandas
- NumPy
- Matplotlib

## Datos Utilizados
Este proyecto utiliza datos clínicos centrados en accidentes cerebrovasculares, extraídos de Kaggle. El conjunto de datos consta de 5111 registros y 12 columnas.
- **Categoricos:**
  - genre
  - ever_married
  - work_type
  - residence_type
  - smoking_status
- **Numéricos:**
  - id
  - age
  - hypertension
  - heart_disease
  - avg_glucose_level
  - bmi
  - stroke

## Baseline
### Análisis de Datos
- 5110 registros y 12 columnas.
- Valores nulos en la columna BMI.
- Datos tanto numéricos como categóricos.
- Parcial escasez de datos.

### Preprocesamiento
- Limpieza de datos y normalización.
- Remover columnas innecesarias.
- Manejo de datos categóricos con One Hot Encoding.
- Normalización de variables.
- Manejo de valores nulos.

### Modelaje
#### División de Datos
- División del conjunto de datos en entrenamiento y prueba.

#### Modelos Utilizados
- MLP (Perceptrón Multicapa).
- Regresión Logística.

### Evaluación del Modelo
- Entrenamiento de modelos y evaluación de métricas.
- Métricas de evaluación para MLP y Regresión Logística.

### Análisis de Resultados
- Problemas con la clasificación y los modelos que no logran aprender patrones.
- Desbalance de clases.

### Feedback
- Desbalance de clases: aumentar datos o submuestrear la clase mayoritaria.
- Construir varios datasets y crear un ensemble.
- Descartar MLP y trabajar con Regresión Logística.

## Entrega Final
### Manejo del Desbalance de Datos
- Submuestreo de la clase mayoritaria (stroke = 0).

### Regresión Logística
- Entrenamiento de múltiples modelos de Regresión Logística.
- Creación de un ensemble con Voting Classifier, Gradient Boosting Classifier y Random Forest.

### Ensemble sin Submuestreo
- Uso de AdaBoost.
- Comparación de diferentes enfoques: MLP, RL, Voting Classifier, Gradient Boosting, Random Forest, y AdaBoost.

## Resultados
| Modelo | Accuracy | Precisión 0 vs 1 |
|--------|----------|------------------|
| MLP sin submuestreo | 0.95 | 0.95 vs 0.00 |
| RL sin submuestreo | 0.75 | 0.99 vs 0.15 |
| RL con sub. y ensemble Voting Classifier | 0.76 | 0.72 vs 0.82 |
| RL con sub. y ensemble Gradient Boosting Classifier | 0.70 | 0.66 vs 0.75 |
| Decision Trees ensamblado con Random Forest | 0.95 | 0.95 vs 0.33 |
| Ensemble AdaBoost sin sub. | 0.95 | 0.95 vs 0.25 |

## Referencias
- [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
