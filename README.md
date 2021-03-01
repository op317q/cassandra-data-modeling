# Introduction

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team 
is particularly interested in understanding what songs users are listening to. Currently, the data reside in a directory of CSV files on user activity on the app. 
 
As a data engineer 
-  to create an Apache Cassandra database which can create queries on song play data to answer the questions
 
To do this , I have to create 

- Apache Cassandra database 
- ETL pipeline for this analysis

# Database Schema and ETL pipeline

The purpose of the NoSQL database is to answer queries on song play data. The data model includes a table for each of the following queries:

- Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4
- Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
- Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'

## Datasets
The dataset : event_data. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:

- event_data/2018-11-08-events.csv
- event_data/2018-11-09-events.csv



## Build ETL Pipeline and Table
ETL will iterate through each event file in event_data to process and create a new CSV file in Python called event_datafile_new.csv
THis file will be used to populate the Cassandra tables that is optimised and denormalized for the 3 queries above. 
The 3 tables will be used to get the result for the above query

- music_history : artist, song title and song length information for a given sessionId and itemInSessionId.

- user_history : artist, song and user for a given userId and sessionId.

- song_history : user names for a given song.


 
# Project Instructions

1. Clone the repository and navigate to the downloaded folder.

```
git clone git@github.com:op317q/cassandra-data-modeling.git
cd cassandra-data-modeling
```

2. Create and activate a new environment.

```
conda create -n cassandra-data-modeling python=3.6
source activate cassandra-data-modeling

```

3. install python package. 
```
pip install -r requirements.txt
```

4. run the cassandra DB in local.
```
docker-compose up
```

5. To run the Jupyter Notebook

```
jupyter notebook Project_1B_Project_Template.ipynb

```

