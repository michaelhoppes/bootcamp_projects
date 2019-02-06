
Objective: After completing an engagement with the Collegeboard, Hoppes LLC was approached by Zillow to build the most accurate prediction possible for home values in Ames, Iowa.


Data:

Our model comes from data compiled by Dean Decock on attributes related to houses in Ames, Iowa. This was originally collected as an alternative to the Boston Housing prices dataset. More background on the dataset can be found here.

http://jse.amstat.org/v19n3/decock.pdf


A more detailed data dictionary can be found here:

https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/data


Methodology:

Data Cleaning and Transformation

There were numerous different types of attributes that needed to be cleaned in different ways to allow the model to more easily see the correlation between the explanaotory variables and the target variabe. One is the date data, where there were 4 variables entered as integers. Instead of making these dummy variables, I subtracted the date of data collection, 2010, by each of the date variables to obtain continuous measures of time that would describe the houses like the age of the home. 

Another type of data that I needed to handle were the ordinal measures. There were a number of quality measures that were ordered starting from low to high quality that could be converted to numeric integers to maintain the ordinal quality of the feature. For those ordinal features that had N/A's however, we dummied out those variables, as there were cases where the house truly didn't have a particular object (like a garage). 

For categorical measures that weren't ordered, we dummied those variables to convert from string objects to numeric objects. 

The final piece of data cleaning we performed was on the null data, as there were 27 variables with null values. For these we either input the null values with a string N/A, a 0, or an aggregate measure like the mean depending on what the scenario called for.


Exploratory Data Analysis

Due to a significant skew in the outcome variable house prices, it became clear that the taking the log of the outcome variable would normalize the distribution and increase the robustness of the model to outliers. Additionally, after testing the model with and without interactor terms the results showed that including the interactor terms of the continuous variables in the dataset would greatly increase the predictive power of our model. Finally, because optimization of the full dataset was of paramount importance, I normalized the features and conducted a Lasso CV, optimizing the model after iterating through 200 possible alpha hyperparameters. In short, the EDA approach in this notebook was not active in the research team selecting variables, but rather used best practices in feature engineering to not delete data, and use all of the possible information at our disposal to let the model determine the best fit. 


Conclusion

R^2 score range ON MY FINAL MODEL . 93
Alpha = .0066
23,363 RMSE 

After testing on the withheld test set, the model performed relatively well on our two held out test sets, with a 23,663 RMSE on our smaller test set and a 28,332 on our larger test set. This means that our estimates typically are within $23-$28K of their actual value at sale. This is useful, as the baseline estimate by taking the mean is around $58K. Therefore, while our prediction can still be a signiifcant amount off of the reality of the sold price, we can still be confident that it is creating value for the consumer over the status quo of just estimating based on the average. 

Next Steps

New Models
Take some of our test set and train on more of it
Outside Data
Actively seeking to create new features not included in our interactor variables.


