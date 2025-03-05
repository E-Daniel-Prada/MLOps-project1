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

Este proyecto contiene un entorno de desarrollo para **Machine Learning** utilizando **Docker Compose**.  
El entorno incluye:

✅ **JupyterLab** para la creación y entrenamiento de modelos.  
✅ **FastAPI** para exponer los modelos como una API de predicción.  
✅ **Carpeta compartida** entre Jupyter y FastAPI para almacenar los modelos entrenados.  

---

## 1. Preprocesamiento de Datos
El pipeline de preprocesamiento se encarga de limpiar, transformar y dividir los datos antes de su uso en el modelo.

### Pasos del pipeline:
1. **Carga del dataset**: Se utiliza Pandas para leer el archivo CSV.
2. **Generación de estadísticas**: Se usa `tensorflow_data_validation` (TFDV) para obtener estadísticas descriptivas de los datos.
3. **División de datos**: Se separa el dataset en conjuntos de entrenamiento (80%) y prueba (20%).
4. **Inferencia de esquema**: Se infiere la estructura de los datos con TFDV.
5. **Detección de anomalías**: Se validan los datos contra el esquema inferido para detectar inconsistencias.
6. **Transformaciones con `tensorflow_transform` (TFT)**: Se normalizan características específicas.
7. **Almacenamiento de los datos preprocesados**: Se guardan los conjuntos de datos transformados en archivos CSV.

## 2. Entrenamiento del Modelo
Se implementa un modelo de clasificación utilizando un **RandomForestClassifier** con preprocesamiento de características y reducción de dimensionalidad.

### Pasos del modelo:
1. **Carga del dataset**
2. **Codificación One-Hot para variables categóricas**
3. **Estandarización de características** con `StandardScaler`
4. **Selección de características** con `SelectKBest`
5. **Reducción de dimensionalidad** con PCA
6. **División de los datos en entrenamiento y prueba**
7. **Entrenamiento del modelo** con Random Forest
8. **Evaluación del modelo** (precisión, recall, F1-score)
9. **Guardado del modelo y preprocesadores** con `joblib`

---

##  **Despliegue del Entorno**  

Para iniciar el entorno:  

```sh
docker compose up --build
```
Esto descargará las imágenes necesarias y levantará los contenedores de **JupyterLab** y **FastAPI**.  

Para detener los contenedores en cualquier momento, usa:  

```sh
docker compose down
```

Para reiniciar todo desde cero (eliminando volúmenes y datos), usa:  

```sh
docker compose down -v
```

---

## 📂 **Estructura del Proyecto**  

```
📂 MLOps-Taller2
│── 📂 jupyter_work/              # Directorio donde se guardan los notebooks
│── 📂 models/                    # Carpeta compartida para almacenar los modelos entrenados
│── 📂 app/                        # Carpeta con la API FastAPI
│   ├── 📂 routes/                 # Endpoints de la API
│   │   ├── 📜 predict.py          # Lógica de predicción y carga de modelos
│   ├── 📜 main.py                 # Configuración principal de FastAPI
│── 📜 docker-compose.yml          # Configuración de los servicios en Docker
│── 📜 Dockerfile                  # Configuración de la imagen para FastAPI
│── 📜 requirements.txt            # Dependencias del proyecto
│── 📜 README.md                   # Documentación del proyecto
```

---

##  **Acceso a JupyterLab**  

Una vez que el contenedor está en ejecución, acceder a **JupyterLab** en:  

🔗 **URL de acceso:**  
```
http://localhost:8888
```
El acceso está configurado para **no requerir token ni contraseña**.  

---


## **Conclusión**

Este pipeline permite:\
✅ Explorar y analizar datos con **TFDV**.\
✅ Detectar anomalías y validar esquemas.\
✅ Aplicar transformaciones con **TFT**.\
✅ Entrenar y evaluar modelos de clasificación.\
✅ Realizar predicciones sobre nuevos datos.

