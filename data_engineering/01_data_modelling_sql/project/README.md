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
- Following is the start schema diagram which dpecits the data model, tables and their relationship.

<img src="https://github.com/santoshjoshigithub/udacity/blob/master/data_engineering/01_data_modelling_sql/images/relational_model.png" width="250" height="250">