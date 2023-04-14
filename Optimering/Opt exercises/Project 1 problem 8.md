Recall our strategy to prove convexity for cable nets, specifically the argument that the squared of a non-negative convex function is also convex. Since $\eqref{*}$ was non-negative and convex, then (4) was convex.

However, this same line of reasoning is not the case for (5), since the corresponding function for (5) is
$$\tilde{g}(X)=\lVert x^{(i)}-x^{(j)} \rVert-l_{ij},$$
which is not non-negative.

**Proposition**
(5) is not convex if $\mathcal{B}≠0$.

**Proof**
We will prove this by a counter-example. The definition of convexity is
$$$$

Take the system $X \in \mathbb{R}^{5 \times3}$ such that $x^{(i)}=p^{(i)}\quad\text{for }i=1,2,3,4$, where
$p^{(1)}=\begin{bmatrix}1 \\ 1 \\ 0\end{bmatrix},\quad p^{(2)}=\begin{bmatrix}-1 \\ 1 \\ 0\end{bmatrix},\quad p^{(3)}=\begin{bmatrix}-1 \\ -1 \\ 0\end{bmatrix},\quad p^{(4)}=\begin{bmatrix}1 \\ -1 \\ 0\end{bmatrix}.$ We set the bar lengths as $l_{15}=l_{25}=l_{35}=l_{45}=\sqrt{3}$. Denote $b_{elast}(X)=\sum\limits_{e_{ij}\in \mathcal{B}}^{}E^{bar}_{elast}(e_{ij})$   and    $b_{grav}(X)=\sum\limits_{e_{ij}\in \mathcal{B}}^{}E_{grav}^{bar}(e_{ij})$. This system admits two solutions where $b_{elast}(X)=0$, namely
$$X_{1}=\begin{bmatrix}\dots  &  \begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix}\end{bmatrix}, \qquad X_{2}=\begin{bmatrix}\dots & \begin{bmatrix}0 \\ 0 \\ -1\end{bmatrix}\end{bmatrix}.$$

