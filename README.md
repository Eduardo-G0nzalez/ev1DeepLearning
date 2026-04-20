# Clasificación de Personajes de Los Simpsons con CNN



Este proyecto implementa una Red Neuronal Convolucional (CNN) diseñada para clasificar imágenes de 18 personajes diferentes de la serie "Los Simpsons". El modelo fue desarrollado como parte de la Evaluación 1 de la asignatura Deep Learning en Duoc UC.

## 🚀 Descripción del Proyecto

El objetivo principal de este trabajo es comparar el rendimiento entre un Perceptrón Multicapa (MLP) y una arquitectura Convolucional (CNN), demostrando cómo esta última es superior para tareas de visión computacional al conservar la jerarquía espacial de los píxeles mediante el uso de filtros.

### Características Clave:

- **Dataset:** Imágenes de 64x64 píxeles procesadas con OpenCV.
- **Arquitectura:** CNN profunda con 3 bloques convolucionales crecientes.
- **Optimizaciones:** Implementación de Batch Normalization y Dropout progresivo para estabilizar el aprendizaje y mitigar el sobreajuste.
- **Rendimiento:** Precisión (Accuracy) final del **89%** en el conjunto de validación.

## 🛠️ Tecnologías Utilizadas

* [Python](https://www.python.org/) - Lenguaje de programación.
* [TensorFlow / Keras](https://www.tensorflow.org/) - Framework principal de Deep Learning.
* [OpenCV](https://opencv.org/) - Procesamiento y normalización de imágenes.
* [Google Colab](https://colab.research.google.com/) - Entrenamiento con soporte de GPU.
* [Scikit-Learn](https://scikit-learn.org/) - Generación de métricas (Precision, Recall, F1) y Matriz de Confusión.


## 📊 Arquitectura del Modelo

El modelo definitivo utiliza una estructura jerárquica optimizada:
1. **Entrada:** Tensores de 64x64x3 (RGB).
2. **Bloques Convolucionales:** Tres etapas con filtros de 32, 64 y 128 respectivamente, seguidos de `MaxPooling2D`.
3. **Normalización:** Capas de `BatchNormalization` tras cada activación ReLU para acelerar la convergencia.
4. **Regularización:** `Dropout` progresivo (desde 0.25 hasta 0.50 en la capa densa) para forzar la generalización.
5. **Clasificador Final:** Capa densa de 512 neuronas y salida `Softmax` de 18 neuronas.

## 📈 Resultados Obtenidos

El modelo superó con creces la meta del 85% exigida, demostrando una alta capacidad de reconocimiento incluso en personajes con rasgos complejos.

| Personaje | F1-Score |
| :--- | :--- |
| Marge Simpson | 0.95 |
| Krusty the Clown | 0.94 |
| Sideshow Bob | 0.95 |
| **Accuracy Global** | **89%** |

### Análisis de Métricas
Se observó un excelente equilibrio entre Precision y Recall. El uso de semillas aleatorias permitió obtener resultados reproducibles, confirmando que la arquitectura es robusta frente a la variabilidad de las imágenes de entrenamiento.

## ⚙️ Instalación y Uso

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/Eduardo-G0nzalez/ev1DeepLearning.git](https://github.com/Eduardo-G0nzalez/ev1DeepLearning.git)
