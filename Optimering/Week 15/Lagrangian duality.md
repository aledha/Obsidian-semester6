**Goal**: 
Develop a method for the solution of non-smooth optimization problems.

For example, non-smooth regression:
	Given $A \in \mathbb{R}^{m \times d}$, and data $b \in \mathbb{R}^{m}$,
	try to find $x \in \mathbb{R}^{d}$ such that
	$Ax≈b$.

Particularly consider the case $m<<d$.
$\implies\quad$ Minimise a functional of the form
	$\frac{1}{2}\lVert Ax-b \rVert^{2}_{2} + \alpha \lVert x \rVert_{1}+ \frac{\beta }{2}\lVert x \rVert^{2}_{2}$,               where $\alpha , \beta >0$.
	Called "elastic net regression".

Problem:
$\lVert x \rVert_{1}=\sum\limits_{i=1}^{d}\lvert x_{i} \rvert$    is non differentiable in all points $x$ with $x_{i}=0$ for some $i \in \{1,\dots,d \}$ 

Consider agian one constrained optimization problem
$$\min_\limits{}f(x) \qquad\text{s.t.}\quad \begin{align*}
c_{i}(x)&\ge 0 \quad\text{for }i\in \mathcal{I}\\
c_{i}(x)&= 0 \quad\text{for }i \in \xi 
\end{align*}$$
If constraint qualifications holds, KKT conditions are necessary optimality conditions:
$$\nabla f(x^{*})-\sum\limits_{i \in \xi \cup \mathcal{I} }^{}\lambda _{i}^{*}\nabla c_{i}(x^{*})=0 \quad\text{for }\quad \begin{align*}
c_{i}(x)&\ge 0 \quad\text{for }i\in \mathcal{I}\\
c_{i}(x)&= 0 \quad\text{for }i \in \xi 
\end{align*}$$
$\lambda _{i}^{*}\ge0 \quad\text{for }i \in \mathcal{I}$,    $\lambda _{i}^{*}c_{i}(x^{*})=0 \quad\text{for }i \in \mathcal{I}$

$$\nabla _{x}\mathcal{L}(x^{*},\lambda ^{*})=\nabla f(x^{*})-\sum\limits_{i \in \xi \cup \mathcal{I} }^{}\lambda _{i}^{*}\nabla c_{i}(x^{*})$$
with 
$$\mathcal{L}(x,\lambda )=f(x)-\sum\limits_{i \in \xi \cup \mathcal{I} }^{}\lambda _{i}c_{i}(x).$$

Now: consider again the Lagrangian
$$\mathcal{L}(x,\lambda )= f(x)-\sum\limits_{i \in \xi \cup \mathcal{L}}^{}\lambda _{i}c_{i}(x)$$
and define 
$$p(x)=\sup_\limits{\lambda \in \mathbb{R}^{\xi \times \mathcal{I}}}\mathcal{L}(x,\lambda )\qquad\text{s.t.}\quad \lambda _{i}\ge0\quad\text{for }i \in \mathcal{I}$$
Then if $c_{i}(x)<0$ for some $i \in \xi \cup \mathcal{I}$, we can choose $\lambda _{i}$ arbitrarily large and get
$$p(x)=+\infty.$$
If $c_{i}(x)>0$ for some $i \in \xi$, we can choose $\lambda _{i}<0$ arbitrarily small and get
$$p(x)=+\infty$$
on the other hand, if $x$ satisfies all constraints, then 
$$\mathcal{L}(x, \lambda )= f(x) -\sum\limits_{i \in \xi}^{}\lambda _{i}c_{i}(x) - \sum\limits_{i \in \mathcal{I}}^{}\lambda _{i}c_{i}(x)$$
Where the first sum is zero, and the second sum is negative, since $\lambda _{i},c_{i}\ge0$
We then get
$$\mathcal{L}(x, \lambda )\le f(x)$$
Then, 
$$p(x)=\begin{cases}
+\infty & \quad\text{if } x \text{ is infeasible} \\
f(x) & \quad\text{if } x \text{ is feasible}
\end{cases}$$
$\implies\quad$ the problem 
$$\min\limits_{x \in \mathbb{R}^{d}}p(x)$$
is equivalent to the original constrained problem.
The original problem can be written as
$$\min_\limits{x \in \mathbb{R}} \qquad \max_\limits{\lambda \in \mathbb{R}^{\xi \times \mathcal{I}}, \lambda _{i}\ge0, i \in \mathcal{I}}\mathcal{L}(x, \lambda )\tag{P}$$
(P for primal)
**Idea of duality**: reverse the order of minimisation and maximisation. 

## Dual problem
Define the **dual problem** as
$$\max_\limits{\lambda \in \mathbb{R}^{\xi \times \mathcal{I}},\lambda _{i}>0,i \in \mathcal{I}}\min_\limits{x \in  \mathbb{R}^{d}}\mathcal{L}(x, \lambda )\tag{D}$$
More explicitly: define
$$q(\lambda )=\inf_\limits{x \in \mathbb{R}^{d}}\mathcal{L}(x,\lambda )$$
and then solve
$$\max_\limits{\lambda \in \mathbb{R}^{\xi \times \mathcal{I}},\lambda _{i}>0,i \in \mathcal{I}}q(\lambda )$$
### Example (duals of linear programmes)
Consider the linear programme 
$$\min_\limits{}c^{T}x \qquad\text{s.t.}\quad Ax\ge b$$
$$\mathcal{L}(x, \lambda )=c^{T}x - \lambda ^{T}(Ax-b)$$
Primal problem:
$$\min_\limits{x}\max_\limits{\lambda \ge0}\mathcal{L}(x, \lambda )$$
Dual problem:
$$\max_\limits{\lambda \ge 0}\min_\limits{x}\mathcal{L}(x, \lambda )=:\max_\limits{\lambda \ge 0}q(\lambda )$$
So
$$q(\lambda )=\min_\limits{x} \left[c^{T}x-\lambda ^{T}(Ax-b) \right]$$
$$\begin{align*}
&= \lambda ^{T}b+\min_\limits{x}\left[(c^{T}-\lambda ^{T}A)x \right]\\
&= \lambda ^{T}b + \begin{cases}
0  & \quad\text{for }\quad c^{T}=\lambda ^{T}A\\
-\infty & \quad\text{for }\quad c^{T}≠\lambda ^{T}A
\end{cases}
\end{align*}$$
The dual problem is
$$\max_\limits{}q(\lambda )\qquad\text{s.t.}\quad \lambda \ge0$$
$$\Leftrightarrow\quad \max_\limits{}b^{T}\lambda \qquad\text{s.t.}\quad \begin{align*}
A^{T}\lambda &= c\\
\lambda &\ge 0
\end{align*}$$

## $l_{1}$ regression
Given $b \in \mathbb{R}^{d}$ and $\alpha >0$, minimize
$$\frac{1}{2}\lVert x-b \rVert^{2}_{2}+\alpha \lVert x \rVert_{1}$$
Can rewrite this as
$$\min_\limits{x,y} \frac{1}{2}\lVert x-b \rVert^{2}_{2} + \alpha \lVert y \rVert_{1}\qquad\text{s.t.}\quad x=y$$
Obtain the Lagrangian
$$\mathcal{L}(x,y,\lambda )= \frac{1}{2}\lVert x-b \rVert^{2}_{2}+\alpha \lVert y \rVert_{1}-\left\langle \lambda  \text{ , } x-y \right\rangle$$
Dual problem:
$$\max_\limits{ \lambda \in \mathbb{R}^{d}}\min_\limits{x,y \in \mathbb{R}^{d}}\left[\frac{1}{2} \lVert x-b \rVert^{2}_{2}+ \alpha \lVert y \rVert_{1}-\left\langle \lambda  \text{ , } x-y \right\rangle \right]=:\min_\limits{\lambda \in \mathbb{R}^{d}}q(\lambda )$$
$$q(\lambda )=\min_\limits{x,y}\left[ \frac{1}{2}\lVert x-b \rVert_{2}^{2}+\alpha \lVert y \rVert_{1}-\left\langle \lambda  \text{ , } x-y \right\rangle \right]$$
$$=\min_\limits{x} \left[ \frac{1}{2}\lVert x-b \rVert_{2}^{2}-\left\langle \lambda  \text{ , } x \right\rangle\right]+\min_\limits{y} \left[\alpha \lVert y \rVert_{1}+ \left\langle y \text{ , } y \right\rangle\right] $$
$$=:q_{1}(\lambda )+q_{2}(\lambda )$$
$q_{1}$: solution of the min-problem is attained for $x_\lambda =\lambda +b$ with value
$$\begin{align*}
q_{1}(\lambda )&=  \frac{1}{2}\lVert x_\lambda -b \rVert^{2}_{2}-\left\langle \lambda  \text{ , } x_\lambda  \right\rangle\\
	&= \frac{1}{2}\lVert \lambda  \rVert_{2}^{2}-\left\langle \lambda  \text{ , } \lambda +b \right\rangle\\
&= - \frac{1}{2}\lVert \lambda  \rVert_{2}^{2}-\left\langle \lambda  \text{ , } b \right\rangle
\end{align*}$$
$q_{2}$:
$$\begin{align*}
		q_{2}(\lambda )&= \min_\limits{y}\left[\alpha \lVert y \rVert_{1}+\left\langle \lambda  \text{ , } y \right\rangle \right]\\
&= \min_\limits{y}\sum\limits_{i=1}^{d}\left(\alpha \lvert y_{i} \rvert+\lambda _{i}y_{i} \right)\\
&= \sum\limits_{i=1}^{d}\min_\limits{y}(\alpha \lvert y_{i} \rvert +\lambda _{i}y_{i})\\
&= \sum\limits_{i=1}^{d}\begin{cases}
0 & \quad \text{if }\alpha &\ge \lvert \lambda _{i} \rvert\\
-\infty & \quad \text{if }\alpha &< \lvert la_{i} \rvert
\end{cases}\\
&= \begin{cases}
0 & \quad \text{if }\alpha &\ge \lvert \lambda _{i} \rvert \quad\forall\quad i\\
-\infty & \quad \text{if }\alpha &< \lvert la_{i} \rvert \quad\forall\quad i
\end{cases}\\
&= \begin{cases}
0 & \quad \text{if }\alpha &\ge \lVert \lambda  \rVert_{\infty}\\
-\infty & \quad \text{if }\alpha &< \lVert \lambda  \rVert_{\infty}
\end{cases}
\end{align*}$$
The dual problem becomes 
$$\max_\limits{\lambda }\left[- \frac{1}{2}\lVert \lambda  \rVert^{2}_{2}-\left\langle \lambda  \text{ , } b \right\rangle \right] \qquad\text{s.t.}\quad \lVert \lambda  \rVert_{\infty}\le \alpha $$

### Relation between primal and dual problem
##### Lemma
For all $x \in \mathbb{R}^{d}$ and all $\lambda \in \mathbb{R}^{\xi  \times \mathcal{I}}$ with $\lambda _{i}\ge 0 \quad\text{for }i \in \mathcal{I}$, we have
$$p(x)\ge q(\lambda )$$
In particular,
$$\min_\limits{x}\max_\limits{\lambda , \lambda _{i}\ge0,i \in \mathcal{I}}\mathcal{L}(x,\lambda )\ge \max_\limits{\lambda _{i}\ge0, i \in \mathcal{I}}\min_\limits{x}\mathcal{L}(x,\lambda )$$
**Proof**
This is a consequence of the general result:
If $h: X \times Y \to \mathbb{R}$, where $X,Y$ are non-empty sets, then
$$\inf_\limits{x}\sup_\limits{y}h(x,y)\ge \sup_\limits{y}\inf_\limits{x}h(x,y)$$
Idea of proof (if all problems admits a solution)
Denote $\hat x(y)$ a solution of 
$$\min_\limits{x}h(x,y) \quad\text{for }\text{fixed }y$$
Then 
$$\sup_\limits{y}\inf_\limits{x}h(x,y)=\sup_\limits{y}h(\hat x(y),y)\le \sup_\limits{y}h(x,y)\quad\forall\quad x$$
This still holds if we take the infimum over $x$.

### Definition: The *duality gap*
The number
$$d:=\inf_\limits{x}p(x)-\sup_\limits{\lambda_{i}\ge0,i \in \mathcal{I} }q(\lambda )$$

### Definition: Saddle point
A point $(x^{*},\lambda ^{*})$ is called a *saddle point* of the Lagrangian if
$$\mathcal{L}(x^{*},\lambda )\le\mathcal{L}(x^{*},\lambda ^{*})\le \mathcal{L}(x, \lambda ^{*})$$
for all $x \in \mathbb{R}^{d}$ and $\lambda \in \mathbb{R}^{\xi \times \mathcal{I}}$ with $\lambda _{i}\ge0,\quad i \in \mathcal{I}$.

### Theorem
Assume that $(x^{*},\lambda ^{*})$ is a saddle point of the Lagrangian, then $x^{*}$ solves the primal problem, and $\lambda ^{*}$ solves the dual problem. The complimentarity condition 
$$\lambda _{i}^{*}c_{i}(x^{*})=0 \quad\forall\quad i \in \mathcal{I} $$
holds. If $f$ and $c_{i}$ are differentiable, then $x^{*}$ is a KKT-point with a corresponding lagrange mulitplier $\lambda ^{*}$.
