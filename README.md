# IMDb Movie Ratings Analysis Project 

## Overview

The aim of this project is to analyze IMDb movie ratings for films released over the past 100 years, from 1920 to 2023, using **Python** for data manipulation and **Tableau** for data visualization. The goal is to uncover trends, patterns, and insights from the data, providing a comprehensive understanding of how movie ratings have evolved over the century. Key area of focus of the analysis is on how movie ratings differ across genres during different release periods. 

### Technologies Used
- **Python**: Data manipulation with **pandas** and visualization with **matplotlib**
- **Jupyter Notebook**: Development environment
- **Tableau**: Creating charts and dashboards

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

- **Trends in Movie Ratings**: Analyze how movie ratings change over the decades in which movies were produced.
- **Genre Analysis**: Explore which genres have the highest and lowest average ratings, and identify which genres have gained or lost popularity over time.
- **Correlation Analysis**: calculates the correlation of ratings for each genre compared to the overall rating average over time. This helps to understand how closely the ratings for each genre follow the overall trend in movie ratings.

## Key Findings

- **Distribution of Average Ratings**: Most movies fall in the 5.5 to 7 rating range indicating that most movies are perceived as average to slightly above average in quality by IMDb's userbase. 
- **Downwards Trend in Average Ratings**: Overall movie ratings have declined over the release period, remaining just below an average of 6 out of 10 for the past two decades, with a slight rebound in the last three years. One possible explanation for this downward trend is rating bias, as newer movies are evaluated by larger, more diverse audiences, resulting in greater variability and potentially lower average ratings.
- **Number of Movies Released and Ratings** have substantially increased over time but both declined harshly during COVID-19.
- **High correlation** between the average rating of genres compared to the overall average over time. Thus, when the overall average rating increases or decreases, the average rating for individual genres tends to move in the same direction. This suggests that ratings across genres are strongly influenced by similar factors influencing the overall trend.
- **Horror, Sci-fi and Thriller** genres had the worst average ratings in the dataset across all periods of time.
- **News, Documentary and Biography** genres had the best average ratings in the dataset across all periods of time.
- **Drama (53%) and Comedy (32%)** genres together dominate the content on IMDb, reflecting a high concentration of movies in these two genres compared to others.
- **Average Movie Runtime** has steadily increased over time, being generally above 100 mins since 1960.
- **The Shawshank Redemption** was the most highly rated movie in the dataset (considering movies with at least 100k reviews), with an average rating of 9.3.
- **The Dark Night** was the most rated movie in the dataset, with a total of 8.58M ratings and an average rating of 9.0.

## Data Cleaning, Transformation, and Manipulation

The data cleaning process involves:

- **Renaming columns** for clarity.
- **Converting columns** to the appropriate data types, e.g numerical data types and strings. 
- **Handling missing values** by either filling them with appropriate values or dropping the rows/columns with missing values.
- **Filtering the data** to include only movies from the past 100 years and with a minimum number of ratings.
- **Splitting the genres column** into multiple rows to allow for genre-level analysis.
- **Creating new columns** for further analysis, such as a column indicating the decade in which the movie was released.

## Exporting the data

The final cleaned and transformed data is exported to a CSV file called 'IMDb_movie_ratingsNEW.csv' for further analysis and visualization in Tableau in the file called 'Movie Rating Visualization vFinal'. This allows for more complex visualizations and a more interactive exploration of the data available on my [Tableau Public Profile](https://public.tableau.com/app/profile/zaki.bouaoudia4587/vizzes).

### Author

Zaki Bouaoudia
