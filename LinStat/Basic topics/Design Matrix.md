>The design matrix, denoted by $\mathbf{X}$, is a matrix that contains the values of the independent variables (also known as predictors or regressors) in a linear regression model. Each row of the design matrix represents an observation or data point, while each column represents a different independent variable.

The design matrix is used in the linear regression model to estimate the coefficients (represented by $\hat{\beta}$) that define the relationship between the independent variables and the dependent variable.

### Example
---
Assume that we have two independent variables, $X_1$ and $X_2$, and three observations. The design matrix $\mathbf{X}$ would be constructed as follows:

$$
\mathbf{X} = \begin{bmatrix}
1 & X_{11} & X_{12} \\
1 & X_{21} & X_{22} \\
1 & X_{31} & X_{32}
\end{bmatrix}
$$

In this example, we have three observations, and for each observation, we have values for X1 (denoted by $X_{11}$, $X_{21}$, $X_{31}$) and X2 (denoted by $X_{12}$, $X_{22}$, $X_{32}$). The first column of ones is added to account for the intercept term in the linear regression model.

To determine $\hat{\beta}$ in the given example, we need to have the corresponding dependent variable values, denoted as $\mathbf{Y}$. Assuming we have three observations, the vector $\mathbf{Y}$ can be represented as:
$$
\mathbf{Y} = \begin{bmatrix}
Y_1 \\
Y_2 \\
Y_3
\end{bmatrix}
$$
To estimate $\hat{\beta}$, we can use the equation:
$$
\hat{\beta} = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{Y}
$$
Substituting the values from the example:
$$
\mathbf{X} = \begin{bmatrix}
1 & X_{11} & X_{12} \\
1 & X_{21} & X_{22} \\
1 & X_{31} & X_{32}
\end{bmatrix}
\text{, }\quad\text{and }\quad
\mathbf{Y} = \begin{bmatrix}
Y_1 \\
Y_2 \\
Y_3
\end{bmatrix}
$$
we can compute $\hat{\beta}$ using matrix operations:
$$
\hat{\beta} = \left((\mathbf{X}^T\mathbf{X})^{-1}\right)\mathbf{X}^T\mathbf{Y}
$$
The estimated coefficient vector $\hat{\beta}$ contains the estimated values for each coefficient in the regression model, including the intercept term. Each coefficient represents the estimated effect of an independent variable on the dependent variable.