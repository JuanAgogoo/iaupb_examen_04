# Examen 4 — Clustering No Supervisado  

**Curso:** Inteligencia Artificial  
**Estudiante:** Juan José Arango  
**Fecha:** 17 de abril de 2026  
**Docente:** Juan Darío Rodas  

---

## 1. Descripción General

El presente trabajo tiene como propósito aplicar técnicas de aprendizaje no supervisado, específicamente algoritmos de clustering, con el fin de identificar patrones y estructuras subyacentes en un conjunto de datos sin el uso de etiquetas durante el proceso de entrenamiento.

Se utiliza el dataset *Palmer Penguins*, el cual contiene información morfológica de distintas especies de pingüinos. Este conjunto de datos permite evaluar la capacidad de los algoritmos para agrupar observaciones basándose únicamente en similitudes estructurales.

---

## 2. Objetivos

### 2.1 Objetivo General  
Aplicar, comparar e interpretar diferentes algoritmos de clustering sobre un conjunto de datos real.

### 2.2 Objetivos Específicos  
- Realizar un análisis exploratorio de datos (EDA) detallado  
- Preprocesar adecuadamente la información para su uso en modelos no supervisados  
- Implementar algoritmos de clustering: K-Means, DBSCAN y Clustering Jerárquico  
- Evaluar el desempeño de los modelos mediante métricas cuantitativas  
- Analizar e interpretar los resultados obtenidos  

---

## 3. Dataset

Se emplea el dataset *Palmer Penguins*, disponible a través de la librería `seaborn`.

### Variables principales:
- `bill_length_mm`: longitud del pico  
- `bill_depth_mm`: profundidad del pico  
- `flipper_length_mm`: longitud de la aleta  
- `body_mass_g`: masa corporal  
- `species`: especie (utilizada únicamente como referencia para validación conceptual)

---

## 4. Análisis Exploratorio de Datos (EDA)

Se realizó un análisis inicial con el objetivo de comprender la estructura del dataset:

### 4.1 Valores faltantes  
- Identificación de datos nulos en variables numéricas  
- Evaluación de su impacto en el análisis  

### 4.2 Distribución de variables  
- Visualización mediante histogramas  
- Identificación de dispersión y posibles sesgos  

### 4.3 Correlaciones  
- Construcción de matriz de correlación  
- Identificación de relaciones lineales entre variables  

### 4.4 Análisis por categoría  
- Comparación de variables por especie mediante boxplots  
- Evaluación visual de separabilidad  

---

## 5. Preprocesamiento de Datos

Para garantizar un desempeño adecuado de los algoritmos, se aplicaron las siguientes transformaciones:

- Imputación de valores faltantes mediante `SimpleImputer`  
- Estandarización de variables con `StandardScaler`  
- Selección de variables numéricas relevantes  
- Reducción de dimensionalidad (opcional) mediante PCA  

---

## 6. Modelos de Clustering

Se implementaron tres enfoques principales:

### 6.1 K-Means  
Algoritmo basado en centroides que busca minimizar la varianza intra-cluster.

- Requiere definir el número de clusters (k)  
- Selección de k mediante método del codo y Silhouette Score  

---

### 6.2 DBSCAN  
Algoritmo basado en densidad que agrupa puntos cercanos y detecta ruido.

- No requiere definir el número de clusters  
- Parámetros clave: `eps` y `min_samples`  
- Capacidad de identificar outliers  

---

### 6.3 Clustering Jerárquico (Agglomerative)  
Método que construye clusters mediante un proceso de fusión progresiva.

- No requiere especificar k inicialmente  
- Permite visualizar la estructura jerárquica mediante dendrogramas  

---

## 7. Métricas de Evaluación

Se utilizaron las siguientes métricas para evaluar la calidad del clustering:

- **Silhouette Score:** mide cohesión y separación de los clusters  
- **Davies-Bouldin Index:** evalúa similitud entre clusters (menor es mejor)  
- **Calinski-Harabasz Score:** mide dispersión relativa entre clusters  

---

## 8. Resultados y Análisis

Los resultados evidencian que:

- Las variables morfológicas permiten distinguir grupos con relativa claridad  
- K-Means presenta buen desempeño en estructuras aproximadamente esféricas  
- DBSCAN logra identificar ruido, pero es sensible a la selección de parámetros  
- El clustering jerárquico facilita la interpretación de la estructura de los datos  

Adicionalmente, se observa una correspondencia significativa entre los clusters generados y las especies reales, lo cual valida la efectividad de los métodos aplicados.

---

## 9. Comparación de Modelos

| Modelo        | Ventajas                          | Desventajas                        |
|--------------|----------------------------------|-----------------------------------|
| K-Means      | Eficiente y simple               | Requiere definir k                |
| DBSCAN       | Detecta ruido y formas arbitrarias | Sensible a parámetros             |
| Jerárquico   | Alta interpretabilidad           | Alto costo computacional          |

---

## 10. Conclusiones

- El aprendizaje no supervisado permite descubrir patrones sin necesidad de etiquetas  
- El preprocesamiento de los datos es fundamental para obtener buenos resultados  
- No existe un único modelo óptimo; la elección depende de la naturaleza del problema  
- La combinación de métricas cuantitativas y análisis visual es clave para validar los resultados  

---

## 11. Tecnologías Utilizadas

- Python  
- Scikit-learn  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  

---

### Selección del Mejor Modelo

Con base en las métricas evaluadas (Silhouette Score, Davies-Bouldin Index y Calinski-Harabasz), el modelo que presenta mejor desempeño global es:

**[NOMBRE DEL MODELO]**

Justificación:

- Presenta el mayor Silhouette Score, indicando mejor separación entre clusters
- Obtiene el menor Davies-Bouldin Index, reflejando menor similitud entre clusters
- Tiene un alto Calinski-Harabasz Score, evidenciando buena dispersión inter-cluster

Por lo tanto, este modelo logra el mejor balance entre cohesión interna y separación externa, siendo el más adecuado para este problema.
