# Pyspark_Classification

**Project Description:** A supermarket is offering a new line of organic products. The supermarket's management wants to determine which customers are likely to purchase these products. The supermarket has a customer loyalty program. As an initial buyer incentive plan, the supermarket provided coupons for the organic products to all of the loyalty program participants and collected data that includes whether these customers purchased any of the organic products. The ORGANICS data set contains 13 variables and 22222 observations.

So, for this classification the dependant variable is "Targetbuy" which is binary. With 0 means no buy and 1 means buy.
First step is to loading the data using spark session and spark.csv. 
The ID column is not needed for machine learning. The variable DemCluster is a nominal variable that includes too many categories, so, I removed this variable and also removed the dependent variable "TargetAmt" which is not used. I also changed the datatype of the interval independent variables including 'DemAffl', 'DemAge', and 'PromTime' from interger into double for convenient data processing 
Now, for the step 2 its data exploration. Here, I used describe function to get stats of both independant and dependant variables and identified missing values for both the variables.
Then, for missing values imputation I used imputer from spark MLIB and replaced them with mean for interval variables and unknown for categorical variables.
Then, after EDA I constructed feature vector using vector assembler that transforms all the data into numerical vectors which is very important for the classification.
Next after dividing the data into 80% and 20%, I performed gradient booster tree algorithm classification and made prediction of the 20% tested data. The AUC score is 0.82.
I also did model evaluation using scikit learn and found precison, accuracy and recall.
