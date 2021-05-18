# System Identification Methods for Dynamic Models of Brain Activity
![Overview](reports/figures/FIG1-1.png "Overview")
![Example Mode](reports/figures/FIG3-1.png "Example Mode")
![Brain Mode 1](reports/figures/mode1.gif "Example Brain Mode 1") 
==============================

This repo is the implementation of our paper *System Identification Methods for Dynamic Models of Brain Activity*.
> [**System Identification Methods for Dynamic Models of Brain Activity**](https://www.sciencedirect.com/science/article/pii/S1746809421003621#!)    
> Tristan Griffith, James Hubbard        
> [Biomedical Signal Processing and Control](https://www.sciencedirect.com/journal/biomedical-signal-processing-and-control)      
> https://doi.org/10.1016/j.bspc.2021.102765

## Reference
If you find this repo useful in your research, please cite our work. Gotta get those rookie numbers up.
```
@article{GRIFFITH2021102765,
title = {System identification methods for dynamic models of brain activity},
journal = {Biomedical Signal Processing and Control},
volume = {68},
pages = {102765},
year = {2021},
issn = {1746-8094},
doi = {https://doi.org/10.1016/j.bspc.2021.102765},
url = {https://www.sciencedirect.com/science/article/pii/S1746809421003621},
author = {Tristan D. Griffith and James E. Hubbard},
keywords = {System identification, Modal decomposition, EEG dynamics},}
```
## Quick Start
### 1. Clone this repository
### 2. Run Classification Model of interest

## Full Pipeline
### 1. Download Data
- DEAP data: The DEAP data set is publicly available, but requires access request [here](http://anaxagoras.eecs.qmul.ac.uk/request.php?dataset=DEAP). It should be placed in the src/data folder
- EEGMMI data: Download the EEGMMI data set into the src/data folder of this repository using: ```wget -r -N -c -np https://physionet.org/files/eegmmidb/1.0.0/``` 
- Alternatively, this repository contains the processed data by default. You can skip generating features and just run the subject classification model.
### 2. Create environment
- Open a terminal to the root of this repository, where ```environment.yml``` is located. 

```conda env create -f environment.yml```

```conda activate eegID```

### 3. Generate Features
- Select Matlab script in ```src/features``` for data and algortithm of interest 
   - ```src/features/DMDheatmaps.m``` generates the heatmaps and tabular input data for the DEAP dataset with the DMD algorithm
   - ```src/features/DMDheatmaps_Physio.m``` generates the heatmaps and tabular input data for the EEGMMI dataset with the DMD algorithm
   - ```src/features/OMAheatmaps.m``` generates the heatmaps and tabular input data for the DEAP dataset with the OMA algorithm
   - ```src/features/DMDheatmaps_Physio.m``` generates the heatmaps and tabular input data for the EEGMMI dataset with the OMA algorithm
- Modify heatmap and tabular output paths according to your needs 

### 4. Run Classification Model
- Select the relevant Jupyter notebook for the generated features
- Modity the path variable to target your features instead of the preprocessed data
- Run the notebook

# Project Organization
------------

    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
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


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
