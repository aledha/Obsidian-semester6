>$$\text{PDF = Probability Density Function. }$$
This function describes the likelihood of a continuous random variable taking on a particular value.

For a random variable $X$, the PDF, often denoted by $f_X(x)$, has the following properties:

1. The PDF is always non-negative, i.e., $f_X(x) \geq 0$ for all $x$.
2. The total area under the curve of the PDF is equal to 1, i.e., $\int_{-\infty}^{+\infty} f_X(x) \, dx = 1$.

The value of the PDF at a specific point can be interpreted as the relative likelihood of the random variable taking on that value. However, because we're dealing with continuous random variables, the probability of the variable taking on any specific value is technically zero. Instead, the PDF is used to calculate the probability that the variable falls within a certain range. This is done by integrating the PDF over that range.

For example, if $X$ is a continuous random variable with PDF $f_X(x)$, the probability that $X$ falls within the range $[a, b]$ is given by:
$$P(a \leq X \leq b) = \int_a^b f_X(x) \, dx$$
In the context of the standard normal distribution $N(0,1)$, the PDF is given by:
$$\phi(x) = \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}$$
This function, $\phi(x)$, describes the likelihood of a standard normal random variable taking on the value $x$.
