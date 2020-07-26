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

When I finished the previous section, I wanted to dive deeper into *what makes a professor "good"*
