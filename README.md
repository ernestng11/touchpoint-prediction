# Aim: Based on a customer's profile, predict which type of touchpoint has the highest probability of resulting in a purchase
X value: age, marital, segment, SocialMedia, income, creditRating, aveSpend, nTouchpoints

Y label: Most recent touchpoint
## Data Cleaning
1. Check for missing values in every column
2. Removed rows with no touchpoints value / nTouchpoints = 0
## EDA
1. Explore the relationship of the segment variable with other variables in the dataset

![Income line plot](/images/plot1.png)
![Average Spending line plot](/images/plot2.png)

2. Discover any presence of multicollinearity and its degree with a heatmap

![Collinearity heatmap](/images/plot3.png)

3. Visualizing distribution of variables with distribution plots and barplots

![Marital plot](/images/plot4.png)
![Segment plot](/images/plot5.png)
![Social media plot](/images/plot6.png)
![Credit rating plot](/images/plot7.png)
![nTouchpoints plot](/images/plot8.png)
![Age plot](/images/plot9.png)
![Age distribution plot](/images/plot10.png)
![Income distribution plot](/images/plot11.png)
![Average spending dist plot](/images/plot12.png)

4. One hot encode categorical variables

## Model Building

Metrics for evaluating models: Multiclass logloss since we are predicting the probabilities of the next touchpoint, I want to find the average difference between all probability distributions

Multi-class classification approach: 

1. Standardize/normalize numerical data

![Age distribution plot](/images/plot13.png)
![Income distribution plot](/images/plot14.png)
![Average spending dist plot](/images/plot15.png)

2. Try baseline ensemble models:  XGBoost, Random Forest, Adaboost

**XGBoost**

![mean logloss plot](/images/plot16.png)
![mean error plot](/images/plot17.png)

**Random Forest**

3. Try neural networks: Simple NN with regularization(L1/L2/dropout) with Tensorflow

## Deploy Model
Using FlaskAPI
