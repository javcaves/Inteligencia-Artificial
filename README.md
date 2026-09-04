# Evaluación 1: Análisis Exploratorio de Datos (EDA)

Desarrollo de diagnóstico, análisis exploratorio (EDA), limpieza y transformación de un conjunto de datos centrado en el rendimiento académico de estudiantes de educación superior, con el fin de prepararlo para un futuro modelo predictivo.



## Integrantes - Grupo 07 

* **Javiera Cuevas** – [javiera.cuevas2201@alumnos.ubiobio.cl](mailto:javiera.cuevas2201@alumnos.ubiobio.cl)
* **Antonia Peña** – [antonia.pena2202@alumnos.ubiobio.cl](mailto:antonia.pena2202@alumnos.ubiobio.cl)
* **Arline Mitchell** – [arline.mitchell2201@alumnos.ubiobio.cl](mailto:arline.mitchell2201@alumnos.ubiobio.cl)
* **Nicolás Morales** – [nicolas.morales2001@alumnos.ubiobio.cl](mailto:nicolas.morales2001@alumnos.ubiobio.cl)



## Descripción 

Este repositorio contiene el desarrollo de la **Evaluación 1**, enfocada en el análisis exhaustivo de la calidad de los datos, la detección de anomalías y el Análisis Exploratorio de Datos (EDA) de un dataset académico. El objetivo principal es estructurar y limpiar los datos para garantizar un rendimiento óptimo en la construcción de un futuro modelo orientado a predecir la calificación final de los estudiantes (`FinalGrade`).



## Contenidos del Notebook

El desarrollo está estructurado en las siguientes fases:

1. **Diagnóstico de Calidad de Datos:**
   * **Caracterización:** Identificación de variables numéricas y categóricas (`StudentID` como identificador y `FinalGrade` como variable objetivo o *target*).
   * **Valores Faltantes (Nulos):** Análisis porcentual y justificación de la estrategia de imputación (mediana para numéricas, moda para categóricas mediante `SimpleImputer`).
   * **Registros Duplicados:** Detección de duplicados basados en el identificador único y su respectiva eliminación.
   * **Inconsistencias:** 
     * *Lógicas (Numéricas):* Tratamiento de valores fuera de rango o inválidos (edades negativas, asistencia mayor al 100%, notas fuera de escala 1.0 a 10.0).
     * *Estructurales (Categóricas):* Normalización de strings (minúsculas, eliminación de espacios y tildes) en variables como `Scholarship` y `Program`.
   * **Valores Atípicos (Outliers):** Análisis mediante diagramas de caja (*boxplots*) y distinción entre errores y comportamientos extremos válidos, manejados posteriormente mediante estandarización (`StandardScaler`).

2. **Análisis Exploratorio de Datos (EDA):**
   * **Distribuciones:** Visualización de histogramas y densidades (`KDE`) para comprender el comportamiento de variables clave como `FinalGrade`, `StudyHours`, `Attendance` y `PreviousGPA`.
   * **Matriz de Correlación:** Análisis de correlaciones lineales entre variables numéricas para identificar relaciones multivariadas.


  
## Estructura del Repositorio
```text
├── E1 – EDA/
│   ├── E1_EDA.ipynb                         # Notebook principal con todo el desarrollo reproducible
│   ├── rendimiento_academico_evaluacion.csv # Dataset original (descargado vía wget en el script)
│   ├── rendimiento_academico_limpio.csv     # Dataset final tratado y exportado
│   └── Análisis Exploratorio y Preparación de Datos.pdf # Presentación resumen con hallazgos y decisiones
└── README.md                                # Documentación del repositorio
```



## Requisitos e Instrucciones de Ejecución

El código está diseñado para ejecutarse en entornos de Jupyter Notebook o **Google Colab**. 

El dataset se descarga automáticamente desde el repositorio mediante un comando `wget` integrado en el script:

```python
!wget -q -O rendimiento_academico_evaluacion.csv '[https://raw.githubusercontent.com/javcaves/Inteligencia-Artificial/refs/heads/main/E1%20%E2%80%93%20EDA/rendimiento_academico_evaluacion.csv](https://raw.githubusercontent.com/javcaves/Inteligencia-Artificial/refs/heads/main/E1%20%E2%80%93%20EDA/rendimiento_academico_evaluacion.csv)'
