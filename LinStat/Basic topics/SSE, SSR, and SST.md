In the context of regression analysis, SSE, SSR, and SST are terms used to describe different sums of squares.

1. SSE (Sum of Squares Error/[sum of squared residuals (SSR)](https://en.wikipedia.org/wiki/Residual_sum_of_squares)): SSE represents the sum of the squared differences between the observed values of the dependent variable and the predicted values obtained from the regression model. It measures the unexplained variation or the residual variation in the model.

2. SSR (Sum of Squares Regression): SSR represents the sum of the squared differences between the predicted values obtained from the regression model and the mean of the dependent variable. It measures the explained variation or the variation in the dependent variable that is accounted for by the independent variables in the model.

3. SST (Sum of Squares Total): SST represents the sum of the squared differences between the observed values of the dependent variable and the mean of the dependent variable. It measures the total variation in the dependent variable.
4. 
Mathematically, these sums of squares can be expressed as follows:

- SSE = $\sum_{i=1}^{n} (y_i - \hat{y}_i)^2=(\textbf{Y} - \textbf{X}\beta)^T(\textbf{Y} - \textbf{X}\beta)$
- SSR = $\sum_{i=1}^{n} (\hat{y}_i - \bar{y})^2$
- SST = $\sum_{i=1}^{n} (y_i - \bar{y})^2$

where $n$ is the number of observations, $y_i$ is the observed value of the dependent variable, $\hat{y}_i$ is the predicted value of the dependent variable, and $\bar{y}$ is the mean of the dependent variable.

These sums of squares are fundamental components in calculating various statistical measures in regression analysis, such as the coefficient of determination ([[R-squared]]), F-statistic, and standard errors of the regression coefficients.