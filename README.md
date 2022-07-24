# Data Modeling with Postgres
The objective of this project is to create a SQL analytics database for a fictional music streaming service called Sparkify. Sparkify's analytics team seeks to understand what, when and how users are playing songs on the company's music app. The analysts need an easy way to query and analyze the data, which is currently locally stored in raw JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app on.

As the data engineer assigned to the project, My role is to create a database schema and upload the data into a PostgreSQL database and implement an ETL pipeline for this analysis.




This project consists of putting into practice the following concepts:

* Data modeling with Postgres
* Database star schema created
* ETL pipeline using Python

# Data
* Song Dataset: all json files are nested in subdirectories under /data/song_data. A sample of this files is:
{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}
* Log datasets: all json files are nested in subdirectories under /data/log_data. A sample of a single row of each files is:
{"artist":"Slipknot","auth":"Logged In","firstName":"Aiden","gender":"M","itemInSession":0,"lastName":"Ramirez","length":192.57424,"level":"paid","location":"New York-Newark-Jersey City, NY-NJ-PA","method":"PUT","page":"NextSong","registration":1540283578796.0,"sessionId":19,"song":"Opium Of The People (Album Version)","status":200,"ts":1541639510796,"userAgent":"\"Mozilla\/5.0 (Windows NT 6.1) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/36.0.1985.143 Safari\/537.36\"","userId":"20"}

# Database Schema
he schema used for this project is the Star Schema: There is one main fact table containing all the measures associated with each event songplays, and 4 dimensional tables songs, artists, users and time, each with a primary key that is being referenced from the fact table.

# Project structure
Files used on the project:

* data folder nested at the home of the project, where all needed jsons reside.
* sql_queries.py contains all your SQL queries, and is imported into the files bellow.

* create_tables.py drops and creates tables. You run this file to reset your tables before each time you run your ETL scripts.

* test.ipynb displays the first few rows of each table to let you check your database.

* etl.ipynb reads and processes a single file from song_data and log_data and loads the data into your tables.

* etl.py reads and processes files from song_data and log_data and loads them into your tables.

* README.md current file, provides discussion on my project.

# How to use 
* Run create_tables.py from terminal to set up the database and tables.
* Run etl.py from terminal to process and load data into the database.
* Launch test.ipynb to run validation and example queries.

