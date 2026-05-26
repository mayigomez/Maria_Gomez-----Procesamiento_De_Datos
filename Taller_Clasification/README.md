# Taller de Métricas y Machine Learning con PySpark
* **Universidad:** Pontificia Universidad Javeriana
* **Asignatura:** Procesamiento de Alto Volumen de Datos
* **Tema:** Métricas y Machine Learning con PySpark
* **Autor:** María Clara Gómez Romero

## Descripción

Este taller desarrolla un análisis exploratorio de datos y un proceso de clasificación utilizando herramientas de Big Data con PySpark. El trabajo fue realizado en el contexto de la asignatura de Procesamiento de Alto Volumen de Datos de la Pontificia Universidad Javeriana.

El objetivo principal consiste en analizar un dataset relacionado con campañas de marketing bancario y construir modelos de Machine Learning que permitan predecir si un cliente aceptará o no un depósito a plazo fijo.

---

## Objetivos del Taller

* Implementar un flujo de trabajo de análisis de datos utilizando PySpark.
* Realizar limpieza y validación de calidad de datos.
* Explorar variables numéricas y categóricas mediante estadísticas y visualizaciones.
* Preparar los datos para modelos de Machine Learning.
* Construir modelos de clasificación.
* Evaluar el desempeño de los modelos mediante métricas.
* Comparar resultados para seleccionar el modelo con mejor rendimiento.

---

## Dataset Utilizado

El dataset corresponde a campañas de marketing directo realizadas por una entidad bancaria. El objetivo es predecir la variable objetivo (**y**), la cual indica si el cliente aceptó o no un depósito a plazo fijo.

### Variables principales

* **AGE:** Edad del cliente.
* **JOB:** Tipo de ocupación.
* **MARITAL:** Estado civil.
* **EDUCATION:** Nivel educativo.
* **BALANCE:** Balance promedio anual.
* **HOUSING:** Crédito hipotecario.
* **LOAN:** Préstamo personal.
* **DURATION:** Duración de la llamada.
* **CAMPAIGN:** Número de contactos realizados.
* **PDAYS:** Días desde el último contacto.
* **PREVIOUS:** Número de contactos previos.
* **Y:** Variable objetivo.

---

## Tecnologías Utilizadas

Este proyecto fue desarrollado utilizando las siguientes herramientas y bibliotecas:

* Python
* PySpark
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Spark MLlib

---

## Proceso Desarrollado

### 1. Importación de bibliotecas y creación de la sesión Spark

Se configuró el entorno de trabajo utilizando PySpark y las librerías necesarias para análisis y visualización de datos.

### 2. Carga del dataset

Se realizó la lectura del conjunto de datos para iniciar el análisis exploratorio.

### 3. Análisis exploratorio de datos (EDA)

Durante esta etapa se analizaron:

* Distribución de la variable objetivo.
* Variables categóricas.
* Variables numéricas.
* Histogramas.
* Diagramas Boxplot.
* Valores atípicos.
* Desbalance de clases.

### 4. Calidad de los datos

Se verificó:

* Valores nulos.
* Tipos de datos.
* Consistencia de la información.
* Distribución de categorías.

### 5. Preparación de datos

Se aplicaron procesos de:
* Escalamiento de variables.
* División entre datos de entrenamiento y prueba.

### 6. Construcción de modelos de clasificación

Se implementaron modelos de Machine Learning utilizando PySpark MLlib para predecir la aceptación del depósito a plazo fijo.

### 7. Evaluación de métricas

Se evaluó el rendimiento de los modelos utilizando métricas como:

* Accuracy
* Precision
* Recall
* F1-Score
* Matriz de confusión

---

## Principales Hallazgos

* El dataset presenta un desbalance importante entre las clases “yes” y “no”.
* La mayoría de los clientes tienen balances bajos o cercanos a cero.
* La duración de la llamada tiene una fuerte relación con la aceptación del depósito.
* Existen valores atípicos en variables como balance y duration.
* Los modelos de clasificación permiten identificar patrones relevantes en el comportamiento de los clientes.

---

## Resultados Esperados

Al ejecutar el notebook se obtendrá:

* Exploración visual y estadística del dataset.
* Preparación de datos para Machine Learning.
* Entrenamiento de modelos de clasificación.
* Evaluación comparativa de métricas.
* Interpretación de resultados.

---

## Conclusiones

El desarrollo del taller permitió aplicar técnicas de análisis de datos y Machine Learning sobre grandes volúmenes de información utilizando PySpark. Además, se evidenció la importancia de la preparación de datos y la evaluación de métricas para obtener modelos de clasificación confiables y útiles para la toma de decisiones.

