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