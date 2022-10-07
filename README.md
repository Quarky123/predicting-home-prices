## Project and Author info
Project: Ames Housing Prices <br />
Author: Dennis Chan Zhen Ye


## Contents 
- [01_data_cleaning](code/01_data_cleaning.ipynb)
- [02_eda](code/02_eda.ipynb)
- [03_Conclusion](code/03_Conclusion.ipynb)
- [Datasets](datasets)
- [Pictures](pictures)
- [Presentation](presentation/DSI%20-%20project%202.pdf)

## Data Dictionary 
link: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
- no additional features were created except for the ones created using get_dummies which converts categorical data into dummy or indicator variables.



## Problem Statement
**Context / Motivation** <br />
The extended periods low interest rate environment has reinvigorated the interest of investors in higher yielding financial instruments such as the RMBS(residential mortgage backed securities), as such a major US investment bank is looking into constructing a RMBS using the mortgages in Ames, a city in Iowa, as the underlying security. Individual residential loans/mortgages will be packaged together/securitised into a single pool of loans called the RMBS. The RMBS consists of different tranches which will then be sold to institutional and accredited investors based on their individual needs as different tranches have a different risk level. 

As part of the calculation for the mortgage default risk on the individual mortgages in the RMBSs, the firm seeks to understand the landscape of the residential real estate market in the city, as part of a due diligence effort that was lacking prior to the '08 financial crisis. The sales price for each house is of particular interest because it is correlated to the mortgage default risk levels. According to Case, Shiller & Weiss (1995), risks are negligible when aggregate prices are increasing rapidly, become substantial when aggregate prices level off for a few years, and become severe when aggregate prices fall. In recent times, it is observed that Non-Agency RMBS have recovered with home prices and the recent range of yield were between 3.5% to 5% as of 31 March 2017 (Alliance BernStein, 2018). Thus, there is a strong incentive to predict the sales price of each house as a proxy of measurement for the health of the Ames real estate market.


**Primary & secondary audience** <br />
The primary audience would be the investment bankers structuring the RMBS as they need to have a good understanding of the nature of the underlying mortgages and also the investors who would eventually invest into the RMBS. They include hedgefunds, pension funds, and some high net worth individuals.

The secondary audience would be the financial regulators such as the SEC, which is incharge of regulating the RMBS market and has also been looking to loosen up the regulations surrounding the RMBS (Johnson, 2019).

**Business problem statement** <br />
Real estate prices is an important input to measure mortgage default risk, thus, the team is tasked with coming up with a predictive model that could evaluate and predict the sales price for each house so as to understand where the nature of housing prices in the city, and possibly the housing market cycle in the region. 
Success of the project will be evaluated based on the accuracy of the sale prices of houses that would be useful as an input factor in the calculation of mortgage default risk and also for monitoring the health of the housing market cycle.

**Data Science problem statement** <br />
The team is tasked to predict the sales price for each house using the Id in the test set to predict the value of the SalePrice variable. The problem can be tackled with regression analysis which includes methods such as lasso regression, ridge regression, and elastic net regression. The train dataset will be fitted into the regression methods and the best dataset will be used to predict the SalePrice for the test dataset. Success of the project will then be evaluated based on how close the predicted SalePrice is to the actual SalePrice (which is not a given dataset). This can be evaluated based on the kaggle score given for the test results. Ideally the kaggle score would be less than 30,000. 




## Executive Summary
**Intention** <br />
This report provides a predictive analysis of the housing sale prices surrounding Ames, a city in Iowa. Methods of analysis used in this report include the use of trend analysis, clasifications based on statistics such as mean median mode, encoding of data, as well as the use of regression analysis tools such as lasso, ridge, and elastic net. The data are also fitted into the regression analysis tool with the highest mean cross-validation score. In this case it happens to be the lasso model.

**Process** <br />
Given that the target (Sale Price) is a continuous varaible, linear regression models will be used. The process flow is as follows.

1. [Data Cleaning](code/01_data_cleaning.ipynb)
 - Data validation
 - Replacement/Imputation of null values with median and 'Unknown'
 - Removal of Outliers

2. [Exploratory Data Analysis (EDA)](code/02_eda.ipynb)
 - Histogram and Distribution Analysis
 - Scatterplot Analysis
 - Box Plot Analysis
 
3. [Model Prep and Feature Engineering](code/02_eda.ipynb)
 - Feature engineering using get_dummies

3. [Business Insights](code/02_eda.ipynb)
 - Comments on correlation and adding value to the house


4. [Model Selection and Evaluation](code/03_Conclusion.ipynb)
 - Creating features and target vector
 - Instantiating Linear Regression Models (`Standard Linear`, `Lasso`, `Ridge`, and `ElasticNet`)
 - Model Selection based on Cross Validation Score
 - Model Fitting and Evaluation
 - Predicting the actual test
 - Kaggle Score


**Key Findings** <br />
Results of the data analysed show that certain neighborhoods command higher mean and median sale prices with StoneBr having the highest median price and MeadowV with the lowest. The report also finds the use of predictive analysis on sale prices of homes in the Aimes region based on the variables provided by the dataset is successful in predicting the sale prices of other (unknown) house prices in the same region as seen from the low kaggle score of 27355.18333. 




## Recommendations and Conclusion
As stated above, the model is useful for predicting house prices in the region and the predictions generated by this model could be used as input for the prediction of mortgage default risk. However, a major area of weakness is that it only provides a snapshot of what house prices between the 2006 to 2010 period, which coincidentally spans across the '08 financial crisis which was in large part due to RMBS products, specifically due to subprime mortgages who are then put into the RMBS. Thus, this may not be the price of houses in this area during normal market conditions. As such, the predictions generated by this model is likely only within the stated period. If the user hopes to generate house prices in the year 2030, it is likely to be inaccurate due to factors such as inflation which affects house prices. <br />

Besides the usefulness of the model as an input for credit default risk, other business applications could also be derived from the results. Overall Quad appears to add the most value to a home as it has a coeff of 0.803, which means that the dependent variable (Overall Quad) is expected to increase when that independent variable (SalePrice increases by one). The Id hurts the value of a home the most, perhaps there is some hidden meaning behind the Id where certain Id (for example smaller numbers) are given to more expensive areas and vice versa. However, it would be hard to speculate. Enclosed Porch with a corr of -0.135713 is the next most negatively correlated with SalePrice. Homeowners could improve could revamp the overall material and finish of the house to increase the value of the house. An investment in houses located in StoneBr is most likely to be a good investment because it has the largest interquartile range which could mean that by revamping the purchased house, the investor could command a good return on their investment. However, the results of the data might not translate well into other areas. It will likely generalise other cities with similar geography as Aimes, but it would not work for cities such as New York where spaces are scarce and land is expensive. 


## Citation
Case, K., Shiller, R., &amp; Weiss, A. (1995). Mortgage Default Risk and Real Estate Prices: The Use of Index-Based Futures and Options in Real Estate. doi:10.3386/w5078 <br />

GUIDE TO MORTGAGE INVESTING (Tech.). (2018). Retrieved https://www.alliancebernstein.com.sg/sites/library/Instrumentation/MORT-MAG-GR-EN-0118-FINAL.PDF <br />

Johnson, K. (2019, October 30). U.S. SEC considers relaxing post-crisis structured mortgage product rules. Retrieved December 16, 2020, from https://www.reuters.com/article/us-usa-sec-abs-idUSKBN1X92MQ