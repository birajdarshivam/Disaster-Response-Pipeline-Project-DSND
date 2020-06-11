# Disaster Response Pipeline Project

## Required libraries
    nltk 
    numpy 
    pandas 
    scikit-learn
    sqlalchemy 


## Files:
.
├── app
│   ├── run.py------------------------# FLASK FILE THAT RUNS APP
│   │ 
│   └── templates
│       ├── go.html-------------------# CLASSIFICATION RESULT PAGE OF WEB APP
│       └── master.html---------------# MAIN PAGE OF WEB APP
├── data
│   ├── DisasterResponse.db-----------# DATABASE TO SAVE CLEANED DATA TO
|   ├── ETL_Preparation.db-----------# DATABASE TO SAVE CLEANED DATA TO
│   ├── disaster_categories.csv-------# DATA TO PROCESS
│   ├── disaster_messages.csv---------# DATA TO PROCESS
│   └── process_data.py---------------# PERFORMS ETL PROCESS
├── models
│   └── train_classifier.py-----------# PERFORMS CLASSIFICATION TASK
|   |
|   └──── classifier.pkl
├──────── ETL Pipeline Preparation.ipynb
|       └── ML Pipeline Preparation.ipynb
## Motivation:
This project will include a web app where an emergency worker can input a new message and get classification results in several categories. The web app will also display visualizations of the data.

## Project Components:
There are three components of this project:


### 1. ETL Pipeline:
File data/process_data.py contains data cleaning pipeline that:

Loads the messages and categories dataset
Merges the two datasets
Cleans the data
Stores it in a SQLite database

### 2. ML Pipeline:
File models/train_classifier.py contains machine learning pipeline that:

Loads data from the SQLite database
Splits the data into training and testing sets
Builds a text processing and machine learning pipeline
Trains and tunes a model using GridSearchCV
Outputs result on the test set
Exports the final model as a pickle file

### 3. Flask Web App:


## Important Files:
data/process_data.py: The ETL pipeline used to process data in preparation for model building.
models/train_classifier.py: The Machine Learning pipeline used to fit, tune, evaluate, and export the model to a Python pickle (pickle is not uploaded to the repo due to size constraints.).
app/templates/*.html: HTML templates for the web app.
run.py: Start the Python server for the web app and prepare visualizations.

### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
