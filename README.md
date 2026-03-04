# BABI-4005---Data-Wrangling-aka-DQM-with-Python

The data analyzed in the Baby Project came from this Kaggle link: https://www.kaggle.com/datasets/mahdimashayekhi/social-media-vs-productivity

**Social Media vs Productivity Analysis**

**Data Source**
This project uses the Social Media vs Productivity dataset from Kaggle. The dataset contains 30,000 records and tracks social media habits, work patterns, and productivity levels.

**Project 1 Summary**
In the first project, I analyzed the dataset to understand what the data looked like and to find patterns in the data to draw a conclusion. 
Project Sequence:
1.	Loaded the data using pandas and imported the visualization libraries matplotlib and seaborn
2.	Viewed the dataset’s structure. It had 30,000 rows and 19 columns covering information such as age, gender, job type, daily social media time, productivity scores, and stress levels
3.	Noticed there were quite a few missing values in several columns like daily_social_media_time and actual_productivity_score (this may be due to the format of the survey or medium that collected the initial information. 
4.	Created summary statistics showing the min, max. mean, standard devation and record count of three columns: daily_social_media_time, perceived_productivity_score and actual_productivity_score
5.	Made visualizations to compare social media usage across different job types (Education, Finance, Health, IT, Student, Unemployed)

**Key Finding:** 
•	There seems to be a consistent relationship that an individuals' perceived productivity on average slightly over estimates their actual productivity
•	This could mean that people estimate their own productivity relatively accurately
•	The summaries reveal there is no conclusive relationship between Daily Social Media Time and Actual Productivity Score

**Project 2 Summary**
For the second project, I practiced joining datasets by adding wellness recommendations to my cleaned data.
Project Sequence:
•	Created a second dataset in perplexity that provided wellness recommendations based on social media platforms
•	Loaded data using pandas
•	Used a left join to merge the two datasets on the social_platform_preference column
•	Which added new columns suggested_social_media_time, suggested_active_time, suggested_breaks_per_day, suggested_weekly_offline_hours and wellness_priority

**Why Left Join? **
I wanted to keep the 30,000 records from the original dataset and add extra wellness information to the dataset
