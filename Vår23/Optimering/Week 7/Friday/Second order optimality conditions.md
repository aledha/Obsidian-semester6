Assume that $x^{*}$ is a point where the [[KKT-conditions]] holds with Lagrange parameters $\lambda^{*}$.
## Critical cone
$$\mathcal{C}(x^{*},\lambda^{*})=\begin{cases}
p\in \mathcal{F}_\Omega(x^{*}):\quad {\left\langle \nabla c_{i}(x^{*}),p \right\rangle}=0
\end{cases}$$
For all $i\in \mathcal{I}\cap \mathcal{A}(x^{*})$ with $\lambda^{*}_{i}>0$
Or
$$p\in \mathcal{C}(x^{*},\lambda^{*})\quad\Leftrightarrow\quad \begin{cases}
{\left\langle \nabla c_{i}(x^{*}),p\right\rangle}=0 \quad\forall\quad i\in \xi \\
{\left\langle \nabla c_{i}(x^{*}),p\right\rangle}\ge0 \quad\forall\quad i\in \mathcal{I}\cap \mathcal{A(x^{*})} \quad \text{with } \lambda^{*}_{i}=0\\
{\left\langle \nabla c_{i}(x^{*}),p\right\rangle}=0 \quad\forall\quad i\in  \mathcal{I}\cap \mathcal{A(x^{*})} \quad \text{with } \lambda^{*}_{i}>0
\end{cases}$$
if $p\in \mathcal{C}(x^{*},\lambda^{*})$, then 
$${\left\langle \nabla f(x^{*}),p \right\rangle}=\sum\limits_{i\in \xi \cup \mathcal{I}}\lambda^{*}_{i}{\left\langle \nabla c_{i}(x^{*}), p \right\rangle}=0$$
if $p\in \mathcal{F}_{\Omega}(x^{*})\backslash \mathcal{C}(x^{*},\lambda^{*})$, then there is an $i\in \mathcal{A}(x^{*})$ such that
$$\lambda_{i}^{*}\quad \text{and }\quad {\left\langle \nabla c_{i}(x^{*}),p \right\rangle}>0$$
$$\Rightarrow\quad {\left\langle \nabla f(x^{*}),p \right\rangle}>0$$

## Theorem
Assume that $x^{*}$ is a local solution of 
$$\min_{}f(x)\quad \text{such that}\quad \begin{cases}
c_{i}(x)=0 & i\in \xi \\
c_{i}(x)\ge  & i\in \mathcal{I}
\end{cases}$$
and that LICQ holds at $x^{*}$. 
Then the [[KKT-conditions]] holds with some Lagrange parameter $\lambda^{*}$.
Moreover
$${\left\langle p,H_\mathcal{L}(x^{*},\lambda^{*})p \right\rangle}\ge0\quad\forall\quad p\in \mathcal{C}(x^{*},\lambda^{*})$$where $$H_\mathcal{L}(x^{*},\lambda^{*})= H_{f}(x^{*})-\sum\limits_{i\in \xi \cup \mathcal{I}}\lambda_{i}^{*}H_{C_{i}}(x^{*})$$
Conversely, if $x^{*}$ is a KKT point with Lagrange multiplier $\lambda^{*}$ and 
$${\left\langle p,H_\mathcal{L}(x^{*},\lambda^{*})p \right\rangle}>0\quad\forall\quad p\in \mathcal{C}(x^{*},\lambda^{*})\backslash(0)$$
(Strict inequality).
Then $x^{*}$ is a strict, isolated local minimum.

### Example from [[Example of KKT]]
Minimize
$$f(x)=-(x-1)^{2}-(y+1)^{2}$$
Such that $y^{3}\ge x^{2}$ and $x^{2}+y^{2}\le0$
(0,0) was not a KKT point, but 
(-1,1) was a KKT point with $\lambda_{1}=0, \quad \lambda_{2}=2$.
$$p\in \mathcal{C}\left(\begin{pmatrix}-1 \\ 1\end{pmatrix}, \begin{pmatrix}0 \\ 2\end{pmatrix}\right) \quad\Leftrightarrow\quad \begin{cases}
{\left\langle p, \nabla c_{1}(-1,1) \right\rangle}\ge0 \\
{\left\langle p, \nabla c_{2}(-1,1) \right\rangle}=0
\end{cases}$$
Remember

$$\nabla c_{1}(x,y)=\begin{pmatrix}-2x  \\ 3y^{2}\end{pmatrix}$$
$$\nabla c_{2}(x,y)=\begin{pmatrix}-2x \\ -2y\end{pmatrix}$$
$$\nabla c_{2}(-1,1)=\begin{pmatrix}2 \\ -2\end{pmatrix} \quad \quad \nabla c_{1}=\begin{pmatrix}2 \\ 3\end{pmatrix}$$
$$\Rightarrow\quad p=(p_{1},p_{2})\in \mathcal{C}\left(\begin{pmatrix}-1 \\ 1\end{pmatrix}, \begin{pmatrix}0 \\ 2\end{pmatrix}\right)$$
$$\quad\Leftrightarrow\quad \begin{cases}
2p_{1}+3p_{2}\ge 0 \\
2p_{1}-2p_{2}=0
\end{cases}$$
$$\Rightarrow\quad \mathcal{C}= \begin{cases}
(p,p)\cdot p\ge0
\end{cases}$$
$$\mathcal{L}(x,y,\lambda_{1},\lambda_{2})= -(x-1)^{2}-(y+1)^{2}-\lambda_{1}(y^{3}-x^{2})-\lambda_{2}(2-x^{2}-y^{2})$$
$$\mathcal{L}(x,y,0,2)= -(x-1)^{2}-(y+1)^{2}-2(2-x^{2}-y^{2})$$
$$H_\mathcal{L}(x,y,0,2)= \begin{pmatrix}2 & 0 \\ 0 & 2\end{pmatrix}$$
$$\Rightarrow\quad {\left\langle (p,p),\quad H_\mathcal{L}((-1,1), (0,2)) \cdot(p,p) \right\rangle}$$
$$={\left\langle (p,p),\quad \begin{pmatrix}2 & 0 \\ 0 & 2\end{pmatrix} \begin{pmatrix}p \\ p\end{pmatrix}\right\rangle}>0$$
Then (-1,1) is a strict local solution.

Note:
if $\lambda_{1},\dots,\lambda_{d}>0$        (i.e. $d$ active inequality constraints)
And LICQ holds, then:
$$\mathcal{C}(x,\lambda)= \begin{cases}
p \in \mathbb{R}^{d}:\quad {\left\langle \nabla c_{i}(x),p \right\rangle}=0 \quad\forall\quad i
\end{cases}$$
LICQ $\quad\Rightarrow\quad$ $\nabla c_{i}(x)$ form a basis for $\mathbb{R}^{d}$.
Then the second order optimality condition is automatically satisfied. $\quad\Rightarrow\quad$ we have found a solutionori