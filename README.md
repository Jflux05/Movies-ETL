# Movies-ETL

## Project Overview:
Amazing Prime is hosting a Hackathon and has asked to create an automated pipeline that takes in new data, from Wikipedia data, Kaggle metadata and the MovieLens rating data. It then performs the appropriate transformations and loads the data into an existing PostgreSQL database. 

There were four deliverables for this analysis:

- Write an ETL function to read three data files: [ETL_function_test.ipynb](ETL_function_test.ipynb)
- Extract and transform the Wikipedia data: [ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb)
- Extract and transform the Kaggle and rating data: [ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb)
- Load the data to a PostgreSQL Movie Database: [ETL_create_database.ipynb](ETL_create_database.ipynb)

## Resources:
- Python 3.7.7, Jupyter Notebook
- PostgreSQL, Pgadmin 4 Version 6.2
- Movie Data sourced from IMDB, Kaggle 

## Analysis:
This stage involves the initial retrieval and reading of data in various formats (csv, json) by using a python environment that can interpret the data.

### Deliverable 1  Write an ETL function to read three data files: [ETL_function_test.ipynb](ETL_function_test.ipynb)

The function takes the Wikipedia JSON, the Kaggle metadata and MovieLens csv files and creates three separate DataFrames.
- Data is extracted from the website in JSON and CSV formats.
- Data is transformed into Pandas data frames.
- JSON file requires extra step – loading file first and then transforming into data frame.

### Deliverable 2 Extract and transform the Wikipedia data: [ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb)

We filtered out the TV shows, consolidated the redundant data, removed the duplicates and formatted the Wikipedia data.

Function clean_movie combines scattered data of alternative languages into one column alt_titles.

Its subfunction change_column_name organizes column names into consistent pattern.

In the function extract_transform_load the transformation process of wiki movies data begins and includes:
- Python list comprehensions.
- apply() and map() methods in combination with lambda functions.
- regular expressions or RegEx.


### Deliverable 3 Extract and transform the Kaggle and rating data: [ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb)

We consolidated the redundant data, removed the duplicates, formatted and grouped the data.
The Kaggle and rating data were then merged with the Wikipedia movies DataFrame.

Function extract_transform_load gets new tasks for cleaning Kaggle data and includes:
- Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
- Filling missing values and filtering unwanted columns.
- Merging data frames using pd_merge method.

### Deliverable 4: Load the data to a PostgreSQL Movie Database: [ETL_create_database.ipynb](ETL_create_database.ipynb)

The function in its final step connects to the database by sqlalchemy library and to_sql method.

The Complete ETL process can be executed with a single function extract_transform_load call.
