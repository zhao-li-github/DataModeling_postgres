# Data Modeling with Postgres
## Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. 
They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis. More specifically, we need to create a database schema and ETL pipeline for this analysis.

## Description

## Datasets
The data in this project reside in two datasets:
### Song dataset: 
A directory with JSON metadata on the songs in their app.
This is a subset of real data from the [Million Song Dataset](http://millionsongdataset.com/). Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset:
> song_data/A/B/C/TRABCEI128F424C983.json   
> song_data/A/A/B/TRAABJL12903CDCF1A.json

### Log dataset:
A directory of JSON logs on user activity on the app.

## Schema
A star schema is defined to optimize data write times by reducing duplicate data entris. It contains 1 fact table (songplays) and 4 dimension tables (songs, artists, time, and users):
![image](https://user-images.githubusercontent.com/60242372/120561899-41311080-c3ba-11eb-9497-496e10575a54.png)


## Running the ETL pipeline
0 Ensure the data folder and all project files are downloaded and that all dependencies are met. Replace the given connection strings in create_tables.py, etl.ipynb and etl.py with your own, pointing to a postgres database server you have set up.
1 Run create_tables.py to initialise the database.
2 Start and run test.ipynb to ensure all tables were created. Shut down the kernel and close the notebook.
3 Start and run etl.ipynb to ensure the transformation and loading scripts work for a single song and log file. Shut down the kernel and close the notebook.
4 Run create_tables.py to reset the database.
5 Run etl.py to start the ETL data pipeline from JSON logs in the data folder to the Sparkify database


An ETL pipeline was developed to move data into a Postgres database
A star schema is used to optimise data write times by reducing duplicate data entries
All CRUD queries are given as well as starter notebooks to verify operation on a subset of the data using given functions
