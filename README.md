# Aim: Based on a customer's profile, predict which type of touchpoint is most likely to result in a purchase
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
