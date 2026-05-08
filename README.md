# Project Title

## Potential project: Do consultants rig the game for themselves?

Assessing whether awarding behaviour is affected by whether a consultant was contracted in the leadup to the procurement proper. 

Theoretically: consultants tend to favour (either explicitly/maliciously or implicitly) proposing a course of action that results in them being awarded a contract

### Data needed: should all be in the procurement dataset, but will need to clean it

- type of contract 
    - (then would create a new binary column for whether it was a consulting contract).
    - Then, assess which contracts come as a potential result of consulting 
        - Finally,** determine whether awarding behaviour is affected by the presence of a consulting contract **
- Company (will need to do the cleaning) - there could be a problem with different names for the consulting branch of a company versus the services/product branch of a company
    - Maybe we check for overlap instead of exact match?
- Dependent variables: binary, whether a contract awarded to the consulting company after a consulting contract was awarded. AND/OR _value_ of contracts awarded after consulting. 



Would need to somehow operationalize which **contracts** are precipitated by a consulting contract 



## Overview

This paper [...]

## File Structure

The repo is structured as follows (change as needed):

### `data/`

- `00-simulated_data` contains simulated data used to test the analysis pipeline.
- `01-raw_data` contains the raw data as obtained from [City of Toronto Open Data](https://open.toronto.ca/).
- `02-analysis_data` contains the cleaned datasets that were constructed.
- `03-table_data` contains formatted data tables used to generate Quarto outputs.

### `scripts/`  

- `00.0-run_pipeline.py` executes the entire data processing pipeline from simulation to final outputs.
- `01.0-simulate_data.py` generates synthetic datasets to test logic.
- `01.1-simulated_data_test.py` tests the structure of the simulated data.
- `02.0-download_data.py`  downloads the raw neighbourhood crime counts (2019–2024) and Census socioeconomic indicators (2021) from the City of Toronto's Open Data Portal.
- `03.0-clean_crime_data.py` preprocesses the raw crime data.
- `03.1-clean_profile_data.py` preprocesses the raw Census data.
- `04.0-merge_crime_profile.py` join the cleaned crime and profile datasets on neighbourhood identifiers.
- `04.1-merged_test.py` tests the structure of the simulated data
- `05-0-eda_neighbourhood_clusters.py` performs exploratory data analysis on socioeconomic proxies, calculates descriptive statistics, and inspects clustering diagnostics.
- `06.0-table_crime_clusters.py` aggregates annual crime rates by cluster (Low-, Medium-, High-Opportunity) and exports formatted tables.
- `07.0-plot_crime_clusters.py` creates visualizations of crime trajectories over time for each cluster.
- `08.0-model_evaluation.py` compares clustering algorithms (K-means vs. Gaussian Mixture Models) using metrics Silhouette Score, Davies–Bouldin Index, and Calinski–Harabasz Score.

### `paper/` 

- `paper.qmd` Quarto manuscript.
- `references.bib` Citations. 
- `paper.pdf` Compiled PDF.
- `fonts/` LaTex font assets (CM Serif).
- `styles/` APA 7 style formatting for Quarto.

### `other/`

- Supplementary materials including figures, literature, notes, and development sketches.

## Statement on LLM usage

This project was developed with the assistance of LLMs. 

**1. AI-assisted code completion** (e.g., GitHub Copilot, Qodo Gen) was used throughout development.

- Error messaging and debugging within selected scripts;
- Refining mathematical notation and function documentation;
- Formatting the Quarto manuscript.

## Pre-requisites

- Install required Python packages as specified in `uv.lock`.
- Run all tests with `pytest`.

## Acknowledgements

- [...]