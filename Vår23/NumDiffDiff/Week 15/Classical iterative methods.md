Iterative methods are based on **splitting**:
$$A=P +(A-P),$$
where $P$ is denoted the preconditioner. It should be invertible, and easy to invert.
$$A \vec{U}=\vec{b}\tag{2}$$
$$\Updownarrow$$
$$P \vec{U}= (P-A)\vec{U}+\vec{b}\tag{3}$$

## Fixed point iteration
$$P \vec{U}^{(k+1)}=(P-A)\vec{U}^{(k)}+ \vec{b}$$
$\Updownarrow$
$$\vec{U}^{(k+1)}= (I-P^{-1}A)\vec{U}^{(k)}+P^{-1}\vec{b}\tag{4}$$
We define $B:=(I-P^{-1}A)$.

#### Error
Denote the error $\vec{e}^{(k)}=\vec{U}-\vec{U}^{(k)}$. We then get
$$\vec{e}^{(k)} \mathop{=}\limits^{P^{-1}\cdot (3)}_{(4)}B \cdot \vec{e}^{(k-1)}=\dots=B^{k}\vec{e}^{(0)}$$
$$\begin{align*}
\lVert \vec{e}^{(k)} \rVert&\le  \lVert B^{k} \rVert \cdot \lVert \vec{e}^{(0)} \rVert\\
	&\le \lVert B \rVert^{k}\cdot \lVert \vec{e}^{(0)} \rVert \tag{5}
\end{align*}$$
### Theroem 1: Convergence of (4)
For any $\vec{U}^{(0)}$
a)  $\lVert \vec{e}^{(k)} \rVert \to 0 \quad\Leftrightarrow\quad \rho (B)\le1$
b)  $\lVert B \rVert=\delta <1 \quad\implies\quad \lVert \vec{e}^{(k)} \rVert\le \delta ^{k}\lVert \vec{e}^{(0)} \rVert$.

#### Remark 1
(i) Sufficient condition for convergence of (4):
	$\lVert B \rVert<1$
(ii) Geometric convergence in (b).
(iii) Smaller $\lVert B \rVert, \rho (B) \quad\implies\quad$ faster convergence
(iv) Equivalens of norms:
	Convergence in one norm $\quad\implies\quad$ convergence in all norms

Note that $\rho (A)\le \lVert A \rVert \quad\forall\quad \lVert \cdot  \rVert$

#### Proof of (a)
$\rho (B)<1 \stackrel{\text{Thm. in B.O.}}{\quad\implies\quad} \lVert B^{k} \rVert \stackrel{k\to \infty}{\to}0$

(5) $\quad\implies\quad \lVert \vec{e}^{(k)} \rVert\to0$.

Now for $\rho (B)\ge1$:
	$\exists \lambda , \vec{y}≠\vec{0} \qquad\text{s.t.}\quad$
	$\lvert \lambda  \rvert\ge1, \quad B \vec{y}=\lambda \vec{y}$.
	Now, take $\vec{U}^{(0)}=\vec{y},$ 
	then $\vec{e}^{(0)}=\vec{y}$, 
	and
	$\lVert \vec{e}^{(k)} \rVert=\lVert B^{k}\vec{y} \rVert=\lVert \lambda ^{k}\vec{y} \rVert$
	$=\lvert \lambda  \rvert^{k}\lVert \vec{y} \rVert\ge \lVert \vec{y} \rVert=\lVert \vec{e}^{(0)} \rVert\qquad (>0)$
	This implies no guaranteed convergence. (Convergence depending on starting point).

## Different iterative methods
$$A=-L+D-U=\begin{bmatrix} &   & -U \\  & D \\ -L\end{bmatrix}$$
Where $D$ is the diagional
### Jacobi
$P=D$

### Gauss-Seidel
$P=D-L$

### SOR
$P= \frac{1}{\omega }(D- \omega L), \qquad \omega >0$
also called the accelerated Gauss-Seidel

### Convergence
(a) $A$ strictly diagonally dominant $\quad\implies\quad$ Jacobi and Gauss-Seidel converges
	Proof for Jacobi:
		$\lVert B \rVert_{\infty}\stackrel{\text{check}}{=}\lVert D^{-1}(L+U) \rVert_{\infty}$
		$=\max_\limits{i} \frac{1}{\lvert a_{ii} \rvert}\sum\limits_{j≠i}^{}\lvert a_{ij} \rvert \stackrel{\text{Str. d.d.}}{<}1$
	Proof of Gauss-Seidel convergence is complicated, not covered here.
(b) $A$ symmetric positive definite $\quad\implies\quad$ Gauss-Seidel converges, and SOR converges for $\omega \in (0,2)$
(c) SOR diverges for $\omega \notin(0,2)$
