*Parameter identification/ non-linear regression*:
Given a vector $y\in \mathbb{R}^{m}$ of measurements
and a function $g:\mathbb{R}^{d}\to \mathbb{R}^{m}$ 
where $d<m$.

Goal: find $x\in \mathbb{R}^{d} \quad\text{s.t.}\quad g(x)$ is as close as possible to $y$.

Solve the optimization problem
$$\min_\limits{x\in \mathbb{R}^{d}} \frac{1}{2}\lVert g(x)-y \rVert^{2}$$
Where we call $f(x):= \frac{1}{2}\lVert g(x)-y \rVert^{2}$.
We could use some gradient descent methods on this problem, but since we know how the problem looks like, we can get better results with taylored methods.

Denote the "residual" $r:\mathbb{R}^{d}\to \mathbb{R}^{m}$ as
$$r(x)=g(x)-y$$
And write $r_{j}(x)=g_{j}(x)-y_{j}$    (the j-th component of r)
Then,
$$f(x) = \frac{1}{2}\lVert r(x) \rVert^{2}= \frac{1}{2}\sum\limits_{j=1}^{m}r_{j}(x)^{2}$$
and 
$$\nabla f(x)=\sum\limits_{j=1}^{m}r_{j}(x)\nabla r_{j}(x)$$
$$H_{f}(x)=\sum\limits_{j=1}^{m}r_{j}(x)H_{r_{j}}(x) + \nabla r_{j}(x)\nabla r_{j}(x)^{T}$$
Close to the solution, we expect that $r_{j}$ is small, so hopefully the first term is small
$$H_{f}≈ \sum\limits_{j=1}^{m}\nabla r_{j}(x)\nabla r_{j}(x)^{T}$$
Which is very nice since this is much simpler to compute than the first term.

So the idea is to approximate the Hessian in this way and then apply a line search or a trust region method.

## Gauss-Newton method

Denote $J(x)\in \mathbb{R}^{m \times d}$ the Jacobian of $r$. Then we can write this nicely as
$$\begin{align*}
\nabla f(x)&= J(x)^{T}\cdot r(x)\\
	H_{f}(x) &= J(x)^{T}J(x)+\sum\limits_{j=1}^{m}r_{j}(x)H_{r_{j}}(x)\\
&≈J(x)^{T}J(x)
\end{align*}$$
With line search method we get
* in step k:
	* compute search direction $p_{k}$ by solving 
	  $J(x_{k})^{T}J(x_{k})\cdot p=-J(x_{k})^{T}r(x_{k})$
	* choose a suitable step length $\alpha_{k}>0$
	* $x_{k+1}=x_{k}+\alpha _{k}p_{k}$

One can show that this works. 
	E.g. $\nabla f(x_{k})\to0$  provided that the singular values of $J(x_{k})$ are bounded away from zero.

## Ledenburg-Maquardt method

Trust region:
	In step k we use the model function
	$m_{k}(p)=f(x_{k})+{\left\langle \nabla f(x_{k}) \text{ , } p \right\rangle}+ \frac{1}{2}{\left\langle p \text{ , } J(x_{k})^{T}J(x_{k})p \right\rangle}$
	$=\frac{1}{2}\lVert r(x_{k}) \rVert^{2}+{\left\langle J(x_{k})^{T}r(x_{k}) \text{ , } p \right\rangle}+ \frac{1}{2}{\left\langle p \text{ , } J(x_{k})^{T}J(x_{k})p \right\rangle}$ 
	$=\frac{1}{2}\lVert r(x_{k}) \rVert^{2}+{\left\langle J(x_{k})^{T}r(x_{k}) \text{ , } p \right\rangle}+ \lVert J(x_{k})p \rVert^{2}$
	$= \frac{1}{2}\lVert r(x_{k}) +J(x_{k})p \rVert^{2}$
	$= \frac{1}{2}\lVert g(x_{k})+J(x_{k})p-y \rVert^{2}$
	Where $g(x_{k})+J(x_{k})p$   is a a linearisation of $g$ around $x_{k}$   (first order taylor)
	
In step k we linearise $g$ around $x_{k}$
	And then solve a *linear* least squares problem subject to the trust region constraints.
	

### Remarks
* Advantages
	* Do not need the Hessian $H_{g}\quad\implies\quad$ can save a *lot* of computation
		* Applicable in high dimensions, for example neural networks
* But:
	* Have to solve
	  $J(x_{k})^{T}J(x_{k})p=J(x_{k})^{T}r(x_{k})$
	  in each step
	  Can be done (approximately) by using the Conjugate Gradient method
In neural networks: should stop the iteration well before convergence to avoid overfitting.
