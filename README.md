# Project 2: Prediction of House Prices

## Problem Statement

Zillow is trying to get the best estimates of house prices across the United States to gain an advantage in today's competitive real estate market.

This proposal analyzes and models the Ames, Iowa housing data from 2006-2010, to get 'Zestimates' of the current house prices in Ames and obtain the most important features that influence the price, and provides recommendations to buyers on what factors to consider in order to get the best return on investment.

## Contents:

1. Data Cleaning
2. Exploratory Data Analysis
3. Feature Extraction/Analysis
4. Modeling
5. Conclusions
6. Recommendations
7. Next Steps

## Models Summary

| Model                      	| Linear Regression-1                                                       	| Linear Regression-2                                                      	| Linear Regression-3                                                                                                              	| Linear Regression-4                                                                                                                              	|
|----------------------------	|---------------------------------------------------------------------------	|--------------------------------------------------------------------------	|----------------------------------------------------------------------------------------------------------------------------------	|--------------------------------------------------------------------------------------------------------------------------------------------------	|
| Description                	| Basic Features                                                            	| Log-transform of Sale Price                                              	| Polynomial Regression                                                                                                            	| Polynomial Regression                                                                                                                            	|
| Feature-selection Method   	| Correlation Matrix                                                        	| Correlation Matrix                                                       	| Correlation Matrix                                                                                                               	| OLS Hypothesis Testing                                                                                                                           	|
| Feature-selection Criteria 	| Corr. Coeff > 0.5                                                         	| Corr. Coeff > 0.                                                         	| Corr. Coeff > 0.75                                                                                                               	| p_value < 0.04                                                                                                                                   	|
| Cross Validation Score     	| 0.860                                                                     	| 0.874                                                                    	| 0.868                                                                                                                            	| 0.872                                                                                                                                            	|
| Training R2 Score          	| 0.866                                                                     	| 0.877                                                                    	| 0.878                                                                                                                            	| 0.861                                                                                                                                            	|
| Testing R2 Score           	| 0.830                                                                     	| 0.828                                                                    	| 0.839                                                                                                                            	| 0.893                                                                                                                                            	|
| Mean Absolute Error        	| 21793.57                                                                  	| 17937.42                                                                 	| 18629.20                                                                                                                         	| 16560.80                                                                                                                                         	|
| Mean Squared Error         	| 902461306.37                                                              	| 649409460.87                                                             	| 721673753.42                                                                                                                     	| 524826604.87                                                                                                                                     	|
| Root Mean Squared Error    	| 30040.99                                                                  	| 25483.51                                                                 	| 26863.97                                                                                                                         	| 22909.09                                                                                                                                         	|
| Most important features    	| Overall qual<br>Ext qual<br>Gr liv area<br>Kitchen qual<br>Total bsmt SF  	| Overall qual<br>Ext qual<br>Gr liv area<br>Kitchen qual<br>Total bsmt SF 	| overall_qual gr_liv_area<br>overall_qual year_built<br>overall_qual garage_yr_blt<br>overall_qual year_remod/add<br>overall_qual 	| overall_qual garage_area<br>overall_qual garage_cars<br>overall_qual garage_yr_blt<br>1st_flr_sf garage_type_Detchd<br>garage_area garage_yr_blt 	|
| Inference                  	| Slight overfitting                                                        	| Slight overfitting                                                       	| Slight overfitting                                                                                                               	| Slight underfitting                                                                                                                              	|

## CONCLUSIONS
- Model 4 has the best R2 testing score, and is the best model for predicting house prices. This model uses polynomial features with feature selection using Hypothesis testing of OLS coefficients.
- Although Model 4 has the best estimates, it's top features seem very counter-intuitive, since most of them are based on garage-values.
- This is because OLS regression is very sensitive to outliers, and there are a few more outliers in the data which weren't removed in this preliminary model.
- So, the most important features for prediction are the features which are common in both the OLS and correlation filters:
    - Overall quality^2
    - Overall quality * External quality
    - Overall quality * Garage area
    - Overall quality * Heating QC
- Overall quality is the best predictor of house prices.
- Neighborhood wasn't accounted for in any of the models, which also seems counter intuitive. So, some statistics of Sale Price based on Neighborhood have been included.


## RECOMMENDATIONS
- Model 4 can be used to predict the house prices in Ames, and the above features can be given more weightage when recommending homes to buyers.
- Apart from those features, up-and-coming neighborhoods(based on sale price trends) can also be recommended to get a higher return on investment.


## NEXT STEPS
- This is only a  preliminary model to be used to get a general idea of the house prices in Ames. A more accurate model can be built using the given data.
- Analyze the data further and remove a few more outliers.
- Deeper analysis of overall quality with other features.
- Choose and scale some features as done with the target.
- Use regularization to prevent overfitting.

