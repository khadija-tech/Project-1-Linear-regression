# Project-1-Linear-regression
We started by theorical understanding then there is the practical phase:
Overview
Introduction to linear Regression
How it works 
Model evaluation : MAE/MAPE
Multiple Linear regression
Model Diagnostics: p-value, R-squared, Adjusted R-squared, VIF.
Use Cases
This a project of linear regression where we predict life expectancy for WHO organization.
         
         
         The bussiness Problem :
Word Health Organisation wants a data driven approach which could help in suggesting a country which area should be given importance in order to improve the life expectancy of its population.

         Data Science Problem :
Build a prediction model which predicts the life expactancy on various feautures like status of the country, GDP, Alchol consumption, Adult Mortalety Rate etc.

         Libraries used in this Project : 
numpy ,pandas, seaborn sklearn and statsmodels.


# Loading and understanding data :
df = pd.read_csv(r"PATH")
df.info()
df.describe()
def.head()

# Printing numerical and categorical columns:
to discover extra spaces in columns names

# Data Pre-Proccessing :
Remove the extra space from column names using strip function.
Import label_encoder object which converts categorical features to numerical ones. 
Print the sum of nan values we are having in each feature and drop them or treat them by replacing them with mean,median...using fillna fct else we can use Algo that supports Nan values.

# Exploratory Data Analysis (EDA):
Check the distribution of Y variables 'Life expectancy' using Seaborn Box Plot information about outliers medians .... and distribution plot. 

# Summary :
The y variable is having very few outliers and is almost linearly distributed. So the assumption for linear regression holds true

# Let's check the multicollinearity of features by checking the correlation matric
Few of the features are having the linear relationship with y variable. So linear regression would be good approach for the same we choose the pair plot which looks like linear distribution to start our model.


# Model Building:
devide data into train and test set. 30% test 70%train using OLS ordinary least squares (OLS) is a type of linear least squares method for estimating the unknown parameters in a linear regression model

Approach 1 : Adding 1 varaible after 1 RESUME : R-squared and Adj. R squared has increased for the model, but we can still improvise over it so let's add more features UNTIL R-squared of `0.72`

Approach 2 : RFE and eleminating by using p-value and VIF.
After passing the arbitary selected columns by RFE we will manually evaluate each models p-value and VIF value. Unless we find the acceptable range for p-values and VIF we keep dropping the variables one at a time based on below criteria.
          High p-value High VIF : Drop the variable
          High p-value Low VIF : Drop the variable with high p-value first
          Low p-value Low VIF : accept the variable
We repeat the process until finding significantes p-values and VIF < 10.

Approach 3 : Stepwise Regression

# Model Prediction and Evaluation
Evaluvation: MSE - MAPE.
we visualize the results scatterplot and histogramme. 
