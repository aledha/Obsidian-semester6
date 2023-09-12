$$u_{t}+Au_{x}=f(x,t)\tag{1}$$
Where $u =(u_1,\dots,u_{l})^{T}$, $\quad A\in \mathbb{R}^{l \times l},\quad f(x,t)\in \mathbb{R}^{l}$
*Hyperbolic if* diagionalisable with real eigenvalues
$$\quad\Rightarrow\quad A=P \Lambda P^{-1}$$
Where $\Lambda=\text{diag}\{\lambda_{i} \}$ are real eigenvalues
$P=\left[\phi_{1},\dots \phi_{l} \right]$  are eigenvectors
Diagionalise (1), $v=P^{-1}u$
$$P^{-1} \cdot (1) \quad\Leftrightarrow\quad v_{t}+\Lambda v_{x}=P^{-1}f$$
Where $\Lambda v_{x}=P^{-1}APP^{-1}u_{x}$

So by diagonalising, we get $l$ *decoupled* scalar PDEs
$$v_{t}^{i}+\lambda_{i}v_{x}^{i}=(P^{-1}f)^{i}\qquad i=1,\dots,l$$
### Example 4
Wave equation:   $w_{tt}= c^{2}w_{xx}$
Using $u_{1}:= w_{t},\qquad u_{2}:=w_{x}$
$$\begin{align*}
(u_{1})_{t}&= w_{tt}=c^{2}w_{xx}&= c^{2}(u_{2})_{x}\\
(u_{2})_{t}&= w_{xt}=w_{tx}&= (u_{1})_{x}
\end{align*}$$
Write this as a system
$$\vec{u_{t}} + \begin{bmatrix}0 & -c^{2} \\ -1 & 0 \end{bmatrix}\vec{u_{x}}=\vec{0}$$
Setting $A=P \Lambda P^{-1}$ we get
$P=\begin{bmatrix}-c & c \\ 1  & 1\end{bmatrix},\qquad \Lambda=\begin{bmatrix}c & 0 \\ 0 & -c\end{bmatrix}$ 
Setting $v=P^{-1}u$
$$\vec{v_{t}+\begin{bmatrix}c & 0 \\ 0 & -c\end{bmatrix}} \vec{v_{x}}=\vec{0}$$
