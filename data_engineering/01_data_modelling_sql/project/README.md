# Summary
Sparkify is a startup company and they are collecting data for songs and user activity in the form of JSON files. The analytics team wants to analyze the data but it's not very easy to do proper data analysis on JSON files. In order to make a scalable and easier solution in this project we will create a relational model in PostgreSQL and create data pipeline using Python.

# Project Modules

### 1. Data Set:
- There are 2 sets of data, songs data and logs data. 
- The songs data set, which is in JSON format, contains metadata about a song and the artist of that song.
- The log data sets are again JSON files which consists of the user activities.

### 2. Data Model:
- The Data model is based on Kimball's star schema based model.
- In the current star schema we have 1 fact table and 4 dimension tables.
- The fact table, songplays, is connected with all the other dimension table.
- There are 4 dimension tables viz: users, songs, artists and time.
- Following is the star schema diagram.

<img src="https://github.com/santoshjoshigithub/udacity/blob/master/data_engineering/01_data_modelling_sql/images/relational_model.png" width="1000	" height="500">

### 3. Data Pipeline:
- The data pipeline is built using Python modules.
- There are basically 3 main modules to set up the pipeline viz: create_tables.py, etl.py and sql_queries. There are 2 note book files which are being used for analysis and testing. 
    - create_tables.py - This file basically creates a connection to the database, also creates and drops all the tables.
    - sql_queries.py - This module is being used by the other 2 modules. This is where all the SQL queries has been written.
    - etl.py - This module basically drives the ETL, it consumes data from the source, transforms the data and loads it in the respective tables. It uses the other 2 modules to achieve it.
- Some data quality/integrity checks has been applied e.g. Primary key is defined for each table and checks are implemented while insertion so that duplicates records are ignored and pipeline doesn't terminate with errors.
    
### 4. Miscellaneous:
- All the JSON files are stored in the Data Folder.
- etl.ipynb file is used to do analysis of the data, transformation etc. The code written in this file is later used by etl.py file.
- test.ipynb file is used to test the results in the respective fact and dimension tables.
- There is an additional image folder which is used to store *.png file for project diagrams.

# High Level Execution Steps:
- Go to the launcher in the Jupyter lab of Udacity project enviroment.
- Open the Terminal and run create_tables.py (>python create_tables.py and then hit run)
- You can execute create_tables.py file from the terminal whenever you start data loading, this will drop and recreate all the tables again for you.
- Sometimes you may encounter errors while running create_tables.py, it probably coz of the existing connection open, then go to any of the notebook file and restart the kernel, this will reset the connection and the error probably would vanish.
- To load data from the JSON files, runetl.py file from the terminal.
- For verification of the data, use test.ipynb file and see if data has been loaded or not.