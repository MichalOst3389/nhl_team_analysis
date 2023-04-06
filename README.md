# Goal

The objective of this undertaking is to conduct a comprehensive analysis of the defensive strategies employed by the Buffalo Sabres in order to identify potential areas for improvement and develop strategic insights aimed at mitigating the risk of opponents scoring against the team.


# Data

The data used for this project has been sourced from moneypuck.com. Specifically, the following datasets have been utilized:

shots_2022.csv: contains shot data for the 2022 season.
BUF.csv: contains team-level statistics for the Buffalo Sabres.
buf_player_stats.csv: contains player-level statistics for the Buffalo Sabres.
BOS.csv: contains player-level statistics for the Boston Bruins.
BOS_team_stats.csv: contains team-level statistics for the Boston Bruins.


### Exploratory Data Analysis

This code performs exploratory data analysis on two NHL teams, Boston and Buffalo, by comparing their total "goalsFor" and "goalsAgainst" statistics. The code groups the data by each team and situation, and calculates the sum of goals for and goals against. It then creates a bar chart to display the data for each team, with bars for goals for and goals against. The chart shows that Boston scores about 100 more goals than they let in, while Buffalo has an even number of goals for and goals against. This indicates that Buffalo has a strong offense but a weaker defense.


  ![Alt Text](https://user-images.githubusercontent.com/87345982/230147215-10c30186-fd99-4832-9940-0ee881d52e98.png)
  
  
  Next, we analyze the defense for both teams in different situations to determine why Boston allows so many fewer goals. It groups the data by team and situation and calculates the sum of goals against for each situation. It then calculates the percentage of each situation's goals against out of the team's total goals against, and plots the data in a bar chart. The chart shows that the percentages for both teams are close to each other for goals against in each situation, indicating that Buffalo allows too many goals overall, rather than just being particularly bad in one situation.


![Alt Text](https://user-images.githubusercontent.com/87345982/230147696-99942c38-2846-4205-894b-901a4c62f339.png)


After analyzing Buffalo's "goalsAgainst" statistic, we identified the key features that are most strongly associated with conceding goals. We used a correlation matrix to examine the relationships between each feature and "goalsAgainst". The results indicate that "high danger goals", total shots, rebounds, and other shot-related metrics all have a positive correlation with "goalsAgainst". These features appear to be the most relevant factors in determining a team's defensive performance. Interestingly, we see a few similar features when we compare Boston's defensive performance to Buffalo's. However, Boston's "highDangerGoalsAgainst" metric is lower than that of Buffalo. This suggests that Boston is doing a better job of keeping shooters out of high danger areas. Specifically, Boston's "highDangerGoalsAgainst" are 0.10 lower than Buffalo's.


In order to identify the high danger zone, I first filtered out shots that did not result in a goal from the shots_df dataframe, and stored the filtered result in a new dataframe called goal_shots. I then used Seaborn's set_style() function to set the style of the plot. Next, I created a figure with one subplot and plotted a KDE plot of the goal_shots dataframe's x and y coordinates using Seaborn's kdeplot() function with a colormap of "Reds" and a shading effect. The resulting plot showed that the most dangerous zone to be scored on was essentially right in front of the net.

To investigate further, I repeated the same process with shots that were not goals. The results showed that shooters who shot from further towards the boards (the edges of the hockey rink) usually had a lower chance of scoring. Therefore, to reduce the chance of a goal being scored, defensemen should push shooters out towards the boards. Overall, these findings emphasize the importance of defensive positioning

![download](https://user-images.githubusercontent.com/87345982/230175582-b5b76a89-fa3d-440e-9aba-c25282a670e1.png)


![download](https://user-images.githubusercontent.com/87345982/230175600-8eb39b1e-ab53-477d-8c54-60af3da6145a.png)


# Regression Model

 Use of a linear regression model was chosen to predict the number of goals scored based on the position of the shot on the hockey rink. We first isolate the shots that are in between -10 and 10 "yCord", and then modify their position by pushing them out 5 feet towards the boards. We then select the features and target, split the data into training and testing sets, fit the linear regression model, and finally make predictions on the modified shot positions to calculate the number of shots predicted to be goals.

The R-squared value of 0.998 tells us that the other features in the dataset explain 99.8% of the variation in xGoal. The coefficients show how much each feature affects xGoal, and the p-values show whether each feature is statistically significant in predicting xGoal. The standard errors indicate how much the coefficients vary from sample to sample, and the confidence intervals show the range within which the true coefficient value is expected to fall with 95% confidence.

Overall, this modelprovides insights into the effects of pushing a shooter out more towards the boards on the probability of scoring a goal in ice hockey. 

### Residual Plot

This plot shows the difference between the predicted values and the actual values of XGoal, called residuals. If the model is doing a good job of predicting XGoal, the residuals should be randomly scattered around a horizontal line at zero. This indicates that the model is capturing the variation in the data, and there is no pattern in the residuals. However, if there is a pattern in the residuals, it suggests that the model is not capturing some important information in the data.


![download](https://user-images.githubusercontent.com/87345982/230179534-3e77133f-1fda-4d49-83c3-4076dfd150bc.png)


### Actual vs. predicted plot

This plot is a scatterplot of the predicted XGoal values (on the x-axis) versus the actual XGoal values (on the y-axis) for each shot. If the model is doing a good job of predicting XGoal, the points on the scatterplot should be close to the diagonal line. If the points are close to the diagonal line, it suggests that the model is making accurate predictions.


![download](https://user-images.githubusercontent.com/87345982/230179674-d560fc3c-ba47-4d0f-a7ca-67a85ca09c81.png)


### Distribution plot

This plot shows the distribution of the predicted XGoal values (in blue) and the actual XGoal values (in orange). If the model is doing a good job of predicting XGoal, the distribution of the predicted values should be similar to the distribution of the actual values. If the distributions are similar, it suggests that the model is making accurate predictions.


![download](https://user-images.githubusercontent.com/87345982/230179807-4eaa4297-76b6-4130-9174-4733e4b69797.png)


After running a linear regression model to predict the number of goals scored from high danger zones in hockey, a bar graph was created to compare the number of actual goals scored versus the number of goals that would be scored if shooters were pushed out 5 feet towards the boards. The graph shows that before the model ran, 4499 goals were scored from the high danger zone. However, after the model ran, it predicted that only 760 of those shots would have resulted in goals if the shooters were pushed outwards. It is important to note that this does not mean that there would ONLY be 760 goals, but rather, that pushing shooters outwards significantly reduces the chances of a shot being a goal.



![download](https://user-images.githubusercontent.com/87345982/230181470-962f21e0-92a3-4918-ba81-71c3a447d5f8.png)


### Rebound Shot Analysis

As we look into the importance of rebounds while defending, we have identified an additional factor that plays a crucial role in determining if a shot results in a goal. We investigated the impact of rebounds on goal scoring and identified which types of shots are most likely to result in rebounds. By doing so, we hope to provide our goalie with valuable insights into which shots are most likely to pose a significant threat even after the initial save.

The analysis included calculating the correlation matrix for the DataFrame and selecting the correlation value between "xGoal" and "xRebound". The correlation coefficient of 0.295 indicated a tendency for higher values of xRebound to be associated with higher values of xGoal, but the strength of this relationship was only moderate. However, when looking at the correlation between just our goals against and rebounds, the correlation was stronger, with a value of 0.320879, suggesting that the Buffalo Sabres do worse than average at defending against rebounds.


We filtered the shots that resulted in a rebound, and created a density plot of the rebound shots using the Seaborn library. The resulting plot shows the density of rebound shots in different areas of the rink, mostly directly in front of the net.

In addition to providing insights for goalies, the density map can also be useful for defensemen, as it can help them anticipate the puck's trajectory and be better positioned to retrieve it. By understanding the most common rebound areas, defensemen can take proactive measures to prevent the opposing team from scoring, contributing to the team's overall defensive strategy and helping to minimize the chances of a goal being scored against them.


![download](https://user-images.githubusercontent.com/87345982/230191623-96fbbab2-6a8b-4c23-9057-6e5586e65c80.png)


# Next Steps

Tailor heatmaps to specific opponents before upcoming games to adopt a more customized defensive approach to each team's playing style.

Analyze the defensive metrics of our own players and provide personalized feedback to help them improve their performance.

Explore the possibility of creating a model to recommend a player with a similar role who may perform better if a player shows no signs of improvement despite giving them sufficient time to improve their defensive play.



