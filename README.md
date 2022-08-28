# WeRateDogs Wrangling Project 

## Project Aim
The goal of this project is to wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. This project will majorly demonstrate my data wrangling skills (Gathering, Assessing, Cleaning, Documenting, and Storing).

## Method of Analysis
I'll start this project by importing the required libraries then gathering data by:
1. Reading the already provided twitter-archive-enhanced data set provided by Udacity.
2. Programmatically downloading the image prediction data from a Udacity hosted webpage.
3. Quering data from Twitter using the Twitter API and tweepy Python library.<br>


Next, I'll visually and programmatically assess the data sets and document the quality and tidiness issues.<br><br>
After that, I'll clean the data using the Python's NumPy and pandas libraries to clean the data.<br><br>
Then, combine the three clean data sets and store in a csv file (`twitter_master.csv`).<br><br>
From there, I'll generate insights and develop visualizations to communicate these insights.

## Datasets
The project requires me to gather data from 3 sources, create data frames from each piece of data I gather and merge all the data after they’ve been assessed and cleaned.
Here are the three data sets I gathered and how I gathered them:
1. ***twitter_archive_enhanced.csv***: This data was handed to me in the classroom, and I just had to download it manually
2. ***image_predictions.tsv***: This data set is hosted on Udacity’s servers, and I programmatically downloaded it using the requests library and a file opening context manager.
3. ***tweet_json.txt***: This data set was gotten from the Twitter API using the tweepy library. After that, I had to read the text file line by line and extract other relevant data, like the retweet_counts and favorite_count.

## Required Modules
* numpy
* pandas
* matplotlib
* seaborn
* tweepy
* json
* timeit
* requests

## Installations
The modules listed in the section above can be downloaded in the anaconda IDE (recommended software to run the ipynb files) using `conda install module_name` or the conventional `pip install module_name`

## Setup
The recommended way to run the ipynb file (`wrangle_act_updated.ipynb`) is by setting up a virtual environment with conda and running the files in a jupyter notebook. Click [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) to learn how to set up and manage virtual environments with conda.<br><br>
The html and pdf files that contains all the necessary codes and findings are also available in the `main` branch

## Known Bugs
The files in this repo currently have no bugs.

## Wrangling Summary
### Quality issues
#### twitter_archive (TA1) dataframe
1. tweet_id, in_reply_to_status_id, in_reply_to_user_id should be an object since no arithemetical operations will be performed on them.
2. timestamp's datatype should be "datetime".
3. Rows that have rating_numerator as 0.
4. Missing data for the expanded_url column.
5. Rows that have retweeted_status_id should be removed
6. Some data cells have "None" placeholder instead of the convential "NaN" to represent that there's no data available for that cell.
7. retweeted_status_timestamp, retweeted_status_id, and retweeted_status_user_id column should also be dropped since we don't need the retweets.
8. Actual sources should be extracted from the source column.
9. The name column with a and an values should replaced with nan.

#### image_predictions (IP1) dataframe
1. The data type of the tweet_id columns should be object.
2. There should be a column that states the breed the neural network determined.

#### tweet_json (TJ1)  dataframe.
1. The datatype of tweet_id should be object.

### Tidiness issues
#### twitter_archive (TA2) dataframe
1. Dog stage (doggo, floofer, pupper, puppo) should be in one column. After further investigations, other quality issues were found from this issue.
2. There should be a column that states the calculated rating instead of 2 columns having the numerator and denominator.

#### image_predictions (IP2) dataframe.
1. Data in this dataframe is supposed to be merged with twitter_archive so that it can each observation forms a row and each type of observational unit forms a table.

#### tweet_json (TJ2) dataframe
1. Data in this dataframe is supposed to be merged with twitter_archive so that it can each observation forms a row and each type of observational unit forms a table.

A more detailed analyses of the wrangling steps can be found in the `wrangle_report.pdf` file.

## Summary of Findings 
1. The most used tweet source is **Twitter for iPhone**.
2. The top dog breeds featured by WeRate are golden retriever, Labrador retriever, Pembroke, Chihuahua, pug, toy poodle, Pomeranian, chow, Samoyed, and malamute.
3. Most dogs have a rating between 1.0 and 1.3.
4. The frequency count reduces with increasing favorite count values.
5. As the retweet count value increases, the frequency decreases.
6. The average favorite count rises steadily from November 2015 to August 2017, but then falls slightly in July 2016, February 2017, and June 2017.
7. The average retweet count rises steadily from November 2015 to August 2017 but falls slightly in July 2016, February 2017, and June 2017.
8. The favorite count will generally increase with an increasing retweet count and vice versa.

A detailed report on the insights and visualizations can be found in the `act_report.pdf` file.

## Contributing
To make a contribution:
- Fork the repo
- Make Changes
- Send your pull request for review

## Show Love 💓
Show Love by giving the Repo a star...😇
