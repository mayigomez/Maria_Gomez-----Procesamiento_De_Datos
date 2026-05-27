

<h1 align="center">
  Procesamiento de Alto Volumen de Datos <br>
  Pontificia Universidad Javeriana <br>
  Facultad de Ingeniería de Sistemas <br>
  <img
    src="https://upload.wikimedia.org/wikipedia/commons/6/6c/Javeriana.svg"
    width="200"
    style="display:block; margin:auto; margin-top:12px;"
    alt="Logo Pontificia Universidad Javeriana">
</h1>
<h2 align="center">
Autores
</h2>

<h2 align="center">
   Andres Jacobo Urrea Ochoa  <br>
   Maria Clara Gomez Romero  <br>
   Juan Camilo Torres Meza <br>
</h2>

# Proyecto de Analítica Territorial y Educativa del ICFES con PySpark


---

# Descripción General del Proyecto

Este proyecto desarrolla un proceso integral de analítica de datos sobre información educativa, socioeconómica y de conectividad en Colombia utilizando Apache Spark y PySpark MLlib.

El objetivo principal consiste en analizar cómo factores asociados al acceso a internet, vulnerabilidad social, estrato socioeconómico y cobertura educativa influyen sobre el desempeño académico medido mediante resultados ICFES.

El proyecto combina:

- Procesamiento distribuido sobre Spark.
- Integración de múltiples datasets heterogéneos.
- Limpieza y transformación masiva de datos.
- Análisis exploratorio territorial.
- Respuesta a preguntas de negocio.
- Modelos supervisados y no supervisados con MLlib.

El enfoque del trabajo busca identificar patrones estructurales asociados a desigualdad educativa entre municipios con diferentes niveles de desarrollo y vulnerabilidad.

---

# Contenido del Proyecto

---

# 1. Preparación del Entorno

En esta primera etapa se importan las librerías necesarias para el procesamiento distribuido, análisis estadístico, visualización y modelado de Machine Learning.

Además, se inicializa la sesión de Apache Spark, indispensable para trabajar con grandes volúmenes de información de manera distribuida.

## Bibliotecas utilizadas

### Bibliotecas generales

- NumPy
- Pandas
- Matplotlib
- Seaborn

### Ecosistema PySpark

- SparkSession
- pyspark.sql.functions
- pyspark.sql.types
- Pipeline
- VectorAssembler
- StringIndexer
- StandardScaler
- Imputer

### Modelos MLlib

- Gradient Boosted Trees (GBTClassifier)
- Bisecting K-Means
- CrossValidator
- ParamGridBuilder

### Métricas y evaluación

- BinaryClassificationEvaluator
- MulticlassClassificationEvaluator
- ClusteringEvaluator
- Métricas complementarias desde Scikit-Learn

---

# 2. Integración de Datasets

El proyecto trabaja con múltiples fuentes de información provenientes de diferentes dominios relacionados con educación, conectividad y vulnerabilidad social.

La integración de datasets permite construir una visión territorial multidimensional sobre los factores que afectan el desempeño académico.

---

## 2.1 Dataset ICFES

Se utiliza información correspondiente a resultados de pruebas Saber 11.

### Variables analizadas

- Puntaje global.
- Lectura crítica.
- Matemáticas.
- Ciencias naturales.
- Sociales y ciudadanas.
- Inglés.
- Género.
- Tipo de colegio.
- Ubicación urbana/rural.
- Estrato socioeconómico.
- Departamento y municipio.

### Objetivo

Analizar diferencias en desempeño académico entre municipios, grupos poblacionales y condiciones socioeconómicas.

---

## 2.2 Dataset de Internet Fijo

Se utiliza información de conectividad asociada a acceso a internet fijo en diferentes municipios.

### Variables relevantes

- Cobertura de internet.
- Número de conexiones.
- Tecnologías predominantes.
- Evolución temporal de conectividad.

### Objetivo

Evaluar cómo el acceso a internet se relaciona con resultados educativos y desigualdad territorial.

---

## 2.3 Dataset de Indicadores Educativos

Incluye indicadores asociados a cobertura y permanencia escolar.

### Variables analizadas

- Cobertura neta.
- Cobertura en secundaria.
- Cobertura en educación media.
- Tasas de deserción.
- Indicadores de permanencia.

### Objetivo

Analizar si los municipios vulnerables presentan menores niveles de cobertura y permanencia educativa.

---

## 2.4 Dataset de Beneficiarios Estrategia UNIDOS

Se incorpora información sobre beneficiarios de programas sociales y población vulnerable.

### Objetivo

Relacionar vulnerabilidad social con desempeño académico y acceso a oportunidades educativas.

---

# 3. Limpieza, Transformación y Preparación de Datos

Antes de cualquier análisis o modelado, se ejecuta un proceso exhaustivo de limpieza y transformación.

Esta etapa es fundamental porque los datasets provienen de fuentes heterogéneas y contienen inconsistencias en formatos, nombres y tipos de datos.

---

## Actividades realizadas

### Normalización de nombres territoriales

Se estandarizan nombres de departamentos y municipios para garantizar compatibilidad entre datasets.

Esto incluye:

- Conversión a mayúsculas.
- Eliminación de espacios innecesarios.
- Corrección de problemas de encoding.
- Homogeneización de nombres territoriales.

---

### Conversión de tipos de datos

Se transforman columnas numéricas cargadas como texto hacia formatos compatibles con operaciones estadísticas y modelos de Machine Learning.

---

### Tratamiento de valores nulos

Se identifican valores faltantes y se aplican estrategias de imputación cuando resulta necesario.

---

### Extracción y transformación de variables

Se construyen nuevas variables derivadas, incluyendo:

- Estrato numérico.
- Variables binarias.
- Indicadores categóricos.
- Variables agregadas territoriales.

---

### Filtrado territorial

Se focaliza el análisis sobre municipios específicos definidos dentro de los grupos de comparación.

Esto permite realizar análisis diferenciales entre:

- Municipios de mayor desarrollo.
- Municipios con alta vulnerabilidad.

---

# 4. Análisis Exploratorio de Datos (EDA)

Se realiza un análisis exploratorio orientado a identificar patrones territoriales, relaciones estadísticas y desigualdades educativas.

El EDA combina análisis descriptivo, visualización y comparación entre grupos poblacionales.

---

# 4.1 Estadísticos Descriptivos

Se calculan métricas descriptivas para las principales variables cuantitativas.

### Métricas utilizadas

- Media.
- Mediana.
- Desviación estándar.
- Mínimos y máximos.
- Distribuciones de frecuencia.

---

# 4.2 Visualización de Puntajes ICFES

Se analizan distribuciones de puntajes promedio por área evaluada.

### Áreas estudiadas

- Lectura crítica.
- Matemáticas.
- Sociales y ciudadanas.
- Ciencias naturales.
- Inglés.
- Puntaje global.

### Objetivo

Identificar diferencias estructurales en desempeño académico.

---

# 4.3 Comparaciones Territoriales

Se comparan municipios pertenecientes a diferentes grupos de desarrollo.

## Variables comparadas

- Resultados ICFES.
- Cobertura educativa.
- Acceso a internet.
- Estrato socioeconómico.
- Vulnerabilidad social.

---

# 5. Respuesta a las Preguntas de Negocio

El proyecto desarrolla un conjunto de preguntas analíticas orientadas a evaluar desigualdad educativa y territorial.

---

## P1. Diferencias de puntaje ICFES y acceso a internet

Se analiza si existen diferencias significativas en los puntajes ICFES entre municipios de alto desarrollo y municipios vulnerables.

Además, se evalúa la relación entre desempeño académico y cobertura de internet fijo.

### Hallazgos buscados

- Brechas territoriales.
- Asociación entre conectividad y rendimiento.
- Impacto del acceso digital.

---

## P2. Cobertura educativa y desempeño ICFES

Se estudia si los municipios vulnerables presentan menor cobertura neta en secundaria y cómo esto se relaciona con resultados académicos.

---

## P3. Brecha entre colegios oficiales y no oficiales

Se analiza la diferencia de desempeño entre instituciones oficiales y privadas dentro de cada municipio.

### Objetivo

Identificar desigualdades institucionales en resultados educativos.

---

## P4. Estrato socioeconómico y desempeño académico

Se evalúa cómo cambia la relación entre estrato y resultados ICFES dependiendo del grupo territorial.

### Objetivo

Determinar si el impacto del nivel socioeconómico es más fuerte en municipios vulnerables.

---

## P5. Beneficiarios sociales y bajo desempeño

Se analiza si los municipios con mayor concentración de beneficiarios de programas sociales coinciden con menores resultados académicos.

---

## P6. Tecnologías de internet predominantes

Se estudia qué tecnologías de conectividad predominan en municipios vulnerables y cómo ha evolucionado su cobertura.

---

## P7. Brecha urbano-rural

Se compara el desempeño ICFES entre zonas urbanas y rurales.

### Objetivo

Evaluar desigualdades territoriales dentro de los mismos municipios.

---

## P8. Relación entre deserción, internet y desempeño

Se investiga si los municipios vulnerables presentan simultáneamente:

- Mayores tasas de deserción.
- Menor acceso a internet.
- Menores resultados ICFES.

---

# 6. Preparación de Datos para Machine Learning

Posteriormente se construye el pipeline necesario para aplicar modelos de aprendizaje automático sobre Spark MLlib.

---

## Transformaciones realizadas

### Indexación de variables categóricas

Se utiliza `StringIndexer` para convertir categorías textuales en índices numéricos.

---

### Vectorización de características

Se emplea `VectorAssembler` para construir el vector final de features requerido por MLlib.

---

### Escalamiento de variables

Se aplica `StandardScaler` sobre variables numéricas para estabilizar distribuciones y mejorar el comportamiento de ciertos algoritmos.

---

### División entrenamiento/prueba

El dataset se divide en conjuntos de entrenamiento y prueba.

Esto permite evaluar capacidad de generalización de los modelos.

---

# 7. Modelado Supervisado — Gradient Boosted Trees (GBT)

Se implementa un modelo supervisado basado en árboles potenciados mediante boosting.

## Objetivo

Clasificar o predecir patrones asociados al desempeño académico utilizando variables territoriales, sociales y educativas.

---

## Características del modelo

- Ensamble secuencial de árboles.
- Corrección iterativa de errores.
- Alta capacidad para modelar relaciones no lineales.
- Buen desempeño sobre datos complejos.

---

## Evaluación del modelo

Se calculan diferentes métricas para evaluar desempeño:

- Accuracy.
- Precision.
- Recall.
- F1-Score.
- AUC.
- Matriz de confusión.

---

## Validación cruzada

Se implementa búsqueda de hiperparámetros usando:

- `CrossValidator`
- `ParamGridBuilder`

El objetivo es optimizar el rendimiento del modelo y reducir riesgo de overfitting.

---

# 8. Modelado No Supervisado — Bisecting K-Means

Se aplica clustering mediante Bisecting K-Means.

## Objetivo

Identificar agrupamientos naturales entre municipios o estudiantes según características educativas y socioeconómicas.

---

## Características del algoritmo

- Variante jerárquica de K-Means.
- División progresiva de clusters.
- Escalable sobre grandes volúmenes de datos.

---

## Evaluación del clustering

Se utiliza `ClusteringEvaluator` para medir calidad de agrupamientos.

### Objetivos del análisis

- Detectar perfiles territoriales.
- Identificar municipios similares.
- Explorar patrones ocultos en los datos.

---

# 9. Visualizaciones y Resultados

A lo largo del proyecto se desarrollan múltiples visualizaciones para facilitar la interpretación de los hallazgos.

## Visualizaciones utilizadas

- Histogramas.
- Gráficas de barras.
- Diagramas comparativos.
- Distribuciones territoriales.
- Matrices de confusión.
- Comparaciones entre municipios.

---

# 10. Conclusiones Finales

## Hallazgos principales

- Existen diferencias significativas entre municipios vulnerables y municipios de mayor desarrollo.
- El acceso a internet muestra relación con desempeño académico.
- Factores socioeconómicos influyen directamente sobre resultados ICFES.
- Las brechas urbano-rurales continúan siendo relevantes.
- Los modelos de Machine Learning permiten capturar patrones complejos asociados a desigualdad territorial.

---

## Aprendizajes técnicos

- Procesamiento distribuido con Spark.
- Integración de múltiples datasets.
- Construcción de pipelines MLlib.
- Análisis exploratorio territorial.
- Aplicación de modelos supervisados y no supervisados.
- Evaluación de desempeño y clustering.

---

# Tecnologías Utilizadas

- Apache Spark
- PySpark
- PySpark MLlib
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

# Referencias

- Apache Software Foundation. (2024). *Apache Spark Documentation.* Recuperado de: https://spark.apache.org/docs/latest/

- Apache Software Foundation. (2024). *PySpark MLlib Guide.* Recuperado de: https://spark.apache.org/docs/latest/ml-guide.html

- Pedregosa, F., et al. (2011). *Scikit-learn: Machine Learning in Python.* Journal of Machine Learning Research, 12, 2825–2830.

- Han, J., Kamber, M., & Pei, J. (2012). *Data Mining: Concepts and Techniques.* Morgan Kaufmann.

- Dataset ICFES Saber 11 — Gobierno de Colombia.

- Ministerio TIC Colombia — Datos de conectividad e internet.

- Ministerio de Educación Nacional de Colombia — Indicadores educativos.

- Departamento Administrativo Nacional de Estadística (DANE).

