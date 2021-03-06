# wine_reviews
By JP Rinfret and Garrett Keyes

## Overview:
Wine is one of the most widely consumed types of alcohol in the world. And many wine drinkers would even consider it the most prestigous. A wine's rating is a major determinant of whether or not a specific bottle/vintage is considered high quality. Wine is rated on a scale from 80 to 100 based on taster reviews by organizations including Wine Spectator, wine.com, vivino, and Wine Enthusiast. But the rating given to each wine may not always be what it should. Using multi-linear regression we seek to predict the rating a wine should receive based on grape variety, province, vintage year, price, and an aggregation of critic reviews. 

[Executive Overview](https://docs.google.com/presentation/d/16AflvwtjYgCDZ4M5CGoQz2o1lbqeyB5Cm6XoSGZy34k/edit?usp=sharing)

## Data:
The data used for this project comes from a Kaggle wine reviews data set composed of 130,000 reviews gathered in 2017.

Please find the raw dataset here: https://www.kaggle.com/zynicide/wine-reviews

## Transformtions and Feature Engineering:
We observed that our data was not noramlly distributed or effeciently homoscedastic after completing the cleaning process and creating dummy variables for our categorical data. And this resulted in the r<sup>2</sup> value being higher than it should have been.

QQ Plot             |  Homoscedasticity    | OLS Regression Results
:-------------------------:|:-------------------------:|:-------------------------:
![alt test](graphs/pre_log_normality.png)  |  ![alt_text](graphs/pre_log_homoscedasticity.png)   | ![alt test](graphs/pre_log_ols.png)

Specifically our price data was not normally distrubted and needed to be transformed into a normal distribution by taking the log() of the column. 
 
 Before Log Transformation             |  After Log Transformation
:-------------------------:|:-------------------------:
![alt test](graphs/pre_log_price.png)  |  ![alt_text](graphs/post_log_price.png)

Transforming price resulted in our data bcoming more normally distributed, having greater homoscedacity, and have a lower r<sup>2</sup> value. 

QQ Plot             |  Homoscedasticity    | OLS Regression Results
:-------------------------:|:-------------------------:|:-------------------------:
![alt test](graphs/post_log_normality.png)  |  ![alt_text](graphs/post_log_homoscedasticity.png)   | ![alt test](graphs/post_log_ols.png)

### Observing Correlations 
Province             |  Grape   
:-------------------------:|:-------------------------:
![alt test](graphs/provinces_heatmap.png) | ![alt test](graphs/grapes_heatmap.png)

Taster             |  Vintage   
:-------------------------:|:-------------------------:
![alt test](graphs/taster_heatmap.png) | ![alt test](graphs/vintages_heatmap.png)

![alt test](graphs/all_data_heatmap.png)

## Testing and Scaling Model:

Separating our data into the training and testing data we used a train test split of 70% - 30% to allow for an acceptable amount of test data without losing too much of the data used to train our model. We also chose to use the StandardScaler to scale the data as opposed to a MinMax scaler because the MinMax scaler can drop some values on both the extremes of the dataset.

![alt test](graphs/train_test_split.png)

Ridge regression produces the lowest Root Mean Square Error(RMSE) of each model. As RMSE is the square root of the variance of the residuals, it is used to show the absolute fit of a model and how close the observed data is to the predicted values. Since the Ridge regression model has the lowest RMSE value it indicates thats the best model for our regression as the observed data is closest to the predictions. 

![alt test](graphs/ridge_lasso_regression.png)

Conducting a KFold test for cross-validation shows, however, the model may not be as reliable as it appears. 
![alt test](graphs/ridge_fold.png)

## Example Predication:
Let's consider a $150 2009 Cabernet Sauvignon from Bordeaux, France bottled in 2009. Our model would predict that Wine Enthusiast rating would be:  
![alt test](graphs/example.png)

## Libraries Used:
**Statsmodels** for OLS formula and QQ plot<br /> 
**Pandas** for dataframes and generating dummy variables<br /> 
**Numpy** for logarithmic transformation<br /> 
**scipy.stats** for statistical operations<br /> 
**sklearn.linear_model** for generating linear, Ridge, and Lasso Models<br /> 
**sklearn.model_selection** for creating train test split and KFold Cross Validation<br /> 
**sklearn.preprocessing** for scaling using StandardScaler<br /> 
**nbimporter** for importing from seperate jupyter notebooks<br /> 
**seaborn** for heatmap visualization<br /> 
**Matplotlib** for data visualization<br /> 
