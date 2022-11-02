# advanced_regression

## Problem Statement
A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia. The data is provided in the CSV file below.

 

The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.

 

The company wants to know:

- Which variables are significant in predicting the price of a house, and

- How well those variables describe the price of a house.

 

Also, determine the optimal value of lambda for ridge and lasso regression.

 

### Business Goal 
You are required to model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.

### Technologies Used:
- Python -3.10.4
- Jupyter Notebook - 1.0.0
- Pandas - v0.23.4
- Numpy - v1.5.1
- Matplotlib - v2.2.3
- Seaborn - v0.9.0
- Sklearn - v0.19.2

### Conclusion
Plain Liner Regression seem to overfit on training dataset and perform poorly on the test dataset.
- Best value for alpha for Ridge Regression seem to be aroung 5:
  - r2_score on training dataset = 0.8885698121048389
  - r2_score on test dataset = 0.8691214605588805
- Best value for alpha for lasso Regression seem to be around 0.0001:
  - r2_score on training dataset = 0.9000951480492267
  - r2_score on test dataset = 0.8681335620224924
- As expected, usage of Lasso regularization causes some of the variable coefficients to drop to 0 effectively removing them from model.
Ridge regression seem to be overall better model as it has slightly better r2 score,RSS and MSE than lasso on test set. However, it should be noted that Lasso seems to perform almost as well and is a much simpler model as it has less number of features and can result in significant savings in production. Therefore the choice of model is heavily dependent on the business usecase and accuracy tolerance.

Top 5 important variables according to Ridge Regularized model that affect Sale Price:
|           |
|-----------|
| GrLivArea |
| OverallQual |          
| 2ndFlrSF |             
| GarageCars |           
| Neighborhood_NoRidge |

Top 5 important variables according to Lasso Regularized model that affect Sale Price:
|           |
|-----------|
| GrLivArea |
| OverallQual |
| LotArea |
| RoofMatl_WdShngl |
| GarageCars |
