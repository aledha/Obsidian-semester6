The variance-covariance matrix, also known as the covariance matrix, is a matrix that captures the linear dependence between pairs of random variables in a multivariate random variable $\mathbf{X}$. If $\mathbf{X} = (X_1, X_2, \dots, X_n)^T$ is a random vector with $n$ elements, the covariance matrix $\Sigma$ is an $n \times n$ symmetric matrix, where each element $(i, j)$ represents the covariance between the $i$-th and $j$-th random variables, denoted as $\operatorname{Cov}(X_i, X_j)$.

The covariance matrix $\Sigma$ is given by:
$$
\Sigma = \begin{pmatrix}
\operatorname{Var}(X_1) & \operatorname{Cov}(X_1, X_2) & \dots & \operatorname{Cov}(X_1, X_n) \\
\operatorname{Cov}(X_2, X_1) & \operatorname{Var}(X_2) & \dots & \operatorname{Cov}(X_2, X_n) \\
\vdots & \vdots & \ddots & \vdots \\
\operatorname{Cov}(X_n, X_1) & \operatorname{Cov}(X_n, X_2) & \dots & \operatorname{Var}(X_n)
\end{pmatrix}
$$
The diagonal elements of the matrix represent the variances of the individual random variables:
$$\operatorname{Var}(X_i) = \operatorname{Cov}(X_i, X_i)$$
The off-diagonal elements represent the pairwise covariances between the random variables:
$$\operatorname{Cov}(X_i, X_j) = E[(X_i - E[X_i])(X_j - E[X_j])]$$
The covariance matrix is an important tool in multivariate statistics and machine learning, as it encodes essential information about the relationships between the components of the random vector $\mathbf{X}$. It is used in various statistical methods, such as principal component analysis (PCA), linear regression, and the multivariate normal distribution.