$$-\partial_{x}(\kappa (x)u_{x})=f(x)\quad\text{on }(0,1)$$
with $u(0)=g_{0},\quad u(1)=g_{1}$
Weak formulation:
	Find $u\in H^{1}_{0}(0,1) \qquad\text{s.t.}\quad u(0)=g_{0}, \quad u(1)=g_{1}$ and
	$$a(u,v):=\int_{0}^{1}\kappa (x)u_{x}v_{x}\text{ d}x=\int_{0}^{1}fv \text{ d}x =: F(v)$$
	$\quad\forall\quad v\in H^{1}_{0}(0,1)$.

**Galerkin approximation**.
**$V_h$**
	Find $u_{h}\in \tilde{V}_{h}=\text{span}\{\phi _{0},\dots, \phi _{M} \}\subset H^{1}(0,1) \qquad\text{s.t.}\quad u_{h}(0)=g_{1},\quad u_{h}(1)=g_{1}$   and
	$$a(u_{h},v_{h})=F(v_{h}) \quad\forall\quad v_{h}\in V_{h}:=\tilde{V}_{h}\cap H^{1}_{0}(0,1).$$
Can write this as a linear system, since any solution would be a linear combination of the basis, i.e. $u_{h}=\sum\limits_{i=0}^{M}U_{i}\phi _{i}(x)$.
$$A \vec{U}=\vec{F}\qquad U_{0}=g_{0},\quad U_{M}=g_{1}\tag{2}$$
where
	$\vec{U}=\left[U_{0},\dots,U_{M} \right]^{T}$,
	$A_{ij}=a(\phi _{j},\phi _{i})$,
	$F_{j}=F(\phi _{j})$.

Choosing a finite element basis
	Solve $V_{h}$ with $\tilde{V}_{h}=X^{1}_{0}(0,1)$ 
	for a given "triangulation" $\tau _{h}$.

#### Subdivision/triangulation $\tau _{h}$ and $\mathbb{P}_{1}$ FEM approximation space $X^{1}_{h}$
Partition: $0=x_{0}<x_{1}<\dots < x_M =1$
Elements: $\mathcal{T} _{h}=\{K_{i} \}_{i=1}^{M}, \quad K_{i}=(x_{i-1},x_{i})$.
	Note:
		In 1d, the element $K_{i}$ are lines
		2d, triangles
Global nodes: $N_{h}=\{x_{0},\dots,x_{M} \}$
Global basis: $\phi _{0},\dots \phi _{M}$ hat functions as defined

The space $X_{h}^{1}(0,1)=\text{span}(\phi _{0},\dots, \phi _{m})$
	$=\{v\in C \left[0,1 \right]:\quad v|_{K}\in \mathbb{P}_{1}\quad\forall\quad K \}$
	This space is only defined if we are given the elements $\mathcal{T}_{h}$

$V_{h}=X_{h}^{1}\cap H^{1}_{0}(0,1)$
	$=\{ v_{h}\in X^{1}_{h}:\quad v_{h}(0)=0=v_{h}(1)\}$
	$=\text{span}\{\phi _{1},\dots, \phi _{M-1} \}$


## Setting up the matrix $A$
Compute element by element
$$\tilde{V}_{h}=X^{1}_{h}\quad\implies\quad A_{ij}=\sum\limits_{K\in \mathcal{T}}^{}\int_{K}\kappa (x)\phi _{j}'\cdot \phi _{i}'\text{ d}x=:\sum\limits_{K\in \mathcal{T}}^{}a^{K}(\phi _{j},\phi _{i})$$
and 
$$F_{j}=\sum\limits_{K\in \mathcal{T}_{h}}^{}\int_{K}f \phi  _{j}=:\sum\limits_{_K\in \mathcal{T}_{h}}^{}F^{K}(\phi _{j})$$

Use a **local basis** for $X_{h}^{1}|_{K}=\mathbb{P_{1}(K)}$:
$\mathbb{P}_{1}(K_{i})=\text{span}\{\phi^{i}_{0},\phi ^{i}_{1} \}$
#insert sketch (during lecture $x_{i}\to x_{i-1},\quad x_{i+1}\to x_{i}$). Length of interval: $h_{i}$
![[Pasted image 20230316124831.png|300]]
Red: $\phi _{0}^{i}$, blue: $\phi _{1}^{i}$


### Observation
$\phi _{i-1}|K_{i}=\phi ^{i}_{0}$,
$\phi _{i}|K_{i}=\phi ^{i}_{1}$.

$(\phi ^{i}_{0}|K_{i})'= - \frac{1}{h_{i}}$
$(\phi ^{i}_{1}|K_{i})'=  \frac{1}{h_{i}}$

and all other basis functions on $K_{i}$ =0.

Hence, 
$$a^{K_{i}}(\phi _{i-1},\phi _{i-1})=a^{K_{i}}(\phi _{i},\phi _{i}),$$
$$=\int_{K_{i}}\kappa (x)(\phi _{1}^{i})'(\phi _{1}^{i})' \text{ d}x= \frac{1}{h_{i}^{2}}\int_{K_{i}}\kappa (x)\text{ d}x$$
and
$$a^{K_{i}}(\phi _{i},\phi _{i-1})=a^{K_{i}}(\phi _{i-1},\phi _{i})$$
$$= -\left( \frac{1}{h_{i}}\right)^{2}\int_{K_{i}}\kappa (x) \text{ d}x$$
No other functions contribute, $a^{K_{i}}(\phi _{k},\phi _{l})=0 \quad\text{for }k,l\notin \{i, i-1 \}$.

$$F^{K_{i}}(\phi _{j})=\int_{K_{i}}f \phi _{j} \quad\text{for }j=i-1,i$$
$$F^{K_{i}}(\phi _{j})=0 \quad\text{for }j\notin \{i-1,i \}$$
Quadrature:
$$\int_{K}g \text{ d}x=Q(g,K)+\mathcal{O}(h^{n})$$
Example trapeziodal rule: $\mathcal{O}(h^{2})$
	$Q(\kappa , K_{i})= \frac{1}{2}(\kappa _{i-1}-\kappa _{i})h_{i}$
	$Q(f \phi _{i-1},K_{i})= \frac{1}{2}(f_{i-1}\cdot \phi _{i-1}(x_{i-1})+ f_{i}\cdot \phi _{i-1}(x_{i}))= \frac{1}{2}(f_{i-1}\cdot 1+0)$
	$Q(f \phi _{i}, K_{i})= \frac{1}{2}(0 + f_{i}\cdot 1)\cdot h_{i}$

### Remark: Alternative way
Reference element $\hat K$
$K_{i}\stackrel{\Phi _{i}^{-1}}{\to}\hat K[0,1]$
$x \to \xi =\Phi _{i}^{-1}(x)$ 

$$\mathbb{P}_{1}(\hat K )=\text{span} \{(1-\xi ), \xi  \}=: \text{span} \{ \}$$
way too complicated.. >:(


### Elemental matrices and vectors

$$A^{K_{i}}=\begin{bmatrix}a^{K_{i}}(\phi _{i-1},\phi _{i-1}) & a^{K_{i}}(\phi _{i-1},\phi _{i}) \\ a^{K_{i}}(\phi _{i},\phi _{i-1}) & a^{K_{i}}(\phi _{i},\phi _{i})\end{bmatrix}$$
$$F^{K_{i}}=\begin{bmatrix}F^{K_{i}}(\phi _{i-1}) \\ F^{K_{i}}(\phi _{i})\end{bmatrix}=\begin{bmatrix}Q(f \phi _{i-1},K_{i}) \\ Q(f \phi _{i},K_{i}) \end{bmatrix}$$
Compute for every $K_{i}$, and then
#### Assembly
#insert sketches

$\phi _{i}≠0$ only in $K_{i}\cup K_{i+1}$       
	($\text{supp}\phi _{i}= \overline K_{i} \cup \overline K_{i+1}$)

Local to global matrix
$$A=\{a(\phi _{j},\phi _{i}) \}^{M}_{i,j=0}$$
and
$$a(\phi _{j} ,\phi _{i})=\sum\limits_{K\in \mathcal{T}_{h}}^{}a^{K}(\phi _{j},\phi _{i})$$
$$=\begin{cases}
a^{K_{i}}(\phi _{i},\phi _{i})+a^{K_{i+1}}(\phi _{i},\phi _{i}), & \quad\text{for }j=i \\
a^{K_{i}}(\phi _{i-1},\phi _{i}), & \quad\text{for }j=i-1  \\
a^{K_{i}}(\phi _{i},\phi _{i-1}), & \quad\text{for }j=i+1 \\
0,  & \quad \text{elsewhere}.
\end{cases}$$
$$=\begin{cases}
A^{K_{i}}_{22}+A_{11}^{K_{i+1}}, & \quad\text{for }j=i \\
A^{K_{i}}_{12}, & \quad\text{for }j=i-1  \\
A^{K_{i}}_{21}, & \quad\text{for }j=i+1  \\
0, & \quad \text{elsewhere}.
\end{cases}$$
For the boundaries,
$j=i=0: \quad A_{11}=a^{K_{1}}(\phi _{0},\phi _{0})$
$j=i=M: \quad A_{MM}=a^K_{M}(\phi _{M},\phi _{M})$

Due to overlap:
#insert sketch over submatrices

## In practice
Local to global map:
	$\alpha :$ local index. Either 0 or 1.
$i=\theta (K_{k},\alpha )=k+\alpha$

Assembly algorithm:
	$A=0\in \mathbb{R}^{(M+1) \times (M+1)}, \qquad \vec{F}:= 0\in \mathbb{R}^{M+1}$
	for $K_{k} \in \mathcal{T}_{h}$:
		for $\alpha =0,1$:
			for $\beta =0,1$
				$i=\theta (K_{k},\alpha )$
				$j=\theta (K_{k},\beta )$
				$A_{ij}+=A_{\alpha \beta}^{K_{k}}$ 
			$F_{i}+=F^{K_{K}}_{\alpha }$

### Remark 2
In computations, typically instead of $(2)$, use reduced system:
$$\tilde{A}\begin{bmatrix}U_{1}  \\ U_{2}\\ \vdots \\ U_{M-2} \\  U_{M-1} \end{bmatrix}=\begin{bmatrix}F_{1} \\ F_{2} \\ \vdots \\ F_{M-2} \\  F_{M-1}\end{bmatrix}+ \begin{bmatrix}g_{0}/h_{1} \\ 0 \\ \vdots \\ 0 \\ g_{1}/h_{M}\end{bmatrix}$$
Where $\tilde{A}$ is a submatrix of $A$, where we delete the first and last column

### Example 1
$h_{i}=h= \frac{1}{M},\quad \kappa =1 \quad f=1$
$$\vec{F}^{K_{i}}=h\begin{bmatrix}1/2 \\ 1/2\end{bmatrix}$$
$$A^{K_{i}}= \frac{1}{h}\cdot 1\cdot \begin{bmatrix}1 & -1 \\ -1 & 1\end{bmatrix}$$
$$\vec{F}=h \begin{bmatrix} 1/2 \\ 1 \\ \vdots \\ 1 \\ 1/2\end{bmatrix}$$
$$A= \frac{1}{h}\begin{bmatrix}1 & -1 \\ -1 & 2 & -1 \\ 0 & -1 & 2 & -1 \\ 0 &   & \ddots & \ddots & \ddots \\  &   &   &   -1 & 1\end{bmatrix}$$
$$\tilde{A}= \frac{1}{h}\text{tridiag }\{-1,2,-1 \}$$
