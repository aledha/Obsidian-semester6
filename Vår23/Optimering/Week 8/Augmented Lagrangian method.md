For equality constraints
Want to solve 
$$\min_\limits{x}f(x) \quad\text{such that}\quad c_{i}(x)=0,\quad i\in \xi \tag{P}$$
## Background
From the [[Quadratic penalty method]]: instead of constraint problem, solve
$$\min_\limits{x\in \mathbb{R}^{d}}f(x)+ \frac{\mu}{2}\sum\limits_{i\in \xi}c_{i}(x)^{2}$$
for large $\mu\to\infty$
Problem for this method is that it becomes ill-conditioned for $\mu\to\infty$, but $\mu\to\infty$ is required for good results.

Recall: Lagrangian of (P) is 
$$\mathcal{L}(x,\lambda)=f(x)-\sum\limits_{i\in \xi}\lambda_{i}c_{i}(x)$$
[[KKT-conditions]] state that
$$\nabla f(x^{*})=\sum\limits_{i\in \xi}^{}\lambda_{i}^{*}c_{i}(x^{*})$$
or
$$\nabla _{x}\mathcal{L}(x^{*},\lambda^{*})=0$$
And: second order optimality conditions state that
If $x^{*}$ is a KKT-point with $\lambda^{*}$ and
$${\left\langle p,H_\mathcal{L}(x^{*},\lambda^{*})p \right\rangle}>0\quad\forall\quad p\in \mathcal{C}(x^{*},\lambda^{*})\backslash\{0\}$$
Then $x^{*}$ is a local solution of (P) $\{0\}$ 

For equality constraint problems, the critical cone is
$$\mathcal{C}(x^{*},\lambda^{*})=\mathcal{F}(x^{*})=\{p:{\left\langle \nabla c_{i}(x^{*}) ,p\right\rangle}=0\}\quad\forall\quad i\in \xi$$
## Definition: Augmented Lagrangian
Penalisation parameter $\mu>0$
$$\begin{align*}
\mathcal{L}_{A} (x,\lambda;\mu)&= \mathcal{L}(x,\lambda)+ \frac{\mu}{2}\sum\limits_{i\in \xi}^{}c_{i}(x)^{2}\\
		&= f(x)-\sum\limits_{i\in \xi}^{}\lambda_{i}c_{i}(x)+ \frac{\mu}{2}\sum\limits_{i\in \xi}^{}c_{i}(x)^{2}
\end{align*}$$
Initial interpretation: penalise the Lagrangian
Alternative interpretation:
Consider the problem 
$$\min_\limits{x}\left[ f(x)+ \frac{\mu}{2}\sum\limits_{i\in \xi}^{}c_{i}(x)^{2}\right] \quad\text{such that}\quad c_{i}(x)=0 \quad\forall\quad i\in \xi \tag{A}$$
(adding the constraints twice?)
$\mathcal{L}_{A}$ is the Lagrangian for (A).
And:
$x^{*}$ is a KKT-point for the original problem (P) with Lagrange multiplier $\lambda^{*}$
$\quad\Updownarrow\quad$
$x^{*}$ is a KKT point for (A) with $\lambda^{*}$

We have 
$$\nabla \mathcal{L}_{A}(x^{*},\lambda^{*})=\nabla f(x^{*})-\sum\limits_{i\in \xi}^{}\lambda^{*}_{i}\nabla c_{i}(x^{*})+\mu \sum\limits_{i\in \xi}^{}c_{i}(x^{*}) \nabla c_{i}(x^{*})$$
and
$$H_\mathcal{L_{A}} (x^{*},\lambda^{*},\mu)=H_{f}(x^{*})-\sum\limits_{i\in \xi}^{}\lambda_{i}^{*}H_{c_{i}}(x^{*})+ \sum\limits_{i\in \xi}\left(c_{i}(x^{*})H_{c_{i}}(x^{*})+\nabla c_{i}(x^{*})\nabla c_{i}(x^{*})^{T}\right) $$
	$$=H_\mathcal{L}(x^{*},\lambda^{*})+\mu \sum\limits_{i\in \xi}^{} \nabla c_{i}(x^{*})\nabla c_{i}(x^{*})^{T}$$
Where the first term is expected positive definite along $\mathcal{F}_\Omega(x^{*})$ and the second is positve definite along $\mathcal{F}_\Omega(x^{*})^\perp$ 
$\Rightarrow\quad$ if $\mu$ is sufficiently large, 
$H_{\mathcal{L}_{A}}(x^{*},\lambda^{*},\mu)$ is positive definite.
$\Rightarrow\quad$ $x^{*}$ will be a strict local solution of $\min_\limits{x\in \mathbb{R}^{d}}\mathcal{L}_{A}(x,\lambda^{*},\mu)$
But we need to find $\lambda^{*}$!

### How to find $\lambda^{*}$
We have 
$$\nabla f(x^{*})=\sum\limits_{i\in xi}^{}\lambda_{i}^{*}\nabla c_{i}(x^{*})$$
Now assume that $x_{\lambda}$ is a solution of 
$$\min_\limits{x}\mathcal{L}_{A}(x,\lambda,\mu)$$
(i.e. the wrong $\lambda$). First order optimality conditions:
$$\nabla f(x_{\lambda})-\sum\limits_{i\in \xi}^{}\lambda_{i}\nabla c_{i}(x_{\lambda})+\mu \sum\limits_{i\in \xi}^{}c_{i}(x_\lambda)\nabla c_{i}(x_{\lambda})=0$$
First order taylor around $x^{*}$
$$\nabla f(x^{*})-\sum\limits_{i\in \xi}^{}(\lambda_{i}-\mu c_{i}(x_{\lambda}))\nabla c_{i}(x^{*})+ \mathcal{O}(||x_\lambda-x^*||)=0$$
$$\Rightarrow\quad \lambda_{i}^{*}= \lambda_{i}-\mu c_{i}(x_\lambda)+\mathcal{O}(||x_\lambda-x^*||)$$
Which can be solved by a fixed point iteration

Start with $x_{0}\in \mathbb{R}^{d}$ and some $\lambda^{(0)}\in \mathbb{R}^{\xi}$
For $k=0,1\dots$ 
	$x_{k+1}=\text{solution of }\min_\limits{x}\mathcal{L}_{A}(x,\lambda^(k),\mu)$
	$\lambda_{i}^{(k+1)}=\lambda_{i}^{(k)}-\mu c_{i}(x_{k+1})\quad\forall\quad i\in \xi$
	$k=k+1$
Stop when the updates are small.

One can show that this converges towards a solution of the constraint problem if the initialisation is sufficiently close to the solution, and $\mu$ is sufficiently large.

Idea: start with a small $\mu>0$, 
After each iteration, check whether $|c_{i}(x)|$ have decreased.
	If not: increase $\mu$
	