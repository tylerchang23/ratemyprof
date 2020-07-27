# RateMyProfessors Data Analysis

You can find the Jupyter Notebook to my work [here!](https://github.com/tylerchang23/ratemyprof/blob/master/RMP_FINAL.ipynb)

## Introduction

When I was in college (last month lol), it was crucial that I had a good professor to succeed in the class. Unlike many of my friends who could easily self-learn / self-study any class, I was that one kid who was at every office hours asking questions from start to finish. One tool that I used throughout my college career was the review site called RateMyProfessors (RMP). Here, I could go through sometimes hundreds of reviews on almost every professor and use that information to schedule myself optimally. For the most part, RMP did a pretty good job at giving an overall rundown of what to expect from a professor. Here, I want to validate my personal experience with data!

![alt text](https://github.com/tylerchang23/ratemyprof/blob/master/images/erin.png)

## Goals

I wanted to answer a couple different questions with this analysis.

* **How were students talking about my old professors?**

* **What do students look for in a good professor?**

* **Do some schools in the UC system get better reviews than others?**

I also wanted to **develop a model that can perform binary classification on the quality ("good" or "bad") of the review**.

## Tools (Python)

* **Data Collection:** *BeautifulSoup*
* **Natural Language Processing:** *CountVectorizer, re, TextBlob*
* **Data Manipulation/Pre-processing:** *pandas, numpy*
* **Data Visualization:** *matplotlib, seaborn, WordCloud*
* **Machine Learning:** *sklearn*

## Results

***How were students talking about my old professors?***

After compiling the reviews for some of my old professors, I found the words/short phrases (tokens) that were commonly found in their reviews, as shown in the WordClouds below! The left side shows the most frequent tokens for one of my best professors at UC Davis, who has an overall quality of 4.5 (out of 5). The flip side shows a professor whose class I performed poorly in. From personal experience, I think these were fairly accurate when describing these professors and their classes. It was interesting to see the shift in tone between a seemingly "good" professor and "bad" professor.

![alt text](https://github.com/tylerchang23/ratemyprof/blob/master/images/wordcloud.png)

***What do students look for in a good professor?***

When I finished the previous section, I wanted to dive deeper into *what makes a professor "good"* at my school. The first task was to define "good."

![alt text](https://github.com/tylerchang23/ratemyprof/blob/master/images/quality_dist.png)

After determining the **distribution of overall quality was approximately normal**, I classified **all professors who had an overall quality that was one standard deviation more than the mean (3.75) to be "good"** The "cutoff" to be a good professor was an overall quality of **4.45**.

| Tag       | Percentage of Good Professors With Tag|
| ------------- |:-------------:|
| Respected| 80% |
| Amazing lectures| 70% |   
| Inspirational | 50% |
| Hilarious | 40% |
| Caring | 40% |

The first detail we examined was the **frequently used tags** used for these good professors. Interestingly, 4 of the 5 most frequently seen tags were **not related to actual teaching style**. Surprisingly, **the majority of frequently seen tags were related to personality!**

To further investigate this result, I again looked at the text of the review and found the most frequent tokens found with the good professors. Based on token frequency, it appears that **students also value teaching style**, with words like '*clear*' and '*helpful*' being prevalent. We can also see that **students may actually be valuing quality over easiness**. There's a good mix of words like "*easy*" and "*hard"*, "*helpful*" and "*difficult*", and words that indicate that you still have to do work to succeed like "*study*", "*homework*", etc..

![alt text](https://github.com/tylerchang23/ratemyprof/blob/master/images/good_prof.png)

***Do some schools in the UC system get better reviews than others?***

In this part, I decided to take a deeper look into the text of the reviews. Within each text, I examined its **polarity and subjectivity** as defined by [`TextBlob`](https://textblob.readthedocs.io/en/dev/). Specifically looking across two departments (Statistics and Economics) at three different UC's (UC Davis, UC Irvine, UC Berkeley), it appears that each school follows a similar pattern in distribution.

![alt text](https://github.com/tylerchang23/ratemyprof/blob/master/images/schools.png)

On average, all of the schools had **slightly positive toned reviews**, but followed a normal distribution. Similarly, each of the schools had **highly subjective ratings**, which makes sense for a student's personal review. From this, we can see that **there was no one school in the UC system that got significantly "better" reviews than the other.**

***Classification***

In the final part of the project, I wanted to wrap things up by creating a model that could classify whether a review was going to be good (quality > 2.5) or bad based on its contents.

| Model      | 10-fold CV Accuracy|
| ------------- |:-------------:|
| Logistic Regression| 84.10% |
| Gradient Boosting Classifier| 83.88% |   
| Gaussian Naive Bayes| 82.40% |
| K-Nearest Neighbors | 77.89% |
| Linear Support Vector Classifier | 77.01% |
| Decision Tree Classifier | 76.00% |
| Stochastic Gradient Descent | 75.64 % |
