![capstone_proj](https://github.com/user-attachments/assets/0b408437-10ef-48d4-9050-995c24e93df5)

## Capstone Project Introduction
An E-commerce company is looking to **attract new customers** to shop on their online marketplace. After some internal investigation and research, the upper management of the company concluded that they would need a new personalised shopping experience for each customer, and also a more personalised or localised marketing for each product and state. 

## Project Objective 
The main objective of this project is to successfully solve the company’s problems with a machine learning model that can aid in the personalisation and localisation of a customer’s shopping experience and product’s marketing plan. 

## Data Source 
Kaggle - https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Data Processing 
Raw data were cleaned with Python on Jupyter Notebook
- Null values and duplicates were removed selectively 
- Products category names were all in Portuguese, thus language was translated to English through merging of Products and Translation table
- Products, Items, and Orders tables were merged as well to provide further analysis, and for preparation of machine learning model usage

## Data Insights (Tableau)
![](transaction_trend.png)
This graph shows the trend of total transaction value and total orders of the top 10 products from 2017 Jan - 2018 Aug. The trend is **moving upwards** as the months past, and **sharp spikes in transaction value and orders** can be seen as well, especially during **November 2017** and **February 2018**. This seems to be aligned with the festive season of **Black Friday, Christmas, and Valentines’ day**, suggesting that their customers shopped the most during these seasons, and the company has to be ready for it.<br/>

<br/>
<br/>

![](state_differences.png)
This map below shows the total order value (Left), and average delivery time (Right), separated into each individual state. States like **São Paulo (SP)** and **Rio de Janeiro (RJ)** observed the highest spends at **$5.9M and $2.1M** respectively, while states like **Roraima (RR)** and **Amapa (AP)** had the least spends at **$10K and $16K** respectively. Delivery time on the other hand, observes the opposite effect. This suggest that each state has its **own personality, spending power and shopping habits**.

## Proposed Solution 

### Prophet

![](prophet_dash_viz.png)
The time series forecasting model was visualised using Dash and Plotly in my Jupyter Notebook. 

It is able to predict the sales of a selected product, for a particular state, 6 months in advance. Prophet was used as it deals with missing data better than other time series models like ARIMA.

**Method:**
- This model was built by grouping the dataset by the Months, Product Category and State
- The price paid by each customer was aggregated to find the total spends on each product, and thus the total revenue for the brand
- State was used as a regressor that can influence the forecast as the spendings of each state is different

**Success Rate of Model**<br/>
This model achieved a low RMSE as compared to the mean value (**77.10% lower**). This suggests that the predictions are close to the actual values. R2 on the other hand, is negative, suggesting that the predicted values are also random. However, the dataset only has about 20 months of data, and different missing Months for each product category. Thus, the accuracy is limited by these factors.

Please view full steps and code in the [Jupyter Source File.](https://github.com/MatthiasJY/GA_Capstone/blob/main/Capstone%20Prophet%20Forecasting%20Code.ipynb)

### Collaborative Filtering Recommendation System

![](collab_filtering_results.png)
The Recommendation System recommended Telephone, Computers Accessories, and Auto product categories for Customer f7ea4eef770a388bd5b225acfc546604.

The Collaborative Filtering method was built to recommend up to 5 Product Categories for each unique customer by comparing with other customers that are closest in terms of Similarity Score.

**Method:**
- Scaling was done to Product Ratings so that higher ratings like 4 or 5, were emphasised more than lower ratings like 1 or 2
- Customers within the same state also produced a higher Similarity Score than customers from different states
- Product Ratings score and State score were combined for the final Weighted score to be included into the User Item Matrix
- Similarity matrix was created with the User Item Matrix
- Recommended categories function was created with a Customer Id input, Similarity dataframe, Customer Table, and selected number of outputs

**Success Rate of Model**<br/>
This model has a **Precision and Recall score of 0.60 and 0.95** respectively. This shows that the model is highly comprehensive and rarely misses relevant product categories (0.95 Recall) but, has some irrelevant product categories that are also included (0.60 Precision). Customers will likely see many relevant product categories which is good for overall sales.

Please view full steps and code in the [Jupyter Source File.](https://github.com/MatthiasJY/GA_Capstone/blob/main/Capstone%20Recommendation%20System%20Code.ipynb)

## Limitations 

The limitations of the Prophet model would be the **lack of "time" of the dataset** and **missing data**. The forecasting model performs well with an adequate amount of “time”. However, this data only recorded about 1.5 years, and thus, was not enough to produce an accurate result.

The limitations for the Collaborative Filtering model would be the **high intensity in computer processing** needed to run a bigger model. This is because it is highly intensive to run a matrix of 100,000 by 100,000 for example, even though it would be more accurate. 

## Recommendations 
In conclusion, I recommend this E-commerce company to make use of the Prophet model and Collaborative Filtering model to achieve their goal of localising marketing strategies and personalising customer experiences. 

The Prophet model helps them know how each product category is predicted to perform in terms of total transaction value 6 months into the future, differing by state as well. This will **prevent generic marketing plans**, but rather, one that is based on predicted sales.

The Collaborative Filtering model integrated into the e-commerce website will allow for a more personalised customer experience. This new shopping experience benefits both existing and new customers as it's a new and novel feature, that is value adding in **recommending relevant products**.

## Final Statement
Feel free to down load the dataset from Kaggle and test it out with the Jupyter Source Files provided. Do let me know if there are other ways to improve on these models as well. Thank you!
