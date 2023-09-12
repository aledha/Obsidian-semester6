>The estimated coefficient vector $\hat{\beta}$ contains the estimated values for each coefficient in the regression model, including the intercept term. Each coefficient represents the estimated effect of an independent variable on the dependent variable.

To estimate $\hat{\beta}$, we can use the equation:
$$
\hat{\beta} = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{Y},
$$
where $\mathbf{X}$ is the [[Design Matrix]],  and  $\mathbf{Y}$ is the corresponding dependent variable values (our observations).

The distrribution of $\hat\beta$ is [[Normal Distribution|normal]]:
$$\hat{\beta} \sim N(\beta, \sigma^2(X^TX)^{-1}).$$