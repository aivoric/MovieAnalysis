## Introduction

This project aims to analyse Netflix movie and tv show listing database which is available on Kaggle.
https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies

The goal of the project is to answer 3 related to the dataset:
- What are the most and the least popular movie genres on Netflix?
- Which actors have played in the most amount of movies and which directors made the most movies?
- Can we predict a movie rating?


## Data & Analysis Files

The raw data has been downloaded and is available in this repository in the following 2 files:
- credits.csv
- titles.csv

All the analysis has been done inside the Jupyter notebook: 
- MovieNotebook.ipynb

## Tools and Libraries Used

Most of the analysis has been carried out using the following python libraries:
- Pandas
- Numpy
- Seaborn
- Matpotlib

For the prediction part XGBoost was used together with SKlearn in order to attempt to build a movie rating prediction model.

## Results

### Q1: What are the most and the least popular movie genres on Netflix?

![Most and least popular genre.](/images/genres.png?raw=true "Most and least popular genre.")

### Q2: Which actors have played in the most amount of movies and which directors made the most movies?

![Most popular actors.](/images/actors.png?raw=true "Most popular actors.")

![Most popular directors.](/images/actors.png?raw=true "Most popular directors.")

### Q3: Can we predict a movie rating?

With the current approach an accurate prediction cannot be achieved.

The goal was to see if an actor being present in a movie can serve as a strong predictor.

Every single actor in the data set was hot encoded, hence producing a table with many features.

The size of this table is:
74140 rows x 54087 colunns

Although an xgboost regression was performed to demonstrate how the algorithm could be used, it would
be innacurate in this case to use it since we don't have enough data samples.

Nevertheless, with the current XGBoost run we managed to achieve a mean squared error of TBD indicating
that there may be some predictive value in this model.
