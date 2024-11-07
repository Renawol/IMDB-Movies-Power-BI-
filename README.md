# IMDB Movies Power BI Analysis

<p align="center">
<img src="https://imgur.com/Kqu38YI.jpg" style="height: 75%; width:75%;"/></center></p>


In this proyect I practice with some visualizations and DAX commands in Power BI. 
The data was taken of [this Kaggle dataset](https://www.kaggle.com/datasets/adriankiezun/imdb-dataset-2023)


## Data context

The dataset contains more than 3300 entries of movies registered in the IMDB webpage. The films date from 1975 until 2023.

Rows contain the unique **id** of the film in the database, its **title**, **duration**, **rating** and **number of votes**, **budget**, **gross income**, **release_date** and **director(s)**

Apparently the dataset downloaded from Kaggle is almost cleaned. Nevertheless, before importing it to Power Bi, we checked it out in Python. We just found that the 0.14% (5 rows) of the *release_date* values were nulls. Since they were that few, we comleted 
the data visiting the IMDB webpage. Moreover, 1.5% of the *gross* values were nulls. In this case, we just dropped this rows.

You can check the Jupyter Notebook in the repository

## Pages:
- "GeneralStudy", where we answer the following questions:
  - Matrix showing the top ten films, director and profit by rating.
  - Columns chart showing the average profit by genre
  - Line plot with the average rating over the years.
  - Pie plot of the number of movies in each category
- "RatingStudy", where we observe patterns related to the *Rating* variable.
  - Bar chart of movies by rating
  - Data slicer to pick the year
  - Relationship between *Rating* and the *number of votes*
  - Columns and lines diagram relating the *budget* and *rating* for different *genres*
- "StevenSpielberg", where a little study in the director is done.
  - Line plot with the profit of the director over the years
  - Matrix comparing the profit made over the decades.
  - Labels of total profit, average profit margin and total movies
  - Text box explaining the dashboard
 
  ## Next commits:
  Powerpoint explaining the dashboards
  Explanation of the measures, commands and tables used.

:pineapple:
