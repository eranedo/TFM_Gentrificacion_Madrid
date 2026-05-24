#Segmentación socioeconómica de los barrios de Madrid mediante técnicas de clustering para el estudio de procesos de transformación urbana

**Autor:** Eduardo Ranedo Martínez  
**Directora:** Anna Muñoz Bollas  
**PRA:** Susana Acedo Nadal  
**Institución:** Universitat Oberta de Catalunya (UOC)  
**Máster:** Máster en Ciencia de Datos  
**Área:** Data Science in complex systems, sustainability and ecology  
**Fecha:** Mayo 2026  
---

##Descripción del proyecto
Este repositorio contiene todo el código, datos procesados y resultados del Trabajo Final de Máster del Máster en Ciencia de Datos de la UOC. El trabajo propone un análisis exploratorio de los 131 barrios del municipio de Madrid mediante técnicas de aprendizaje no supervisado, con el objetivo de identificar patrones socioeconómicos comunes y detectar posibles dinámicas de transformación urbana, incluyendo la gentrificación.

El análisis combina dos herramientas complementarias:
- **Segmentación territorial** mediante el algoritmo K-Means 
- **Índice de gentrificación compuesto**

Todos los datos utilizados son de carácter público y abierto, descargados de fuentes oficiales del Ayuntamiento de Madrid y el Instituto Nacional de Estadística.

---

##Estructura del repositorio

```text
TFM_Gentrificacion_Madrid/
│
├── data/
│   ├── raw/                               #Datos originales sin modificar
│   │   ├── comercio_IAE.xlsx              #Censo de Locales y Actividades IAE
│   │   ├── poblacion_grandes_grupos.xlsx  #Padrón - grandes grupos de edad
│   │   ├── poblacion_quinquenal.xlsx      #Padrón - grupos quinquenales 15-44 años
│   │   ├── alquiler_barrio.xlsx           #Precio alquiler €/m² por barrio (2023)
│   │   ├── alquiler_distrito.xlsx         #Precio alquiler €/m² por distrito (2018-2024)
│   │   ├── valor_catastral.xlsx           #Valor catastral residencial por barrio (2020-2024)
│   │   └── barr2025.shp                   #Shapefile barrios Madrid
│   │
│   ├── processed/                         #Datasets procesados individualmente
│   │   ├── df_comercio.csv                #Indicadores comerciales por barrio
│   │   ├── df_poblacion.csv               #Indicadores demográficos por barrio
│   │   ├── df_alquiler.csv                #Indicadores de alquiler por barrio
│   │   └── df_catastral.csv               #Indicadores catastrales por barrio
│   │
│   └── final/                             #Dataset unificado para el análisis
│       ├── dataset_barrios.csv            #Dataset final (131 barrios, 17 variables, 0 nulos)
│       └── dataset_barrios_clusters.csv   #Dataset con resultados del clustering
│
├── notebooks/                             #Notebooks de Jupyter con todo el código
│   ├── Procesamiento_actividad_comercial.ipynb
│   ├── Procesamiento_poblacion.ipynb
│   ├── Procesamiento_alquiler.ipynb
│   ├── Procesamiento_catastral.ipynb
│   ├── Unificacion_dataset.ipynb
│   ├── EDA.ipynb
│   ├── Clustering.ipynb
│   └── Indice_gentrificacion.ipynb
│
├── outputs/
│   ├── figures/                           #Gráficos y mapas generados
│   │   ├── histogramas_variables.png      #Distribución de variables
│   │   ├── boxplots_outliers.png          #Detección de outliers
│   │   ├── correlaciones.png              #Matriz de correlaciones
│   │   ├── top10_variables.png            #Top 10 barrios por variable
│   │   ├── desbalanceo_clustering.png     #Análisis de desbalanceo
│   │   ├── optimo_clusters.png            #Método codo + silueta
│   │   ├── perfil_clusters.png            #Perfil normalizado de clusters
│   │   ├── pca_clusters.png               #Visualización PCA
│   │   ├── boxplots_clusters.png          #Distribución por cluster
│   │   ├── indice_gentrificacion.png      #Distribución del índice
│   │   ├── cruce_clustering_indice.png    #Cruce clustering vs índice
│   │   ├── Mapa_clusters.png              #Mapa segmentación territorial
│   │   └── Mapa_indice.png                #Mapa índice de gentrificación
│   │
│   └── tables/                            #Tablas de resultados
│       ├── estadisticas_descriptivas.csv
│       ├── resumen_outliers.csv
│       ├── resultados_clustering.csv
│       ├── indice_gentrificacion.csv
│       ├── sensibilidad_pesos_indice.csv
│       └── datos_mapa.csv
│
└── memory/                                #Memoria de TFM
    └── TFM_eranedo.pdf
