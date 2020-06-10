# Aim: Based on a customer's profile, predict which type of touchpoint is most likely to result in a purchase
### X value: age, marital, segment, SocialMedia, income, creditRating, aveSpend, nTouchpoints
### Y label: Most recent touchpoint
## Data Cleaning
1. Check for missing values in every column
2. Removed rows with no touchpoints value / nTouchpoints = 0
## EDA
1. Explore the relationship of the segment variable with other variables in the dataset

![Income line plot](/images/plot1.png)
![Average Spending line plot](/images/plot2.png)

2. Discover any presence of multicollinearity and its degree with a heatmap

![Collinearity heatmap](/images/plot3.png)
