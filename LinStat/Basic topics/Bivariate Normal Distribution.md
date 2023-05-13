The bivariate normal distribution can also be expressed using the covariance matrix. The covariance matrix for the variables $X$ and $Y$ is denoted as $\Sigma$ and defined as:

$$\Sigma = \begin{bmatrix} \sigma_X^2 & \rho\sigma_X\sigma_Y \\ \rho\sigma_X\sigma_Y & \sigma_Y^2 \end{bmatrix}$$

Here, $\sigma_X^2$ and $\sigma_Y^2$ are the variances of $X$ and $Y$, respectively, and $\rho$ is the correlation coefficient between $X$ and $Y$.

The probability density function (PDF) of the bivariate normal distribution using the covariance matrix is given by:

$$f(x, y) = \frac{1}{2\pi|\Sigma|^{1/2}}\exp\left(-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^T\Sigma^{-1}(\mathbf{x}-\boldsymbol{\mu})\right)$$

In this equation:
- $\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}$ is a column vector of the random variables $X$ and $Y$.
- $\boldsymbol{\mu} = \begin{bmatrix} \mu_X \\ \mu_Y \end{bmatrix}$ is a column vector of the means of $X$ and $Y$.
- $\Sigma^{-1}$ represents the inverse of the covariance matrix $\Sigma$.
- $|\Sigma|$ denotes the determinant of the covariance matrix.

Note that in the formula above, the inverse of the covariance matrix $\Sigma$ is used instead of the individual variances and correlation coefficient as in the previous formula. This formulation is particularly useful when working with higher-dimensional multivariate normal distributions.