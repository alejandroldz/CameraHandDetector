# Sistema de Reconocimiento de Gestos en Tiempo Real
MODELOS EN: https://drive.google.com/file/d/1E4KEBXoFKHbPzPg1Jlvz9tyIE4c3dFhO/view?usp=drive_link

>  Un estudio comparativo y una implementación de pipeline de Deep Learning de dos etapas (Detección + Clasificación).
<img width="1269" height="1001" alt="Captura de pantalla 2026-01-04 190131" src="https://github.com/user-attachments/assets/d943c853-91fc-4408-bb77-734404168d28" />

## Descripción General

Este repositorio contiene el código fuente, experimentos y modelos finales para un sistema capaz de reconocer gestos de la mano estáticos utilizando una webcam estándar. El proyecto se centra en la optimización para **CPU**, buscando el equilibrio entre la precisión de las redes neuronales modernas y la baja latencia necesaria para la interacción en tiempo real.

El código abarca desde técnicas clásicas de visión hasta el estado del arte en Deep Learning.

### Gestos Soportados (Dataset HaGRID)
El sistema clasifica 8 gestos funcionales:
* `call`, `fist`, `like`, `ok`, `palm`, `peace`, `rock`, `stop`.

## Estructura del Código

El archivo principal `proyectofinalvc.ipynb` está estructurado en 6 secciones lógicas que narran la evolución del proyecto:

1.  **Configuración y Datos:** Descarga y preparación del dataset HaGRID (submuestreado a ~3000 imgs/clase).
2.  **Experimento 1: Template Matching:** Implementación de Correlación Cruzada Normalizada (NCC) como *baseline* de visión clásica.
3.  **Experimento 2: Clasificación (Deep Learning):** Entrenamiento y comparativa de backbones (ResNet, MobileNet, EfficientNet, ConvNext) sobre imágenes recortadas (ROI).
4.  **Experimento 3: Contexto Completo:** Evaluación del impacto del ruido de fondo entrenando sin recorte previo.
5.  **Implementación YOLOv8:** Entrenamiento de un detector de objetos propio para localizar la mano, comparándolo con MediaPipe.
6.  **Demos en Vivo:** Scripts para ejecutar la inferencia en tiempo real usando Webcam.

## Instalación y Requisitos

El proyecto utiliza **PyTorch** con **FastAI** para la clasificación y **Ultralytics** o Mediapipe (según el script) para la detección.

