>Lasso (Least Absolute Shrinkage and Selection Operator) regression minimizes the [[SSE, SSR, and SST|sum of the squared residuals]] (similar to ordinary least squares regression) but adds a penalty term that encourages some regression coefficients to be exactly zero. This penalty term is a function of the absolute values of the coefficients, known as the L1 norm. 

This penalty term encourages sparsity in the model and address the issue of overfitting. In Lasso regression, the objective is to minimize the following quantity with respect to the regression coefficients β:
$$(Y - X\beta)^T(Y - X\beta) + \lambda \sum_{j=1}^{p} |\beta_j|$$
In this equation:
- $Y$ = vector of observed values of the dependent variable.
- $X$ = design matrix containing the independent variables.
- $\beta$  = vector of regression coefficients.
- $\lambda$  = regularization parameter that controls the strength of the penalty term. It determines the trade-off between the least squares criterion (goodness of fit) and the penalty term (sparsity).
