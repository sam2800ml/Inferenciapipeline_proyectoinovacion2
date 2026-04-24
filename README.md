# Pipeline de Inferencia para Reconocimiento de Dígitos (LeNet-5)

Este proyecto implementa un pipeline completo de Visión Artificial y Deep Learning para la detección y clasificación de dígitos escritos a mano a partir de imágenes capturadas en entornos reales. El sistema integra técnicas de procesamiento digital de imágenes con la arquitectura clásica **LeNet-5**.

## 👥 Autores
Este proyecto fue desarrollado como parte de la formación en Inteligencia Artificial Aplicada por:
* **Santiago Aristizabal**
* **Alejandra Forero**
* **José Luis Realpe**

---

## 🚀 Descripción del Proyecto
El objetivo principal es cerrar la brecha entre el dataset controlado **MNIST** (imágenes perfectas de 28x28) y la **fotografía del mundo real** (alta resolución, iluminación variable y ruido). 

El pipeline se divide en tres grandes etapas:
1. **Visión Clásica (OpenCV):** Segmentación, umbralización adaptativa y detección de contornos.
2. **Estandarización Geométrica:** Centrado por masa y ajuste de aspecto para emular el formato de 1998 de Yann LeCun.
3. **Inferencia (TensorFlow/Keras):** Clasificación mediante una red neuronal convolucional (CNN) pre-entrenada.

---

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.x
* **Librerías de Visión:** OpenCV (cv2), Scipy (ndimage)
* **Deep Learning:** TensorFlow / Keras
* **Procesamiento de Datos:** NumPy
* **Visualización:** Matplotlib

---

## 📋 Estructura del Pipeline

### 1. Preprocesamiento y Segmentación
* **Conversión a Grises y Blur:** Reducción de ruido térmico.
* **Umbralización Adaptativa:** Manejo de iluminación no uniforme en fotografías.
* **Morfología Matemática:** Dilatación de trazos para asegurar conectividad.
* **Filtrado Dinámico:** Selección de candidatos basada en área y *aspect ratio*.

### 2. Normalización MNIST-Ready
* Redimensionamiento a 28x28 preservando la relación de aspecto.
* Aplicación de **Padding** para alcanzar dimensiones de 32x32.
* Alineación mediante **Centro de Masa** para corregir asimetrías en la escritura manual.

### 3. Inferencia de Red Neuronal
* Carga del modelo `.h5` desde repositorio remoto.
* Normalización de tensores en rango $[0, 1]$.
* Predicción de clases con análisis de confianza probabilística.
