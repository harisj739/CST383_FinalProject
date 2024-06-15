# Team SSS - NBA Regular Season and Playoff Predictor
## Introduction
The project we tackled was to determine the most important statistics that result in success in the NBA regular season and playoffs. Due to the nature of basketball, injuries and other non-statistical factors play a role in the NBA regular season and playoffs. However, our group wanted to analyze what the NBA standings and playoffs would look like if they were determined based on specific playoff statistics. Using the key playoff statitistics in which the 2022-23 NBA champions Denver Nuggets were ranked Top 3 in, we predicted the 2023-24 NBA regular season standings (the winning percentage of each team) and compared them to the actual results. In addition, we predicted the 2023-24 NBA playoffs (who wins in each matchup) and compared our predictions to the actual results.
## Selection of Data
The dataset was read using data in four formatted tables found on **Basketball Reference**. Each table was read using url's, first read into a different dataframe. It was later combined into two new dataframes (one for regular seasons statistics and one for the playoffs) including a dataframe with playoff team regular season and playoff statistics. The regular season per team statistics tables contained _30 rows (representing the 30 NBA teams) and 25 features (various per game statistics)_. The regular season advanced statistics tables also contained _30 rows but 28 features_.  The playoff per team statistics tables contained _16 rows (16 teams are eligible to make the playoffs) and 25 features_. The playoffs advanced statistics tables contained _16 rows but 28 features_. The regular season statistics dataframe had _30 rows and 42 features_ and playoff statistics dataframe had _16 rows and 42 features_. The very last dataframe with all the playoff team stats had _16 rows and 84 features_.

The following measures were undertaken to implement feature engineering:
  1. As the advanced statistics tables contained header columns for certain statistics, the two advanced statistics dataframe table columns were read as a multi-index. To disregard the header         columns, the dataframe columns were updated to only contain the statistics desired.
  2. The advanced statistics dataframes still contained some bogus columns and irrelevant statistics. The following columns and features were dropped: _**Unnamed: 15_level_1, Unnamed:            17_level_1, Unnamed: 20_level_1, Unnamed: 22_level_1, Unnamed: 27_level_1, Arena, Attend., Attend./G', 'PW', 'PL'**_.
  3. The following rows were dropped: the last row (league average) from the regular season per game and advanced statistics dataframes, and the last 5 rows (the 4 play-in tournament teams and league average) from the playoffs per game and advanced statistics dataframes.
  4. The **_Win%_** column was added to the regular season advanced stats dataframe.
  5. In the _**Team**_ column, we removed the asterisks for the teams that made the playoffs.
  6. The column Rk was removed and the column Team was set as the index. Additionally, the regular season advanced statitistics were modified to exclude the columns for opponent _**eFG%, TOV%, ORB%, and FT/FGA**_.
## Methods
- Tools:
  - Python libraries NumPy, Pandas, Matplot for data processing and visualtization
  - Google Colab notebooks for sharing and running code
  - Scikit-learn machine learning processes:
    - Train Test Split
    - Cross Validation
    - Linear Regression
    - Random Forest Regression
    - Standard Scaler

## Results
- Initially we determined a set of predictors relevant to an NBA team's success including field goal percentage and three-point field goal percentage. We used these predictors to determine a team's predicted winning percentage. After splitting the data into training and testing sets we fit a linear regression model to the training set and plotted the results.
  
![NBA_demo1](https://github.com/harisj739/CST383_TeamSSS_FinalProject/assets/126642844/ab5b6d5e-7533-49f3-9969-443e921dbdf9)

- We also attempted to fit the data to a Random Forest Regression Model. However this resulted in increases to RMSE and a decrease in r-squared compared to our initial run in determining predicted winning percentage.
  
![NBA_randomforest](https://github.com/harisj739/CST383_TeamSSS_FinalProject/assets/126642844/fd37d269-5846-4ed0-b18b-b36334d9fbe9)

- After separating the teams into their respective conferences, we created new dataframes with the teams along with their predicted winning percentages. These were used to create a playoff simulation where we estimated which team would ultimately become NBA champion.
<img width="618" alt="NBA_championScreenshot" src="https://github.com/harisj739/CST383_TeamSSS_FinalProject/assets/126642844/c2575f99-2ca0-41a5-9bb7-ce511b1ebd5f">


## Discussion
This project shows the importance of various statistics in determining the success of NBA teams during the regular season and playoffs. By looking at advanced and per-game stats from the 2022-23 NBA season, we experimented with predicting the outcomes of the 2023-24 NBA season and playoffs. Our findings suggested that metrics like offensive rating (ORtg), defensive rating (DRtg), net rating (NRtg), and effective field goal percentage (eFG%) are highly correlated with a team’s success and win percentage. 
Our analysis showed the predictive power of both linear regression and random forest regressor models. The random forest regressor gave predictions that were slightly more accurate in comparison to linear regression overall, but linear regression provided more accurate final playoff standings than rfr did. This aligns with existing research that suggests ensemble methods can be better at predicting more complex data sets than linear models.
The results of this study can be useful for teams and analysts that may want to improve their performance or predict outcomes. Future research could build on this foundation by using more detailed data, such as player-level statistics and game-by-game performance metrics. In addition, it is also important to take into account the variable factors, such as injuries or big trades, since factors such as these can cause unexpected results. A potential implementation that could improve predictive accuracy could be the implementation of machine learning models that can handle time-based data. An example of this could be the use of recurrent neural networks or long short-term memory networks.

## Summary
The most important findings from our analysis are:

- Certain key statistics, such as those where the Denver Nuggets excelled, can be predictive of NBA success. The predictors that we used included field goal percentage, 3-point percentage, 2-point percentage, defensive rebounds, assists, offensive rating, defensive rating, net rating, and effective field goal percentage.
- Our predictive models for the regular season and playoffs were able to approximate actual outcomes with relatively high accuracy. This shows the value of data science in sports analysis.
- Feature engineering and selection played a very important role in improving both the performance and accuracy of the project.
- The use of cross-validation helped in identifying the most impactful features, which could help teams and analysts find specific areas to direct more focus to.

In conclusion, our project focuses on experimenting with sports analytics data and applying both statistical analysis and predictive modeling in order to understand and predict NBA team performance.

## Contributors
Andrew Grant, Anthony Matricia, & Haris Jilani

## Dataset References
1. https://www.basketball-reference.com/leagues/NBA_2024.html#per_game-team
2. https://www.basketball-reference.com/playoffs/NBA_2024.html#per_game-team
3. https://www.basketball-reference.com/leagues/NBA_2024.html#advanced-team
4. https://www.basketball-reference.com/playoffs/NBA_2024.html#advanced-team

