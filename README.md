## Airbnb Kaggle Competition: New User Bookings

This repository contains the ipynb I wrote for the [Airbnb's Kaggle competition](https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings). It's written in **Python** with **Jupyter Notebook**.

I didn't actually take part in this competition. Just used this resource as an experience to develop the skills in data science. This code produces predictions with scores around 0.86615 in the public leader-board, and 0.86991 in the private leader-board.

Feel free to contact me if you have any questions or suggestions.

## Description

New users on *Airbnb* can book a place to stay in 34,000+ cities across 190+ countries. By accurately predicting where a new user will book their first travel experience, *Airbnb* can share more personalized content with their community, decrease the average time to first booking, and better forecast demand.

In this competition, the goal is to predict in which country a new user will make his or her first booking. There are 12 possible outcomes of the destination country and the datasets consist of a list of users with their demographics, web session records, and some summary statistics.

## Data

Due to the [Competition Rules](https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/rules), the data sets can not be shared. If you want to take a look at the data, head over the [competition](https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings) page and download it.

**Note**: Since the train users file is the one re-uploaded by the competition administrators, rename ```train_users_2.csv``` as ``` train_users.csv ```.

## Main Ideas

1. The provided datasets have lots of NaNs and some other *outliers*, so a good preprocessing is the primary key to get a good solution:
	* Replace -outliers- with NaNs
    * Replace NaNs with -1
	* Clean age values
	* Extract day, weekday, month, year, dayofyear etc. from ``` date_account_created ``` and ``` timestamp_first_active ```
	* Create new features using the features I have
	* One-hot encoding the categorical data
    
2. This kind of classification task works nicely with tree_based methods, I used XGBoost library along scikit-learn to make the probabilities predictions.

## Output

* The output is a csv file contains the top 5 possible cities of each user that might go when they first book their trip on Airbnb.com . 

## Requirements

To replicate the findings and execute the code in this repository you will need basically the following Python packages:
* Numpy
* Pandas
* Jupyter
* Sci-kit Learn
* XGBoost

## Resources
* XGBoost Documentation - A library designed and optimized for boosted (tree) algorithms.
# Kaggle_Airbnb_NewUserBookings
