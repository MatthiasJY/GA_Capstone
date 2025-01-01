## GA_Capstone
Capstone project that I did for my final submission at General Assembly Data Analyst Bootcamp

## Problem Statement 
An E-commerce company is looking to attract new customers to shop on their online marketplace. After some internal investigation and research, the upper management of the company concluded that they would need a new personalised shopping experience for each customer, and also a more personalised or localised marketing when it comes to the products themselves. 

<img src="https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExZThwaGxuc3ZmZTd5ZWoyb25kcXdkaWljbDI2ZDB3aHVtdTN4cHYwZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/QAVfJ35dd0GT5v1mCZ/giphy-downsized-large.gif" width="50" height="70" />

## Project Objective 
The main objective of this project is to successfully solve the company’s problems with a prediction model that can aid in the personalisation and localisation of a customer’s shopping experience and product’s marketing plan. 

## Target Audience
The target audience for this project would be Business Decision Makers who are looking to make data driven business decisions for their company. It is for people who believe in the power of data and are looking to plan and strategise based on that.    

Persona 1: Tom, Head of Marketing 
Tom Lee, a new in charge of the marketing department in this e-commerce company, was given the task by the C-suites to look into personalised and localised marketing in view of the upcoming customer acquisition campaign. Tom has always believed that working with data is essential for any marketing plan, and machine learning is the way forward. Tom struggles to introduce this new way of strategising that's heavy on Big Data, and wants to show his team and company’s management the efficacy and benefits of implementing them into their daily work process.       

Persona 2: Arthur, Head of Customer Experience 
Arthur Francisco has been the Head of Customer Experience for 5 years now and has been a long time employee, climbing the ranks for the past 10 years. He is used to the old ways of doing things, but has always been interested in upskilling to  keep up with modern times. He recently learned about machine learning and coding and would like to see how it can be implemented in his daily tasks. He is open minded, and eager to learn and be exposed to new ideas, but would need some convincing.   

## Data Source 
Kaggle - https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Data Processing 
Data Cleaning 
All data used has been cleaned and cleared of null values. As product category names were all in Portuguese, language has been translated to English for easier analysis. After that, it was merged with the products table. Products, Items, and Orders tables were merged as well to analyse the data further, and use them in the prediction models. 

## Insights 
![](transaction_trend.png)
This graph shows the trend of total transaction value and total orders of the top 10 products from 2017 Jan - 2018 Aug. The trend is moving upwards as the months past, and sharp spikes in transaction value and orders can be seen as well, especially during November 2017 and February 2018. This seems to be aligned with the festive season of Black Friday and Christmas, as well as Valentines’ day, suggesting that their customers shopped the most during these seasons, and the team has to be ready for it.

![](state_differences.png)
This map below shows the total order value (Right), and average delivery time (Left), separated into each individual state. States like São Paulo (SP) and Rio de Janeiro (RJ) observed the highest spends at $5.9M and $2.1M respectively, while states like Roraima (RR) and Amapa (AP) had the least spends at $10K and $16K respectively. Delivery time on the other hand, observes the opposite effect. This suggest that each state has its own personality, spending power and shopping habits.

## Proposed Solution 
**Success Criteria**
The success metric for the first prediction model will be achieving the lowest RMSE possible for the Prophet model. For the Collaborative Filtering model, Precision@K between 0.60 - 0.65 and Recall@K between 0.80 - 0.85 would be the success metric.

**Prophet**
A time series forecasting model was built to be able to predict the sales of a selected product, for a particular state, 6 months in advance. Prophet was used as the time series model as it deals with missing data better than other time series models.

This model was built by grouping the dataset by the months, followed by each product category and state that each customer lives in. The price paid by each customer was also aggregated to find the total spends on each product, and thus the total revenue for the brand. Customer state was used as an external factor that can influence the forecast as the spendings of each state is different.

Please view the example below for the visualisation of the forecasting done with Python, in the Jupyter Source File submitted.


## Recommendations 
In conclusion, we recommend this e-commerce brand to make use of the Prophet model and Collaborative Filtering model to achieve their goal of localising marketing strategies and personalising customer experiences. 

The Prophet model helps them know how each product category is predicted to perform in terms of total revenue 6 months into the future, and how it differs from each individual state as well. 

The Collaborative Filtering model integrated into the e-commerce website will allow for a more personalised customer experience. This new shopping experience only benefit existing customers as it's a new and novel feature, but also attract new customers as it is an experience that they are searching for. 

