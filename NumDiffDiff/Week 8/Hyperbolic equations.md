(1d + time)

## Examples of second order equations
$$au_{xx}+2bu_{xy}+cu_{yy}=f(x,t,u,u_{x},x_{y})\tag{1}$$
Hyperbolic if $b^{2}-ac>0$.
### Example 1: Wave equation
$$u_{tt}=c^{2}u_{xx}\quad \text{in}\quad \mathbb{R}\times(0,T)$$
$$\begin{align*}
	u(x,0) &= u_{0}(x)\\
u_{t}(x,0)&= h(h)\\
\end{align*}$$
From 4K:
$$u(x,t)= \frac{1}{2}\left[ u_{0}(x+ct)+u_{0}(x-ct) + \frac{1}{2c} \int_{x-ct}^{x+ct}h(s)\text{d}s\right]$$
## First order equations
First order equations are always conservative
$$u_{t}+a(x,t,u)u_{x}=b(x,t,u)\tag{2}$$
(Non conservatice)
Or 
$$u_{t}+\partial_{x}f(x,t,u)=0$$
(conservative, mass preserved)

Where conservative means
$$\frac{\partial }{\partial t}\int_{x_{1}}^{x_{2}}u_{t}\text{d}x=\int_{x_{1}}^{x_{2}}u_{t}\text{d}x=-\int_{x_{1}}^{x_{2}}\partial_{x}f \text{d}x$$
$$=-(f(x_{2})-f(x_{1}))=\text{"flux"}=\text{"flow in - flow out"}$$
### Example 2: Transport equation
$$u_{t}=au_{x}\quad \text{in }\quad \mathbb{R}\times(0,T)$$
$$u(x,0)=u_{0}(x)$$
Solution: (4k)
$$u(x,t)=u_{0}(x-at)$$
(First figure)

### Example 3: Burger's equation
$$u_{t}-uu_{x}=u_{t}+\partial_{x}\left(\frac{1}{2}u^{2}\right)=0$$
LHS is conservative.


## First order systems
$$\vec{u_{t}}+A \vec{u_{x}}=\vec{b}\tag{3}$$
(non conservative)
or
$$\vec{u_{t}}+\partial_{x}\vec{f}(t,x,\vec{u})=0$$
(conservative)
**Hyperbolic** if $A$ (and $\nabla_{u}\vec{f}$) 
are diagonalisable with **real** eigenvalues.

### Example 3: Wave equation as a first order system
$$u_{tt}-c^{2}u_{xx}=(\partial_{t}u-c\partial_{x})(\partial_{t}+c \partial_{x})u=0$$
Subsititute $v=(\partial_{t}+c \partial_{x})u$
$$\begin{align*}
u_{t}+cu_{x}&= v\\
v_{t}-cv_{x}&= 0\\
A&= \begin{pmatrix}c & 0\\
0 & -c\end{pmatrix}
\end{align*}$$
## Remark 1: Linear problems
($A$ and $f$ do not depend on $u$)
* $(1)$ can always be formulated as the system $(3)$ 
* $(3)$ can (if linear) always be formulated as **decoupled** equations $(2)$:
(3) $\quad \stackrel{A=P \Lambda P^{T}}{\Leftrightarrow}\quad$ $\vec{v_{t}}+ \Lambda \vec{v_{x}}=\vec{\tilde{b}}$
and $\vec{v}=P^{T}\vec{u}$
and $\Lambda=\text{diag}(\lambda_{i})$ eigenvalues of $A$

* By the two last points, we need only to solve (2)!

