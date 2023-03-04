We want to solve $\min_\limits{x}f(x)$. In step $k$ we have the model function
$$m_{k}(p)=f(x_{k})+ {\left\langle \nabla f(x_{k}) \text{ , } p \right\rangle}+ \frac{1}{2}{\left\langle p \text{ , } B_{k}p \right\rangle}$$
For line search:
* Compute $p_{k}=\underset{p\in \mathbb{R}^{d}}{\text{argmin }}m_{k}(p)$
* Choose a step length $\alpha _{k}>0$ according to Armijo, Wolfe $\dots$
* Update $x_{k+1}=x_{k}+\alpha _{k}p_{k}$

## Idea
* Choose some upper bound for the radius of a "trust region", on which you expect $m_{k}$ to be a good model of the function $f$.
* Define $p_{k}$ as a solution of the constraint problem $\min_\limits{p}m_{k}(p) \quad\text{s.t.}\quad \left\lVert p \right\rVert\le \Delta$.
* Define $x_{k+1}=x_{k}+p_{k}$.
