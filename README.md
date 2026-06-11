# 📊 Portafolio Multidominio: Análisis Inicial y Selección de Problema
## Fase I: Análisis Exploratorio de Datos Avanzado (EDA), Limpieza Estructurada y Sincronización (v1.0.0)

[![Python Version](https://img.shields.io/badge/python-3.9%20%7C%203.10-teal.svg?style=flat-square)](https://www.python.org/)
[![EDA](https://img.shields.io/badge/Exploratory%20Data%20Analysis-Advanced-blue?style=flat-square)](https://pandas.pydata.org/)
[![Statistical Tests](https://img.shields.io/badge/Tests-Shapiro--Wilk%20%7C%20Pearson-orange?style=flat-square)](https://scipy.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

## 📋 Descripción del Proyecto e Importancia
Este proyecto consolida la primera etapa de un sistema adaptativo de ciencia de datos enfocado en la extracción, diagnóstico estadístico y justificación analítica de múltiples fuentes de datos. La importancia de esta Fase I radica en establecer un entendimiento profundo y empírico de las variables antes de construir cualquier pipeline predictivo, garantizando que las decisiones de ingeniería de características y modelado estén respaldadas por pruebas matemáticas rigurosas y no por suposiciones.

---

## ⚖️ Conjuntos de Datos Analizados

Para evaluar la versatilidad técnica en diferentes entornos y estructuras, se analizaron estratégicamente cuatro conjuntos de datos disímiles:

1. **Dataset 1: Iris (Botánica y Taxonomía):** Conjunto tabular clásico, pequeño y balanceado en sus etiquetas, utilizado como entorno de control para analizar fronteras de decisión geométrica.
2. **Dataset 2: Real Estate (Economía Urbana):** Datos numéricos continuos con un fuerte componente geográfico, ideales para evaluar interdependencias espaciales en la valoración de activos inmobiliarios.
3. **Dataset 3: Retail Sales (Operaciones Comerciales):** Registro histórico transaccional caracterizado por una alta asimetría y variaciones temporales marcadas por la estacionalidad del mercado.
4. **Dataset 4: Fungal Enzymes (Ciencias Ómicas y Biotecnología):** Big Data compuesto por secuencias de texto crudo (IUPAC) y métricas de calidad de secuenciación para la identificación de biocatalizadores fúngicos.

---

## 🔬 Resumen del EDA Inicial y Hallazgos Principales

El diagnóstico exploratorio automatizado sobre los conjuntos de datos arrojó los siguientes hallazgos críticos:
* **Fronteras Solapadas (Iris):** Se identificó un solapamiento parcial en las distribuciones de las clases *versicolor* y *virginica* al cruzar los descriptores de pétalo, lo que requerirá modelos con flexibilidad no lineal.
* **Dependencia Espacial (Real Estate):** Se detectó una relación matemática directa y no lineal entre la geolocalización (latitud/longitud) y el precio, además de la presencia de valores atípicos en sectores de alta gama.
* **Sesgo Transaccional (Retail Sales):** Las variables de volumen de ventas muestran una asimetría positiva severa y picos críticos condicionados por la estacionalidad de la demanda.
* **Anomalías Biológicas y Redundancia (Fungal Enzymes):** * Se determinó que `SEQUENCE_LENGTH` posee una asimetría positiva extrema inducida por macrocomplejos macromoleculares legítimos, descartando el uso de escaladores lineales tradicionales.
  * Se descubrió una **multicolinealidad perfecta (correlación de 1.00)** entre `AMBIGUOUS_COUNT` y `AMBIGUITY_RATE`, determinando la eliminación del conteo absoluto para proteger la estabilidad de los algoritmos.
  * Se aplicó el **Test de Shapiro-Wilk** ($\alpha = 0.05$), obteniendo valores p críticamente bajos que **rechazan formalmente la hipótesis nula ($H_0$) de normalidad** en todas las variables predictoras clave.

---

## 🎯 Problema Seleccionado, Justificación y Objetivos

* **Problema Seleccionado:** Clasificación Binaria Compleja (`is_enzyme`) utilizando la estructura predictiva del **Dataset 4 (Fungal Enzymes)**.
* **Justificación de la Elección:** Representa el mayor desafío metodológico y de ingeniería del portafolio. Permite automatizar la anotación funcional y el descubrimiento de biocatalizadores industriales directamente desde genomas globales, reduciendo los costos del tamizaje experimental clásico en laboratorio. Además, fuerza el desarrollo de técnicas avanzadas de *Feature Engineering* para transformar texto biológico IUPAC en descriptores fisicoquímicos continuos útiles para Machine Learning.
* **Objetivos Específicos:**
  1. Diseñar un pipeline de preprocesamiento robusto que maneje datos no gaussianos y nulos experimentales sin incurrir en fuga de datos (*Data Leakage*).
  2. Implementar clasificadores no paramétricos basados en ensambles de árboles de decisión que toleren la asimetría extrema y el desbalance de clases.
  3. Optimizar el rendimiento del clasificador maximizando estrictamente la métrica Macro F1-Score mediante estrategias de búsqueda avanzada.

---

## 🚀 Instrucciones para Ejecutar y Reproducir

1. **Clonar el repositorio localmente:**
   ```bash
   git clone [https://github.com/tu_usuario/tu_repositorio.git](https://github.com/tu_usuario/tu_repositorio.git)
   cd tu_repositorio

2. **Instalar las dependencias de análisis matemático y visualización:**

pip install -r requirements.txt

3. **Reproducir los análisis:**
Abre tu entorno de Jupyter Notebook o VS Code, dirígete a la carpeta notebooks/ y ejecuta secuencialmente los cuadernos, prestando especial atención a EDA_dataset4.ipynb para validar los gráficos de distribución (KDE) y las pruebas de Shapiro-Wilk.

👥 Autores y Roles
Iván Cortés - Ingeniero Químico (UChile) & PhD (c) Ciencias Biológicas (UN Tucumán)

Rol: Científico de Datos Principal, Diseñador del Diagnóstico Estadístico Ómico, Especialista en Dominio Biológico

📄 Licencia
Este proyecto está bajo la Licencia MIT. Esto significa que el código es completamente libre y abierto para su uso, modificación y distribución, siempre que se mantenga el reconocimiento de la autoría original. Para más detalles, consulta los términos de la licencia estándar MIT.