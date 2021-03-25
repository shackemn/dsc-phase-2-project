# Regression Analysis for King County Housing Market

Author: Micah Shackelford



## Business Case

A real estate firm is looking to adopt a more data driven approach to analyze their properties. They are looking to improve their methods in which to choose which properties to aquire and how to price houses. 

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this repo. It includes over 20,000 different sales listings. It includes the price of these houses along with various different features whch are listed below.  

id - unique identified for a house
Date - house was sold
Price -  is prediction target
bedroomsNumber -  of Bedrooms/House
bathroomsNumber -  of bathrooms/bedrooms
sqft_living -  footage of the home
sqft_lot -  footage of the lot
floorsTotal -  floors (levels) in house
waterfront - House which has a view to a waterfront*view** - Has been viewed
condition - How good the condition is ( Overall )*grade** - overall grade given to the housing unit, based on King County grading system  sqft_above - square footage of house apart from basement
sqft_basement - square footage of the basement
yr_built- Built Year
yr_renovated - Year when house was renovated
zipcode - zip
lat - Latitude coordinate
long - Longitude coordinate
sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors




### Data Cleaning

Filled is missing values for waterfront, view, and yr_renovated

sqft_basement was originally an object data type since it included values of "?". We used the difference of sqft_living and sqft_above
to replace these values. Most were simply meant to be 0, but we did gather some data on basements we otherwise would not have. 

### Exploration
Taking a closer look at the data, We classified our features into continuous and categorical features. Then we looked at visualizations
to explore their linear relationship to price. We also looked at multicolinearity and removed  few features which would cause problems with our model.

Something noteworthy found was the mean sales price of waterfront homes was over three times greater than the average mean price of other homes. This can be observed in the visualization below.

![Price by Location.png](https://github.com/shackemn/dsc-phase-2-project/blob/main/Price%20by%20Location.png)






### Feature Engineering

Categorical: We seprated our categorical features into dummy variables, dropping the first of each.
Continuous: We log transformed some of our features to create a more normal ditribution. 

## Model

We separated our data into train and test at 75%. 

Our original model had an R-Squared value of 0.727, but it had a lof of features with P Values past the threshold of .05

We removed these problem features and ran the model again. This gave us an R-Squared of 0.678
Train RMSE = 207649.69
Test RMSE = 214703.66

## Next Steps

Improve our model with more up-to-date data.
We had very little data on renovations. Explore how these renoavations affect our price. 

