# IMDb Movie Ratings Analysis Project 

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/imdb-top-50%20movies%20photo.png" alt="mdb-top-50 movies photo" width="600" height="300">

## Project Overview

IMDb is one of the most popular online databases for movies, TV shows, and celebrities, offering details on casts, production crews, plot summaries, and user ratings on a scale of 1 to 10.

This project analyzes IMDb movie ratings for films released between 1920 and 2023, utilizing **Python** for data manipulation and **Tableau** for data visualization. The objective is to uncover trends and patterns in movie ratings over time, with a particular focus on how ratings vary across genres.

The analysis highlights the following key areas:
- **Distribution of Ratings**: Visualized movie rating distributions across 0.25-point intervals to identify patterns
- **Trends in Movie Ratings Over Time**: Explored how average ratings have evolved over the past century, reflecting shifts in audience preferences and industry standards
- **Trends in Number of Movie Releases and Ratings**: Examined growth in movie releases, the impact of COVID-19, and pre-existing declines in IMDb ratings over time.
- **Genre Popularity Analysis**: Identified trends in genre popularity by examining average ratings over time, revealing shifts in audience preferences
- **Correlation Between Genres and Ratings**: Measured the relationship between genre-specific ratings and the overall average rating, uncovering how closely each genre aligns with general audience trends over time
- **Number of Movie Ratings**: Ranked the most rated movies and illustrated the growth in rating activity over time, linking it to the increase in movie releases and demonstrating the effect of filtering data by minimum rating counts 
- **Number of Movies on IMDb Broken Down by Genre**: Provided a breakdown of the number of movies available on IMDb by genre for a clearer view of representation

Advanced visualizations and interactive exploration of the data are available on my [Tableau Public Profile](https://public.tableau.com/app/profile/zaki.bouaoudia4587/vizzes).

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

- **Renaming columns** to improve clarity, such as changing 'Start Year' to 'Release Year'
- **Removing columns** to exclude unnecessary information, such as dropping the 'Original Title' and 'End Year' columns
- **Converting columns** to the appropriate data types, such as reformatting columns in the `titles.basic` table from object type to numerical, string, and boolean types
- **Handling missing values** by either filling them with NaN values or dropping the rows/columns with missing values.
  - Checked for null values in the data frame using the `df.isnull().sum() method`
  - Removed 76k rows where 'Genres' column had '\N' values
  - Removed 1.4M records with null values in the 'Release Year' as it was a crucial fields for analysis
  - Converted displaced year values that appeared in the 'Is Adult' column to null using a mapping dictionary
- **Filtering the data** to include only movies from the past 100 years and with a minimum number of ratings of 278.
  - Included only rows where the Title Type column has values 'movie' or 'tvMovie' using `title_basics[title_basics['Title Type'].isin(['movie', 'tvMovie'])]`
  - Filtered movies by setting a minimum threshold for the number of ratings per movie at the top 75th percentile, equating to 278 ratings to avoid noise and improve data reliability
- **Merging tables** by performing an inner join on the filtered_movies and imdb_ratings dataframes using the 'Title ID' column to create a unified DataFrame for analysis.
- **Splitting the genres column** into multiple rows to allow for genre-level analysis.
- **Creating new columns** deeper analysis, such as a 'Decade' column, to minimize short-term fluctuations from individual years and emphasize meaningful, actionable trends
  - Created a Movie Genre ID to uniquely identify genres associated with each title

## Overview of Findings

Successfully identified all genres in the IMDb dataset and found average ratings for each genre in the dataset. mention that the genres with the lowest scores are usually the ones that have the most movies and reviews on IMDb which is the opportise for genres with the highest scores.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Ratings%20by%20Genre.png" alt="Distribution of Ratings Histogram" width="700" height="600">

## Insights Deep Dive
- **Distribution of Average Ratings**: The majority of movies have ratings between 5.5 and 7, with the 6.5 to 6.75 interval receiving the highest number of ratings (137k). This suggests that most movies are viewed as average to slightly above average in quality by IMDb's user base, with extreme ratings being uncommon
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Distribution%20of%20ratings%20Histogram.png" alt="Distribution of Ratings Histogram" width="700" height="350">

- **Trends in Movie Ratings Over Time**: Overall movie ratings have declined over the release period, with movies from the 1920s typically receiving ratings in the high 6s, compared to movies from the 2010s and 2020s generally receiving low 6s and high 5s. It is important to emphasize that this trend does not necessarily indicate a decline in movie quality over time. IMDb, established in 1990, primarily caters to younger audiences and does not fully represent the earlier decades in the dataset. One plausible explanation for the downward trend in ratings is **rating bias**: newer movies are assessed by larger, more diverse audiences, leading to greater variability and potentially lower average ratings. In contrast, older movies are often watched by smaller, niche audiences who are likely to appreciate these films more and rate them favorably. This dynamic will be explored further in the next chart.
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Ratings%20Over%20Time.png" alt="Distribution of Ratings Histogram" width="900" height="550">

- **Number of Movies Released and Ratings**: Over time, there has been a significant increase in both the number of movies released and the volume of ratings on IMDb. This growth is likely driven by the expansion of the film industry and increased internet accessibility, which have contributed to higher ratings for more recent movies. As illustrated in the graph, the volume of ratings for movies released after 1990 (the year IMDb was launched) far exceeds those for earlier movies, reinforcing the idea that rating bias has influenced the downward trend in movie ratings over time.
  - Another notable observation is the sharp decline in the number of movies released and rated during COVID-19. With movie production largely halted, fewer new films were available for audiences to rate, leading to a significant drop in the volume of IMDb ratings from 2019 to 2020.
  - When examining the period before COVID-19, it becomes evident that the number of movie ratings on IMDb had been declining since 2014, suggesting that COVID-19 did not initiate this downward trend but rather exacerbated it. One possible explanation for this decline is that IMDb's dataset may have become less comprehensive over time. However, a more plausible explanation points to a decline in user engagement. IMDb now faces significant competition from platforms like Rotten Tomatoes and Metacritic, which provide alternative perspectives on film reviews, as well as newer apps like Letterboxd, which have gained traction by addressing user frustrations. Issues such as unpopular redesigns, increased promotional content, and the lack of engaging social features have driven some users to these newer platforms, which offer a more tailored and interactive experience.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Movie%20Ratings%20vs%20Release%20Year.png" alt="Movie Ratings vs Movies Released" width="950" height="400">

- **Genre Popularity Analysis**: This heatmap suggests that the average ratings were higher in earlier decades (1920-1960s) but dropped in more recent years. As mentioned earlier, this pattern could be due to rating bias, as older films are often rated by niche audiences who appreciate them, leading to higher average ratings despite few total ratings. In contrast, the decline in ratings for recent decades could reflect a more diverse and varied audience or an increase in the quantity of mediocre films diluting the overall quality. 
  - *Horror, Sci-fi, and Thriller* genres consistently had the worst average ratings in the dataset across all periods of time.
  - *Documentary, Biography, and Animation* genres had the best average ratings in the dataset across all periods of time.
  
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Genre%20Heatmap%20Ratings.png" alt="Heatmap of Genre Ratings" width="900" height="400">

- **Correlation Between Genres and Rating**:
<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Average%20Genre%20Rating%20Over%20Time%202.png" alt="Average Rating by Genre Over Time" width="700" height="350">

- When visualizing the average ratings of specific genres over the years, such as drama, comedy, and action, we observe that their ratings closely align with the overall average rating (represented by the black dotted line), indicating a strong correlation between them.

- After calculating the correlations above, the findings suggest that many genres have strong correlations between their average ratings and the overall average rating over time. This is namely the case with drama, comedy, and action, which had correlations of 0.91, 0.96, and 0.91, respectively, with the overall average. This indicates that as the overall average rating rises or falls, the average ratings for these genres tend to follow a similar pattern.

- We also notice, however, that news, documentary and biography genres have very low to negative correlations, implying that the ratings for these types of movies are less tied to the overall trend. This makes sense, as these genres have had the highest ratings throughout time. While other movie genres as a whole have decreased over time, the genres have maintained their popularity over time. 

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Gener%20Correlation%20results.png" alt="IMDb Movie Count Broken down by Genre" width="800" height="325">

- **Number of Ratings by Genre**: Drama, comedy, and action account for nearly half of all ratings, significantly amplifying their influence on overall trends. The aggregate average movie rating trend is largely driven by these genres, which explains the strong correlation between their individual ratings and the overall ratings. Genres with the highest ratings, such as news, documentary, and biography, have a much smaller share of total ratings, which limits their influence on overall rating trends over time. In contrast, horror and sci-fi, which have some of the lowest average ratings, have significantly higher total ratings, giving them a greater impact on the overall trends.

<img src="https://github.com/Zaki978/Project-Portfolio/blob/main/assets/Number%20of%20Ratings%20by%20Genre.png" alt="Total Number of Ratings by Genre" width="600" height="550">

- Other Observations
  - **Average Movie Runtime** has steadily increased over time, being generally above 100 mins since 1960.
  - **Number of Movies on IMDb Broken Down by Genre**: *Drama (53%) and Comedy (32%)* genres together dominate the content on IMDb, reflecting a high concentration of movies in these two genres compared to others.
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
