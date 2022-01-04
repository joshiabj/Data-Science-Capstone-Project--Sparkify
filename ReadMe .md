Data Science Capstone Project

Churn Prediction at Sparkify


1) Project Overview:

This project looks at the sparkify dataset which is assumed to be similar to a popular music service such as Spotify or Pandora.
A user can perform multiple actions while he is on the service platform and can effectively leave the service as well. 
This is what is known as customer churn. Churn happens when a customer cancels his/her membership or sometimes downgrades his/her services.


2) Problem Statement and Motivation:

Our task is to effectively predict the churn rate so that we can retain the customers and hence help the business save revenue.
Predicting churn rates is a challenging and common problem that data scientists and analysts regularly encounter in any customer-facing business.
Additionally, the ability to efficiently manipulate large datasets with Spark is one of the highest-demand skills in the field of data.


3) Summary of the Analysis:

The original size of the dataset is 12GB which is too large for an analysis. Hence I used the small dataset (128MB) to perform the data exploration process 
and build the model on it.

The dataset contains around 280k rows and 18 columns.
Out of the 18 columns, the column page contains the various actions that a user can take when on the platform page such as cancelling, downgrading, 
giving a thumbs up/thumbs down, playing next song among others.

After removing the blank/null user ids, the churn variable was created where the user page action was "Cancellation Confirmation". 52 unique users were identified.

After a thorough EDA and exploration of the dataset and its variables which looked at answering a few questions regarding the trend shown by users who churned and did not churn
the following variables were selected to be part of the model building process:

a) Downgrade- Number of times user downgraded 
b) Thumbs Down-  Number of times user has given a thumbs down
c ) Thumbs Up-  Number of times user has given a thumbs up
d) Add to Playlist- Number of times user has added song to playlist
e) Add Friend- Number of times user has added a friend
f)  Error- Number of times user faced errors
g) Home- Number of times user is back to home page
h) Roll Advert- Number of times advertisment has come up
i) gender_feat- Whether user is male or female ( 0 for female and 1 for male)
j) level_feat- Whether user has a paid or free account (0 for free and 1 for paid)
k) time_since_reg_feature- Time since the user registered
l) total_artists_played_feat- Total number of artists played by user
m) listening_time_feat- Total length of songs listened to by user
n) total_songs- Total number of songs played by the user

After splitting the data into train and test with a 70:30 split, the following models were used to train on the data
Logistic Regression
Random Forest
XGBoost

Cross validation was used for all the three models.
Hyperparameter tuning was performed for the decision tree models to decide the optimal parameters.

The metrics used to determine the model performance were F1 score and false positive rate of the models.
As we have an uneven class distribution with only 23 percent of churn population, we can use F1 score as a performance metric.

Althought both the XGBoost and Random Forest have a better F1 Score of 74.5 % than the the 71 % of logistic regression model, the false postive rate at 7% is the lowest for LR.   

4) Overview of Files:

ReadMe.md File - This Readme file
Sparkify.ipynb- The python file containing all the code and the analysis
mini_sparkify_event_data.json - Input Dataset name provided

The link for the medium blog is : https://medium.com/@abhijayjoshi93/customer-churn-prediction-in-pyspark-bbe25dd50d7e

5) Libraries Used:

seaborn 
matplotlib
datetime
numpy
subprocess
Various pyspark ml and sql librarires

