$$\begin{cases}
-\Delta u=f  & \quad\text{on } \Omega \in \mathbb{R}^{2} \\
u=0 & \quad\text{on }\Gamma _{D} \\
u_{x}=0 & \quad\text{on }\Gamma _{N}
\end{cases}$$
#insert potato

$$\Downarrow -\int \Delta u \cdot v=\int_{\Omega }\nabla u \cdot \nabla v - \int_{\partial \Omega } \partial_{n}u \cdot v$$
where $\int_{\partial \Omega } \partial_{x}u \cdot v=0$ since $u_{x}=0 \quad\text{on }\Gamma _{N}$ and $u=0 \quad\text{on }\Gamma _{D}$.

Problem (V):
Find $u\in V \qquad\text{s.t.}\quad a(u,v)=F(v)\quad\forall\quad v \in V$,
where 
$V=H^{1}_{\Gamma _{N}}(\Omega )=\{v\in H^{1}(\Omega ): \quad v|_{\partial \Omega \backslash \Gamma _{N}}=0 \}$
and 
$$a(u,v)=\int_\Omega \nabla u \cdot \nabla v,\qquad F(v)=\int_{\Omega }f \cdot v.$$

#insert triangulation

Elements: $K_{i}$
Triangulation: $\mathcal{T}=\{K_{i} \}_{i=1}^{M}$
Global nodes: $x_{i}$
Collection of global nodes: $N_{h}=\{x_{i} \}_{i=0}^{M}$

Enumuration:
	Many possibilities. Have to choose.

Element $K$:
#insert triangle

Local nodes: $L,M,N$.

We need a local to global map: $i=\Theta (K, P)$ 
	where
	$i:$ global node
	$K:$ Element
	$P:$ local node

Write it as a table
#insert table

Approximation space
$V_{h}=X_{h}^{1}\cap V$
where $X_{h}^{1}=\{v\in C(\overline \Omega ):\quad v|_{K}\in \mathbb{P}_{1}\quad\forall\quad K \}$

Basis: $\phi _{0},\dots,\phi _{M}$
	$\phi _{i}(x_{j})=\begin{cases}1, & \quad\text{for }i=j \\0 & \quad\text{for }i≠j \end{cases}$

#insert tent

Now any solution $u_{h}$can be written as
$$u_{h}=\sum\limits_{j=0}^{M}U_{j}\phi _{j}(x),$$
where we impose $U_{j}=0$ for $x_{j} \in \Gamma _{D}$.

$$(V_{h})\quad\Leftrightarrow\quad A \vec{V}=\vec{F},$$
where 
	$A_{ij}=a(\phi _{j},\phi _{i})= \sum\limits_{K \in \mathcal{T}_{h}}^{}a^{K}(\phi _{j},\phi _{i})$,
	$F_{j}=F(\phi _{j})=\sum\limits_{K \in \mathcal{T}_{h}}^{}F^{K}(\phi _{j})$

**Remark 2**
* $a^{K}(\phi _{j},\phi _{i})≠0 \quad\Leftrightarrow\quad x_{i},x_{j} \text{ are vertices of }K$.
* $F^{K}(\phi _{j})≠0 \quad\Leftrightarrow\quad x_{j} \text{ is a vertex of }K$.

**Next time**
* Elementwise computations.
* Assembly