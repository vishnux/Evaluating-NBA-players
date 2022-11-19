# Evaluating NBA Players Using Physical, and Statistical Characteristics

Utilized National Basketball Association (NBA) player's statistics based on physical and statistical characteristics to answer three guiding questions:

1) Using classification models (Logistic Regression, Classification Trees, Random Forest, Gradient Boosted Trees) can we apply NBA players' weights and heights to classify players based on positions?

2) Using classification models (Logistic Regression, Classification Trees, Random Forest, Gradient Boosted Trees) can we apply NBA players' in-game statistics to classify players based on positions?

3) Using PCA and K Means clustering can we find similar groups of players for each position and discover the most productive players and seasons by position?

The five positions that exist in the NBA are Point Guard (PG), Shooting Guard (SG), Small Forward (SG), Power Forward (PF), and Center (C). We will take advantage of both the statistical outputs of these players and their physical characteristics to classify players by position. Furthermore, we will then implement dimensionality reduction and k-means clustering for each position. This will help us find the players with similar play styles within the positions and the outstanding players that are the best or most productive at those positions.

# What was our motivation?

In 2019, NBA teams spent over 3 billion dollars of guaranteed salaries to players in the first three days of free agency. These expensive contracts often locked a player into the team over multiple years. While the athlete is receiving significant monetary gain, the team is attempting to collect the pieces it believes are necessary to contend for an NBA championship. These expensive salaries come with significant risks to the organization. To mitigate the associated dangers with paying an individual so much money it is essential to gain deeper insights into basketball positions, players, and how certain statistics and physical attributes contribute to these factors. Who are the best players in the league? Is there a lot of overlap with positions to the point that NBA positions are interchangeable? These are some of the questions that motivated this project. This deeper context and understanding can illuminate the ways that coaches and organizations can fill the positions and roles that their roster is currently lacking.

# Methodology

To take advantage of the interactive and 3D graphs that will be presented in this report, our writings and code will be detailed inside a Google Colab notebook. This will also allow for seamless transitions between technical coding explanations and the more abstract graphical interpretations. Further, this section will give a brief overview of the steps that will be taken to achieve our goal in this paper.

First and foremost, the dataset and its source will be acknowledged. Then, the various wrangling and cleaning procedures that occurred will be detailed. This includes downloading, merging, and altering the datasets. Once the data has been treated and organized, we review and discuss exploratory analysis to increase our knowledge and illustrate the significant details of the five positions in the NBA. Some other minor data cleaning may occur where needed.

After familiarising ourselves with the dataset we will apply a correlation matrix to the data frame's columns and remove values that exhibit multicollinearity. This will eliminate some of the extraneous categories from our rather large number of features.

Following these essential introductory tasks, six classification models will be tested to classify player positions based on height and weight:

* Logistic Regression Analysis
* Polynomial Regression Analysis
* Support Vector Classification
* Decision Tree
* Random Forest Classification
* K Nearest Neighbour Classification

The reason so many different classification methods are being used is that we are unsure which method will be the most appropriate for our data. Consequently, we will compare and contrast the best methods and results.

Once this process is complete, we will complete a similar process to classify players' positions based on in-game statistical categories:

* Logistic Regression Analysis
* Polynomial Regression Analysis
* Support Vector Classification
* Decision Tree
* Random Forest Classification
* K Nearest Neighbour Classification

The reason that we completed separate classification techniques for the in-game statistics is that we view whether or not physical attributes are accurate at classifying players by position as a separate analysis. Doing these processes separately will increase our understanding of the impacts of physical attributes and individual skills on deciding positions in the NBA substantially.

Once our classification analysis is complete, we will attempt to answer the last question of our project, which is to find groups of similar players and the best individual season within each position. After separating our data into five separate data frames (one for each position), the final two data science techniques we will employ in our paper to reach this goal are:

* Principal Component Dimensionality Reduction
* K-Means Clustering

# Data Source

We found the original data for our project from Basketball Reference (www.basketball-reference.com) which records the in-game performance and statistics of basketball players in the NBA during games. The second set of datasets we will be using comes from the NBA’s official website which records the players heights and weights for every NBA season.
