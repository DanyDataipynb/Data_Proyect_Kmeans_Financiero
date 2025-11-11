# 🧠 Segmentación de Clientes con K-Means – Proyecto Analítico

**Autor:** Daniel Felipe Ramírez  
**Rol:** Data & Reporting Analyst  
**Tecnologías:** Python · Pandas · Scikit-learn · Matplotlib · Power BI  

---

## 🎯 Objetivo del proyecto

Este proyecto busca **identificar segmentos de clientes con comportamientos similares** en el uso de tarjetas de crédito, utilizando el algoritmo de *Machine Learning no supervisado* **K-Means Clustering**.  

El objetivo final es transformar datos financieros en **insights accionables** para estrategias de marketing, retención y gestión de riesgo.

---
## 🔍 Proceso analítico paso a paso

1. **Carga y exploración de datos (EDA):**  
   - Revisión de estructura, valores nulos y distribución de variables.  
   - Identificación de variables relevantes (edad, límite de crédito, transacciones, etc.).  

2. **Preprocesamiento:**  
   - Eliminación de identificadores irrelevantes (`CLIENTNUM`).  
   - Escalamiento de variables numéricas con `StandardScaler` para homogenizar magnitudes.  

3. **Selección del número de clusters (`k`):**  
   - Aplicación del método del **codo (Elbow)** y del **Silhouette Score**.  
   - Elección final: *k* óptimo según coherencia entre ambos métodos.  

4. **Entrenamiento de modelo:**  
   - Implementación de `KMeans` con inicialización múltiple (`n_init=20`).  
   - Asignación de etiquetas de cluster a cada registro.  

5. **Perfilamiento y visualización:**  
   - Comparación de variables clave por grupo (edad, gasto, uso del crédito).  
   - Visualización con histogramas y reducción de dimensionalidad **PCA (2D)**.  

6. **Exportación de resultados:**  
   - `reports/cluster_summary.csv` con promedios y dispersión por cluster.  
   - `reports/customers_with_cluster.csv` con la etiqueta asignada a cada cliente.  

---

## 🔍 Reflexión sobre el número de clusters

El análisis de Silhouette sugiere que **2 clusters** es el punto de mayor separación entre grupos.
Esto indica que mis datos reflejan **dos comportamientos predominantes**:

- **Cluster 0:** clientes activos, con alto número de transacciones y gasto.
- **Cluster 1:** clientes de bajo uso o potencialmente inactivos.

Probé aumentar `k` a 3 y 4, pero la mejora en Silhouette fue mínima y los grupos empezaron a solaparse.
Por eso decidí mantener 2 clusters como resultado final, priorizando **simplicidad e interpretabilidad**.
