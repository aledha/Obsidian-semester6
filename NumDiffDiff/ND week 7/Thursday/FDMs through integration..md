	Also Finite Volume Schemes (FVM)
Always conservative by construction
	very gud :>

## Divergence theorem
$$\int_{\Omega}\nabla \cdot \vec{F} \quad \text{d}x \text{d}y=\oint_{\partial \Omega} \vec{F}\vec{n} \quad \text{d}s\tag{DT}$$

$\vec{n}$: outward unit normal
$\partial \Omega$: piecewise $C^{1}$
![[Pasted image 20230216163435.png|400]]
## Elliptic problem in divergence form

$$-\mathcal{L}u=f\quad \text{in }\mathbb{\Omega}\tag{P}$$
$$\mathcal{L}u=\nabla \cdot (A \nabla u)$$
Where $A=\begin{pmatrix}a_{11} & a_{12} \\ a_{12} & a_{22}\end{pmatrix}$   (Symmetric)
And $\nabla =\begin{pmatrix}\partial_{x} \\ \partial_{y}\end{pmatrix}$
$$\mathcal{L}u=\partial_{x}(a_{11}u_{x})+ \partial_{x}(a_{12}u_{y})+ \partial_{y}(a_{12}u_{x})+\partial_{y}(a_{22}u_{y})$$
For $K \subset \Omega$
$$\int_{K}f \quad \text{d}x \text{d}y \stackrel{(P)}{=} - \int_{K} \nabla \cdot(A \nabla_{u})\text{d}x \text{d}y \stackrel{DT}{=}-\oint_{\partial K}A \nabla u \cdot \vec{n} \text{d}s$$
And $=\oint_{\partial K}a \frac{\partial u}{\partial n}$ if $A=aI$

### Remark 2
1. (Heat) Flux $\vec{\phi}=-A \cdot \nabla u$
2. Flux boundary conditions:
	$$A \nabla u \vec{n}=h$$
	Where if $A=aI \quad \Rightarrow\quad a \frac{\partial u}{\partial n} = h$, which is a Neumann condition