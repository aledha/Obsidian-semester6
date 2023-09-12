## Definition: Weak derivative
$g$ is a weak $\partial_{i}$ derivative of $f$ if 
	$g\in L^{1}_{}(\Omega )$ and
	$\int_{\Omega }gv=-\int_{\Omega }f \partial_{i}v \quad\forall\quad v\in C_{0}^{1}(\Omega )$

(where $v\in C_{0}^{1}$ means that $v\in C^{1}$  and $v|_{\partial \Omega }=0$)

#### Remark 2
* $\partial_{i}f$ exists $\quad \stackrel{i.b.p.}{\Rightarrow}\quad g=\partial_{i}f$          ("differentiable $\quad\implies\quad$ weakly differentiable")
* Example:   $f=|x| \quad\Rightarrow\quad g=\begin{cases}-1 & x<1 \\+1 & x>0 \end{cases}$
	* Obs $g$ not differentiable at $x=0$         ("weak differentiable $\quad\nRightarrow\quad$ differentiable")
	  
* $f=\begin{cases} -1 & x<0  \\+1 & x>0\end{cases}$ 
  has no weak derivative  
	  Would be $g=2 \delta(x)$  but $\delta\notin L^{1}(\Omega )$

## Sobolev spaces
$$H^{k}(\Omega )=\{f:\quad f, \nabla f, \nabla ^{2}f,\dots, \nabla ^{k}f \in L^{2}(\Omega ) $$
Note:
	$H^{0}(\Omega )=L^{2}(\Omega )=\{f \text{ "measurable" and } \int_{\Omega }\left\lvert f \right\rvert^{2}<\infty$ 
	(not very important in this course)

$H^{k}(\Omega )$ are *Hilbert spaces* with corresponding inner products
$${\left\langle u \text{ , } v \right\rangle}_{H^{k}(\Omega )}=\int_{\Omega }uv+ \int_{\Omega }\nabla u \cdot \nabla v + \ldots + \int_{\Omega }\nabla ^{k}u \cdot \nabla ^{k}v$$
And norm 
$$\lVert u \rVert_{H^{k}(\Omega )}^{2}=\lVert u \rVert_{k}^{2}=\lVert u \rVert^{2}_{L^{2}}+\lVert \nabla u \rVert_{L^{2}}^{2}+\ldots+ \lVert \nabla ^{k}u \rVert^{2}_{L^2}$$
$$H_{0}^{1}=\{ f\in H^{1}(\Omega ): \quad \text{"}f=0 \text{ on } \partial_{}\Omega \text{"}$$
Such that any $\int_{\partial \Omega } f =0$

#### Remark 3
* $u\in H_{0}^{1}(\Omega )\cap C(\overline \Omega ) \quad\implies\quad u=0 \text{ on } \partial_{}\Omega$
* $f=1-\left\lvert 2x-1 \right\rvert\in H^{1}_{0}$        but $f\notin C^{1}$
	* ![[Pasted image 20230308121914.png|50]]


We take a closer look at the space
## $H_{0}^{1}(0,1)$
$$a(u,v)=\int_{0}^{1}u_{x}v_{x}\text{ d}x$$
is an (equivalent) inner product. Requirements for an inner product:
* $a(u,v)=a(v,u)$
* $a(c_{1}u_{1}+c_{2}u_{2},v) = c_{1}a(u_{1},v) + c_{2}a(u_{2},v)$
* $a(u,u)=\int_{0}^{1}u_{x}^{2} \ge \frac{1}{C} \lVert u \rVert^{2}_{H^{1}(0,1)}$
	* $a(u,u)\ge0, \qquad a(u,u)=0 \quad\Leftrightarrow\quad u=0 \text{ in }H^{1}$

Further,
$$F(v)=\int_{0}^{1}f \cdot v$$
is a linear functional. (given $f\in L^{2}$).

Is $F(v)$ bounded?
	Dual norm:    $\lVert F \rVert= \max_\limits{v\in H^{1}} \frac{{\lvert F(v) \rvert}}{{\lVert v \rVert}_{H^{1}}}$           ($v≠0$)
$$\begin{align*}
{\lVert F \rVert} &\le  \max_\limits{v} \frac{{\lVert f \rVert}_{2} {\lVert v \rVert}_{2}}{{\lVert v \rVert}_{H^{1}}}\\
	\stackrel{\lVert v \rVert_{L^{2}}\le \lVert v \rVert_{H^{1}}}{\le}& \lVert f \rVert_{2}\cdot 1 \quad \stackrel{f\in L^{2}}{<}\infty
\end{align*}$$
So $F(v)$ is bounded.

Using *Riesz representation theorem*
	There exists a unique $u\in H^{1}_{0}(0,1) \quad\text{s.t.}\quad$
	$a(u,v)=F(v) \quad\forall\quad v\in H^{1}_{0}(0,1)$

So there exists a unique *weak* solution of (1)!                          $-u_{xx}=f \qquad \text{in }(0,1)$


### Remark 4
Similarly, there exists a unique solution $u\in H^{1}_{0}(\Omega)$ of (4) if
	$\Omega$ is a bounded domain,
	$A=A^{T}\in L^{\infty}$,
	$x^{T}Ax\ge \lambda \lvert x \rvert^{2}>0 \quad\forall\quad \lambda \in \mathbb{R}^{d}, \quad x≠0$

