The MGF of a random variable $X$ is defined as:
$$M_X(t) = E[e^{tX}],$$
where $E[\cdot]$ is the expectation operator, and $t \in \mathbb{R}$. This function generates the moments of the distribution, in the sense that the $n$-th derivative of the MGF evaluated at $t=0$ gives the $n$-th moment of the distribution.

The multivariate moment generating function (MMGF) is an extension of this concept to multiple random variables. Let $\mathbf{X} = (X_1, X_2, ..., X_k)^T$ be a random vector, where $T$ denotes the transpose operation. The MMGF of $\mathbf{X}$ is defined as:
$$M_{\mathbf{X}}(\mathbf{t}) = E[e^{\mathbf{t}^T\mathbf{X}}] = E[e^{t_1X_1 + t_2X_2 + ... + t_kX_k}],$$
where $\mathbf{t} = (t_1, t_2, ..., t_k)^T$ is a vector of real numbers. Just as with the univariate case, the MMGF can be used to find the moments of the joint distribution of the random variables in $\mathbf{X}$.

In the multivariate case, the moments are not just individual values, but rather matrices. The first moment is the mean vector, a vector where the $i$th entry is the expected value of $X_i$. The second moment is the covariance matrix, a $k \times k$ matrix where the $(i, j)$th entry is the covariance between $X_i$ and $X_j$.

However, it's important to note that the MMGF does not always exist. For it to exist, the expectation $E[e^{\mathbf{t}^T\mathbf{X}}]$ must be finite for all $\mathbf{t}$ in some neighborhood of the origin. If the MMGF exists, it uniquely determines the probability distribution of $\mathbf{X}$.
