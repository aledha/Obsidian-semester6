## Example, nonzero duality gap
Consider the problem 
$$\min_\limits{x \in \mathbb{R}}- \frac{1}{x^{2}+1}\qquad\text{s.t.}\quad x^{2}\ge1$$
#insert graph
Solutions are $x^{*}=\pm 1$.

Also $x^{*}$ is a [[KKT-conditions|KKT]] point with Lagrange parameter $\lambda^{*} = \frac{1}{4}$.

Now: compute the dual problem:
$$\mathcal{L}(x,\lambda )= -\frac{1}{x^{2}+1}-\lambda (x^{2}-1)$$
The dual objective function is
$$q(\lambda )=\min_\limits{x \in \mathbb{R}}\left[-\frac{1}{x^{2}+1} -\lambda (x^{2}-1)\right]$$
$$=\begin{cases}
-\infty & \quad\text{for }\lambda >0 \\
-1+\lambda  & \quad\text{for }\lambda \le0
\end{cases}$$
$\quad\implies\quad$ the dual problem is
$$\max_\limits{\lambda\ge0 }q(\lambda )\quad\Leftrightarrow\quad \max_\limits{}-1+\lambda  \qquad\text{s.t.}\quad \lambda =0$$
Solution is $\lambda ^{*}=0$. With $q(\lambda ^{*})=-1$.
$\implies\quad$ The optimal function value for the primal problem $= - \frac{1}{2}>$ optimal value for the dual problem $=-1$.
And: no relation between the dual solution and the optimal Lagrange parameter.
Note: this is a problem with **non-convex** constraints.

### With convex programme
Now consider a convex programme
$$\min_\limits{x}f(x) \qquad\text{s.t.}\quad \begin{cases}
c_{i}(x)\ge0,\quad i \in \mathcal{I} \\
A_{1}x\ge b_{1}, \\
A_{2}x=b_{2}.
\end{cases}$$
with $f$ convex, $c_{i}$ concave, and $A_{i} \in \mathbb{R}^{m_{i}\times d}, b_{i}\in \mathbb{R}^{m_{i}}$.

Recall:
[[Slater's constraint qualification]] holds if there exists $x \in \mathbb{R}^{d}\qquad\text{s.t.}\quad$
$$A_{1}x\ge b_{1},\quad A_{2}x=b_{2},\quad \text{and }c_{i}(x)>0\quad\forall\quad i \in \mathcal{I}.$$
## Duality theorem 
Assume that $f$ is convex and Slater's constraint qualification holds, and that $\inf_\limits{x}p(x)>-\infty$, where $p(x)$ is the primal problem.
Then the dual problem has a solution $\lambda ^{*}$, and the duality gap is 0.
If the primal problem has any solution $x^{*}$, then $(x^{*},\lambda ^{*})$ is a saddle point of the Lagrangian.
If, in addition, $f$ and $c_{i}$ are differentiable, then $x^{*}$ is a KKT point with Lagrange multiplier $\lambda ^{*}$.

### Example:
Elastic net regression
$$\min_\limits{x} \frac{1}{2}\lVert Ax-b \rVert^{2}_{2}+ \alpha \lVert x \rVert_{1} \frac{\beta }{2}\lVert x \rVert^{2}_{2}$$
with $A \in \mathbb{R}^{m \times d},\quad  b \in \mathbb{R}^{m}$  with ($d>>m$) and $\alpha , \beta >0$.

Can rewrite this as
$$\min_\limits{x,y} \frac{1}{2}\lVert Ax-b \rVert^{2}_{2}+\alpha \lVert y \rVert_{1}+ \frac{\beta}{2}\lVert x \rVert^{2}_{2}\qquad\text{s.t.}\quad x=y$$
have a convex problem with linear and feasible.
$\implies\quad$ The duality theorem applies.
**Computing the dual problem**
$$q(\lambda )=\min_\limits{x,y}\left[\frac{1}{2}\lVert Ax-b \rVert_{2}^{2}+\alpha \lVert y \rVert_{1}+ \frac{\beta }{2}\lVert x \rVert^{2}_{2}- \left\langle \lambda  \text{ , } x-y \right\rangle \right]$$
$$\begin{align*}
&= \min_\limits{x}\left[\frac{1}{2}\lVert Ax-b \rVert_{2}^{2}+ \frac{\beta }{2}\lVert x \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x \right\rangle \right]+\min_\limits{y} \left[\alpha \lVert  y\rVert_{1}+\left\langle \lambda  \text{ , } y \right\rangle \right]\\
&=:q_{1}(\lambda )+q_{2}(\lambda ) 
\end{align*}$$
From [[Lagrangian duality]] we computed
$$q_{2}(\lambda )=\begin{cases}
-\infty & \quad\text{for }\lVert \lambda  \rVert_{\infty}>\alpha  \\
0 & \quad\text{else}
\end{cases}$$
Now let us compute
$$q_{1}(\lambda )=\min_\limits{x}\left[\frac{1}{2}\lVert Ax-b \rVert_{2}^{2}+ \frac{\beta }{2}\lVert x \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x \right\rangle \right]$$
Solution of $q_{1}$ is attained at $x_\lambda$ satisfying
$$A^{T}(Ax_{\lambda} -b)+\beta x_{\lambda }-\lambda =0$$
that is,
$$x_\lambda =(A^{T}A+\beta I)^{-1}(A^{T}b+\lambda )$$
and 
$$q_{1}(\lambda )= \frac{1}{2}\lVert Ax_\lambda -b \rVert_{2}^{2}+ \frac{\beta }{2}\lVert x_\lambda  \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x_\lambda  \right\rangle$$
$\implies\quad$ the dual problem becomes
$$\max_\limits{\lambda }\left[\frac{1}{2}\lVert Ax_{\lambda }-b \rVert_{2}^{2}+ \frac{\beta }{2}\lVert x_{\lambda } \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x \right\rangle \right]\qquad\text{s.t.}\quad \lVert \lambda  \rVert_{\infty}\le \alpha $$
where $x_\lambda =(A^{T}A+\beta I)^{-1}(A^{T}b+\lambda )$. The inequality comes from $q_{2}$.

The duality theoerem tells us that there exists a saddle point $(x^{*},y^{*},\lambda ^{*})$ of the Lagrangian.
Here:
* $\lambda ^{*}$ solves the dual problem
* $(x^{*},y^{*})$ solves the primal problem
**But**
$(x^{*}.y^{*})$ also minimises $\mathcal{L}(x,y,\lambda ^{*})$,
where $\lambda ^{*}$ solves the dual problem.

So $x^{*}=x_{\lambda ^{*}}=(A^{T}A+\beta I)^{-1}(A^{T}b+\lambda ^{*})$. 

Can solve the dual problem by projected gradient ascent:
$$\begin{align*}
\hat \lambda _{k+1}&= \lambda _{k}+ \tau \nabla _{}q_{1}(\lambda _{k}),\\
\lambda _{k+1}&= \pi _\Omega (\hat \lambda _{k+1}),
\end{align*}$$
with $\Omega =\{\lambda :\lVert \lambda  \rVert_{\infty}\le \alpha  \}$. We will now compute the individual parts of the algorithm.

**Computation of $\nabla q_{1}(\lambda _{k})$:**
$$\begin{align*}
q_{1}(\lambda )&= \min_\limits{x}\left[\frac{1}{2}\lVert Ax-b \rVert_{2}^{2}+ \frac{\beta }{2}\lVert x \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x \right\rangle \right]\\
	&=: \min_\limits{x}g(x,\lambda )
\end{align*}$$
So $q_{1}(\lambda )=g(x_\lambda ,\lambda )$ with $\nabla _{x}g(x_{\lambda },\lambda )=0$.
$$\begin{align*}
\implies\quad \nabla q_{1}(\lambda) &=  D_{\lambda} g(x_{\lambda} ,\lambda )^{T}\\
&= (D_{\lambda }x_{\lambda })^{T}\nabla _{x}g(x_{\lambda },\lambda )+ \nabla _{\lambda }g(x_{\lambda },\lambda )\\
&= \nabla _{\lambda }g(x_{\lambda },\lambda )=-x_{\lambda }
\end{align*}$$

**Computation of $\pi _\Omega (\lambda )$**
$$\begin{align*}
(\pi _{\Omega }(\lambda ))_{i}&= \begin{cases}
-\alpha  & \quad\text{for }\lambda _{i}<\alpha  \\
\lambda _{i} & \quad\text{for }-\alpha \le \lambda _{i}\le \alpha  \\
\alpha  & \quad\text{for }\lambda _{i}>\alpha .
\end{cases}\\
	&= \max_\limits{}\{\min_\limits{}\{\lambda _{i},\alpha  \},-\alpha  \}
\end{align*}$$
Now the gradient ascent becomes:
In each iteration:
	$x_\lambda =(A^{T}A+\beta I)^{-1}(A^{T}b+\lambda )$
	$\hat \lambda =\lambda -\tau x_{\lambda }$
	$\lambda =\max_\limits{}\{\min_\limits{}\{\lambda _{i},\alpha  \},-\alpha  \}$

Have **convergence** if $0<\tau <2\beta$.
And: can use the "duality gap" as  stopping criterion:
	We always have that 
	$$p(x_{\lambda })\ge p(x^{*})= q(\lambda ^{*})\ge q(\lambda )$$
	$\implies\quad p(x_{\lambda })-q(\lambda )=p(x_{\lambda })-p(x^{*})+q(\lambda ^{*})-q(\lambda )$
	$\implies\quad p(x_{\lambda })-q(\lambda )$ is an indicator for how close we are to solving both the primal and dual problem.
	$\implies\quad$ choose some $\epsilon >0$ and stop the iteration when $p(x_{\lambda })-q(\lambda )<\epsilon$.

**Note**
$p(x_{\lambda })-q(\lambda )=\alpha \lVert x_{\lambda } \rVert-\left\langle \lambda  \text{ , } x_{\lambda } \right\rangle$
