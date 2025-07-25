# Diamond-Dataset
# Description

The dataset for this assignment contains the prices and other attributes of 50,000 diamonds.

Your task is to perform an Exploratory Data Analysis on the dataset. 

Submit an R Markdown report summarising your findings together with the source code.

# Dataset

First download the dataset. As the dataset contains 50K records, generating the plots may take a few moments.

One way is to start with a small sample and carry out analysis, for example, you can pick 10,000 observations (without replacement) using the function: sample.

Run the following code to do so:

    s <- sample(nrow(diamonds.dataset), size=10000, replace = FALSE, prob = NULL)

    diamonds.subset <- diamonds.dataset[s, ]

The above piece of code creates a new dataset named: diamonds.subset containing 10,000 observations from diamond dataset.

You can use the sampled dataset (diamonds.subset) first to write and test your code.

And then use the full dataset for completing the task given below. 


Variables in dataset are:
    price - in US dollars ($326 to $18,823)
    carat - weight of the diamond (0.2 to 5.01)
    cut - quality of the cut (Fair, Good, Very Good, Premium, Ideal)
    color - diamond colour, from J (worst) to D (best)
    clarity - a measurement of how clear the diamond is (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best))
    depth - total depth percentage = z / mean(x, y) = 2 * z / (x + y) *table - width of top of diamond relative to widest point (43 to 95)
    x - length in mm (0 to 10.74)
    y - width in mm (0 to 58.9)
    z - depth in mm (0 to 31.8)


As we see, just looking at price and carat relationships in the model and putting line through middle wouldn’t do much good. So I would offer other option. As we know, linear regression is like relationships between two variables, one (or more) that is independent (x) and one that’s dependent (y), so, if the x value changes, the y value changes with it. This model is meant to hepl predicting next values from those, that are given, so to say, it gives as the mean value of all of those we have, give or take some errors in it (it might seem confusing, but you need to square those) and You can find some regularities and useful precedents.
For now I will stop with almost theory from my side, and show these words in action. In model below You can see the same relationship - carat and price, but the difference we added lines that shows every values connection to cut. From this we get even better information, because we can see mean values for each cut, that still is linked to price and carat range. Even though the errors are still there, the comprehension of this dataset is obviously deeper.

        carat	cut	       color	clarity	    depth	table	price	x	    y	    z
        0.23	Ideal	    E	    SI2	        61.5	55	    326	    3.95	3.98	2.43
        0.21	Premium	    E	    SI1	        59.8	61	    326	    3.89	3.84	2.31

### REMEMBER! You must report your findings on the full dataset.    

In your final report, there is no need to include your findings on the sampled dataset.

When you load the dataset, you will find the following variables in the dataset:

    carat:	weight of diamond (0.2 to 5.01)

    cut:	quality of the Cut (Fair, Ideal, Good, Very Good, Premium)

    color:	diamond color from D (Best) to J (Worst)

    clarity: a measurement of how clear the diamond is from I1 (Worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (Best) table: width of top of the diamond

    x:length in mm

    y:width in mm

    z:depth in mm

    depth:	total depth percentage = 2*z/(x+y)

    price:	price in US dollars

# Task

Your task is to perform EDA and calculate the strength of relationships between the variables of the dataset.

## Consider below as a guideline:

1.Your first task is to clean the dataset and prepare it for analysis by e.g. removing/replacing NAs and incorrect values.

2.Begin your analysis with a summary of the variables (use basic statistical methods). Briefly describe your understanding.

    Prepare 4 plots: bar chart, histogram, scatter plot. 

    Each plot should display different variables (do not use price variable now). 

    Each plot must have a title and meaningful labels.
 
3.Focus your analysis on the price variable: 

    (a)Show the histogram of the price variable. Describe it briefly. Include summary statistics like mean, median, and variance.

    (b)Group diamonds by some price ranges (like low, medium, high, etc.) and summarise those groups separately.

    (c)Explore prices for di€erent cut types. You might want to use the boxplot.

    (d)How different attributes are correlated with the price? Which 3 variables are correlated the most with price?


4.Now focus your analysis on the carat, depth, table and dimensions (x, y , z) variables:

    (a)Compute a volume variable from x, y, z - add it to the dataset. Plot it against the price. Describe your findings.

    (b)Are the carat and volume attributes correlated? Is that a strong relationship? Draw a plot with regression line.

    (c)Explore the relationships between table and depth variables.

    (d)Now explore relationships between table and rest of other variables. Compute correlations and describe your findings.

# Insights

1.	First we have to import the functions
2.	Load the data set 
3.	After problem statements like data info and data describes and go with that null values and zero values
4.	After using isnull function We have to plot the graph of that normal distribution that is histplot.
5.	If there is any zero value is in that the columns we have to replace with the mean value because it is in the normal distribution
6.	Plot the graph according to that eda analysis
7.	In the data preprocessing we have to go with the Encoding especially go with the order encoding because of that it is in ordinal encoding it is in the hierarchy. Ordinal encoding for cut, colour, clarity
8.	After completed that encoding we have to go with the help plot that the graph of that normal distribution if there is any skewed or high kurtosis we have to substitute and we have to reduce that skewness
9.	use the power transform to handling skewness and kurtosis
10.	After that we have to plot the graph of that normal distribution
11.	Using power transformer if any value is doesn’t change we have to remain same If there is any high value we have to skip that one
12.	In that dataset in y column there is outlier so we have to use winsorize technique applying limit 1% for both ends to reduce outlier
13.	In this process I used two seperate outlier technique for to reduce outliers
    1.	Winsorization
14.	After removed the categorical columns like cut, color,clarity and separate that values because for training and scaling.
15.	Train the model using train_test_split
16.	Load the linear regression model
17.	Find r2_score, mean_squared_error, mean_absolute_error,adj_r2
18.	If we need to increase the percentage of adj_r2 and r2_score use Random forest regressor 


