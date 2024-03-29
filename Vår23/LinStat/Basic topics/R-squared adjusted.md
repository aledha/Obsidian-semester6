>R2 adj (adjusted R-squared) adjusts the R2 value to account for the number of predictors in the model and the sample size. It penalizes the inclusion of additional variables that do not contribute significantly to improving the model's fit. <u>R2 adj is a more reliable measure when comparing models with different numbers of predictors.</u>

$$R^2_{adj} = 1 - \left(1 - R^2\right) \frac{n - 1}{n - k - 1}$$
where n is the number of observations and k is the number of predictors in the regression model.

The adjusted R-squared formula adjusts R2 by penalizing the inclusion of additional predictors that do not contribute significantly to the model. It takes into account the sample size (n) and the number of predictors (k) to provide a more accurate assessment of the model's goodness of fit and to avoid overfitting.