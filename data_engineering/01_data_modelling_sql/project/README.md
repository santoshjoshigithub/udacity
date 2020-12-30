# Project Synopsis
Sparkify is a startup company and they are collecting data for songs and user activity in the form of JSON files. The analytics team wants to analyze the data but it's not very easy to do proper data analysing on JSON files. In order to make a scalable and easier solution in this project we will create a relational model and create data pipeline using Python. We will also apply data quality controls in order to have the clean data for further analysis.

# Project Modules
This project can be divided into 2 main modules, which we will see in details:
- The data model
- The data pipeline

### The Data Model:
- The Data model is based on Kimball's star schema based model.
- In the star schema we have 1 fact table and 4 dimension tables.
- The fact table, songplays, is connected with all the other dimension table. It has few keys and other junk dimensions and it could be extended to have different measures e.g. duration of the songs into it.
- There are 4 dimension tables viz: users, songs, artists and time.
- Following is the star schema diagram which dpecits the data model, tables and their relationship.

<img src="https://github.com/santoshjoshigithub/udacity/blob/master/data_engineering/01_data_modelling_sql/images/relational_model.png" width="1000	" height="500">

### The Data Pipeline:
- The data pipeline is built using Python modules.
- There are basically 3 main modules to set up the pipeline viz: create_tables.py, etl.py and sql_queries. There are 2 note book files which are being used for analysis and testing. They are etl.ipynb and test.ipynb.
    - create_tables.py - This file basically creates a connection to the database, creates and drops the table.
    - sql_queries.py - This module is being used by the other 2 modules. This is where all the SQL queries has been written.
    - etl.py - This module basically drives the ETL, it consumes data from the source, transforms the data and loads it in the respective tables. It uses the other 2 modules to achieve it.
- Some data quality/integrity checks has been applied e.g. Primary key is defined for each table and checks are implemented while insertion so that duplicates records are ignored and pipeline doesn't terminate with errors.
    
### Miscellaneous:
- All the JSON files are stored in the Data Folder.
- etl.ipynb file is used to do analysis of the data, transformation etc. The code written in this file is later used by etl.py file.
- test.ipynb file is used to test the results in the respective fact and dimension tables.
- There is an additional image folder which is used to store *.png file for project diagrams.

# High Level Steps:
- Go to the launcher in the Jupyter lab of Udacity project enviroment.
- Open Terminal and run create_tables.py (>python create_tables.py and then hit run)
- Please note, run create_tables.py file whenever you start data loading, this will drop and recreate all the tables again.
- Sometimes you may encounter errors while running create_tables.py, it probably coz of the existing connection open, then go to any of the notebook file and restart it, this will reset the connection.
- To load data from the JSON files, runetl.py file from the terminal.
- For verification of the data, use test.ipynb file and see if data has been loaded or not.