# Regression Modelling on King County Data Set for use by A Mortgage Valuer

## Table of contents
  
* Introduction  
* Business problem and data understanding 
* Stakeholder
* Modeling
* Regression Results
* Conclusions



 ## Introduction

We analyze data from King County House sales to determine the best direction for pricing decisions to Mipaka, a real estate company, exploratory data analysis is applied to generate insights for the data and we apply various modeling techniques to determine price determinants in the market while presenting three main business recommendations.


 ## Business problem 
 
Morgage valuers are facing challenges of optimizing pricing strategies for properties in a fast changing market.To attract the best buyers they need to competitively price while also maximizing profits. We can use data driven insights with predictive modeling techniques to solve for this problem.We use different models to help Mipaka, a fictional company in the real estate field mortgage valuation. This project uses different regression models that will help Mipaka predict house values more accurately, and identify factors that have the most influence on a property's price. The goal is to help Mipaka optimize its pricing strategies and maximize profits.

## Data understanding

We used housing  data was collected from :

* King County House Sales dataset-kc_house_data.csv.

The datasets contains valuable variables such as price, sqft living, year built,bathrooms, grade, conditions etc. 

Our target variable is the price, it serves as the independent variable in our modeling, we determine what influences house pricing.



## Business stakeholder

Mipaka,a fictional company in the real estate field. They specialize in mortgage evaluation they also assess property values to determine risk for market lenders.

## Modeling

We have developed and evaluated several mmachine learning models to predict pricing

*  Model I

  Decription: We established a baseline Model using sqft_living column, it showed the highest correlation.

  Performance :The variable square foot living explains 49% of the variance in price. 
  
  Insights: while the contribution is noticeable, it's not enough to be used entirely to predict changes in price. Or predict a price of a house
   
*  Model II
  
  Decription: We tried a new model including a few more variables This model considered the age of the building, square foot of the living room and number of bathrooms.

  Performance: It explained 53.1% of the variance in price making it a better predictor than our baseline model.
  The model is statistically significant, with a p-value below 0.05.with RMSE of $251,695.880
  
  Insights: its coefficient of determination is still less than 0.7 which is a common benchmark value for business decisions, we therefore add a new variable to improve prediction.

 *  Model III
   
  Decription: We added a categorical variable (grade) to try and improve the accuracy of our model. We used one hot (dummy) encoding using pandas 

  Performance : This model explains 63.9% of the variance in our dependent variable, which is an improvement over Model II which explained 53% of the same.
                All the coefficients are statistically significant, with a p value below 0.05, With RMSE of $ 220,735.107
  
  Insights: sqft_living : 125.83 : the cost of a house increases by about $125.2765 for every 1 square foot increase in living space
            age: the price increases by about $3664 for each extra year.
            bathroom : the price os a house increases by $ 58,250 for each additional bathroom.

 *  Model IV
   
  Decription:We use another categorical variable and add it on to what we had in model III

  Performance :  From the R squared, the fourth model explains 64.0% of the variance in the price
                 p-value is below 0.05 so the model is statistically significant
                 RMSE is 220,298.52 which is slightly lower than what we got from model III
                 
  Insights: sqft_living : $124.9077 : the cost of a house increases by this amount for 1 square foot increase in living space
            bathrooms: 56,230: the cost of a house increases by $56,230 for each extra bathroom

  *  Model V
    
  Decription: We analyze the relationship between sale price and location using latitude and longitude variables.Locations at the centre of the county appeared to have dieefrent prices.
              We built two KRegressor models to try and predict house sale prices based on location.

  Performance: RMSE for the first kregression model with k=25 has an RMSE of 245412.12396420678.
  
  ![image](https://github.com/KarimiNyaga/dsc-phase-2-project-v2-3/assets/136931914/c0546f27-d662-4bab-a43d-10e470ddac6c)
  
  RMSE for the second kregression model with k=1000 has an RMSE of 254195.0352946489

  ![image](https://github.com/KarimiNyaga/dsc-phase-2-project-v2-3/assets/136931914/29ffb009-128f-482a-98dc-7b40f5c633af)

  Insights: The RMSE for the first model is 236992.59, while the RMSE for the second model is 259889.70. This means that, for the first model, our prediction of price is off by $ 
            236992.59.
            The RMSE is increasing with an increase in kvalue. This means tht the first model is performing better than the second one.The optimal k value is a low k value. The lower 
            the k, the better the prediction.
 
  


## Regression Results

* To improve accuracy- Mipaka should use a combination of the following factors : sqft_living, age, bathrooms, grade, condition to improve their price prediction. Based on our regression analysis, the model created based on these factors accounted for the most variance in change in prices.

* For maximum returns- Mipaka should look to develop new housing developments on the Western Side of King County. Based on our models, the prices towards the East show a slight decrease in price, therefore being less likely to bring in profits. However, the company should note that price prediction based on location is very sensitive to local variations, prices are only similar within a small distance of each other.


## Conclusion
This analysis equips Mipaka with data-driven insights and predidctive modeling strategies to make strategic decisions in the competitive real estate industry. By focusing on popular ways to determine fair pricing using factors like sqft living, age, grade, condition to improve its profit maximization.
