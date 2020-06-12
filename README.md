# Aim: Based on a customer's profile, predict which type of touchpoint has the highest probability of resulting in a purchase
X value: age, marital, segment, SocialMedia, income, creditRating, aveSpend, nTouchpoints

Y label: Most recent touchpoint
## Data Cleaning

### 1. Check for missing values in every column

### 2. Removed rows with no touchpoints value / nTouchpoints = 0

## EDA

### 1. Explore the relationship of the segment variable with other variables in the dataset

![Income line plot](/images/plot1.png)
![Average Spending line plot](/images/plot2.png)

### 2. Discover any presence of multicollinearity and its degree with a heatmap

![Collinearity heatmap](/images/plot3.png)

### 3. Visualizing distribution of variables with distribution plots and barplots

![Marital plot](/images/plot4.png)
![Segment plot](/images/plot5.png)
![Social media plot](/images/plot6.png)
![Credit rating plot](/images/plot7.png)
![nTouchpoints plot](/images/plot8.png)
![Age plot](/images/plot9.png)
![Age distribution plot](/images/plot10.png)
![Income distribution plot](/images/plot11.png)
![Average spending dist plot](/images/plot12.png)

### 4. One hot encode categorical variables

## Model Building

Metrics for evaluating models: 
1. Multiclass logloss since we are predicting the probabilities of the next touchpoint, I want to find the average difference between all probability distributions
2. F1-Score(Micro) since we have imbalanced classes of labels

### 1. Standardize/normalize numerical data

![Age distribution plot](/images/plot13.png)
![Income distribution plot](/images/plot14.png)
![Average spending dist plot](/images/plot15.png)

### 2. Try baseline ensemble model:  Random Forest

**Random Forest**

I picked RF Classifer simply because it runs fast and I am able to use GridSearchCV to iterate to the best model possible efficiently. 
After initializing and tuning my RandomForestClassifier model with GridSearchCV, I got a train accuracy of 1.0 and test 
accuracy of 0.77688 which shows overfitting.

![FI](/images/plot20.png)

Our RF Classifier seems to pay more attention to average spending, income and age. 

### 3. Explore ensemble model: XGBoost


**XGBoost**

Initial XGB model

![mean logloss plot](/images/plot16.png)
![mean error plot](/images/plot17.png)

XGB model after tuning with *GridSearchCV* : max_depth, min_child_weight and reg_alpha

![mean logloss plot](/images/plot18.png)![mean error plot](/images/plot19.png)

![FI](/images/plot21.png)

Our XGBoost model pays high attention to the 'unknown' marital status. This could be due to the fact that there are only 44 customers with 'unknown' marital status, hence to reduce bias, our xgb model assigns more weight to 'unknown' feature.

XGBoost Accuracy: 0.9678972712680578

XGBoost F1-Score (Micro): 0.9678972712680578

I will pick the final XGBoost model since it gives significantly higher F1-score and accuracy. We can also easily control overfitting by further tuning the reg_alpha value in our model.

## Model Deployment

I included a pickle file for further deployment of the model into FlaskAPI in the future!
