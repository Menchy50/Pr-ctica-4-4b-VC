# Práctica 4: Detección de Matrículas y Reconocimiento Óptico de Caracteres (OCR vs VLM)

**Autor:** Mencey Montesdeoca Álamo  
**Asignatura:** Visión por Computador  

---

## Descripción
Este repositorio contiene el desarrollo de la cuarta práctica de Visión por Computador, enfocada en la implementación de un sistema completo de detección de matrículas y la evaluación comparativa del reconocimiento óptico de caracteres (OCR) mediante un enfoque clásico frente a un modelo de lenguaje multimodal (Vision-Language Model).

---

## Tareas Desarrolladas

### Tarea 1: Entrenamiento y Detección de Matrículas con YOLOv11
- **Descripción:** Implementación de un modelo de detección de objetos basado en arquitecturas ultraligeras para la localización precisa de matrículas en vehículos.
- **Metodología y Funcionamiento:** 
  - Uso de la arquitectura **YOLOv11n** (`yolo11n.pt`) configurada para la tarea de detección de cajas delimitadoras.
  - Estructuración y validación de un dataset personalizado compuesto por imágenes de vehículos con sus respectivas etiquetas formateadas para YOLO.
  - Configuración y entrenamiento local en entornos de Anaconda (`VC_P4`), gestionando la concurrencia y variables de entorno de OpenMP (`KMP_DUPLICATE_LIB_OK`).
- **Resultado:**
  ![Detección de Matrículas con YOLO](deteccion_yolo.png)

---

### Tarea 2: Extracción de Texto: PaddleOCR (Clásico) vs SmolVLM (Multimodal)
- **Descripción:** Procesamiento y lectura de los caracteres contenidos en los recortes de matrículas obtenidos por el detector.
- **Metodología y Funcionamiento:**
  - **PaddleOCR:** Sistema clásico optimizado para la localización y reconocimiento secuencial de texto de manera local y ligera.
  - **SmolVLM:** Evaluación de un modelo multimodal(VLM) ejecutados para interpretar de forma directa y semántica la imagen de la matrícula.

---

### Tarea 3: Evaluación de Rendimiento e Inferencia en Vídeo
- **Descripción:** Análisis comparativo del tiempo de inferencia y la precisión en la lectura de caracteres entre ambos sistemas sobre secuencias de vídeo.
- **Metodología y Funcionamiento:**
  - Integración del pipeline completo: Detección de la matrícula mediante YOLO y envío del recorte al motor de OCR correspondiente.
  - Sincronización del almacenamiento de archivos pesados y secuencias de vídeo mediante **Git LFS** (*Large File Storage*) en el repositorio.
- **Resultado:**
  ![Está en el archivo llamado Comparacion.csv]

---

## Requisitos y Ejecución

### Dependencias
Para ejecutar correctamente los scripts y cuadernos de esta práctica se requieren las siguientes librerías de Python:
- `ultralytics` (YOLOv11)
- `paddleocr` y `paddlepaddle`
- `transformers` y `torch` (para SmolVLM)
- `opencv-python` (`cv2`)
- `numpy` (`np`)
- `pandas` (`pd`)
- `ipykernel` e `ipywidgets`

### Utilización de IA
1. Mejorar rendimiento OCR
   A la hora de utilizar el PaddleOCR, me iba a muy bajo rendimiento, por lo cuál utilicé la IA para tener una solución la cuál es hacer que el PaddleOCR solo detecte cada N frames, lo cuál me ayudó mucho con el rendimiento.
2. Comprender el funcionamiento de los tracks_id.
   A la hora de realizar la forma en como los vehículos, personas... se mueven a cualquier dirección y los tracks_id(o el tracking), le pedí ayuda a la IA, ya que el tracking era algo que no comprendí.
