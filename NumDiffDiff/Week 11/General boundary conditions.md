PDE:
$$-Lu=f \quad \text{in } \Omega$$
And boundary conditions on $\partial_{}\Omega$.

Weak formulation:
Find $u\in V$ such that 
$$a(u,v)=F(v)\quad\forall\quad v\in V \tag{V}$$

Galerkin method:
Find $u_{h}\in V_{h}$ such that
$$a(u_{h},v_{h})=F(v_{h})\quad\forall\quad v_{h}\in V_{h} \tag{Vh}$$

Some questions for non-zero boundary conditions:
	1. What is $a(\cdot ,\cdot )$, $F$ and $V$
	2. How to choose $V_{h}$?
	3. How to solve $(V_{h})$

# General Dirichlet boundary conditions
$$-Lu=f \quad \text{in } \Omega , \qquad u=g \quad \text{on }\partial_{}\Omega $$
### a) First approach
Let $u_{h}$ have boundary conditions $≠0$.
	Find $u_{h}\in X^{1}_{h} \quad\text{s.t.}\quad u_{h}=g \quad \text{on }\partial_{}\Omega$
	and
	$a(u_{h},v_{h})=F(v_{h})\quad\forall\quad v_{h}\in V_{h}$
	Where $V_{h}=\{v_{h}\in X^{1}_{h}: \quad v_{h}=0 \quad \text{on } \partial_{}\Omega  \}$
Easier to implement in 1D

### b) Second approach
Solve problem with boundary conditions=0

Definition: Lifting function
	$\tilde{g}\in H^{1}\quad\text{s.t.}\quad \tilde{g}|_{\partial \Omega }=g$
	and $\tilde{u}=u-\tilde{g}$.
Then,
$$\begin{cases}
-L \tilde{u}=-Lu+L \tilde{g} = f + L \tilde{g} & \text{in }\Omega  \\
\tilde{u}=0 & \text{in }\partial_{}\Omega.
\end{cases}$$
$$\Downarrow \cdot v\in H^{1}_{0},\quad \int \text{ d}x, \quad \text{i.b.p.}$$
$$\begin{align*}
a(\tilde{u},v)&= \int fv-a(\tilde{g},v)\\
&= :\tilde{F}(v)\quad\forall\quad v \in H_{0}^{1}
\end{align*}$$
Galerkin: $u=\tilde{u}+ \tilde{g}$
Where $\tilde{u}$ solves
$$\text{Find }\tilde{u}\in V_{h} \qquad\text{s.t.}\quad a(\tilde{u},v)=\tilde{F}(v)\quad\forall\quad v \in V_{h}\tag{tilde Vh}$$

## Example: 1d
$$-u_{xx}=f(x) \quad\text{on }(0,1) \qquad u(0)=g_{0}, \quad u(1)=g_{1}$$
Lifting function: $\tilde{g}(x)=(1-x)g_{0}+xg_{1}$
or $\tilde{g}=$ ![[Pasted image 20230425193659.png|300]]
(second is easy to generalise to multi-d)
$$\Downarrow \tilde{u}=u-\tilde{g}$$
$$\begin{align*}
			-\tilde{u}_{xx}&= -u_{xx}+\tilde{g}_{xx}=f+\tilde{g}_{xx} \quad\text{on }(0,1)\\
\tilde{u}(0)&= 0=\tilde{u}(1)
\end{align*}$$
$$\Downarrow v \in H^{1}_{0}, \quad \int \text{ d}x, \quad \text{i.b.p-}$$
$$\int_{0}^{1}\tilde{u}_{x}v_{x}\text{ d}x -\left[\tilde{u}_{x}v \right]_{0}^{1}= \int_{0}^{1}fv \text{ d}x-\int_{0}^{1}\tilde{g}_{x}v_{x}\text{ d}x+\left[\tilde{g} v\right]_{0}^{1}$$
Since $v(0)=0=v(1)$, this simplifies to
$$\int_{0}^{1}\tilde{u}_{x}v_{x}\text{ d}x = \int_{0}^{1}fv \text{ d}x-\int_{0}^{1}\tilde{g}_{x}v_{x}\text{ d}x$$
By our definitions,
$$\begin{align*}
a(u,v)&= \int_{0}^{1}\tilde{u}_{x}v_{x}\text{ d}x,\\
a(\tilde{g}, v)&= \int_{0}^{1}\tilde{g}_{x}v_{x}\text{ d}x,\\
\tilde{F}(v)&=\int_{0}^{1}fv \text{ d}x-\int_{0}^{1}\tilde{g}_{x}v_{x}\text{ d}x. 
\end{align*}$$
### Remarks
1. $\tilde{F}$ bounded linear function on $H^{1}$
	Proof:
	$\lvert \tilde{F}(v) \rvert \stackrel{\text{C.S.}}{\le} \lVert f \rVert_{L^{2}}\cdot \lVert v \rVert_{L^{2}}+ \lVert \tilde{g}_{x} \rVert_{L^{2}}\cdot \lVert v_{x} \rVert_{L^{2}}$
		We have that $\lVert v \rVert_{L^{2}}\le \lVert v \rVert_{H^{1}}, \quad \lVert \tilde{g}_{x} \rVert_{L^{2}}\le \lVert g \rVert_{H^{1}}, \quad \lVert v_{x} \rVert_{L^{2}}\le \lVert v \rVert_{H^{1}}$ 
	$\lvert \tilde{F}(v) \rvert\le (\lVert f \rVert_{L^{2}}+\lVert \tilde{g} \rVert_{H^{1}})\cdot \lVert v \rVert_{H^{1}}$
	$\implies\quad \lVert \tilde{F} \rVert= \sup_\limits{v≠0} \frac{\lvert \tilde{F}(v) \rvert}{\lVert v \rVert_{H^{1}}}$
	$\lVert \tilde{F} \rVert\le \lVert f \rVert_{L^{2}}+\lVert \tilde{g} \rVert_{H^1}<\infty$
2. Boundary conditions in weak sense:
	$u-\tilde{g}\in H^{1}_{0}$
	1d:
		$u$ continuous $\quad\implies\quad \lim_\limits{x \to x_{0}\in \partial_{}\Omega } u(x)=g(x_{0})$ 
	multi-d:
		$u$ need not be contionuous.
		$\quad\implies\quad$ boundary conditions in trace sense
		