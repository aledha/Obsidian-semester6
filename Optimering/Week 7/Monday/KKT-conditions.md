### Theorem
Assume that $x^{*}$ is a local solution to (P) and the LICQ holds at $x^{*}$. 
Then there exists a "Lagrange multiplier" 
$$\lambda^{*}\in \mathbb{R}^{\xi \cup \mathcal{I}}$$
Such that the KKT- conditions holds:
* $$\nabla _{x}\mathcal{L}(x^{*},\lambda^{*})=0$$
* $$\begin{align*}
	c_{i}(x^{*})&= 0 \quad\forall i\in \xi\\
c_{i}(x^{*})&\ge 0\quad\forall i\in \mathcal{I}
\end{align*}$$
* $$\lambda_{i}^{*}\ge0 \quad\forall i\in \mathcal{I}$$
$$c_{i}(x^{*})\lambda_{i}^{*}=0 \quad\forall i\in \mathcal{I}$$
## Proof
Write $g=\nabla f(x^{*})$.
LICQ holds at the local solution $x^{*}$.
$$\Rightarrow\quad {\left\langle g,p \right\rangle}\ge 0\quad\forall\quad p\in \mathbb{R}^{d}\text{ such that}$$
$$\begin{align*}
{\left\langle \nabla c_{i}(x^{*}),p \right\rangle}&= 0 \quad\forall i\in \xi\\
{\left\langle \nabla c_{i}(x^{*}),p \right\rangle}&\ge 0\quad\forall i\in \in \mathcal{I} \cup \mathcal A(x^{*})
\end{align*}$$
[[Farkas' Lemma]] $\Rightarrow\quad$ we can write
$$g=\sum\limits_{i\in \xi}\alpha_{i}\nabla c_{i}(x^{*}) + \sum\limits_{i\in \mathcal{I} \cup \mathcal A(x^{*})} \beta_{i}\nabla c_{i}(x^{*})$$
Define 
$$\lambda_{i}^{*}=\alpha_{i}\quad\forall i\in \xi$$
$$\lambda_{i}^{*}=\beta_{i}\quad\forall i\in \mathcal{I} \cup \mathcal A(x^{*})$$
$$\lambda_{i}^{*}=0\quad\forall i\in \mathcal{I} \backslash \mathcal A(x^{*})$$
$$\Rightarrow\quad \nabla f(x^{*})=g=\sum\limits_{i \in \mathcal{I} \cup \mathcal A(x^{*})}\lambda_{i}^{*}\nabla c_{i}(x^{*})$$
$$\Leftrightarrow\quad \nabla _{x}\mathcal{L}(x^{*},\lambda^{*})=0$$
And $\lambda_{i}^{*}\ge0\quad\forall i\in \mathcal{I}$ 
and if $c_{i}(x^{*})>0$, then $\lambda_{i}=0$ $\square$
