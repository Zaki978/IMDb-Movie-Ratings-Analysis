# IMDb Movie Ratings Analysis Project 

## Overview

This project aims to analyze IMDb movie ratings for films released over the past 100 years, from 1920 to 2023. The goal is to uncover trends, patterns, and insights from the data, providing a comprehensive understanding of how movie ratings have evolved over the century. Key area of focus of the analysis is on how movie ratings differ across for genres during different release periods. 

## Setup and Installation

This project is implemented in Python, using Jupyter Notebook. To set up and run the project, you will need to have Python and Jupyter Notebook installed on your machine. To set up the project environment, follow these steps:

1. **Get the Data**: 
   - Visit IMDb Non-Commercial Datasets: [IMDb Datasets](https://developer.imdb.com/non-commercial-datasets/)
   - Download the title.basics.tsv.gz and the title.ratings.tsv.gz files.

2. **Clone the Repository**: 
   - Open GitHub Desktop and sign in with your GitHub account.
   - Click on File > Clone Repository.
   - In the URL tab, paste the URL of the repository you want to clone.

3. **Run Jupyter Notebook**
   - Run the Jupyter notebook called 'Movie Rating Analysis Project V2.ipynb'. 

## Data Sources

The primary data source for this project is the IMDB database, which provides comprehensive information on movies, including ratings, release dates, genres, and more.

## Key Areas of Exploration

- **Trends in Movie Ratings**: Analyze how movie ratings have changed over the decades.
- **Genre Analysis**: Explore which genres have the highest and lowest average ratings, and identify which genres have gained or lost popularity over time.
- **Correlation Analysis**: calculates the correlation of ratings for each genre compared to the overall rating average over time. This helps to understand how closely the ratings for each genre follow the overall trend in movie ratings.

## Key Findings

- **XXX**: 
- **YYY**: 

## Data Cleaning, Transformation, and Manipulation

The data cleaning process involves:

- **Renaming columns** for clarity.
- **Converting columns** to the appropriate data types, e.g numerical data types and strings. 
- **Handling missing values** by either filling them with appropriate values or dropping the rows/columns with missing values.
- **Filtering the data** to include only movies from the past 100 years and with a minimum number of ratings.
- **Splitting the genres column** into multiple rows to allow for genre-level analysis.
- **Creating new columns** for further analysis, such as a column indicating the decade in which the movie was released.

## Exporting the data

The final cleaned and transformed data is exported to a CSV file called 'IMDb_movie_ratingsNEW.csv' for further analysis and visualization in Tableau in the file called 'Movie Rating Visualization vFinal'. This allows for more complex visualizations and a more interactive exploration of the data.

### Author

Zaki Bouaoudia
