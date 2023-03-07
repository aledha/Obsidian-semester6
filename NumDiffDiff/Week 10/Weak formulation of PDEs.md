## 1 dimension
1d poisson equation
$$-u_{xx}=f \qquad \text{in }(0,1)\tag{1}$$
with $u(0)=0=u(1)$.

$$\cdot v \text{  (smooth)} \qquad \Downarrow\qquad \int_{0}^{1}\text{ d}x$$

$$\int_{0}^{1}(-u_{xx})v \text{ d}x=\int_{0}^{1}fv \text{ d}x$$
Using integration by parts
$$\left[-u_{x}v \right]_{0}^{1}-\int_{0}^{1}(-u_{x})v_{x}\text{ d}x=\int_{0}^{1}fv \text{ d}x$$
$$\Updownarrow \quad \text{choosing  }v(0)=0=v(1)$$
$$\int_{0}^{1}u_{x}v_{x} \text{ d}x=\int_{0}^{1}fv \text{ d}x \tag{1}$$
### Observation 1
* $(2)$ is well-defined if the functions $u_{x}, v_{x},v,f\in L^{2}(0,1)$
	* i.e. $u,v\in H^{1}(0,1) =\{g:\quad g,g_{x}\in L^{2} \}$
	* (not $u\in C^{2}$)
* If $u\in C^{2}(0,1)\cap C(0,1]\cap H^{1}(0,1)$
  solves (1)
	* $\quad\Rightarrow\quad$ $u$ solves (2) $\quad\forall\quad v\in H^{1}_{0}(0,1)$
Where $H_{0}^{1}(0,1)=\{f\in H^{1}(0,1):f(0)=0=f(1) \}$

## Definion: Weak solution
$u\in H^{1}_{0}(0,1)$ is a *weak solution* of $(1)$ if
$$\int_{0}^{1}u_{x}v_{x}\text{ d}x=\int_{0}^{1}fv \text{ d}x \quad\forall\quad v\in H^{1}_{0}(0,1)\tag{3}$$
### Remark
* A classical solution is a weak solution (from observation 1, part 2)
* A smooth weak solution is a classical solution.
	* (2)$\quad\forall\quad v\in H_{0}^{1}$  and $u$ smooth $\quad\Rightarrow\quad (1)$.
* Dirichlet boundary conditions are given as part of the space $H_{0}^{1}$


# Multi dimension
$$-\mathcal{L}u=f \quad \text{in } \Omega \in \mathbb{R}$$
with $u=0$ on $\partial_{}\Omega$.
With
$$\mathcal{L}u=\sum\limits_{}^{}\partial_{i}(a_{ij} \partial_{_{j}})u=\nabla \cdot(A \nabla u)$$
Integration by parts in multi-d
$$\int_{\Omega }(\nabla \cdot \vec{G})\cdot v=\int_{\Omega }\nabla \cdot(\vec{G v})-\vec{G}\cdot \nabla v$$
	Since 
	$(\partial_{{i}}G_{i})v=\partial_{i}(G_{i}v)-G_{i}\partial_{i}v$
	And $(\nabla \cdot\vec{G})\cdot v=\sum\limits_{i}^{}(\partial_{{i}}G_{i})v$

So we get 
$$\int_{\Omega} (\nabla \cdot \vec{G})\cdot v=-\int_\Omega \vec{G}\cdot \nabla v+\int_{\Omega }\nabla \cdot (\vec{G}v)$$
We can also use the divergence theorem on the last term
$$\int_{\Omega }\nabla \cdot (\vec{G}v)$$
Now we take $(4)\cdot v$, take $\int_\Omega \text{ d}x$ and do integration by parts. (with $\vec{G}=-A \nabla u$)
$$\Downarrow$$
$$\int_{\Omega }A \nabla u \cdot \nabla v-\int_{\partial \Omega }A$$