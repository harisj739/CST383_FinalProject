# Team SSS - NBA Regular Season and Playoff Predictor
## Introduction
The project we tackled was to determine the most important statistics that result in success in the NBA regular season and playoffs. Due to the nature of basketball, injuries and other non-statistical factors play a role in the NBA regular season and playoffs. However, our group wanted to analyze what the NBA standings and playoffs would look like if they were determined based on specific playoff statistics. Using the key playoff statitistics in which the 2022-23 NBA champions Denver Nuggets were ranked Top 3 in, we predicted the 2023-24 NBA regular season standings (the winning percentage of each team) and compared them to the actual results. In addition, we predicted the 2023-24 NBA playoffs (who wins in each matchup) and compared our predictions to the actual results.
## Selection of Data
The dataset was read using data in four formatted tables found on **Basketball Reference**. Each table was read using url's, first read into a different dataframe and later combined into two new dataframes (one for regular seasons statistics and one for the playoffs). The regular season per team statistics tables contained _30 rows (representing the 30 NBA teams) and 25 features (various per game statistics)_. The regular season advanced statistics tables also contained _30 rows but 28 features_.  The playoff per team statistics tables contained _16 rows (16 teams are eligible to make the playoffs) and 25 features_. The playoffs advanced statistics tables contained _16 rows but 28 features_. 

The following measures were undertaken to implement feature engineering:
  1. As the advanced statistics tables contained header columns for certain statistics, the two advanced statistics dataframe table columns were read as a multi-index. To disregard the header         columns, the dataframe columns were updated to only contain the statistics desired.
  2. The advanced statistics dataframes still contained some bogus columns and irrelevant statistics. The following columns and features were dropped: _**Unnamed: 15_level_1, Unnamed:            17_level_1, Unnamed: 20_level_1, Unnamed: 22_level_1, Unnamed: 27_level_1, Arena, Attend., Attend./G', 'PW', 'PL'**_.
  3. The following rows were dropped: the last row (league average) from the regular season per game and advanced statistics dataframes, and the last 5 rows (the 4 play-in tournament teams and league average) from the playoffs per game and advanced statistics dataframes.
  4. The **_Win%_** column was added to the regular season advanced stats dataframe.
  5. In the _**Team**_ column, we removed the asterisks for the teams that made the playoffs.
  6. The column Rk was removed and the column Team was set as the index. Additionally, the regular season advanced statitistics were modified to exclude the columns for opponent _**eFG%, TOV%, ORB%, and FT/FGA**_.
## Methods
## Results
![NBA_demo1](https://github.com/harisj739/CST383_TeamSSS_FinalProject/assets/126642844/ab5b6d5e-7533-49f3-9969-443e921dbdf9)




## Discussion
## Summary
