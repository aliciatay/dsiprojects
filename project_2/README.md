# Project 2 - Ames Housing Data and Kaggle Challenge

## Background

We are a team of property consultants engaged by the District Council of Iowa to help valuate the residents' properties.

As part of our analysis, the objective of this study is to provide:

* An accurate and recognised value of a property
* Strategies on possible improvements to homeowners on how to maximise the value of their property

## Business Problem

* Build a model to predict prices for house listings in Ames, Iowa USA, based on features such as size, features, and location
* Identify 30 most influential features, with the goal of identifying strategies for potential home sellers to maximize profit

## Data, Methods & Models

* Data: Ames housing prices between 2006-2010
    - Train dataset has 2051 properties and Test dataset has 879 properties
    - Train dataset has 81 features with the target variable "Sale Price"
    - Test dataset has 80 features, without the target variable
    - Data Dictionary can be found via this [link](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)
* Model: Linear Lasso Regression Model has been chosen to predict prices due to its easy interpretability, lowest RMSE score, and highest Adjusted R2 score.
* Methods:
    - Data cleaned and preprocessed for OHE, Ordinal mapping. Features with high multi-collinearity have been removed as well.
    - Feature Elimination: 
        1. First, we dropped variables that had high null values during EDA, alongside a few variables that were found to have high multi-collinearity.
        2. Next, we ran the remaining variables to a Lasso model to remove zero-ed out features
        3. Lastly, the final 30 variables were chosen by top absolute value from a Ridge model
    - Feature Engineering: New variables such as Season, TotalSF have been generated
    - Polynomial Features: Interaction elements created to help with the accuracy of model
    
## Assumptions 

1. Features are independent of each other, follows a Gaussian distribution, and has a linear relationship with Saleprice.
2. Features with more than 80% null values are not considered significant to this study as we have sufficient data points

## Findings
1. About the model
    * Models improved by 8% when a singular polynomial feature is added
    * Linear Regression and Lasso Regression Models are the best performing models, with Lasso Regression inching slightly ahead due to its lower RMSE score.
2. Improvements that homeowners can take:
    * The more the better!
        - Doing up a renovation to include more features such as a porch, masonry and garage may be a well-paid off investment that can help offset costs and multiply in folds.  
        - Maximise space by converting any unused space into another bedroom/bathroom. More rooms also increases home price favourably.
    * What are you made of? Substance is key to the pot of Gold
        - Overall quality of the material and finishing is very important to prospective buyers
        - Particular features such as Brick Face on the house exterior, along with a roof material of Wood Shingles appears to have a positive effect of pushing the sale price up.
    * Not all is created equal
        - Neighborhoods Northridge Heights,Stone Brook,Northridge, Crawford seems to be premium attractive areas that have big impact on the sale price. 
        - For homeowners in this area, market your property with emphasis on the neighborhood it is located in.
        
## Future Improvements
1. More could be done to improve the model's accuracy, such as:
    * Being more sensitive to outliers rather than removing them, and experimenting with more polynomial features. This might include the need of experimenting further beyond linear regression models, such as Neural Networks
    * More features could be added to the model so that there are more predictors that the model can learn from to predict the nuances in price changes
    * Skewed variables could be treated with a log transformation, especially on the dependent variable
    * However, one of the great advantages of linear regression models relative to more complex machine-learning techniques is its interpretability. 
    
2. Dataset
    * Our dataset was collected between 2006-2010. The subprime mortgage crisis happened during the period 2007 - 2010. This could have influenced that data, and might not be accurate for a 2020 time frame
    * Understanding the difference between the listed and sale price, along with the negotiations and discussions between homeowners and agents could help us understand more on the factors that influences price

## Kaggle Score
I achieved a score of 25098.835 on Kaggle
