# nyc-taxi-trip-duration-prediction

==============================

Machine Learning Ops project to predict trip duration for taxis in NYC


#### Project Highlights (Technical):
1) This project aims to use the latest MLOps tools to maintain ML models in production like - DVC, git for data and code versioning, and Docker to containerize the models and expose models as service by wrapping up with APIs. (I have used cookiecutter for the project code structure).
2) I have taken the widely used NYC Taxi dataset for this project and experimented with various ML models - XGBoost, RandomForest, Linear Regression and Time series baselines like - Moving average and exponential smoothing. Please refer to this notebook for detailed EDA - [notebook][https://github.com/avsk80/nyc-taxi-trip-duration-prediction/blob/master/notebooks/NYC%20taxi.ipynb]
3) To track the code I used git, and to track the data files I used DVC where my local storage is remote. This can be easily extended to any of the cloud services like S3, GCS, Blob storage etc. in the future.
4) [To be done] Use MLFlow to track model experimentation and results as a dashboard. Mlflow gives a more detailed view than DVC.
     
#### Business Impact
5) The business impact of building such models is that taxis can be diverted to locations where the probability of finding passengers is more likely. Thereby, increasing revenue stream for both the drivers as well as the Taxi vendor services. 

#### To execute this project:
1) Download or clone this repository
2) Run the FastAPI script as
```cmd
   python app.py
```

## Important

This code will give error until the project is installed as a package in the environment that has all the dependencies for the project.

After creation of environment and installation of all required packages using pip run this command in the command terminal.

```cmd
pip install -e .
```

| This will fix all the import statement errors such as `ModuleNotFoundError` when recreating pipelines using command

```cmd
dvc repro
```

## Docker

Download Docker Desktop from the link [download here](https://www.docker.com/products/docker-desktop/)

Once you are in project folder just type in the command

```cmd
docker init
```

> It is advised to check the DOCKERFILE before committing to the build image phase. You can check the DOCKERFILE in the project.

The next command to run is

```cmd
docker compose up --build
```

## Project Organization

------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
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
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io

------------
