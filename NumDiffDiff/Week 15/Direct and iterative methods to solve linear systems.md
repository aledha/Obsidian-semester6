We want to solve the problem
$$-\mathcal{L}u=f \quad\text{on }\Omega \quad + \text{ B.C.}\tag{P}$$
#insert sketch of potato

Grid: $\overline{\mathbb{G}}=\mathbb{G}\cup \partial\mathbb{G}$ 
	$= \{P:\quad P \in \overline{\mathbb{G}} \}$

Finite difference method:
$$\alpha _{PP}U_{P}-\sum\limits_{U≠P}^{}\alpha _{PQ}U_{Q}=f_{P}\quad\forall\quad P \in \mathbb{G}\tag{Ph}$$
$$\Downarrow \qquad \vec{U}=\begin{bmatrix}U_{P_{0}},\dots, U_{P_{N}}\end{bmatrix}$$
$$A \vec{U}=\vec{b},\tag{1}$$
where $A\in \mathbb{R}^{(M+1) \times(M+1)}$  is sparse, invertible, and often hard to set up.

### How to solve (1)
1. Direct methods
	   E.g., gauss elimination
	   $\mathcal{O}(M^{3})$ operations, and storage problems
2. Iterative methods
	Jacobi, Gauss seidel, SOR, Conjuagte gradient
	$\mathcal{O}(M^{2})$ operations per iteration
		Fast compared to direct methods if few iterations are sufficient
		Requires much less storage.
		Do not need to set up the matrix $A$.
			Use $Ph$ directly.

### Example 1
Solving (Ph) with Jacobi iterations
Define $U_{P}=\lim_\limits{k \to \infty}U^{(k)}_{P}$, 
	where 
	$$U_{P}^{(k+1)}= \frac{1}{\alpha _{PP}}\left(\sum\limits_{Q≠P}^{} \alpha _{PQ}U_{Q}^{(k)}+f_{P}\quad\text{for }P\in \mathbb{G} \right)$$
	and $U^{(k+1)}_{P}=$ B.C.$\quad\text{for }P \in \partial_{}\mathbb{G}$.