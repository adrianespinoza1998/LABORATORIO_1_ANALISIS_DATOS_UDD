## Laboratorio 2

## Tabla de Contenidos
Descripción del Proyecto
Requisitos
Estructura del Repositorio
Instalación
Ejecución
Análisis y Resultados
Tecnologías Usadas

## Descripción del Proyecto
El objetivo de este proyecto fue analizar el conjunto de datos paired_bladder_2022_clinical_data.tsv para identificar los factores que 
influyen en la Carga Mutacional Tumoral (TMB) y en la supervivencia general de los pacientes con cáncer de vejiga.


El análisis transitó desde modelos de regresión lineal múltiple, que mostraron ser inadecuados debido a la violación de supuestos estadísticos clave, hacia 
un enfoque de análisis de supervivencia, culminando en un modelo de riesgos proporcionales de Cox multivariado.


## Requisitos
* Python 3.8 o superior

pip para la instalación de paquetes

Estructura del Repositorio
El proyecto está organizado de manera lógica para garantizar la transparencia y facilitar la navegación.


data/: Contiene el conjunto de datos original.

src/: Almacena los scripts de Python para la limpieza de datos y el modelado.


notebooks/: Incluye el notebook de Jupyter que documenta cada paso del análisis.


reports/: Carpeta para los resultados finales, incluyendo el informe técnico y visualizaciones.

## Instalación
Clona el repositorio:

Bash

git clone https://github.com/adrianespinoza1998/LABORATORIO_1_ANALISIS_DATOS_UDD.git
Navega al directorio del proyecto:

Bash

cd LABORATORY_1_DATA_ANALYSIS_UDD
Instala las dependencias:

Bash

pip install pandas numpy matplotlib seaborn statsmodels lifelines
Ejecución
Para reproducir el análisis, abre y ejecuta el notebook de Jupyter en el directorio notebooks/.

Inicia Jupyter Notebook:

Bash

jupyter notebook
Abre el notebook de análisis:
Navega a la carpeta notebooks/ y abre el archivo .ipynb correspondiente.

Ejecuta las celdas:
Sigue las celdas del notebook en orden para ver cada paso del proceso, desde la carga y limpieza de datos hasta el modelado y la interpretación de resultados.


##  Análisis y Resultados
Modelado con Regresión Lineal:
Se intentó predecir la TMB con modelos de regresión lineal. El Modelo 2 alcanzó un R² notablemente alto del 87%. Sin embargo, el diagnóstico reveló violaciones graves de 
los supuestos del modelo, incluyendo multicolinealidad, heterocedasticidad y no linealidad, lo que invalidó sus resultados.

* Análisis de Supervivencia:

Kaplan-Meier: Las curvas de supervivencia mostraron una mediana de supervivencia menor para los pacientes con TMB alto (60.5 meses) en comparación con aquellos con TMB bajo 
(95.6 meses). Sin embargo, esta diferencia no fue estadísticamente significativa (p = 0.158).
Modelo de Cox: El análisis multivariado identificó predictores significativos e independientes de la supervivencia:
Fraction Genome Altered (HR ≈ 2.42).
Specimen Stage (HR ≈ 2.11).
Age at Diagnosis (HR ≈ 1.01).

## Conclusión
La variable TMB (nonsynonymous) no emergió como un predictor independiente y estadísticamente significativo del pronóstico de supervivencia en este modelo multivariado
(HR ≈ 1.01, p = 0.44).


## Tecnologías Usadas

Pandas: Manipulación de datos.
NumPy: Operaciones numéricas.
Matplotlib: Visualización de datos.
Seaborn: Visualizaciones estadísticas.
Statsmodels: Modelos de regresión lineal.
Lifelines: Modelos de supervivencia.

## Autoría

Vanessa Camaggi: vcamaggig@udd.cl 
Adrián Alexis Espinoza Arévalo: a.espinozaa@udd.cl 
Miguel Angel Segovia: m.segoviac@udd.cl 
Ricardo Castro Vera: rcastrov@udd.cl 
