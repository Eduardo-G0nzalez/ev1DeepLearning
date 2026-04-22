# Clasificación de Personajes de Los Simpsons: Estudio Comparativo CNN vs. MLP

Link drive (compartido al profesor): [https://drive.google.com/drive/folders/1YzJ-F6BnRasTDSS3cOAvW2ZUps6t0rIb?usp=sharing](https://drive.google.com/drive/folders/1YzJ-F6BnRasTDSS3cOAvW2ZUps6t0rIb?usp=sharing)

Este proyecto implementa y contrasta dos arquitecturas de Deep Learning diseñadas para clasificar imágenes de 18 personajes diferentes de la serie "Los Simpsons". El modelo fue desarrollado como parte de la Evaluación 1 de la asignatura Deep Learning en Duoc UC.

## 🚀 Descripción del Proyecto

El objetivo principal de este trabajo es demostrar empíricamente la superioridad de las Redes Neuronales Convolucionales (CNN) sobre las redes densas clásicas en tareas de visión computacional. 

Para lograr esto, **se desarrollaron por completo dos líneas de experimentación**:
1. **Un modelo Perceptrón Multicapa (MLP) optimizado**, que sirvió como caso de control para demostrar el "techo arquitectónico" que sufren estas redes al destruir la jerarquía espacial de los píxeles mediante la capa `Flatten`.
2. **Una arquitectura Convolucional (CNN) profunda**, que logró extraer exitosamente las siluetas y paletas de colores complejas de los personajes.

### Características Clave del Desarrollo:
- **Dataset:** Imágenes estandarizadas a 64x64 píxeles procesadas con OpenCV.
- **Rigor Científico:** Implementación de experimentos controlados aislando variables (ej. impacto del *Learning Rate* a 0.001 vs 0.01) en ambas arquitecturas.
- **Optimizaciones:** Uso exhaustivo de `Batch Normalization` y `Dropout` progresivo para estabilizar el aprendizaje y mitigar el sobreajuste.
- **Rendimiento:** Precisión (Accuracy) final del **89%** en la CNN, superando con creces la meta académica del 85%.

## 🛠️ Tecnologías Utilizadas

* [Python](https://www.python.org/) - Lenguaje de programación.
* [TensorFlow / Keras](https://www.tensorflow.org/) - Framework principal de Deep Learning.
* [OpenCV](https://opencv.org/) - Procesamiento y normalización de imágenes.
* [Google Colab](https://colab.research.google.com/) - Entrenamiento con soporte de aceleración por GPU.
* [Scikit-Learn](https://scikit-learn.org/) - Generación de métricas de evaluación (Precision, Recall, F1) y Matriz de Confusión.

## 📊 Arquitecturas Implementadas

### 1. El Modelo Definitivo (CNN Optimizada)
* **Bloques Convolucionales:** Tres etapas con filtros espaciales crecientes (32, 64 y 128) seguidos de `MaxPooling2D`.
* **Normalización:** Capas de `BatchNormalization` tras cada activación `ReLU` para acelerar la convergencia matemática.
* **Regularización:** `Dropout` progresivo (desde 0.25 hasta 0.50 en la capa densa final) para forzar la generalización.
* **Clasificador Final:** Capa densa de 512 neuronas y salida `Softmax` de 18 clases.

### 2. El Modelo de Control (MLP Optimizado)
* **Entrada Aplanada:** Transformación de la matriz 2D a un vector 1D de más de 12.000 dimensiones.
* **Capas Ocultas Anchas:** Tres capas densas (1024, 512 y 256 neuronas), equipadas también con `BatchNormalization` y `Dropout`. *(Nota: A pesar de esta profunda optimización, la arquitectura falló en superar el 40% de precisión, confirmando la teoría de la "ceguera espacial" del MLP).*

## 📈 Resultados y Comparativa

El desarrollo de ambas redes nos permitió generar la siguiente tabla comparativa, demostrando que ninguna cantidad de optimización puede compensar una arquitectura que no procesa información espacial:

| Arquitectura Utilizada | Regularización / Optimización | Accuracy (Validación) |
| :--- | :--- | :--- |
| **MLP Base** (Capas Dense) | Dropout básico (0.3) | ~30.4% |
| **MLP Optimizado** (Red Profunda) | BatchNormalization + Dropout Progresivo | ~27.8% (Sobreajuste por ruido) |
| **CNN Base** (2 Bloques Conv2D)| Dropout básico (0.3) | ~78.3% |
| **CNN Optimizada** (3 Bloques) | **BatchNormalization + Dropout Progresivo** | **~88.6% (Excelente)** |

### Aciertos Destacados de la CNN
Se observó un excelente desempeño en personajes con rasgos cromáticos y físicos muy distintivos:
* **Marge Simpson:** F1-Score de **0.94**
* **Krusty the Clown:** F1-Score de **0.94**
* **Jefe Gorgory (Chief Wiggum):** F1-Score de **0.93**

## ⚙️ Instalación y Uso

1. Clona este repositorio en tu máquina local:
   ```bash
   git clone [https://github.com/Eduardo-G0nzalez/ev1DeepLearning.git](https://github.com/Eduardo-G0nzalez/ev1DeepLearning.git)
