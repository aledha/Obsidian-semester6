Consider a non-quadratic optimization problem with non-linear equality constraints:
$$\min_\limits{x}f(x) \qquad\text{s.t.}\quad c_{i}(x)=0 \quad\forall\quad i\in \xi \tag{P}$$
If $x^{*}$ is a local solution where [[LICQ]] holds, then $x^{*}$ solves the [[KKT-conditions]] system. 
That is, there exists $\lambda_{i} ^{*} \qquad\text{s.t.}\quad$
$$\nabla f(x^{*})-\sum\limits_{i\in \xi }^{}\lambda ^{*}_{i}\nabla c_{i}(x^{*})=0 \qquad\text{s.t.}\quad c_{i}(x^{*})=0 \quad\text{for }i\in \xi .$$
Or, collect the equations in some vector function $c:\mathbb{R}^{d}\to \mathbb{R}^{\xi }$   with Jacobian $A(x)\in \mathbb{R}^{\xi \times d}$.
Then,
$$\nabla f(x^{*})-A(x^{*})^{T}\lambda ^{*}=0, \quad \text{and }c(x^{*})=0.$$
Apply Newtons method for the solution of this non-linear system.
Idea: First order Taylor expansion and solve the linearized system.

Given $x_{k}, \lambda _{k}$, we define 
$$x_{k+1}=x_{k}+p_{k}\qquad \text{and}\qquad \lambda _{k+1}=\lambda _{k}+q_{k},$$
where $p_{k},\lambda _{k}$ solve the linearised system
$$\nabla f(x_{k})+H_{f}(x_{k})\cdot p -\sum\limits_{i\in \xi }^{}\lambda _{i,k}(\nabla c_{i}(x_{k})+H_{c_{i}}(x_{k})p_{k})-\sum\limits_{i\in \xi }^{}q_{i}\nabla c_{i}(x_{k})=0,$$
and $c(x_{k})+A(x_{k})p=0$.
Here, $k$ refers to step, $i$ refers to component.
$H_{f}(x_{k})p-\lambda _{i,k}H_{c_{i}}p=H_\mathcal{L} (x_{k},\lambda _{k})$, so this can be rewritten to
$$H_\mathcal{L} (x_{k},\lambda _{k})p-A(x_{k})^{T}q=-\nabla f(x_{k})+A(x_{k})^{T}\lambda _{k},$$
and $A(x_{k})p=-c(x_{k})$.

In matrix form:
$$\begin{bmatrix}H_\mathcal{L}(x_{k},\lambda _{k}) & -A(x_{k})^{T} \\ A(x_{k}) & 0 \end{bmatrix}\begin{bmatrix}p \\ q\end{bmatrix}=-\begin{bmatrix}f(x_{k}) -A(x_{k})^{T}\lambda _{k} \\ c(x_{k}) \end{bmatrix}$$
If $f, c_{i}$ are sufficiently smooth, and the matrix $\begin{bmatrix}H_\mathcal{L}(x^{*},\lambda _{k}) & -A(x^{*})^{T} \\ A(x^{*}) & 0 \end{bmatrix}$ is non-singular, then the iteration converges locally quadratically towards a solution.

If [[LICQ]] holds at $x^{*}$ and the matrix $H_\mathcal{L}(x^{*},\lambda ^{*})$ is positive definite on $\text{ker}A(x^{*})$,
	(which are precisely the second order optimality conditions.)
then the matrix is non-singular $\quad\implies\quad$ local quadratic convergence.

## Global convergence

But we want **global convergence**, so would like to combine this with some line search.
Challenge: decrease of function values does not indicate whether a step is reasonable.
	Need to include the constraints as well.

Try to find a **merit function**, that combines the cost function $f$, and the equations $c_{i}(x)=0$ in a way that works for the line search. That is: a function with $x^{*}$ as a local minimiser such that the Newton direction $p_{k}$ is a descent direction.

### $\Phi _{1}$ merit function
$$\Phi _{1}(x,\mu )=f(x) +\mu \sum\limits_{i\in \xi }^{}\lvert c_{i}(x) \rvert$$
$$=f(x)+\mu \lVert c_{i}(x) \rVert_{1}$$
### Lemma
Assume that $x^{*}$ is a KKT point with Lagrange parameter $\lambda ^{*}\qquad\text{s.t.}\quad$ LICQ holds at $x^{*}$ and the that the second order optimality conditions holds. Then $x^{*}$ is a local minimiser of $\Phi _{1}$,    if $\mu >\lVert \lambda ^{*} \rVert_{\infty}$.

Idea of proof:
	if $x$ is close to $x^{*}\qquad\text{s.t.}\quad c(x)=0$, then
		$\Phi _{1}(x,\mu )=f(x)>f(x^{*})=\Phi _{1}(x^{*},\mu )$.
		If $x$ is close to $x^{*} \qquad\text{s.t.}\quad c(x)≠0$, then
		$$\Phi _{1}(x,\mu )=f(x)+\mu \sum\limits_{i\in \xi }^{}\lvert c_{i}(x) \rvert$$
		$$≈f(x^{*})+{\left\langle \nabla f(x^{*}) \text{ , } x-x^{*} \right\rangle}+\mu \sum\limits_{i\in \xi }^{}\lvert c_{i}(x) \rvert$$
		$$=\sum\limits_{i\in \xi }^{}\lambda _{i}^{*}\nabla c_{i}(x^{*})$$
		$$f(x^{*})+\sum\limits_{i\in \xi }^{}(\lambda _{i}^{*} {\left\langle \nabla c_{i}(x^{*}) \text{ , } x-x^{*} \right\rangle}+\mu \lvert c_{i}(x) \rvert)$$
		$$≈c_{i}(x)-c_{i}(x^{*})=c_{i}(x)$$
		$$≈f(x^{*})+\sum\limits_{i\in \xi }^{}(\lambda _{i}^{*}c_{i}(x)+\mu \lvert c_{i}(x) \rvert)$$
		since $\mu >\lambda _{i}^{*}\quad\forall\quad i,$  and everything we sum over is larger than $0$, we have
		$$>f(x^{*})=\Phi _{1}(x^{*},\mu )$$
##### End "proof"

For Armijo line search, we will need a derivative of $\Phi _{1},$ but this is problematic since $\Phi _{1}$ is not differentaible.
Instead consider the one-sided derivative 
$$D \phi _{1}(x,\mu ;p)=\lim_\limits{t \to 0^{+}} \frac{1}{t} (\Phi _{1}(x+tp ,\mu )-\Phi _{1}(x,\mu ))$$

### Lemma
Assume that $p_{k}$ satisfies 
$$c_{i}(x_{k})+{\left\langle \nabla c_{i}(x_{k}) \text{ , } p_{k} \right\rangle}=0.$$
Then,
$$D \Phi _{1}(x_{k},\mu ;p_{k})={\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle}-\mu \lVert c_{}(x_{k}) \rVert_{1}$$

**Proof**
	$$\Phi _{1}(x_{k}+tp_{k},\mu )=f(x_{k}+tp_{k})+\mu \sum\limits_{i\in \xi }^{}\lvert c_{i}(x_{k}+tp_{k}) \rvert$$
$$=f(x_{k})+t {\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle}+\mathcal{O}(t)+ \mu \sum\limits_{i\in \xi }^{}\lvert c_{i}(x_{k}) +t {\left\langle \nabla c_{i}(x_{k}) \text{ , } p_{k} \right\rangle} + \mathcal{O}(t)\rvert \tag{*}$$
	Where the second inner product, ${\left\langle \nabla c_{i}(x_{k}) \text{ , }  p_{k}\right\rangle}=-c_{i}(x_{k})$, so we get
	$$=f(x_{k})+t {\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle}+\mathcal{O}(t)+\mu \sum\limits_{i\in \xi }^{}\lvert (1-t) c_{i}(x_{k})+\mathcal{O}(t)\rvert$$
	Now, $\lvert (1-t)c_{i}(x_{k})+\mathcal{O}(t) \rvert \stackrel{\text{small } t}{\le}  (1-t)\lvert c_{i}(x_{k}) \rvert+\mathcal{O}(t)$
	and  $\lvert (1-t)c_{i}(x_{k}) + \mathcal{O}(t) \rvert\ge (1-t)\lvert c_{i}(x_{k}) \rvert-\mathcal{O}(t)$
	Thus:
	$$(*)=f(x_{k})+t {\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle} + \mu (1-t)\sum\limits_{i\in \xi }^{}\lvert c_{i}(x_{k}) \rvert+\mathcal{O}(t)$$
	for small t.
	Then,
	$$D \Phi _{1}(x_{k},\mu ; p_{k})=\lim_\limits{t \to 0^{+}} \frac{1}{t}(\Phi _{1}(x_{k}+tp_{k},\mu )-\Phi _{1}(x_{k}, \mu ))$$
	$$=\lim_\limits{t \to 0^{+}} \frac{1}{t} (t {\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle}- \mu t \lVert c(x_{k}) \rVert_{1}+ \mathcal{O}(t))$$
	$$={\left\langle \nabla f(x_{k}) \text{ , } p_{k} \right\rangle}- \mu \lVert c(x_{k}) \rVert_{1}$$
	$\square$.

## SQP Method

1.  Choose initial guess $x_{0}$ and contraction factor $1>\rho  > 0$. and $1>c>0$
2.  Choose initial value $\mu > 0$, set $k = 0$.
3.  Repeat until convergence: 
	1. Set $R_{k}(p,q)=\begin{bmatrix}H_\mathcal{L}(x_{k},\lambda _{k}) & -A(x_{k})^{T} \\ A(x_{k}) & 0 \end{bmatrix}\begin{bmatrix}p \\ q\end{bmatrix}+\begin{bmatrix}f(x_{k}) -A(x_{k})^{T}\lambda _{k} \\ c(x_{k}) \end{bmatrix}$
	2. a. Compute $p_{k}$ and $q_{k}$ by solving the linearised system $R_{k}(p_{k},q_{k})=0$. 
	3. b. Use backtracking line search to find step size $\alpha_{k}$. 
		1. Set $\alpha =1$
		2. While $\Phi _{1}(x_{k}+\alpha p_{k};\mu )>\Phi _{1}(x_{k};\mu )+ \alpha c D \Phi _{1}(x_{k},\mu ,p_{k})$
			1. $\alpha =\rho \alpha$
	4. Set $x_{k+1} = x_{k} + \alpha_{k}p_{k}$ and $\lambda_{k+1} = \lambda_{k} + q_{k}$. 
5.  Return $x_{k+1}$.

Note:
	It can happen that $\alpha =1$ never satisfies the Armijo condition
		It can happen that we lose convergence of the line search.

There exist quasi-Newton modifications of this idea, but they are more technical.