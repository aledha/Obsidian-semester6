[[Trust region methods]]
## Choice of $\Delta _{k}$ 
(Trust region radius)
In each step:
	Compute the expected decrease in function value $m_{k}(p_{k})-m_{k}(0)$
	Compare with the actual decrease $f(x_{k}+p_{k})-f(x_{k})$
	Compute
	$$\mathcal{S}_{k}= \frac{f(x_{k}+p_{k})-f(x_{k})}{m_{k}(p_{k})-m_{k}(0)}$$
	If $\mathcal{S_{k}}$ is close to 1, then $m_{k}$ looks like a good model of $f$.
		$\quad\implies\quad$ Increase the trust region $\Delta _{k}$ for the next step.
	If $\mathcal{S}_{k}$ is close to 0, or negative, $m_{k}$ is a bad model
		$\quad\implies\quad$ Decrease the trust region $\Delta _{k}$

## Practical implementation
Initialise $x_{0}\in \mathbb{R}^{d},\quad \Delta _{0}>0, \quad 0<n< \frac{1}{4}$.
While not converged:
	$p_{k}=$ solution of $\min_\limits{p}m_{k}(p) \qquad\text{s.t.}\quad \lVert p \rVert\le \Delta _{k}$
	$\mathcal{S}_{k}= \frac{f(x_{k}+p_{k})-f(x_{k})}{m_{k}(p_{k})-m_{k}(0)}$ 
	if $\mathcal{S}_{k}> \frac{3}{4}$:
		$\Delta _{k+1}= 2 \Delta _{k}$
	else if $\mathcal{S_{k}}<\frac{1}{4}$:
		$\Delta _{k+1}= \frac{1}{4}\Delta _{k}$
	else:
		$\Delta _{k+1}=\Delta _{k}$
	if $\mathcal{S}_{k}>\eta$:
		$x_{k+1}=x_{k}+p_{k}$
	else:
		$x_{k+1}=x_{k}$

Note: we decrease $\Delta$ more than we increase.

We will arrive at the solution of the problem 
$$\min_\limits{p}m(p)\qquad\text{s.t.}\quad \lVert p \rVert\le \Delta $$
with $m(p)=f(x) +{\left\langle g \text{ , } p \right\rangle} + \frac{1}{2}{\left\langle p \text{ , } Bp \right\rangle}$,       where $g(x)=\nabla f(x)$.

The constraint $c(p)= \frac{1}{2}(\Delta ^{2}-\lVert p \rVert^{2})$   is a concave function, and for $\Delta >0 \quad\implies\quad c(0)= \frac{1}{2}\Delta ^{2}>0$.
	[[Slater's constraint qualification]] holds.
	Then, the [[KKT-conditions]] are necessary optimality conditions.