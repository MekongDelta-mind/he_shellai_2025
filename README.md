# he_shellai_2025

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

A short description of the project.

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         he_shellai and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── he_shellai   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes he_shellai a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------


# Improvemnts or Additions to the project

1. Adding the MLFlow experiment tracking code from Eugene Yan's website.
    1. [Paper and mlflow repo example](https://github.com/MekongDelta-mind/papermill-mlflow)
    1. [Blod explaining how to implement it](https://eugeneyan.com/writing/experimentation-workflow-with-jupyter-papermill-mlflow/?)
    1. I think most importantly I should be wokring with the following code in the modelling notebook:
    ```python
    with mlflow.start_run():
        mlflow.log_param('index', index)
        mlflow.log_param('model', model_name)
        mlflow.log_metric('auc', auc)
        mlflow.log_metric('recall', recall)
        mlflow.log_metric('precision', precision)
        mlflow.log_metric('f1', f1)
        mlflow.log_artifact(model_path)
        mlflow.log_artifact(roc_path)
        mlflow.log_artifact(pr_path)
    ```
1. I haven't used the LightGBM model.
    1. also have to add the Hypertmetric tuning of the LighGM model code.