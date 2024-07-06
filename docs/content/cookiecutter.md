
# Cookiecutter

## Estructura

Está basada en [Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/) pero simplifacada en el [Template IDS Cookiecutter](https://github.com/aastroza/cookiecutter-ids).

```
├── LICENSE
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
│
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g. generated with `pip freeze > requirements.txt`
```

## Los datos son inmutables

* Nunca se debe editar la data cruda (raw data).
    * Nunca se debe editar manualmente.
        * Nunca se debe editar en Excel.
* Nunca se debe sobre-escribir raw data.
* No se debe guardar múltiples versiones de un archivo de raw data
* El código que se escriba debe mover la data cruda por medio de un pipeline hacia el análisis final.
* Cualquier persona debería poder reproducir los resultados sólo teniendo la carpeta `data/raw` y el código en la carpeta `src`.
* Si los datos son inmutables entonces no necesita tener el mismo control de versiones que el código. Por defecto el directorio data debería estar incluido en el archivo `.gitignore`.

## Los notebooks son para exploración y comunicación

* Son muy buenos para análisis exploratorio pero no tan buenos para reproducir de forma efectiva ese análisis.
* Se sugiere trabajar en carpetas dentro del directorio notebooks.
* Se sugiere seguir una convención para nombrar los archivos: `<step>-<ghuser>-<description>.ipynb`. Ejemplo: `03-aastroza-visualize-distributions.ipynb`
* Hay que hacer refactorizaciones de las partes claves. No se debe repetir el código de la misma tarea en diferentes notebooks. Si el código es útil, escribanlo siempre a la carpeta `src`.
* Por ejemplo: si es una tarea de preprocesamiento de datos, hay que poner el pipeline en `src/data/make_dataset.py` y cargar datos desde `data/interim`. 

## Refactorizando código en módulos compartidos

A medida que avance tu proyecto, querrás refactorizar tu código de manera que sea fácil de compartir entre notebooks y scripts. Recomendamos crear un módulo en la carpeta {{ src.module_name }} que contenga el código que usas en tu proyecto. Esta es una buena forma de asegurarte de que puedas usar el mismo código en varios lugares sin tener que copiar y pegar.

Dado que la estructura predeterminada es un paquete de Python y está instalado por defecto, puedes hacer lo siguiente para que ese código esté disponible dentro de un cuaderno de Jupyter.

Primero, recomendamos activar la extensión autoreload. Esto hará que Jupyter siempre vuelva al código fuente del módulo en lugar de almacenarlo en caché en la memoria. Si tu cuaderno no refleja los últimos cambios realizados en un archivo .py, intenta reiniciar el kernel y asegúrate de que autoreload esté activado. Agregamos una celda al inicio del notebook con lo siguiente:

```python
%load_ext autoreload
%autoreload 2
```

Ahora todo tu código debería ser importable. Podrías usarlo importándolo de la siguiente manera:

```python
from src.data import make_dataset

data = make_dataset()
```

Ahora debería ser fácil hacer cualquier refactorización que necesites para que tu código sea más modular y reutilizable.
