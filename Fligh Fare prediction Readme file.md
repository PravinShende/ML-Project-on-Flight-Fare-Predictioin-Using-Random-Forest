
# Flight Fare Predition Model:

Fare prediction done using Random Forest Algorithms.  Hyperparameter tunning also used to find best parameters.


## Problem  Statement:


Problem Statement
Flight ticket prices can be something hard to guess, today we might see a price, check out the price of the same flight tomorrow, it will be a different story. We might have often heard travelers saying that flight ticket prices are so unpredictable. As data scientists, we are gonna prove that given the right data anything can be predicted. Here you will be provided with prices of flight tickets for various airlines between the months of March and June of 2019 and between various cities. Size of training set: 10683 records

Size of test set: 2671 records

FEATURES: Airline: The name of the airline.

Date_of_Journey: The date of the journey

Source: The source from which the service begins.

Destination: The destination where the service ends.

Route: The route taken by the flight to reach the destination.

Dep_Time: The time when the journey starts from the source.

Arrival_Time: Time of arrival at the destination.

Duration: Total duration of the flight.

Total_Stops: Total stops between the source and destination.

Additional_Info: Additional information about the flight

Price: The price of the ticket


## Motivation:

Motivation
What to do when you are at home due to this pandemic situation? I started to learn Machine Learning model to get most out of it. I came to know mathematics behind all supervised models. Finally it is important to work on application (real world application) to actually make a difference.
## Importing Dataset:


Importing dataset
Since data is in form of excel file we have to use pandas read_excel to load the data

After loading it is important to check the complete information of data as it can indication many of the hidden infomation such as null values in a column or a row

Check whether any null values are there or not. if it is present then following can be done,


    Imputing data using Imputation method in sklearn

    Filling NaN values with mean, median and mode using fillna() method

    Describe data --> which can give statistical analysis
## Explanation of Terms Used:

pd.set_option('display.max_columns',None)

         By default , if columns are maximum the it show just first and last some columns .
         To chech the field or attributes in the file we need to see the columns so using this 
         option , we can do it.




EDA(Exploratory data analysis):

From description we can see that Date_of_Journey is a object data type,\ Therefore, we have to convert this datatype into timestamp so as to use this column properly for prediction

For this we require pandas to_datetime to convert object data type to datetime dtype.

**.dt.day method will extract only day of that date**\ **.dt.month method will extract only month of that date**


MAE:Mean Absolute Error

MSE:Mean square error

RMSE:Root mean square error




## Hyperparameter Tuning

Choose following method for hyperparameter tuning

        RandomizedSearchCV --> Fast

        GridSearchCV

Assign hyperparameters in form of dictionery

Fit the model

Check best paramters and best score




### Handling Categorical Data:

One can find many ways to handle categorical data. 

Some of them categorical data are,


**Nominal data** --> data are not in any order --> **OneHotEncoder** is used in this case

**Ordinal data** --> data are in order --> **LabelEncoder** is used in this case



### Feature Selection Finding out the best feature which will contribute and have good relation with target variable. 


**Following are some of the feature selection methods**,

heatmap

feature_importance_

SelectKBest



## Fuction and  Methods Used:



replace()

value_counts()

head()

tail()

concatenate()

OneHotEncoder()

LabelEncoder()

.shape

ExtraTreesRegressor

      helps to find feature importance





## Machine Learning Algorithms Used:


### Fitted model using Random Forest:

Split dataset into train and test set in order to prediction w.r.t X_test

If needed do scaling of data .But Scaling is not done in Random forest

Following steps followed to use Random Forest Algorithm:


    Import model

    Fit the data

    Predict w.r.t X_test

    In regression check RSME Score

    Plot graph