# 📸 Proyecto de Reconocimiento de Ciclistas por Número de chapa

Este proyecto procesa fotografías de ciclistas para detectar la ubicación de la chapa, generar un recorte de la misma y exportar los resultados a un archivo Excel para su transcripción manual.

Inicialmente se intentó utilizar OCR para automatizar la lectura de números, pero debido a su baja precisión, se optó por la revisión manual a partir de los recortes.

---

## 📂 Resultados generados

Se crean dos archivos de salida en Excel:

### ✅ Dorsales detectados

En este archivo se incluyen todos los recortes donde YOLO logró encontrar un dorsal.

![Formato excel detectados](./img_readme/formato_dorsales_recortes.png)

Aquí, el número del dorsal se transcribe en la columna adyacente, lo que permite organizar y procesar fácilmente la información.

---

### ❌ Dorsales no detectados

En el caso de que YOLO no logre reconocer el dorsal, se genera un Excel con el nombre del archivo y un link directo a la imagen original para poder identificarlo manualmente.

![Formato excel no detectados](./img_readme/formato_no_reconocidos.png)

---

## 📌 Funcionamiento

1. Se colocan todas las fotos en la carpeta `Imagenes/`.
2. El programa ejecuta YOLO para detectar dorsales y genera los recortes en la carpeta `recortes/`.
3. Se generan dos archivos Excel:
- dorsale_recortex.xlsx
- no_detectados.xlsx

---

## 🚀 Tecnologías utilizadas

- Python
- OpenCV – para procesamiento de imágenes
- YOLO – para detección de dorsales
- Pandas / OpenPyXL – para la generación de archivos Excel

---

## 🔧 Instalación y uso

```bash
# Clonar el repositorio
git clone https://github.com/JorgeBou/reconocimiento-ciclistas.git
cd reconocimiento-ciclistas

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar el script principal
python excel.py
```

---

## 🔮 Futuras mejoras

- Entrenar un modelo específico para dorsales.
- Mejorar el entrenamiento de YOLO para aumentar la precisión.
- Integrar una interfaz web para cargar imágenes y visualizar resultados sin necesidad de abrir Excel.

