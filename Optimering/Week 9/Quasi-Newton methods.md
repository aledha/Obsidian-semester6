## Recall: Newton's method
$$\begin{align*}
p_{k}&= -H_{f}(x_{k})^{-1}\nabla f(x_{k})\\
x_{k+1}&= x_{k}+ \alpha_{k}p_{k}
\end{align*}$$
Advantages:
* Quadratic convergence (close to the solution)

Disadvantages:
* Requires the Hessian of $f$: $H_{f}$ 
	* $f$ may not be twice differentiable
	* if we are in higher dimensions, the Hessian may be costly to compute
* Need to solve a linear system in each step $H_{f}(x_{k})p_{k}=\nabla f(x_{k})$
* $p_{k}$ is guaranteed to be a descent direction only if the Hessian is positive definite at $x_{k}$
	* $f$ convex$\quad\Rightarrow\quad$ Hessian positive definite everywhere
	* for non-convex problems, modifications are necessary

### Interpretation of Newton's method
In step $k$, consider the approximate (using Taylor)
$$f(x_{k}+p)≈f(x_{k})+{\left\langle \nabla f(x_{k}),p \right\rangle}+ \frac{1}{2}{\left\langle p,H_{f}(x_{k})p \right\rangle}=:m_{k}(p)$$
Construct a model of $f$ around $f$
If $H_{f}(x_{k})$ is positive definite, $m_{k}$ is strictly convex and has a unique minimiser 
$$p_{k}=-H_{f}(x_{k})^{-1}\nabla f(x_{k})$$
Then add line search for stabilising the update.

## Quasi-Newton methods
Same approximation for $m_{k}(p)$, but replace $H_{f}(x_{k})$ by some positive definite, symmetric approximation $B_{k}$
$$f(x_{k}+p)≈m_{k}(p):=f(x_{k})+{\left\langle \nabla f(x_{k}),p \right\rangle}+ \frac{1}{2}{\left\langle p,B_{k}p \right\rangle}$$
Solve the minimiser $p_{k}$
$$p_{k}=-B_{k}^{-1}\nabla f(x_{k})$$
Define $B_{k}$ step-by-step:
	Compute $B_{k+1}$ by modifying the previous one, $B_{k}$ (as little as possible) such that
	$$\nabla m_{k+1}(-\alpha_{k}p_{k})=\nabla f(x_{k})$$
	Going back one step. From $x_{k+1}=x_{k}+\alpha_{k}p_{k}$ it follows that
	$p=-\alpha_{k}p_{k}\quad\Rightarrow\quad m_{k+1}(-\alpha_{k}p_{k})≈f(x_{k+1}+p) =f(x_{k})$

$$\nabla m_{k+1}(-\alpha_{k}p_{k})=\nabla f(x_{k+1})+B_{k+1}(-\alpha_{k} p_{k})$$
$\Rightarrow\quad \text{Require }$ $B_{k+1}$ to satsify
$$\nabla f(x_{k+1})-\alpha_{k} B_{k+1}p_{k}=\nabla f(x_{k})$$
Or with $-s_{k}:=-\alpha_{k}p_{k}=x_{k}-x_{k+1}$                    ($s_{k}=x_{k+1}-x_{k}$)
and $\nabla f(x_{k+1})-\nabla f(x_{k})=y_{k}$
We get
$$B_{k+1}s_{k}=y_{k}\tag{Secant equation}$$

Find $B_{k+1}$ by modiying $B_{k}$ as little as possible such that the secant equation holds.

[[SR1-method]]