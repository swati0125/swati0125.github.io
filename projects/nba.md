## Automated Ad Classification
[GitHub](https://github.com/abhinav314/nbaPerfPrediction)

### Problem Definition

Develop a framework to help NBA teams predict player performance for upcoming seasons, based on their on-court efficiency. Finally, recommend player trades based on user-entered budget and PER values.

### Solution Overview

My team started off by identifying the most "efficient" players position-wise. We chose the Player Efficiency Rating [PER](http://insider.espn.com/nba/hollinger/statistics/_/order/false) provided by ESPN as our guiding metric. 

Our aim was to predict the PER values for players in the upcoming season (2019-20) based on historical data. Relying on the predicted PER values, and a user inputted budget, we recommend player trades and generate a sample roster within the budget for the upcoming season. 

We chose to implement the solution for Indiana Pacers, within a budget of $50 Mn.

![alt text](/images/nba2.png "Position-wise Statistics")

### Data Gathering

Web scrape ESPN's NBA data for the past decade. Data cleaning and feature engineering was not required due to the quality of the database. However, the number of features were high (~50), hence we implemented feature selection using recursive feature elimination to reduce dimensionailty and correlation.

![alt text](/images/nba1.png "Selected Features - Correlation Heatmap")

### Data Modeling

Linear models, bagging and boosting algorithms were tested. The gradient boosting algorithm worked the best, with an accuracy of 98% on the holdout data.

![alt text](/images/nba3.png "Predicted PER - Indiana Pacers")

### Roster Selection

The top 5 players for the Indiana Pacers were identified based on our PER predictions. These were the players to be retained for the upcoming season. Taking note of the positions of these players, we developed an algorithm to generate player trades optimizing the "bang-for-buck" factor. The solution is scalable and each end-to-end run takes less than a minute. It can be extended to any sport with model re-training and the budget cap as an input.

![alt text](/images/nba4.png "Final Roster")