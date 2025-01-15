# IMDb Movie Ratings Analysis Project 

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/imdb-top-50%20movies%20photo.png" alt="mdb-top-50 movies photo" width="600" height="300">

## Project Overview

IMDb is one of the most popular online databases for movies, TV shows, and celebrities, offering details on casts, production crews, plot summaries, and user ratings on a scale of 1 to 10.

This project analyzes IMDb movie ratings for films released between 1920 and 2023, utilizing **Python** for data manipulation and **Tableau** for data visualization. The objective is to uncover trends and patterns in movie ratings over time, with a particular focus on how ratings vary across genres.

The analysis highlights the following key areas:
- **Distribution of Ratings**: Visualized movie rating distributions across 0.25-point intervals to identify patterns
- **Trends in Movie Ratings Over Time**: Explored how average ratings have evolved over the past century
- **Trends in Number of Movie Releases and Ratings**: Examined growth in movie releases, the impact of COVID-19, and pre-existing declines in IMDb ratings over time.
- **Genre Popularity Analysis**: Identified trends in genre popularity by examining average ratings over time, revealing shifts in audience preferences
- **Correlation Between Genres and Ratings**: Measured the relationship between genre-specific ratings and the overall average rating, uncovering how closely each genre aligns with general audience trends over time
- **Number of Ratings by Genre**: Analyzed the disproportionate influence of frequently rated genres on overall rating trends.

Below are three interactive Tableau dashboards on genre ratings and the number of IMDb Ratings:
- [IMDb Movie Genre Rating Dashboard 1](https://public.tableau.com/app/profile/zaki.bouaoudia4587/viz/IMDbGenreRatingsDashboard/IMDbGenreRatingsDashboard)
- [IMDb Movie Genre Rating Dashboard 2](https://public.tableau.com/app/profile/zaki.bouaoudia4587/viz/IMDbGenreRatingsDashboard2/IMDbGenreRatingsDashboard2)
- [Number of IMDb Movie Ratings Dashboard](https://public.tableau.com/app/profile/zaki.bouaoudia4587/viz/NumberofIMDbMovieRatingsDashboard/NumberofIMDbMovieRatingsDashboard)

A Tableau story is used to walk through ratings, genre and relationship level analysis and can be found here [Tableau Story](https://public.tableau.com/app/profile/zaki.bouaoudia4587/viz/IMDbMovieRatingStoryAnalysis/IMDbMovieRatingAnalysisStory).

### Technologies Used
- **Python**: Data manipulation with **pandas** and visualization with **matplotlib**
- **Tableau**: Creating charts, dashboards and stories
- **Jupyter Notebook**: Development environment

## Dataset Structure
IMDb has a subset of its data accessible to customers for personal and non-commercial use [avalaible here](https://developer.imdb.com/non-commercial-datasets/). 
This project utilizes two tables from IMDb's online database downloaded in April of 2024: `title.basics`, `title.ratings` with a total row count of 12.72M records. A description of each table is as follows:

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/IMDb%20Project%20Table%20Schema.png" alt="IMDb Table Schemas" width="600" height="300">

## Data Cleaning, Transformation, and Manipulation

Prior to starting my investigation, a variety of data cleaning, transformation and manipulation processes were conducted which can be viewed on the [Jupyter Notebook file](https://github.com/Zaki978/IMDb-Movie-Ratings-Analysis/blob/main/Movie%20Rating%20Analysis%20Project%20V2.ipynb). These steps were essential in ensuring that the data was accurate, consistent, relevant, and structured appropriately for analysis and improved the reliability of the results.

- **Renamed columns** to improve clarity, such as changing 'Start Year' to 'Release Year'
- **Removed columns** to exclude unnecessary information, such as dropping the 'Original Title' and 'End Year' columns
- **Converted columns** to the appropriate data types, such as reformatting columns in the `titles.basic` table from object type to numerical, string, and boolean types
- **Handled missing values** by either filling them with NaN values or dropping the rows/columns with missing values.
  - Checked for null values in the data frame using the `df.isnull().sum() method`
  - Removed 76k rows where 'Genres' column had '\N' values
  - Removed 1.4M records with null values in the 'Release Year' as it was a crucial fields for analysis
  - Converted displaced year values that appeared in the 'Is Adult' column to null using a mapping dictionary
- **Filtered the data** to include only movies from the past 100 years and with a minimum number of ratings of 278.
  - Included only rows where the 'Title Type' column has values 'movie' or 'tvMovie'
  - Filtered movies by setting a minimum threshold for the number of ratings per movie at the top 75th percentile, equating to 278 ratings to avoid noise and improve data reliability
- **Merged tables** by performing an inner join on the 'filtered_movies' and 'imdb_ratings' dataframes using the 'Title ID' column to create a unified DataFrame for analysis.
- **Split the genres column** into multiple rows to allow for genre-level analysis.
- **Created new columns** deeper analysis, such as a 'Decade' column, to minimize short-term fluctuations from individual years and emphasize meaningful, actionable trends
  - Created a 'Movie Genre ID' field to identify genres associated with each title uniquely

## Overview of Findings

Successfully analyzed all genres in the IMDb dataset, identifying their average ratings. The findings revealed that **News, Documentary, and Biography** were the highest-rated genres, with averages in the high 6s to low 7s, while **Thriller, Sci-Fi, and Horror** had the lowest ratings, averaging in the low 5s. Additionally, the top-rated genres had a significantly smaller share of total ratings on IMDb, whereas the lowest-rated genres accounted for a much larger share.

Most genres showed a strong correlation with the overall average movie rating trend over time, except for the top three highest-rated genres. These genres maintained their popularity over time despite the general downward trend in ratings, as further illustrated in the heatmap.

Another key finding was the evolution of IMDb ratings and movie releases, with a sharp increase in both after IMDb's launch in 1990, followed by a significant decline in the past decade.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Ratings%20by%20Genre.png" alt="Distribution of Ratings Histogram" width="700" height="600">

## Insights Deep Dive
- **Distribution of Average Ratings**: The majority of movies have ratings between 5.5 and 7, with the 6.5 to 6.75 interval receiving the highest number of ratings (137k). This suggests that most movies are viewed as average to slightly above average in quality by IMDb's user base, with extreme ratings being uncommon
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Distribution%20of%20ratings%20Histogram.png" alt="Distribution of Ratings Histogram" width="700" height="350">

- **Trends in Movie Ratings Over Time**: Movie ratings have declined over time, with 1920s films averaging high 6s and recent decades averaging low 6s to high 5s. It is important to emphasize that this trend does not necessarily indicate a decline in movie quality over time. This does not necessarily reflect a decline in quality but may result from **rating bias**, as newer films are rated by larger, more diverse audiences, while older films attract smaller, niche audiences who rate them more favourably.
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Ratings%20Over%20Time.png" alt="Distribution of Ratings Histogram" width="900" height="550">

- **Number of Movies Released and Ratings**: Over time, the number of movies released and ratings on IMDb has grown significantly, likely driven by the expansion of the film industry and increased internet accessibility, contributing to greater ratings for newer movies. Movies released after IMDb's launch in 1990 far surpass earlier films in rating volume, reinforcing the idea of rating bias on declining rating averages. 
  - A sharp decline in movies released and rated occurred during COVID-19. As production halted, fewer movie releases led to a significant drop in IMDb ratings from 2019 to 2020.
  - IMDb had been declining since 2014, suggesting that COVID-19 did not initiate this downward trend but rather exacerbated it. This decline is likely due to reduced user engagement, driven by competition from platforms like Rotten Tomatoes and Letterboxd, which offers features addressing frustrations with IMDb's redesigns, promotional content, and limited social interactivity.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Movie%20Ratings%20vs%20Release%20Year.png" alt="Movie Ratings vs Movies Released" width="950" height="400">

- **Genre Popularity Analysis**: This heatmap suggests that the average ratings were higher in earlier decades (1920-1960s) but dropped in more recent years. As mentioned earlier, this pattern could be due to rating bias, as older films are often rated by niche audiences who appreciate them, leading to higher average ratings despite few total ratings. In contrast, the decline in ratings for recent decades could reflect a more diverse and varied audience or an increase in the quantity of mediocre films diluting the overall quality. 
  - *Horror, Sci-fi, and Thriller* genres consistently had the worst average ratings in the dataset across all periods of time.
  - *Documentary, Biography, and Animation* genres had the best average ratings in the dataset across all periods of time.
  
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Genre%20Heatmap%20Ratings.png" alt="Heatmap of Genre Ratings" width="900" height="400">

- **Correlation Between Genres and Rating**: - When visualizing the average ratings of specific genres over the years, such as drama, comedy, and action, we observe that their ratings closely align with the overall average rating (represented by the black dotted line), indicating a strong correlation between them.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Genre%20Rating%20Over%20Time%202.png" alt="Average Rating by Genre Over Time" width="700" height="350">

- After calculating the correlations below, the findings suggest that many genres have strong correlations between their average ratings and the overall average rating over time. This is namely the case with drama, comedy, and action, which had correlations of 0.91, 0.96, and 0.91, respectively, with the overall average. This indicates that as the overall average rating rises or falls, the average ratings for these genres tend to follow a similar pattern.

- We also notice, however, that news, documentary and biography genres have very low to negative correlations, implying that the ratings for these types of movies are less tied to the overall trend. This makes sense, as these genres have had the highest ratings throughout time. While other movie genres as a whole have decreased over time, the genres have maintained their popularity over time. 

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Gener%20Correlation%20results.png" alt="IMDb Movie Count Broken down by Genre" width="800" height="325">

- **Number of Ratings by Genre**: Drama, comedy, and action account for nearly half of all ratings, significantly amplifying their influence on overall trends. The aggregate average movie rating trend is largely driven by these genres, which explains the strong correlation between their individual ratings and the overall ratings.
  - High-rated genres, such as news (>0.1%), documentary (0.48%), and biography (2.5%), had a much smaller share of total ratings, limiting their influence on overall rating trends.
  - In contrast, low-rated genres like horror (3.79%), thriller (6.48%), and sci-fi (4.79%) accounted for a larger share of total ratings, giving them a greater impact on overall trends.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Number%20of%20Ratings%20by%20Genre.png" alt="Total Number of Ratings by Genre" width="600" height="550">

- Other Observations
  - **Average Movie Runtime** has steadily increased over time, being generally above 100 mins since 1960.
  - **Number of Movies on IMDb by Genre**: *Drama (53%) and Comedy (32%)* dominated, reflecting a high concentration of movie content in these two genres.
  - **The Shawshank Redemption** was both the most highly rated and the most rated movie in the dataset, with an average rating of 9.3 and a total of 2.88M ratings. 
  - **The Dark Night** was the second most-rated movie in the dataset, with a total of 2.86M ratings, while having the 4th highest average rating of 9.0.
  - **The Godfather** was the second most highly rated movie with an average rating of 9.2 while being the 8th most rated movie in the dataset. 

## Assumptions and Caveats
- **Genre Classification**: The project assumes that the genre classification provided by IMDb is accurate, although genre classification can be subjective and open to interpretation. IMDb limits each title to a maximum of three genres, even though a title could belong to more. Furthermore, the dataset includes 28 standardized genres, which, while useful for consistency, is not fully comprehensive and omits certain relevant genres, such as satire or niche categories
- **Ratings Threshold**: The project filters out movies with less than 278 ratings i.e the 75th percentile of the 'Number of Ratings' column. While this threshold helps ensure that only movies with sufficient audience engagement are included, thereby enabling more reliable conclusions, it remains somewhat arbitrary. Adjusting this threshold could influence the analysis and potentially alter the results.
- **Missing Data**: The project involves dropping rows with missing values in certain columns like 'Release Year' and "Genre", which had 1.4M and 76k missing values, respectively. This could potentially introduce bias if the missingness is not completely at random
- **Data Entry Errors**: Throughout the project, several data entry errors were identified, such as year values appearing in the 'Is Adult' column or release years exceeding the current calendar year. While many of these errors were addressed, it is possible that other unnoticed errors remain in the dataset
- **Data Source**: The data used in this project comes from IMDb, which primarily represents the opinions of its user base. Therefore, the insights may not be representative of the broader population's views on movies

### Author

Zaki Bouaoudia
