# data-512-a2

Welcome to the bias through data on Wikipedia politician articles project!

## Goal
The goal of this project is to explore the concept of bias through data on Wikipedia articles - specifically, articles on political figures from a variety of countries. We will combine a dataset of Wikipedia articles with a dataset of country populations, and use a machine learning service called ORES to estimate the quality of each article.


## Data source
The Wikipedia politicians by country dataset can be found on Figshare: https://figshare.com/articles/dataset/Untitled_Item/5513449

The population data is available in CSV format as WPDS_2020_data.csv. This dataset is drawn from the world population data sheet published by the Population Reference Bureau:
https://www.prb.org/international/indicator/population/table/

We will use a service ORES to obtain the prediction scores for each article, details can be found here:
https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model

## Project structure

### Python notebook (under `src/`)
This will be the main noteboook that contains code that performs data acquisition, data processing and analysis. The notebook `hcds-a2-bias.ipynb` will be the main execution point for the project.

### Raw data (under `data/`)
This directory contains raw data files that are collected directly from the sources above. 

### Cleaned data (under `data-cleaned/`)
This directory contains the csv files that are cleaned and processed, also including the prediction responses from ORES.

### Combined data (under `data-combined`)
This directory contains a csv file that contains a joint dataset from the data sources above, along with their prediction scores.

## How to run the project
To run the project, open the notebook `hcds-a2-bias` under `src/`. Select `Cell -> Run All`. This will generate the analysis results and all intermediate datasets including the raw data and procssed data.

Note that by default it will not call ORES API to get the prediction scores, rather it will read from the cached pickle file in the repository. To let it call ORES API, you will need search `run_queries` and change it to `True` 

