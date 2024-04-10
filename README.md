# Business Understanding
The selling price of a home is a critical factor in the real estate market, as it directly influences the financial outcome for both buyers and sellers. For homeowners, the selling price represents the return on their investment and can significantly impact their financial well-being. Potential buyers, on the other hand, rely on the selling price to make informed decisions about purchasing a property within their budget and assessing its value relative to similar properties in the market.
House price is influenced by a multitude of factors, which can be broadly categorized into three main categories: property-specific factors, market factors, and external factors. Property-specific factors encompass attributes such as location, size, condition, amenities, architectural style, and age of the property. Market factors include supply and demand dynamics, interest rates, mortgage availability, and prevailing economic conditions. External factors can range from neighborhood characteristics, such as school quality and crime rates, to broader influences like government policies, infrastructure development, and demographic trends.
Understanding the factors that influence the selling price of residential properties is of paramount importance to various stakeholders involved in the real estate industry. Real estate agents need this knowledge to provide accurate pricing recommendations and effective marketing strategies for their clients. Homeowners can benefit from understanding these factors to make informed decisions when pricing their properties. Investors and developers can leverage this knowledge to identify promising investment opportunities and maximize their returns. 

## Problem Statement
Real estate market is highly volatile, influenced by economic conditions, housing demand, and external factors. As such setting inappropriate prices and making uninformed decisions of when to sell a house can be counterproductive.  Research is essential to understand market trends and identify the best time to sell a home for maximizing its selling price. Analyzing property characteristics such as location, size, amenities, condition, and recent market trends through research aids in setting an appropriate selling price. By understanding how different home characteristics impact selling prices, the agency can help home owners mitigate the risk of setting inappropriate prices or making poor investment decisions.  

### Objectives
1. To understand factors that affect price of a house
2. To develop a model that can predict housing price based on various features. 
3. To make recommendations on how home owners can optimize selling price of a house
 ## Modelling 
The Baseline model consists of 2 simple linear regression models demonstarting the relationship between price and two highly correlating variables

 ## Model evaluation approach 
R-squared indicates the proportion of variance in the dependent variable (price) explained by the independent variables included
The Durbin-Watson statistic tests for autocorrelation in the residuals, with values close to 2 indicating no autocorrelation.

##  Model comparison approach 
Root Mean Squared Error (RMSE): This is the square root of the MSE, which gives a measure of the average magnitude of the errors in the predicted values.
Mean Squared Error (MSE): The MSE measures the average squared difference between the actual and predicted values.
A lower MSE indicates better model performance, with a value of 0 indicating a perfect fit. 

### REGRESSION RESULTS
**For our baseline model**, we conducted simple linear regression analyses to explore the relationships between the housing price and two highly correlated variables: bathrooms and square footage of living space (sqft_living).

First, we tested the hypothesis that the coefficient of 'sqft_living' is zero, suggesting no linear relationship between the size of the living space and the price. However, our analysis revealed a p-value close to zero (less than 0.05) , leading us to reject the null hypothesis. 
This implies a statistically significant linear relationship between 'sqft_living' and 'price'. 
The coefficient estimate for 'sqft_living' is 283.4564. It indicates that for each additional unit increase in square footage of living space, we expect the price to increase by $283.4564, assuming all other variables remain constant.

Next, we examined the relationship between the number of bathrooms and the price. Initially, we hypothesized that the coefficient of 'bathrooms' would be zero, indicating no linear relationship. Yet, the analysis yielded a low p-value (close to 0.0), prompting us to reject the null hypothesis. 
We concluded a statistically significant linear relationship between the number of bathrooms and the price. 
The coefficient estimate for 'bathrooms' is 0.3779, indicating that for each additional bathroom, the price is expected to increase by 0.3779 units, all else being equal.


**From our final multiple linear regression model**, the following key findings were observed:

* Bedrooms: Each additional bedroom is associated with a decrease in the estimated price by 0.0683 units, holding all other variables constant. This suggests that, contrary to intuition, an increase in the number of bedrooms is linked with a lower housing price in our model.

* Sqft_lot: The coefficient for square footage of lot area indicates that for each additional square foot of lot area, the estimated price decreases by $1.214e-05, holding all other variables constant. This suggests that larger lot sizes are associated with lower housing prices in our model.
* Waterfront: Properties with a waterfront view are estimated to have a price increase of 0.6570 units compared to those without a waterfront view, holding all other variables constant. This indicates a significant positive impact of waterfront views on housing prices.

* Sqft_above and Sqft_basement: Each additional square foot of living space above ground level (sqft_above) and in the basement (sqft_basement) is associated with an estimated price increase of 0.0006 and 0.0005 units, respectively, holding all other variables constant. This suggests that larger living spaces contribute positively to housing prices.

* Yr_built: With each passing year of construction, the estimated price decreases by 0.0034 units, holding all other variables constant. This implies that newer properties tend to have lower prices compared to older ones.

From this, we can deduce that waterfront view, and living space (both above ground and in the basement) positively influence housing prices. Additionally, newer properties tend to command lower prices compared to older ones.
Our analysis also suggests that newer properties generally have lower prices compared to older ones. Additionally, both the number of bedrooms and the size of the lot are associated with lower prices.


**Our polynomial regression model** is preferred as it achieved the highest R-squared value of 0.58, surpassing both the multiple linear regression model (0.53) and the simple regression analyses (0.41 and 0.29)


**The cross-validation results** provide valuable insights into the performance of our model. 
The mean R-squared score of 0.510 and the test R-squared score of 0.510 indicate that our model explains approximately 51% of the variance in the target variable. Additionally, the mean MSE of 0.136 and the test MSE of 0.137 suggest that our model's predictions are, on average, off by approximately 0.137 units. 
These consistent scores across cross-validation folds and the test set validate the robustness and generalization capability of our model, indicating its reliability in making accurate predictions on unseen data.
## Conclusions
Based on our analysis, we have uncovered several significant insights into the factors influencing housing prices. 
Firstly, features such as waterfront views, larger living spaces (both above ground and in the basement), and certain construction attributes positively impact housing prices. 
Conversely, newer properties tend to command lower prices compared to older ones, and factors like the number of bedrooms and lot size are associated with decreased prices.

## Limitations
1. The dataset may lack additional property-specific characteristics that could provide further insights into housing prices.

2. Multicollinearity: The existence of correlated predictors within the dataset can result in multicollinearity problems, complicating the accurate interpretation of the individual impacts of each feature.

3. Overfitting: Polynomial regression models are prone to overfitting. This is where the model tightly conforms to the training data but may struggle to perform well on new, unseen data.
Overall the model was the best fit model for this prediction

## Recommendations
**Further Data Collection:** the dataset could be expanded to include additional property-specific characteristics that may influence housing prices, such as proximity to amenities and neighborhood demographics, and property condition. This can provide a more comprehensive understanding of the housing market dynamics.

**Guard Against Overfitting:** To mitigate the risk of overfitting in polynomial regression models, using techniques such as cross-validation, regularization could be considered, or reducing the complexity of the model by selecting an appropriate degree for the polynomial features.

**Continuous Model Monitoring:** Continuously monitoring the model's performance and validity over time as new data becomes available or market conditions change. Regular updates and recalibration may be necessary to ensure the model remains relevant and accurate.
