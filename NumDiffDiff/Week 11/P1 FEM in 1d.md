![[Pasted image 20230425193749.png|500]]
Elements: $\tau _{h}=\{K_{i} \}_{i=1}^{M}$
	$K_{i}=(x_{i-1},x_{i}), \quad h_{i}=\lvert x_{i}-x_{i-1} \rvert$.

Global nodes:
	$N_{h}=\{x_{i} \}_{i=0}^{N}$

Global basis:
	$\phi _{0},\dots,\phi _{N}$

Space $X_{h}^{1}(0,1)=\text{span}\{\phi _{i} \}_{i=0}^{N}$.

Test function space 
	$V_{h}=\{v_{h}\in X^{1}_{h}:\quad v_{h}(0)=0=v_{h}(1) \}$

$$-u_{xx}=f \quad\text{on }(0,1)\tag{1}$$
with $u(0)=g_{0},\quad u(1)=g_{1}$

Weak formulation:
$$\text{Find }u_{h}\in X_{h}^{1}\qquad\text{s.t.}\quad \begin{cases}
u_{h}(0)=g_{0} \\
u_{h}(1)=g_{1}
\end{cases}$$
and 
$$a(u_{h},v_{h})=F(v_{h})\quad\forall\quad v_{h}\in V_{h}$$
$$\text{Linear system}\qquad \Downarrow \qquad u_{h}=\sum\limits_{i=0 }^{M}U_{i}\phi _{i}(x), \qquad v_{h}=\phi _{j}\quad\text{for }j=0,\dots ,M$$
$$A \vec{U}=\vec{F}, \qquad \vec{U}=(U_{0},\dots U_{M})^{T}, \quad U_{0}=g_{0},\quad U_{M}=g_{1}$$
Where for $i,j=0,\dots, M$,
$$A_{ij}=a(\phi _{j},\phi _{i})=\sum\limits_{K\in \tau _{h}}^{}\int_{K}\phi _{j}'\phi _{i}'\text{ d}x,$$
and
$$F_{j}=\int_{0}^{1}f \phi _{j}\text{ d}x=\sum\limits_{K\in \tau _{h}}^{}\int_{K}f \phi _{j}\text{ d}x.$$
Observation
	$\phi _{i}'(x)\begin{cases} \frac{1}{h_{i}}, & x \in K_{i} \\- \frac{1}{h_{i}}, & x \in K_{i+1} \\0 & \text{otherwise} \end{cases}$
	$\phi _{0}'=\begin{cases}- \frac{1}{h_{1}}, & x \in K_{0} \\0 & \text{otherwise}\end{cases}$

$$\Downarrow$$
$$A_{ij}=\int_{K_{i}}\phi _{j}' \frac{1}{h_{i}}\text{ d}x+\int _{K_{i+1}}\phi _{j}'\left(- \frac{1}{h_{i+1}}\right)\text{ d}x+0$$
$$A_{ij}=\begin{cases}
&\left(- \frac{1}{h_{i}}\right)\cdot \frac{1}{h_{i}} \cdot h_{i}&+\quad 0 & \quad\text{for }j=i-1 \\
&\frac{1}{h_{i}}\cdot \frac{1}{h_{i}}\cdot h_{i} &+ \left(- \frac{1}{h_{i+1}}\right)\left(- \frac{1}{h_{i+1}}\right)\cdot h_{i+1}  & \quad\text{for }j=i \\
&0&+\frac{1}{h_{i+1}}\left(- \frac{1}{h_{i+1}}\right)h_{i+1}  & \quad\text{for }j=i+1 \\
&0 && \quad \text{otherwise}
\end{cases}$$
Boundary:
$$A_{0j}=\begin{cases}
\frac{1}{h_{1}} & \quad\text{for }j=0 \\
-\frac{1}{h_{1}} & \quad\text{for }j=1 \\
0 & \quad \text{otherwise}
\end{cases}$$

Hence (Vh) without boundary conditions becomes
$$\begin{bmatrix} \frac{1}{h_{1}} & - \frac{1}{h_{1}} \\ - \frac{1}{h_{1}} & \frac{1}{h_{1}}+ \frac{1}{h_{2}} & - \frac{1}{h_{2}} \\ 0 & - \frac{1}{h_{2}} & \frac{1}{h_{2}}+ \frac{1}{h_{3}} & -\frac{1}{h_{3}} \\ 0 & 0 & \ddots & \ddots & \ddots \\ 0 & 0 & 0 &  - \frac{1}{h_{M}} &   \frac{1}{h_{M}}\end{bmatrix}\vec{U}=\vec{F}$$
Where $A \in \mathbb{R}^{(M+1)\times(M+1)}, \quad \vec{U} \in \mathbb{R}^{M+1}, \quad \vec{F}\in \mathbb{R}^{M+1}$

Setting boundary conditions
$$\qquad \Downarrow \qquad U_{0}=g_{0}, \quad U_{M}=g_{1}$$
$$\begin{bmatrix}   \frac{1}{h_{1}}+ \frac{1}{h_{2}} & - \frac{1}{h_{2}} \\  - \frac{1}{h_{2}} & \frac{1}{h_{2}}+ \frac{1}{h_{3}} & -\frac{1}{h_{3}} \\ 0 & 0 & \ddots & \ddots & \ddots \\ 0 & 0 & 0 &  - \frac{1}{h_{M-1}} &   \frac{1}{h_{M-1}}+ \frac{1}{h_{M}}\end{bmatrix} \begin{bmatrix}U_{1} \\  \\ \vdots \\  \\ U_{M-1}\end{bmatrix}=\begin{bmatrix}F_{1} \\  \\ \vdots \\  \\ F_{M-1}\end{bmatrix}+ \begin{bmatrix} \frac{g_{0}}{h_{1}} \\ 0 \\ \vdots \\ 0 \\ \frac{g_{1}}{h_{M}}\end{bmatrix}$$
### Remark 2
1. $A$ symmetric, diagonally dominant, not invertible
2. $\tilde{A}$ submatrix of $A$ (deletes the first and last row and column).
	Symmetric, weakly chained diagonally dominant
	$\quad\implies\quad$ invertible
3. $h_{i}=h \quad\forall\quad i \quad\implies\quad A= \frac{1}{h}\text{tridiag}\{-1,2,-1 \}$
	(Same as for FDM)