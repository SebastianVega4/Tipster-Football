# ⚽ Pronósticos Inteligentes de Fútbol - Flask & ML

[![Python](https://img.shields.io/badge/Built%20with-Python%203.9%2B-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Web%20Framework-Flask-black?style=for-the-badge&logo=flask)](https://flask.palletsprojects.com/)
[![Scikit-learn](https://img.shields.io/badge/Machine%20Learning-Scikit--learn-orange?style=for-the-badge&logo=scikit-learn)](https://scikit-learn.org/)
[![API-Football](https://img.shields.io/badge/Data%20Source-API--Football%20(RapidAPI)-red?style=for-the-badge&logo=react)](https://rapidapi.com/api-sports/api/api-football)
[![License](https://img.shields.io/badge/License-GPL%203.0-brightgreen?style=for-the-badge)](https://www.gnu.org/licenses/gpl-3.0.html)

---

## 🎯 Descripción General

Este proyecto implementa una **aplicación web en Flask** para predecir los resultados de partidos de fútbol utilizando datos reales obtenidos de la **API-Football (RapidAPI)** y modelos de **Machine Learning (Scikit-learn)**. La aplicación permite a los usuarios seleccionar dos equipos y una liga, para luego generar pronósticos detallados sobre el marcador, el resultado del partido, estadísticas clave y un análisis textual basado en el rendimiento histórico y los enfrentamientos directos.

El core del sistema se apoya en modelos de regresión **Poisson** para la predicción de goles y un clasificador **Random Forest** para el resultado del partido, ambos entrenados con datos simulados (o históricos si se extienden) para ofrecer predicciones robustas. Incluye también un sistema de **caché** para optimizar las llamadas a la API y mejorar la eficiencia.

---

## ✨ Características Destacadas

* **Predicción de Resultados**: Pronostica el marcador exacto, el resultado (victoria local, empate, victoria visitante) y otras métricas de apuestas como "Over/Under" y "Ambos equipos marcan".
* **Integración con API-Football**: Obtiene datos en tiempo real (o de la temporada anterior para estadísticas) sobre ligas, equipos, estadísticas detalladas de partidos y el historial de enfrentamientos directos (Head-to-Head).
* **Modelos de Machine Learning**:
    * **Regresión de Poisson**: Utilizado para predecir la cantidad de goles esperados por cada equipo.
    * **Random Forest Classifier**: Empleado para predecir el resultado final del partido (victoria, empate, derrota).
* **Análisis Dinámico**: Genera un análisis textual descriptivo de los factores clave que influyen en la predicción, como el rendimiento ofensivo/defensivo de los equipos y el historial H2H.
* **Interfaz Web Intuitiva**: Permite a los usuarios seleccionar fácilmente equipos y ligas a través de un formulario simple en una aplicación Flask.
* **API RESTful**: Ofrece endpoints para consultar competiciones, equipos y realizar predicciones programáticamente, facilitando la integración con otras aplicaciones.
* **Caché de API**: Implementa un sistema de caché para reducir las llamadas repetitivas a la API-Football, mejorando la velocidad y la adherencia a los límites de la API.

---

## ⚙️ Tecnologías Utilizadas

* **Backend**: Python 3.9+
* **Framework Web**: Flask
* **Manejo de Peticiones HTTP**: `requests`
* **Procesamiento Numérico**: `numpy`
* **Machine Learning**: `scikit-learn` (PoissonRegressor, RandomForestClassifier, StandardScaler)
* **Base de Datos / Fuente de Datos**: API-Football (a través de RapidAPI)
* **Templating**: Jinja2 (integrado en Flask para las vistas `HTML`)
* **Estructura**: HTML, CSS (básico)

---

## 📂 Estructura del Repositorio

La estructura del proyecto es sencilla y se centra en el archivo `app.py` que contiene toda la lógica de la aplicación Flask, la interacción con la API y los modelos de ML.
```
Football_Predictor/
│
├── app.py                      # Lógica principal de la aplicación Flask, API y modelos ML
├── templates/                  # Archivos HTML de la interfaz de usuario
│   ├── index.html              # Página principal para seleccionar equipos
│   ├── result.html             # Página para mostrar los resultados de la predicción
│   └── error.html              # Página para mostrar mensajes de error
├── .gitignore                  # Archivos y carpetas excluidas del control de versiones
└── README.md                   # Documentación del proyecto
```

---

## 🚀 Instrucciones de Ejecución

Para poner en marcha este proyecto en tu entorno local, sigue estos pasos:

### Requisitos

* **Python 3.9+**
* **pip** (gestor de paquetes de Python)
* Una **API Key de API-Football** (puedes obtener una en [RapidAPI](https://rapidapi.com/api-sports/api/api-football)).

### Pasos para la ejecución

1.  **Clonar el repositorio**:
    ```bash
    git clone https://github.com/SebastianVega4/Tipster-Football/
    cd Football_Predictor
    ```

2.  **Crear un entorno virtual (opcional pero recomendado)**:
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Linux/macOS
    # venv\Scripts\activate   # En Windows
    ```

3.  **Instalar dependencias**:
    ```bash
    pip install -r requirements.txt
    ```
    Si no tienes un `requirements.txt`, puedes crearlo manualmente o instalar las dependencias una por una:
    ```bash
    pip install Flask requests numpy scikit-learn
    ```

4.  **Configurar tu API Key**:
    Abre el archivo `app.py` y reemplaza tu propia API Key de RapidAPI en la línea `API_KEY`.
    ```python
    API_KEY = "TU_API_KEY"
    ```

5.  **Ejecutar la aplicación Flask**:
    ```bash
    python app.py
    ```

6.  **Acceder a la aplicación**:
    Abre tu navegador y navega a `http://127.0.0.1:5000/`.

---

## 👨‍🎓 Autor

Desarrollado por **Sebastián Vega**

📧 *Sebastian.vegar2015@gmail.com*

🔗 [LinkedIn - Johan Sebastián Vega Ruiz](https://www.linkedin.com/in/johan-sebastian-vega-ruiz-b1292011b/)

---

## 📜 Licencia

Este repositorio se encuentra bajo la Licencia **GPL 3.0**.

**Permisos:**
* Uso comercial
* Modificación
* Distribución
* Uso privado

---

Facultad de Ingeniería — Ingeniería de Sistemas 🧩

**🏫 Universidad Pedagógica y Tecnológica de Colombia**
📍 Sogamoso, Boyacá 📍

© 2025 — Sebastian Vega

---
