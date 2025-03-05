# Covertype ML

Este proyecto contiene un pipeline de **Machine Learning** para el preprocesamiento, análisis y entrenamiento de modelos basado en **TensorFlow Data Validation (TFDV)** y **TensorFlow Transform (TFT)**.

---

## **Características del Proyecto**

✅ **Carga de datos** desde un archivo CSV.\
✅ **Análisis exploratorio** con estadísticas y visualización de datos.\
✅ **Detección de anomalías** y validación del esquema de datos.\
✅ **Preprocesamiento de datos** utilizando TensorFlow Transform.\
✅ **División del dataset** en entrenamiento y prueba.\
✅ **Almacenamiento de datos preprocesados**.

---

## **Requerimientos Previos**

Para ejecutar el proyecto, asegúrate de tener instaladas las siguientes dependencias:

```sh
pip install -r requirements.txt
```

---

## **Estructura del Proyecto**

```plaintext
📂 covertype-ml
│── 📂 data/                     # Directorio para almacenar el dataset
│── 📂 notebooks/                # Notebooks para exploración y análisis
│── 📂 models/                   # Carpeta para almacenar modelos entrenados
│── 📂 src/                      # Código fuente del proyecto
│   ├── 📜 preprocess.py         # Script para preprocesamiento de datos
│   ├── 📜 train.py              # Script para entrenamiento de modelos
│   ├── 📜 predict.py            # Script para realizar predicciones
│   ├── 📜 utils.py              # Funciones auxiliares
│── 📜 dataset.csv               # Dataset utilizado en el proyecto
│── 📜 requirements.txt          # Dependencias del proyecto
│── 📜 README.md                 # Documentación del proyecto
```

---

## **Ejecutar el Proyecto**

### 1️⃣ **Preprocesar los Datos**

Ejecuta el script de preprocesamiento para generar estadísticas, validar el esquema y transformar los datos:

```sh
python src/preprocess.py
```

Este paso genera estadísticas exploratorias y detecta anomalías en los datos.

---

### 2️⃣ **Entrenar un Modelo**

Ejecuta el siguiente comando para entrenar un modelo sobre los datos preprocesados:

```sh
python src/train.py
```

El modelo entrenado se guardará en la carpeta `models/`.

---

### 3️⃣ **Realizar Predicciones**

Ejecuta el script de predicción con datos nuevos:

```sh
python src/predict.py --input "47.2,13.7,214.0,4925.0,1,2"
```

O puedes importar las funciones en un entorno interactivo:

```python
from src.utils import load_model, predict

model = load_model("models/trained_model.pkl")
data = [[47.2, 13.7, 214.0, 4925.0, 1, 2]]
prediction = predict(model, data)
print("Predicción:", prediction)
```

---

## **Conclusión**

Este pipeline permite:\
✅ Explorar y analizar datos con **TFDV**.\
✅ Detectar anomalías y validar esquemas.\
✅ Aplicar transformaciones con **TFT**.\
✅ Entrenar y evaluar modelos de clasificación.\
✅ Realizar predicciones sobre nuevos datos.

