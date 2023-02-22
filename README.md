# Baylor-NCSAC-Final
Repository for project that won first place in Baylor's National Collegiate Sport Analytics Championship

## Overview
In this project, I use data from the Big-12's 2018-2019 Conference season supplied by the organizers of the National Collegiate Sport Analytics Championship. In conducting preliminary analysis of shot selection, I noticed that the conference's top teams were taking midrange jump shots at nearly twice the rate of of the conference's worst teams. Though this ran counter to my intuition of the mid-range as an inefficient shot, I created a project that utilized R to produce various visualizations, multi-variate regressions, and ultimately apply a Machine Learning model to understand the effect that taking more mid-range jump shots might have for a team.

## Introduction
The mid-range jumper has been a topic of much debate in the world of basketball analytics in recent years. Traditionally, the mid-range shot has been a staple of basketball offenses, with players like Michael Jordan, Kobe Bryant, and Dirk Nowitzki making it a key part of their game. However, in recent years, the prevailing wisdom in the sport has shifted towards prioritizing three-point shots and shots at the rim, as these are generally considered to be more efficient.

Despite this shift, some players and coaches continue to value the mid-range shot, arguing that it can be a valuable weapon in certain situations. For example, some players may be better at hitting mid-range shots than three-point shots, or may find it easier to create space for a mid-range jumper when the defense is focused on taking away the three-point shot or the drive to the basket.

Against this backdrop, the analysis presented in this project provides an important contribution to the ongoing debate about the value of the mid-range shot. By examining the relationship between shot selection and team performance in the Big-12 conference, the analysis sheds new light on the potential benefits of taking more mid-range jump shots. These findings have important implications for coaches, players, and analysts, and suggest that a more nuanced understanding of shot selection may be necessary to maximize team performance in the modern game of basketball.


## Methodology

### 1. Data Cleaning and Preparation
Cleaning and preparing the data is a crucial step in any data analysis project, and this project was no exception. The dataset provided by the organizers of the National Collegiate Sport Analytics Championship contained a vast amount of data on every play in the Big-12 conference's 2018-2019 season, including information on the time and location of each shot attempt, the player attempting the shot, and the outcome of the shot.
This cleaning process involved removing any missing or erroneous values, converting variables to the correct data type, and merging multiple datasets together.

Once the data had been cleaned and prepared, I calculated various statistics for each team and player in the conference, including shooting percentages, three-point percentages, and mid-range shooting percentages. This allowed me to get a better understanding of the performance of each team and player in the conference.

### 2. Visualization of Shot Attempts
After the data had been cleaned and prepared, I created a series of visualizations to help me better understand the patterns in the data. In particular, I created visualizations of shot attempts for each team in the conference.

According to these visualizations, there appears to be a strong correlation between mid-range attempt rate/FG% and wins:

<img width="506" alt="Screen Shot 2023-02-21 at 9 00 59 PM" src="https://user-images.githubusercontent.com/105028034/220510334-7b03e4a2-524f-4132-b760-8f4614125531.png">
<img width="390" alt="Screen Shot 2023-02-21 at 9 01 13 PM" src="https://user-images.githubusercontent.com/105028034/220510359-0a60cff0-3d16-4ae7-ad58-551236eefc7b.png">


These visualizations allowed me to see at a glance which teams were taking more mid-range shots than others. For example, the visualization for Kansas State, the team that ultimately won the conference, showed that they took a relatively large number of mid-range shots compared to other teams. On the other hand, the visualization for Texas, a team that missed the tournament, showed that they took relatively few mid-range shots.

Differences in midrange attempt rate between Texas and Kansas State can be seen below:

<img width="419" alt="Screen Shot 2023-02-21 at 9 01 36 PM" src="https://user-images.githubusercontent.com/105028034/220510411-ff18b679-598c-4263-b481-2aeca511b9b2.png">
<img width="418" alt="Screen Shot 2023-02-21 at 9 01 48 PM" src="https://user-images.githubusercontent.com/105028034/220510435-64b1a550-3989-4a8a-aec9-35695462b18e.png">


### 3. Multivariate Linear Regression
To further explore the relationship between shot selection and team performance, I conducted a multivariate linear regression. This allowed me to determine which factors were statistically significant predictors of team performance.
The regression analysis included a range of variables, including mid-range attempt rate, mid-range field goal percentage, three-point field goal percentage, and rim field goal percentage. The results of the analysis showed that both mid-range field goal percentage and mid-range attempt rate were statistically significant predictors of team wins. Specifically, teams that took more mid-range shots tended to have higher shooting percentages and were more likely to win games.


Results from multi-variate regression which interestingly only show mid-range attempt rate and mid-range field goal % as the only statistcally significant regressors

<img width="329" alt="Screen Shot 2023-02-21 at 9 11 33 PM" src="https://user-images.githubusercontent.com/105028034/220511722-d056e5b9-259c-4c09-832f-e6f6ea4e7c37.png">

### 4. Machine Learning Model
The machine learning section of this project was an important component of the analysis, as it allowed me to quantify the potential impact of increasing a team's mid-range attempt rate on their overall performance. Here is a more detailed description of the machine learning techniques that I used:

Machine learning is a powerful tool that can be used to build models that can make predictions based on data. In this project, I used a random forest machine learning model to predict the impact of increasing mid-range attempt rate on a team's shooting percentage.

A random forest model is a type of decision tree-based machine learning algorithm that is commonly used in regression and classification problems. The algorithm works by creating a large number of decision trees and then combining their predictions to make a final prediction. Each decision tree is trained on a random subset of the data and uses a random subset of the available features to make its predictions. By combining the predictions of many decision trees, the random forest model is able to make more accurate predictions than any individual decision tree.

The first step in building the model was to split the data into a training set and a testing set. The training set was used to train the model, while the testing set was used to evaluate the model's performance.

Once the data had been split, I used R's randomForest package to build the random forest model. I used a range of hyperparameters, including the number of decision trees in the model, the number of features used to train each decision tree, and the maximum depth of each decision tree, to optimize the model's performance.

After the model had been trained, I used it to simulate the impact of increasing Baylor's mid-range attempt rate from 7.2 shots per game to 12.6 shots per game, a 75% increase. I found Baylor to be an interesting case study for several reasons, as they had several solid midrange shooters in Jared Butler and Makai Mason, but their attempt rate was relatively low when compared to other winning teams in the Big-12. 

Comparison between Kansas State's shot chart and Baylor's

<img width="924" alt="Screen Shot 2023-02-21 at 9 20 21 PM" src="https://user-images.githubusercontent.com/105028034/220512911-ccdbaf99-3520-4bfe-8973-acb091f37529.png">

It is worth noting that while the random forest model was able to make accurate predictions in this case, it is not always the best choice for every problem. In some cases, other machine learning algorithms, such as neural networks or support vector machines, may be more appropriate. However, for this particular problem, the random forest model was a good choice as it allowed me to accurately quantify the potential impact of increasing mid-range attempt rate on a team's shooting percentage.

In conclusion, the machine learning section of this project was an important component of the analysis, as it allowed me to make accurate predictions about the potential impact of increasing a team's mid-range attempt rate on their shooting percentage. The use of a random forest model was a good choice for this particular problem, as it allowed me to accurately simulate the impact of changing a single variable on a team's performance.

These were the changes I made between my train and test dataset:
<img width="909" alt="Screen Shot 2023-02-21 at 9 16 46 PM" src="https://user-images.githubusercontent.com/105028034/220512412-3e402216-8989-4bef-89ed-3aba630448de.png">

## Results and Discussion

The results of this analysis provide insight into the potential impact of increasing a team's mid-range attempt rate on their overall performance. Using data from the Big-12's 2018-2019 Conference season, I was able to conduct a preliminary analysis of shot selection and noticed that the conference's top teams were taking mid-range jump shots at nearly twice the rate of the conference's worst teams.

To further investigate the impact of mid-range attempt rate on a team's performance, I created various visualizations and conducted a multivariate linear regression. The regression showed that mid-range field goal percentage and mid-range attempt rate were statistically significant predictors of wins, suggesting that taking more mid-range jump shots could lead to improved performance.

To quantify the potential impact of increasing mid-range attempt rate, I then used a random forest machine learning model to simulate the impact of increasing Baylor's mid-range attempt rate from 7.2 shots per game to 12.6 shots per game, a 75% increase. The results of the model showed that increasing the mid-range attempt rate by 75% would lead to an increase in expected points per game from 72.6 to 75.1 and an increase in expected wins by 1.1.

<img width="814" alt="Screen Shot 2023-02-21 at 9 23 26 PM" src="https://user-images.githubusercontent.com/105028034/220513337-e41266d6-871b-48d9-8571-8910236d4912.png">

These findings have important implications for teams looking to improve their performance. While there is often a focus on three-point shooting and limiting mid-range shots, this analysis suggests that increasing mid-range attempt rate could lead to improved performance. It is important to note, however, that this does not necessarily mean that teams should abandon three-point shooting altogether. Rather, a balanced approach that includes mid-range shots could lead to improved performance.

It is also worth noting that the findings of this analysis are specific to the Big-12's 2018-2019 Conference season and may not be generalizable to other leagues or seasons. Additionally, while the machine learning model was able to accurately simulate the impact of increasing mid-range attempt rate, there are other factors that could impact a team's performance that were not included in this analysis.

## Conclusion
In conclusion, this analysis has shed light on the potential impact of increasing a team's mid-range attempt rate on their overall performance. The findings suggest that taking more mid-range jump shots could lead to improved performance, which may run counter to the popular notion that mid-range shots are inefficient. However, it is important to maintain a balanced approach that includes three-point shooting as well.

Future research could investigate the impact of mid-range shots on team performance in other leagues and seasons, as well as explore the potential benefits and drawbacks of taking a more mid-range-heavy approach to shot selection. Additionally, further investigation could explore the factors that contribute to mid-range shot success, such as player positioning, ball movement, and defensive strategies.

Overall, this analysis has provided a valuable contribution to the field of sports analytics and highlights the importance of considering all types of shots when developing game strategies. Coaches and players who incorporate a balanced approach to shot selection, including mid-range shots, may be able to improve their team's performance on the court and achieve more victories.






