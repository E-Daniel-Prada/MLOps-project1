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

