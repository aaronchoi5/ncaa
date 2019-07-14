## Overview

In this project, I hope to use machine learning to create a model that can predict the winner of a game between two teams. This way, I can try to predict the winner of the NCAA Basketball Tournament (and hopefully get a perfect bracket LOL). I've separated this project into a couple of different components. Since I like to do this every year, I wanted to keep this code general enough so that it can work from year to year, you'll just have to add new data for the current year. 

* Data: The Data folder contains different CSVs that show team stats, regular season game results, etc. It will contain data that I've scraped, data from Kaggle, and a folder that contains precomputed xTrain and yTrain matrices so that we don't have to keep recomputing the training set. 
* DataPreprocessing.py: Script where we create our training matrices. 
* MarchMadness.py: Script where we apply machine learning models to the training set. We can also create our Kaggle submissions here. 

## Requirements and Installation

* python 3
* [pipenv](https://pipenv.readthedocs.io/en/latest/) for managing virtualenv and pip package dependencies.

## What To Do Every March
* Download data files from [Kaggle](https://www.kaggle.com/c/mens-machine-learning-competition-2019), who will normally have a competition going (look for the competition for the current year). They will provide CSV files that show the results from games since 1985, information on conferences, tourney seed history, etc. It's important to download this data every year because Kaggle will add data from the most recently completed season and so you'll have a bit more training data. 
* We also want to get the advanced rating statistics from Basketball Reference. Basically, go to https://www.sports-reference.com/cbb/seasons/2019-ratings.html (and replace 2019 with whatever year you're looking at), choose to get the table as a CSV (available in one of the dropdowns), copy that over to a new text doc in Sublime (or any text editor), save it as a CSV, and then upload it
* We also want to get the regular season statistics from Basketball Reference. Basically, go to https://www.sports-reference.com/cbb/seasons/2019-school-stats.html (and replace 2019 with whatever year you're looking at), choose to get the table as a CSV (available in one of the dropdowns), copy that over to a new text doc in Sublime (or any text editor), save it as a CSV, and then upload it.
    * For both of the above steps, make sure that the column names are the same from year to year! In 2019, Basketball Reference made some small changes to the column names (X3P to 3PA for example)
* Run DataPreprocessing.py in order to get the most up to date training matrices.
* Run MarchMadness.py. 

## What You Can Do
* Try to modify MarchMadness.py to include more ML models
* Modify DataPreprocessing.py to create different features to represent each game/team
* Perform data visualizations to see which features are the most important
* Decide what type of additional data preprocessing might be needed

## Getting Started
1. Download and unzip this repo, either interactively, or by entering the following in your Terminal.
    ```bash
    git clone https://github.com/aaronchoi5/ncaa.git
    ```
2. Navigate into the top directory of the repo on your machine
    ```bash
    cd March-Madness-ML
    ```
3. Create a virtualenv and install the package dependencies
    ```bash
    pipenv install
    ```
4. First create your xTrain and yTrain matrices by running 
    ```bash
    pipenv run python DataPreprocessing.py
    ```
   This may take a while (Still trying to figure out ways to make this faster).
5. Then run your machine learning model 
    ```bash
    pipenv run python MarchMadness.py
    ```
