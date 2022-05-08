# Prediction-of-Boston-house-prices-
Disclaimer: - Given solution in this project is only use for study purpose.

	In this project I used Applied machine learning concept of Multiple Linear Regression. This project is having dataset of Boston house prices and different parameters, on the basis of those features one need to predict the future price of hoses in that area.
	This data set is downloaded from Kaggle dataset repository, this dataset is having 506 rows, and 14 feature columns, those are 
1.	CRIM - per capita crime rate by town
2.	ZN - proportion of residential land zoned for lots over 25,000 sq.ft.
3.	INDUS - proportion of non-retail business acres per town.
4.	CHAS - Charles River dummy variable (1 if tract bounds river; 0 otherwise)
5.	NOX - nitric oxides concentration (parts per 10 million)
6.	RM - average number of rooms per dwelling
7.	AGE - proportion of owner-occupied units built prior to 1940
8.	DIS - weighted distances to five Boston employment centres
9.	RAD - index of accessibility to radial highways
10.	TAX - full-value property-tax rate per dollar 10,000
11.	PTRATIO - pupil-teacher ratio by town
12.	B - 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
13.	LSTAT - Percentage lower status of the population
14.	MEDV - Median value of owner-occupied homes in dollar 1000's
So, first I explore the data checked any missing values are there are not. Then plot the distribution of output variable which looks normal with some outliers.
# Univariate analysis
	In this I have plot the distribution and boxplot of all the independent variables.
# Bivariate Analysis
	In bivariate analysis I plot scatter plot of all independent variables with the output variable. From scatter plot it looks like lstat and rm have some linearity with output variable. Then plot correlation heatmap, from correlation lstat having negative and rm is having positive correlation with the output variable.
# Model Building
-	Model 1 : OLS with all features 
I split the data into 80% in train and 20% in test. And run the OLS model on train dataset got the 73% accuracy. But from the model we can see that by looking at p value there is no relationship between ‘crim’, ‘indus’ and ‘age’ with output variable.

-	Model 2 : We drop those columns who does not have relationship with output variable and run the model again. There is no change in R – squared value. 

-	Model 3 : Then we run model with features who is having linearity with dependent variable ie. OLS with lstat. From this model lstat alone is giving ony 54% accuracy on train dataset.
-	Model 4 : After that we add rm to that feature, we run model with rm and lstat we got approx. 63% accuracy. 
-	Model 5 : In this model to increase the accuracy of the model we use polynomial feature with lstat only with degree of 2 and got accuracy 64%
-	Model 6 : Now I use lstat and rm as independent variable with polynomial feature of degree 2 and I got 75% accuracy on train data and 76% on test data which is very good.  

Then I did error analysis on on model 6 plot the error distribution plot, from this observation I came to know that there are few outliers which increases error. Then replaced one outlier which is at right side having rm ~8.8 and medv ~23 from scatter plot of rm & medv with median value of rm

-	Model 7 : Now ran the model and got accuracy approx. 78% 

    Plot the Error distribution plot


# Conclusion : Using polynomial feature I achieve 77.8% accuracy.

