# A/B Testing at Blue Academy
![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/istockphoto-1395685005-1024x1024.jpg)

# Overview:
A/B testing, also known as a randomized controlled experiment, is demonstrated by this project. Private companies use A/B testing to improve email marketing and product pricing. Political campaigns use it to test messages. Additionally, scientists use it in their research.

# Project Scenario:
Blue Academy is an education platform that provides a learning path about data science and machine learning. There is no condition to enroll in this path except passing a short Python quiz. However, many applicants to the path never complete the Python quiz, which is a prerequisite for admission. Therefore, we designed an experiment to see if we could increase quiz completion.

**Note**: This project is based on synthetic data that mimics real data, including names, birthdays, and email addresses.

# Data Processing and Analysis: 
First, we connected to the academy's MongoDB database and analyzed the demographic information of the applicants. We used an open-source library called Country Converter to standardize the nationality data. We created a map to visualize the regional trends. We also utilized the date diff operator to convert the birth dates to ages. Lastly, we sorted the education levels into a dictionary comprehension to make it easier to read in a horizontal chart.

![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/nat_bar.png)
![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/map.png)
![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/ages.png)
![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/education.png)

To prepare our data for the experiment, we moved to the ETL (extract, transform, and load) process. We identified the no-quiz applicants who opened an account on the platform but did not take the admissions quiz. We then developed a research question, a null hypothesis, and an alternate hypothesis. Our null hypothesis was that there's no relationship between getting and sending an email to an applicant and completing the quiz. Our alternate hypothesis was that there is a relationship, and if we send them an email, they are more likely to complete the quiz.

We assigned the applicants to either the treatment or control groups. The treatment group received an email, while the control group did not. We then created a function that exported the treatment group's emails for the email campaign.

Also, we wrote a function to update multiple documents in a database for loading the data.

We created a Mongo repository class with all the necessary attributes and ETL methods for an improved experimental process.

In the third phase of our project, we carried out an experiment. Initially, we performed a power calculation to determine the precise number of observations required to invite into the study. This calculation allowed us to obtain significant results if there was a significant relationship between the variables under observation. We then computed a cumulative density function (CDF) to determine the necessary duration of the experiment.

Once the experiment was complete, we collected the resulting data and constructed a contingency table, also known as a 2x2 table. We performed a chi-square test to analyze the data and determine whether there was a significant relationship between sending an email and completing the quiz.
![](https://github.com/SawsanYusuf/AB-Testing-at-Blue-Academy/blob/main/images/results.png)
