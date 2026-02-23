# 🍄 Taller de Aprendizaje Automático No Supervisado – Mushroom Dataset

Este proyecto explora técnicas de **Aprendizaje Automático No Supervisado**, usando **PCA** y **K-Means**, y se compara con un modelo supervisado (**Random Forest**) para clasificar hongos como **comestibles (e)** o **venenosos (p)**.

> 🧑‍💻 Este proyecto fue realizado **en solitario**, siguiendo buenas prácticas de control de versiones con Git.
---

## 📂 Dataset

- **Fuente:** [Mushroom Dataset - UCI Repository](https://www.kaggle.com/datasets/uciml/mushroom-classification)  
- **Instancias:** 8124  
- **Variables:** 21, todas categóricas (forma, color, olor, etc.)  
- **Variable objetivo:** `class` (`e` → edible / comestible, `p` → poisonous / venenoso)  

> 📝 Nota: La columna `odor` es la que más relación tiene con la clase (`class`).

---

## 🧹 ETL / Preprocesamiento

El flujo ETL realizado fue:

1. **Limpieza de datos**  
   - Eliminadas columnas poco informativas: `veil-type` y `gill-attachment`.  
   - Eliminación de nulos y valores inconsistentes.

2. **Feature Engineering**  
   - Creación de una columna nueva: `has_odor` → indica si el hongo tiene olor o no.  
   - One-Hot Encoding de todas las variables categóricas.  
   - Escalado de features con **StandardScaler**.

3. **Separación de datos**  
   - `X` → features  
   - `y` → clase (`class`)  

---

## 🧠 Objetivos del Taller

- Cargar y explorar un dataset categórico complejo.  
- Preprocesamiento de datos y creación de nuevas variables.  
- Reducción de dimensionalidad con **PCA**.  
- Detección de patrones ocultos con **K-Means**.  
- Comparación de desempeño con **Random Forest** supervisado.  

---

## 🔍 Análisis Exploratorio y PCA

- **PCA 2D:** Permite visualizar la separabilidad de los hongos comestibles y venenosos.  
- **Insight visual:** Los datos se agrupan naturalmente en varias regiones diferenciadas, confirmando patrones internos.  

---

## 🌳 Clasificación Supervisada – Random Forest

- Entrenamiento con **10 componentes PCA**  
- **Accuracy:** 0.998  
- Las predicciones muestran una casi perfecta separación entre clases.  
- Esto confirma que la PCA conserva la información relevante para clasificación.

---

## 🔄 Clustering – K-Means

- **Número óptimo de clusters:** k = 4 (método del codo)  
- Los clusters reflejan agrupaciones naturales del dataset, aunque no coinciden 100% con las clases reales.  
- **Homogeneidad:** 0.653  
- **Completitud:** 0.407  

---
## 🗂️ Estrategia de Ramas Git

El proyecto se desarrolló con la siguiente estructura de ramas:

- `feature/setup` → creación de la estructura de carpetas y archivos iniciales  
- `feature/eda` → análisis exploratorio de datos  
- `feature/cleaning` → limpieza y feature engineering (`has_odor`)  
- `feature/model` → entrenamiento y evaluación de Random Forest + PCA, y K-Means  
- `develop` → integración de todas las funcionalidades y generación del informe ejecutivo  

> 💡 Esto permitió un flujo de trabajo organizado y modular, facilitando pruebas y seguimiento de cambios.
---
## 📸 Reporte Visual

El informe ejecutivo en PDF incluye todas las gráficas y análisis:

- `report/informe_ejecutivo_mushrooms.pdf`  
  - Scatterplots PCA 2D por clase y clusters  
  - Comparación Random Forest vs K-Means  
  - Resumen de métricas y observaciones

---

## 🗂️ Estructura del Proyecto
```
project-9-Pablo-Rodriguez/
│
├─ data/
│ ├─ raw/
│ │ └─ mushrooms.csv
│ └─ clean/
│   └─ clean_mushrooms.csv
│   └─ clean_mushrooms.parquet
│
├─ notebooks/
│ ├─ Eda_Mushrooms.ipynb
│ ├─ data_cleaning.ipynb
│ └─ Mushroom_Unsupervised_Learning_PCA_KMeans.ipynb
│
├─ report/
│ └─ informe_ejecutivo_mushrooms.pdf
│
└─ README.md
```

---

## 📝 Conclusión

- El **aprendizaje no supervisado** permite detectar patrones internos y clusters.  
- La **PCA** facilita la visualización y conserva la información relevante.  
- El **Random Forest** con componentes PCA logra casi predicción perfecta.  
- La columna `odor` y la variable `has_odor` son clave para entender la clasificación de los hongos.  

---

## 📚 Referencias

- [Mushroom Dataset - UCI Repository](https://www.kaggle.com/datasets/uciml/mushroom-classification)  
- [Scikit-learn PCA](https://scikit-learn.org/stable/modules/decomposition.html)  
- [Scikit-learn KMeans](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)  
- [Seaborn / Matplotlib documentación oficial](https://seaborn.pydata.org/)
