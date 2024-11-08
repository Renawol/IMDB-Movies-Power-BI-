# IMDB Movies Power BI Analysis

<p align="center">
<img src="https://imgur.com/Kqu38YI.jpg" style="height: 75%; width:75%;"/></center></p>


In this proyect I practice with some visualizations and DAX commands in Power BI. 
The data was taken of [this Kaggle dataset](https://www.kaggle.com/datasets/adriankiezun/imdb-dataset-2023).

Please, in case of any doubts, refer to this README carefully.

## Data context

The dataset contains more than 3300 entries of movies registered in the IMDB webpage. The films date from 1975 until 2023.

Rows contain the unique **id** of the film in the database, its **title**, **duration**, **rating** and **number of votes**, **budget**, **gross income**, **release_date** and **director(s)**.

Apparently the dataset downloaded from Kaggle is almost cleaned. Nevertheless, before importing it to Power Bi, we checked it out in Python. We just found that the 0.14% (5 rows) of the *release_date* values were nulls. Since they were that few, we comleted 
the data visiting the IMDB webpage. Moreover, 1.5% of the *gross* values were nulls. In this case, we just dropped this rows.

You can check the Jupyter Notebook in the repository.

## Technical Knowledge Used:
- Review and format correction with **PowerQuery**
### Tables
- Creation of the unpivot table *GENRES UNPIVOT* from the main table. To generate this table, it was first necessary to **expand** the ***genre* field** into three new columns and then **unpivot the columns**.
- Creation of the hidden table *GENRESCOUNT* (func. SUMMARIZE) to count the occurrences of genre values.
- Creation of the *DATES* table as an auxiliary calendar from a new table.
- Creation of the *MEDIDAS* table that contains all the measures.

### Calculated Columns
- *DATES*: CALENDARAUTO, YEAR, MONTH and MONTH NAME (func. FORMAT)
- *GENRES UNPIVOT*: "Classification", where genres with occurrences less than two percent of the total will be classified as "Others", and the rest will remain the same. (funcs. IF, RELATED, SUM)
- *IMDB*: "neat", resulting of the gross income minus the budget. "Main Genre", where The first genre contained in the "genres" column is stored as the "main genre". (VAR, RETURN, funcs. SEARCH, LEFT)

### Measures
- Profit: Total neat income (func. SUM)
- 1980/1990/2000 Decade: Calculate profit for the last ten, twenty, and thirty years compared to the spicified year (2010 decade in this case). (funcs. CALCULATE, PARALLELPERIOD)
- AVERAGE PROFIT MARGIN: Calculates the average profit margin. (func. AVERAGEX)
- Steven Films Labels: This measure is used as a label. It shows a string containing the titles of the Steven Spielberg films separated by commas. (funcs. FIRSTNONBLANK, IF, LASTNONBLANK, BLANK)
- Steven Lineplot Labels: Combines the previous measure with the profit. (funcs. IF, BLANK)
- TOTAL MOVIES: Counts the number of movies

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
- Powerpoint explaining the dashboards.

:pineapple:
