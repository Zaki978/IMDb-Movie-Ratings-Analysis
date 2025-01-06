# IMDb Movie Ratings Analysis Project 

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/imdb-top-50%20movies%20photo.png" alt="mdb-top-50 movies photo" width="600" height="300">

## Project Overview

IMDb is one of the world's most popular online databases for information on movies, TV shows, and celebrities. The IMDb platform allows users to view details on casts, production crews, biographies, plot summaries and the ability to rate movies on a scale of 1 to 10. 

The aim of this project is to analyze IMDb movie ratings for films released over the past 100 years, from 1920 to 2023, using **Python** for data manipulation and **Tableau** for data visualization. The goal is to uncover trends, patterns, and insights from the data, providing a comprehensive understanding of how movie ratings have evolved over the century. Key area of focus of the analysis is on how movie ratings differ across genres during different release periods. 

The main insights concentrate on the following subjects: 
- **Distribution of Ratings**: Visualized movie rating distributions across 0.25-point intervals to identify key patterns
- **Trends in Movie Ratings Over Time**: Analyzed how average ratings have evolved over the past century, reflecting shifts in audience preferences and industry standards
- **Genre Popularity Analysis**:  Identified trends in genre popularity by analyzing average ratings over time, revealing shifts in audience preferences
- **Correlation Between Genres and Ratings**: Measured the relationship between genre-specific ratings and the overall average rating, uncovering how closely each genre aligns with general audience trends over time
- **Number of Movie Ratings**: Ranked the most rated movies and illustrated the growth in rating activity over time, linking it to the increase in movie releases and demonstrating the effect of filtering data by minimum rating counts 
- **Number of Movies on IMDb Broken Down by Genre**: Provided a breakdown of the number of movies available on IMDb by genre for a clearer view of representation

### Technologies Used
- **Python**: Data manipulation with **pandas** and visualization with **matplotlib**
- **Tableau**: Creating charts, dashboards and stories
- **Jupyter Notebook**: Development environment

## Dataset Structure
IMDb has a subset of its data accessible to customers for personal and non-commercial use [avalaible here](https://developer.imdb.com/non-commercial-datasets/). 
This project utilizes two tables from IMDb's online database: title.basics, title.ratings with a total row count of 12.72M records. A description of each table is as follows:

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/IMDb%20Project%20Table%20Schema.png" alt="IMDb Table Schemas" width="600" height="300">

## Data Cleaning, Transformation, and Manipulation

Prior to starting my investigation, a variety of data cleaning, transformation and manipulation processes were conducted which can be viewed on the [Jupyter Notebook file](https://github.com/Zaki978/IMDb-Movie-Ratings-Analysis/blob/main/Movie%20Rating%20Analysis%20Project%20V2.ipynb). These steps were essential in ensuring that the data was accurate, consistent, relevant, and structured appropriately for analysis and improved the reliability of the results.

- **Renaming columns** to improve clarity, such as changing 'Start Year' to 'Release Year'
- **Converting columns** to the appropriate data types, such as reformatting columns in the `titles.basic` table from object type to numerical, string, and boolean types
- **Handling missing values** by either filling them with appropriate values or dropping the rows/columns with missing values.
- **Merging tables** merged the 'filtered_movies' and 'imdb_ratings' DataFrames using 'Title ID' to create a comprehensive dataframe for analysis
- **Filtering the data** to include only movies from the past 100 years and with a minimum number of ratings.
- **Splitting the genres column** into multiple rows to allow for genre-level analysis.
- **Creating new columns** deeper analysis, such as a decade column, to minimize short-term fluctuations from individual years and emphasize meaningful, actionable trends

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



## Exporting the data

The final cleaned and transformed data is exported to a CSV file called 'IMDb_movie_ratingsNEW.csv' for further analysis and visualization in Tableau in the file called 'Movie Rating Visualization vFinal'. This allows for more complex visualizations and a more interactive exploration of the data available on my [Tableau Public Profile](https://public.tableau.com/app/profile/zaki.bouaoudia4587/vizzes).

## Assumptions and Caveats


### Author

Zaki Bouaoudia
