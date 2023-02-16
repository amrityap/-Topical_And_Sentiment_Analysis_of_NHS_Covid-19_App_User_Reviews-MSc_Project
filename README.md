# Topical_And_Sentiment_Analysis_of_NHS_Covid-19_App_User_Reviews-MSc_Project

Kindly open the "MSc Thesis.pdf" to read the research paper on this project.

## Introduction

The covid-19 virus has caused one of the worst pandemic in history. Various countries have taken the route of 
Contact Tracing to control the infection rate of Covid-19. To achieve this aim of contact tracing, several mobile 
applications have been developed in different countries. However, as these applications are downloaded by 
citizens of different countries and everyone carries their own perspective on the application, it becomes necessary 
to understand how people feel and think about using these contact tracing applications. Various topics can pop 
into the minds of people using these apps, such as performance, privacy, and the purpose of the applications. Also, 
people will carry either a positive, negative, or neutral sentiment associated with the topics they have in their 
minds regarding the contact tracing application they are using. To understand what topics people have in mind 
and how the sentiments associated with those topics changes with time, this paper will introduce a topic-wise 
temporal sentiment classification method. The focus of this paper will be on the NHS COVID-19 App, which is 
a contact tracing app used in the UK. To achieve this task, we will first train and test a sentiment classification 
model on a large-scale manually annotated dataset consisting of reviews of contact tracing apps from 46 countries. 
Then, we will scrape the user reviews of the NHS COVID-19 application from the Google Play Store app to create 
another dataset and extract topics from it. And then finally, we will conclude on the topic-wise temporal sentiment 
classification of the NHS COVD-19 app user reviews where, for user reviews under each topic, we create two 
trendlines, one trendline for the sum of positive sentiments per month and the other trendline shows the sum 
negative sentiment per month. The accuracy of 97.31% on the validation dataset and 94.06 % on testing confirm 
the feasibility of the sentiment classification model. Moreover, high accuracies of the sentiment classifier for 
different topics of the NHS COVID-19 APP user reviews will prove that this pipeline will give us a deeper insight 
into the minds of the people reviewing the NHS COVID-19 APP. For those topics where the sentiment classifier 
achieves low accuracy, the reasons will be discussed, and we will understand why those topics are more important 
than the ones for which we have achieved higher accuracies.

## Code execution

All the required code and files for this project are inside the folder named "code_files". Inside "code_files" there are four folders and ten files and I will now give details about each file and folder. This project was done on 
Jupyter Notebook. There are three Jupyter files named ScrapingData.ipynb,
SentimentclassificationOfUserReviews.ipynb, and TopicWiseTemporalSentimentAnalysis.ipynb. Also, two 
CSV files named t2_data_train.tsv and t2_data_test.tsv contain the dataset of user reviews of contact tracing 
apps from 46 countries. The folder named ‘trainedmodel’ will save and store the trained sentiment classifier 
model and is necessary. The folder named ‘.ipynb_checkpoints’ can be deleted as it saves the checkpoint of 
the Jupyter notebook when it is manually saved. The folder named ‘results’ is the output directory where the 
prediction and checkpoints of the sentiment classifier model are stored in binary format. The TensorBoard 
uses it to visualise various parameters related to the model, such as loss per epoch, model graph etc. But this 
folder is not directly related to the project and is considered metadata. The folder named ‘logs’ store the 
summary files whenever the TensorFlow training model is run. Logs folders should be kept, but the summary 
files are not used in this project. Covid19_GooglePlayData.csv, covid19_googleplaydata_with_topics1.csv
and covid19_googleplaydata_with_topics2.csv are the output files that we will get after we run the Jupyter 
Files.
The steps to run the code are as follows:
• First, run the ScrapingData.ipynb. This file will scrape the NHS COVID-19 app user reviews on the 
google play store and save it in a CSV file named Covid19_GooglePlayData.csv. Libraries needed 
to run this code are google_play_scraper, Pandas and NumPy.
• Then run the SentimentclassificationOfUserReviews.ipynb file.This file is being used to train and 
test the sentiment classifier model. We need t2_data_train.tsv and t2_data_test.tsv files as these files 
contain the datasets on which the sentiment classifier model is trained and tested. The Trained model 
will be saved in the ‘trainedmodel’ folder. Libraries required to run this Jupyter file are transformers, 
TensorFlow, pandas, NumPy, matplotlib, and sklearn.
• Finally, we need to run the TopicWiseTemporalSentimentAnalysis.ipynb Jupyter file. We will also 
need Covid19_GooglePlayData.csv, which contains the dataset for which we perform Topic-wise 
Temporal Sentiment Analysis. The sentiment classifier model saved in the ‘trainedmodel’ will be 
imported into this Jupyter File. After running this code, two CSV files,
covid19_googleplaydata_with_topics1.csv and covid19_googleplaydata_with_topics2.csv, will be 
created. covid19_googleplaydata_with_topics1.csv contained the user reviews and topics when the 
Topic Extraction model (BERTopic) was used with its default hyper-parameters. 
covid19_googleplaydata_with_topics2.csv includes the user reviews and the topics extracted after 
tuning the hyper-parameters of BERTopic. Libraries needed to run 
TopicWiseTemporalSentimentAnalysis.ipynb are regular expressions, pandas, NumPy, BERTopic, 
hdbscan, matplotlib, sklearn, transformers and TensorFlow
