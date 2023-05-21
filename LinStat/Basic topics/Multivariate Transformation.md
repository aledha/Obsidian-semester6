>The multivariate transformation formula, also known as the Jacobian formula, is a mathematical expression used to compute the probability density function (PDF) of a transformed random vector. It allows us to determine the distribution of a function of multiple random variables.

Let's consider a transformation from an initial set of variables $\mathbf{X} = (X_1, X_2, \ldots, X_n)$ to a new set of variables $\mathbf{Y} = (Y_1, Y_2, \ldots, Y_m)$, where $n$ and $m$ represent the dimensions of the initial and transformed spaces, respectively.

<u>The multivariate transformation formula states</u> that if $\mathbf{Y}$ is a function of $\mathbf{X}$ defined by $\mathbf{Y} = \mathbf{g}(\mathbf{X})$, where $\mathbf{g}$ is a vector-valued function, the joint probability density function (PDF) of $\mathbf{Y}$ can be computed as follows:
$$
f_{\mathbf{Y}}(\mathbf{y}) = f_{\mathbf{X}}(\mathbf{x}) \left\lvert \det \left( \frac{\partial \mathbf{g}}{\partial \mathbf{x}} \right) \right\rvert,
$$
where $f_{\mathbf{X}}(\mathbf{x})$ is the joint PDF of $\mathbf{X}$ evaluated at $\mathbf{x}$, and $| \det \left( \partial_{\mathbf{x}} \mathbf{g} \right) |$ represents the determinant of the Jacobian matrix, which is the matrix of partial derivatives of the components of $\mathbf{g}$ with respect to the components of $\mathbf{x}$.

In essence, the formula accounts for the stretching, shrinking, and rotation of the probability distribution due to the transformation. It incorporates the effects of changes in scale and orientation when mapping from the initial space to the transformed space.

It's worth noting that the multivariate transformation formula assumes that the transformation $\mathbf{g}$ is one-to-one and differentiable. Additionally, the formula holds for continuous random variables. For discrete random variables, appropriate adjustments need to be made.

# Example

Find the [[pdf]] of the [[F-distribution]].

![[Pasted image 20230514173326.png]]
