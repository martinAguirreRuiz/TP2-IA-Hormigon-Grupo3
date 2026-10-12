# Estimación de la resistencia a compresión del hormigón mediante Redes Neuronales Artificiales

Trabajo Práctico N° 02 — Inteligencia Artificial, Ingeniería en Sistemas de Información
Universidad Tecnológica Nacional, Facultad Regional Buenos Aires — 2026 — Grupo N° 03

**Integrantes:** Martin Federico Aguirre Ruiz, Agustina Guitman Dalla Riva, María Victoria Massaini, Facundo Pastorino, Matías Germán Rainhart, Facundo Slaibe, Ignacio Villarruel, Federico Waldman.

## Descripción

Sistema inteligente basado en Redes Neuronales Artificiales Multi-Perceptrón con entrenamiento Backpropagation (RNA MLP BP) que estima la resistencia a compresión de un hormigón (en MPa) a partir de su dosificación y de su edad. Se entrenaron tres modelos:

| Modelo | Tarea | Topología | Resultado sobre los datos de prueba |
|---|---|---|---|
| M1 | Estimación | 8-8-1 | Error absoluto medio 4,36 MPa (14,6%), R² 0,87 |
| M2 | Estimación | 9-16-8-1 | Error absoluto medio 3,92 MPa (13,8%), R² 0,88 |
| M3 | Clasificación en 5 clases | 8-16-8-5 | Exactitud 63,2% |

Como referencia, una regresión lineal múltiple obtiene un error absoluto medio de 7,78 MPa y un R² de 0,67.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `TP2_Hormigon_IA.ipynb` | Cuaderno con el código completo y sus resultados (preparación de los datos, entrenamiento de M1, M2 y M3, métricas y comparación final). |
| `Concrete_Data.xls` | Conjunto de datos original (1030 ensayos). |
| `entrenamiento.csv` | Datos de entrenamiento: 703 ensayos (70%). |
| `validacion.csv` | Datos de validación: 101 ensayos (10%). |
| `prueba.csv` | Datos de prueba: 201 ensayos (20%). |

Los tres archivos CSV contienen los 1005 ensayos que quedan tras eliminar 25 registros duplicados, divididos de forma estratificada por clase de resistencia con semilla aleatoria 42, exactamente como en el cuaderno. Columnas: `cemento`, `escoria`, `cenizas`, `agua`, `superplast`, `agr_grueso`, `agr_fino` (en kg/m³), `edad` (en días) y `resistencia` (en MPa, atributo objetivo).

## Cómo ejecutar el cuaderno

1. Abrir `TP2_Hormigon_IA.ipynb` y hacer clic en **Open in Colab**.
2. En el panel de archivos de Colab (ícono de carpeta), subir `Concrete_Data.xls`.
3. Ejecutar **Entorno de ejecución → Ejecutar todas**.

La división de los datos y la inicialización de las redes usan semilla fija, por lo que los resultados son reproducibles; pueden aparecer diferencias mínimas entre entornos por redondeo numérico.

## Herramientas

Python 3, Google Colab, pandas, NumPy, scikit-learn, TensorFlow/Keras y matplotlib. Se utilizó Claude (Anthropic) como asistente de inteligencia artificial.

## Datos

Yeh, I-C. (1998). *Concrete Compressive Strength* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5PK67 — Licencia CC BY 4.0.

Yeh, I-C. (1998). Modeling of strength of high-performance concrete using artificial neural networks. *Cement and Concrete Research*, 28(12), 1797–1808.
