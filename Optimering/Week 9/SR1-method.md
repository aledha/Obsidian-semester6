Requirement:
$B_{k+1}-B_{k}$ is a (symmetric) rank-one matrix.

Define 
$$B_{k+1}=B_{k}+\sigma vv^{T}$$
With $v\in\mathbb{R}^{d}$ and $\sigma=\{\pm 1 \}$  in such a way that
$$B_{k+1}s_{k}=y_{k}\tag{*}$$
Remember that $s_{k}:=x_{k+1}-x_{k}$  and $\nabla f(x_{k+1})-\nabla f(x_{k})=y_{k}$

Denote $ab^{T}= a\otimes b$ 
$(*)$ implies that
$$(B_{k}+\sigma v \otimes v)s_{k}=y_{k}\quad \text{or}$$
$$y_{k}-B_{k}s_{k}=\sigma {\left\langle v ,s_{k}\right\rangle}\cdot v$$
Where the dimensions are $\mathbb{R}^{d}-\mathbb{R}^{d}=\mathbb{R} \cdot \mathbb{R}^{d}$. This implies that
$$v=\delta(y_{k}-B_{k}s_{k})\quad\text{for some }\delta\in \mathbb{R}$$
$$\begin{align*}
y_{k}-B_{k}s_{k}&=  \sigma {\left\langle \delta(y_{k}-B_{k}s_{k}),\quad s_{k} \right\rangle}\delta(y_{k}-B_{k}s_{k})\\
&= \sigma \delta^{2} {\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}\cdot(y_{k}-B_{k}s_{k})
\end{align*}$$
This implies that 
$$\sigma \delta^{2}{\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}=1$$
Since $\sigma\in \{\pm1 \}$, we need
$$\begin{align*}
\sigma&= \text{sign}({\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle})\\
\delta&= |{\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}|^{-1/2}
\end{align*}$$
so that
$$\sigma \delta^{2}= \frac{\text{sign}({\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle})}{|{\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}|}= \frac{1}{{\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}}$$
Obtain that
$$B_{k+1}=B_{k}+ \frac{(y_{k}-B_{k}s_{k}) \otimes (y_{k}-B_{k}s_{k})}{{\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}}$$
Assuming that ${\left\langle y_{k}-B_{k}s_{k},s_{k} \right\rangle}≠0$.

## Method
Choose some $B_{0}\in \mathbb{R}^{d \times d}$, for example $B_{0}=I$
for $k=0,1,\dots$:
	compute $p_{k}=-B_{k}^{-1}\nabla f(x_{k})$
	find a suitable step length $\alpha_{k}>0$ (Wolfe/backtracking etc..)
	set $x_{k+1}=x_{k}+\alpha_{k} p_{k}$
	set $s_{k}=x_{k+1}-x_{k},\qquad y_{k}=\nabla f(x_{k+1})-\nabla f(x_{k})$
	set $z_{k}=y_{k}-B_{k}s_{k}$
	update $B_{k+1}=B_{k}+ \frac{z_{k} \otimes z_{k}}{{\left\langle z_{k},s_{k} \right\rangle}}$ 

Probably the most expensive part is solving the linear system, $p_{k}=-B_{k}^{-1}\nabla f(x_{k})$.

Next idea: Try to approximate the inverse of the inverse of the Hessian
$\Rightarrow\quad$ try to work with $H_{k}=B_{k}^{-1}$ instead

## Lemma: Sherman-Morrison-Woodbury formula
Assume $B\in\mathbb{R}^{d \times d}$ is non-singular and $a,b\in \mathbb{R}^{d}$. If 
$$\hat B=B+a \otimes b$$
Is non-singular, then
$$\hat B^{-1}=B^{-1}- \frac{(B^{-1}a)\otimes (B^{-T}b)}{1+{\left\langle b,B^{-1}a \right\rangle}}$$

Using this lemma, and $H_{k}=B_{k}^{-1}$ we get

$$H_{k+1}=H_{k}- \frac{(H_{k}y_{k}-s_{k})\otimes (H_{k}y_{k}-s_{k})}{{\left\langle H_{k}y_{k}-s_{k}\text{ , }y_{k} \right\rangle}}$$
## Modified method
Initialise $H_{0}$
for $k=0,1,\dots$
	$p_{k}=-H_{k}\nabla f(x_{k})$
	find a step length $\alpha_{k}$
	set $x_{k+1}=x_{k}+\alpha_{k}p_{k}$
	set $s_{k}=x_{k+1}-x_{k}\qquad y_{k}=\nabla f(x_{k+1})-\nabla f(x_{k})$
	set $z_{k}=H_{k}y_{k}-s_{k}$
	$H_{k+1}=H_{k}- \frac{z_{k}\otimes z_{k}}{{\left\langle z_{k} \text{ , } y_{k} \right\rangle}}$

### Problems
* ${\left\langle z_{k} \text{ , } y_{k} \right\rangle}$ might be close to $0$.
	* might have to skip updates for $H_{k}$ if this is the case
* If ${\left\langle z_{k} \text{ , } y_{k} \right\rangle}>0$, then $H_{k+1}$ might be indefinite (even if $H_{k}$ was positive definite)

### Remark
$H_{k+1}=H_{0}+\sum\limits_{j=0}^{k} \frac{z_{j}\otimes z_{j}}{{\left\langle z_{j} \text{ , } y_{j} \right\rangle}}$ 
$H_{k+1}v=H_{0}v-\sum\limits_{j=0}^{k} \frac{{\left\langle z_{j} \text{ , } v \right\rangle}}{{\left\langle z_{j} \text{ , } y_{j} \right\rangle}} \cdot z_{j}$
Need only store the $z_{j}$, storing the $H$ matrices will take a lot of space.
