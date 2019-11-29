# wine_reviews
By JP Rinfret and Garrett Keyes

## Overview:
Wine is one of the most widely consumed types of alcohol in the world. And many wine drinkers would even consider it the most prestigous. A major determinant in whether a wine a of high quality or not is what its associated rating is. Wine is rated on an 80-100 scale based on taster reviews by organizations including Wine Spectator, wine.com, vivino, and Wine Enthusiast. But the rating given to each wine may not always be what it should. Using multi-linear regression we seek to predict the rating a wine should receive based on grape , province, vintage year, price, and an aggregation of critic reviews. 

## Data:
The data used for this project comes from a Kaggle wine reviews data set composed of 130,000 reviews gathered in 2017.

Please find the raw dataset here: https://www.kaggle.com/zynicide/wine-reviews

## Exploratory Data Analysis:


## Transformtions and Feature Engineering:
We observed that our data was not noramlly distributed or effeciently homoscedastic after completing the cleaning process and creating dummy variables for our categorical data. 


QQ Plot             |  Homoscedasticity
:------------------------:|:----------------------------:
![alt test](/pre_log_normality.png)  |  ![alt_text](/pre_log_homoscedasticity.png)

Upon realizing ourobserving this  After cleaning our data and checking for homoscedacity, normality, multicolinearity 

## Testing Models:
After 
## Outcomes:

## Libraries Used:
**Statsmodels** for OLS formula and QQ plot
**Pandas** for dataframes and generating dummy variables
**Numpy** for logarithmic transformation
**scipy.stats** for statistical operations
**sklearn.linear_model** for generating linear, Ridge, and Lasso Models
**sklearn.model_selection** for creating train test split 
**sklearn.preprocessing** for scaling using StandardScaler
**nbimporter** for importing from seperate jupyter notebooks 
**seaborn** for heatmap visualization
**Matplotlib** for data visualization 
