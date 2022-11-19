**Evaluating NBA Players Using Physical, and Statistical Characteristics**

Utilised National Basketball Association (NBA) players statistics based on physical and statistical characteristics to answer three guiding questions:

1)Using classification models (Logistic Regression, Classification Trees, Random Forest, Gradient Boosted Trees) can we apply NBA players weights and heights to classify players based on positions?

2)Using classification models (Logistic Regression, Classification Trees, Random Forest, Gradient Boosted Trees) can we apply NBA players in-game statistics to classify players based on positions?

3)Using PCA and K Means clustering can we find similar groups of players for each position and discover the most productive players and seasons by position?

The five positions that exist in the NBA are Point Guard (PG), Shooting Guard (SG), Small Forward (SG), Power Forward (PF) and Center (C). We will take advantage of both the statistical outputs of these players and their physical characteristics to classify players by position. Furthermore, we will then implement dimensionality reduction and k-means clustering for each position. This will help us find the players with similar play styles within the positions, and the outstanding players that are the best or most productive at those positions.

**What was our motivation?**
In 2019 NBA teams spent over 3 billion dollars of guaranteed salary to players in the first three days of free-agency. These expensive contracts often locked a player into the team over multiple years. While the athlete is receiving significant monetary gain, the team is attempting to collect the pieces it believes are necessary to contend for an NBA championship. These expensive salaries come with significant risk to the organisation. In order to mitigate the associated dangers with paying an individual so much money it is essential to gain deeper insights into basketball positions, players, and how certain statistics and physical attributes contribute to these factors. Who are the best players in the league? Is there a lot of overlap with positions to the point that NBA positions are interchangeable? These are some of the questions that motivated this project. This deeper context and understanding can illuminate the ways that coaches and organisations can fill the positions and roles that their roster is currently lacking.

**Methodology**
In order to take advantage of the interactive and 3D graphs that will be presented in this report, our writings and code will be detailed inside of a google colab notebook. This will also allow for seamless transitions between technical coding explanations and the more abstract graphical interpretations. Further, this section will give a brief overview of the steps that will be taken to achieve our goal in this paper.

First and foremost, the dataset and its source will be acknowledged. Then, the various wrangling and cleaning procedures that occurred will be detailed. This includes downloading, merging and altering the datasets. Once the data has been treated and organised, we review and discuss exploratory analysis to increase our knowledge and illustrate the significant details of the five positions in the NBA. Some other minor data cleaning may occur where needed.

After familiarising ourselves with the dataset we will apply a correlation matrix to the dataframe’s columns and remove values that exhibit multicollinearity. This will eliminate some of the extraneous categories from our rather large number of features.

Following these essential introductory tasks, six classification models will be tested to classify player positions based on height and weight:

* Logistic Regression Analysis
* Polynomial Regression Analysis
* Support Vector Classification
* Decision Tree
* Random Forest Classification
* K Nearest Neighbour Classification

The reason so many different classification methods are being used is that we are unsure which method will be the most appropriate for our data. Consequently, we will compare and contrast the best methods and results.

Once this process is complete, we will complete a similar process to classify players positions based on in-game statistical categories:

Logistic Regression Analysis
Polynomial Regression Analysis
Support Vector Classification
Decision Tree
Random Forest Classification
K Nearest Neighbour Classification
The reason that we completed separate classification techniques for the in-game statistics is because we view whether or not physical attributes are accurate at classifying players by position as a totally separate analysis. Doing these processes separately will increase our understanding of the impacts of physical attributes and individual skills on deciding positions in the NBA substantially.

Once our classification analysis is complete, we will attempt to answer the last question of our project, which is to find groups of similar players and the best individual season within each position. After separating our data into five separate dataframes (one for each position), the final two data science techniques we will employ in our paper to reach this goal are:

Principal Component Dimensionality Reduction
K-Means Clustering
Data Source
We found the original data for our project from Basketball Reference (www.basketball-reference.com) which records the in-game performance and statistics of basketball players in the NBA during games. The second set of datasets we will be using comes from the NBA’s official website which records the players heights and weights for every NBA season.

Datasets
For our project there were no individual datasets available that met the requirements for our project. However, there were a series of individual datasets that could be combined and transformed to be sufficient. We desired a dataset containing individual NBA player statistics over a ten year span. Some of the major statistics necessary for this research were (but not limited to) points per game, assists per game, rebounds per game and various other figures regarding scoring efficiency such as true-shooting percentage. Finally, there needed to be basic physical attributes available for each player such as height and weight.

The first dataset we discovered came from Basketball Reference and listed every player's position and their stats for an individual season in the forms of totals. For example, instead of points per game, it had ‘total points’ accumulated over the season. Overall, each of these individual datasets contained anywhere from 300-500 rows (depending on how many players played that season) along with 31 columns. In excel we added a year column to indicate which season the dataset represented. Once this initial process was completed, we individually downloaded each of these datasets from the years 2010 to 2019 (which is 10 seasons) and uploaded them into google colab.

One of the initial issues we discovered was that within the same season there existed duplicate players, because some players were traded midseason. To simplify our data we sorted each dataset by ‘games played’ and removed duplicates of the same player. In the arguments of the drop duplicates function we indicated to keep the first of the duplicate pair that showed up, which coupled with our sorting guaranteed we kept the row that the traded individual played the most.

Next, we merged the 10 datasets into one large dataframe with around 5000 rows and 31 columns. However, this data still lacked a lot of our required information as it lacked per game numbers and physical characteristic information. To solve the first issue, we simply divided each relevant statistic by total games and stored it in a newly created column. For example, total points was divided by total games in a new column labelled ‘PTS/G’.

The second issue was a lot more complicated and required the introduction of a second group of datasets. We discovered on the NBA’s official website a list of ‘player bios’ where (among other information) the weights and heights of players were included for each season. Similar to the original dataset we individually downloaded the seasons from 2009 to 2019, added year columns and then merged these into a single dataframe. Finally, once all of this data collection and preparation was complete a left join based on the ‘Player’ column was conducted to only add data where players names are already available to our original dataframe. Our final dataframe contains 4006 rows and 49 columns.
