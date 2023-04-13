Problem (P):
$$-\Delta u=1 \quad\text{on }(0,1)\times(0,1)$$
and boundary conditions.

Triangulation:
![[Pasted image 20230412162812.png|500]]

Two different types of elements:
![[Pasted image 20230412163140.png|300]]
Jacobian: $J_{K}=\nabla _{\vec{\xi }}\vec{x}= \begin{bmatrix}h & 0 \\ 0 & h\end{bmatrix}$

![[Pasted image 20230412163202.png|300]]
$J_{K}=\begin{bmatrix}-h & 0  \\ 0 & -h\end{bmatrix}$.

$\lvert K \rvert= \frac{1}{2}h^{2}$,
$$\begin{align*}
G&= J_{K}^{-T}\cdot \begin{bmatrix}-1 & 1 & 0 \\ -1 & 0 & 1\end{bmatrix}\\
&= \pm \frac{1}{h}\begin{bmatrix}-1 & 1 & 0\\
-1 & 0 & 1\end{bmatrix}
\end{align*}$$
Now, the elemental matrix:
$$\begin{align*}
		A^{K}&= \lvert K \rvert G^{T}G\\
&= \frac{1}{2} h^{2} \frac{1}{h^{2}}\begin{bmatrix}-1 & -1\\
1 & 0\\
0 & 1\end{bmatrix}\begin{bmatrix}-1 & 1 & 0\\
-1 & 0 & 1\end{bmatrix}\\
&= \frac{1}{2}\begin{bmatrix}2 & -1 & -1\\
-1 & 1 & 0 \\
-1 & 0 & 1\end{bmatrix}
\end{align*}$$
Elemental load vector: (f=1)
$$\vec{F}_{K}=2 \lvert K \rvert\begin{bmatrix}Q(1\cdot \psi _{L}, \hat K) \\ Q(1 \cdot \psi  _{M},\hat K) \\ Q(1 \cdot \psi _{N}, \hat K) \end{bmatrix}$$
With midpoint rule:
$$\vec{F}_{K}= h^{2} \begin{bmatrix}\psi _{L}\left(\frac{1}{3}, \frac{1}{3} \right)\cdot \lvert \hat K \rvert \\\psi _{M}\left(\frac{1}{3}, \frac{1}{3} \right)\cdot \lvert \hat K \rvert \\\psi _{N}\left(\frac{1}{3}, \frac{1}{3} \right)\cdot \lvert \hat K \rvert \\  \end{bmatrix}$$
$$\vec{F}_{K }=h^{2} \frac{1}{2} \cdot \frac{1}{3}\begin{bmatrix}1 \\ 1 \\ 1\end{bmatrix}$$
