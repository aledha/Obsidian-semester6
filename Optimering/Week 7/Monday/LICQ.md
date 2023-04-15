=Linear independance constraint qualification
## Definition:
Let $\Omega\in \mathbb{R}^d$ be given by the constraints
$$\begin{cases}
c_{i}=0  &  i\in \xi \\
c_{i}\ge 0 & i\in \mathcal{I}
\end{cases}$$
And let $x\in \Omega$. We say that the "linear independence constraint qualification" (LICQ) is satisfied if the set
$$\nabla c_{i}(x), \qquad i\in \mathcal{A}(x)$$
is linearly independent.
### Example 1
$$c_{1}(x,y) =x^{2}+y^{2}-1 \stackrel{!}{=}0$$
$$c_{2}(x,y)=x\ge0$$
At $(0,1)$ both constraints are active and
$$\nabla c_{1}(0,1)= \begin{bmatrix}0 \\ 2\end{bmatrix}$$
$$\nabla c_{2}(0,1)=\begin{bmatrix}1 \\ 0\end{bmatrix}$$
$$\Rightarrow\quad \text{LICQ holds. At (1,0) }c_{1} \text{ is active and}$$
$$\nabla c_{1}(1,0)=\begin{bmatrix}2 \\ 0\end{bmatrix}$$
LICQ holds
### Example 2
$$c_{1}(x,y)=xy\ge 0$$
At (0,0) the constaint is active and
$$\nabla c_{1}(0,0)=\begin{bmatrix}0 \\ 0\end{bmatrix}$$
$\begin{bmatrix}0 \\ 0\end{bmatrix}$ is **not** linearly independant $\Rightarrow$ LIQC does **not** hold.

## Theorem
Let $x\in \Omega$. 
Then
$$T_{\Omega}(x)\subset \mathcal{F}_\Omega(x)\tag{1}$$
Additionaly,
$$\text{LICQ holds at } x \quad \text{i.e., } \nabla c_{i}(x),\quad  i\in \mathcal{(x)} \text{ is linearly independant}$$$$\quad\Rightarrow\quad T_\Omega(x)=\mathcal{F}_\Omega(x)\tag{2}$$
Where
$$\mathcal{F}_{\Omega}(x)=p:\begin{cases}
{\left\langle p,\nabla c_{i}(x) \right\rangle}=0 & i\in \xi \\
{\left\langle p,\nabla c_{i}(x) \right\rangle}\ge0 & i\in \mathcal{A(x)}\cup \mathcal{I}
\end{cases}$$
### Proof (hardest proof in the course)
(1) is essentialy a Taylor series expansion. Se NB for proof.
(2):
Assume LICQ holds. Assume that all the constraints are active (inactive doesn't play any role at $x$), without loss of generality.
i.e.,
$$\mathcal{A}(x)= \xi \cup \mathcal{I}$$
Let $p\in \mathcal{F}_\Omega(x)$. Need to show that $p\in T_\Omega(x)$. 
Idea: construct a curve $z(t)$ such that
$$z(t)\in \Omega \qquad \text{for small }t>0$$
and 
$$z'(t)=p$$
$$\Rightarrow\quad p= \stackrel{\text{lim}}{t\rightarrow0} \frac{z(t)-x}{t}$$
$$p\in \mathcal{F}_{\Omega(x)}$$$$\quad\Rightarrow\quad {\left\langle \nabla c_{i},p \right\rangle}=0, \qquad i\in \xi$$
$${\left\langle \nabla c_{i}(x),p \right\rangle}\ge 0, \qquad i\in \mathcal{I}$$
And (LICQ) the vectors
$$\nabla c_{i}(x), \qquad i\in \xi\cup \mathcal{I}$$
are linearly independant.
Write $c(x)=(c_{i}(x))_{i\in \xi\cup \mathcal{I}}$.
$$c: \mathbb{R}^{d}\rightarrow \mathbb{R}^{\xi\cup \mathcal{I}}$$
and let the Jacobian
$$J_{c}(x)=:A\in\mathbb{R}^{\xi\cup \mathcal{I}}$$
(rows of $A$ are $\nabla c_{i}(x)^{T}$) $\Rightarrow\quad$ A has full rank.
Let $w_{1},\dots,w_m$ where $m=d- |\xi\cup \mathcal{I}|$
be a basis of the orthogonal complement of the space spanned by $\nabla c_{i}(x)$ for $i\in \xi\cup \mathcal{I}$ and let
$$W=(w_{1},\dots, w_{m})$$
The matrix 
$$\begin{bmatrix}A \\ W_{T} & \end{bmatrix}\in \mathbb{R}^{d\times d}$$
is non-singular.
Define the function 
$$R:\mathbb{R}^{d}\times \mathbb{R} \rightarrow \mathbb{R}^d$$
$$R(z,t)= \begin{bmatrix}c(z)-tAp \\ W^{T}(z-x-tp)\end{bmatrix}$$
Then notice
$$R(x,0)=\begin{bmatrix} c(x)\\ 0\end{bmatrix}=\begin{bmatrix}0 \\ 0\end{bmatrix}$$
Since all the constraints are active. And the jacobian
$$J_{z}(R(z,t))= \begin{bmatrix}J_{c}(z) \\ W_{T}\end{bmatrix}$$
$$\Rightarrow\quad J_{z}(R(x,0))= \begin{bmatrix}A \\ W_{T}\end{bmatrix}$$
Which we have shown is non-singular.
#### Implicit function theorem
There exists an open interval $I$ with $0\in I$ and a (unique) differentiable function $z:I\rightarrow \mathbb{R}^{d}$ such that
$$z(0) =x$$
and
$$R(z(t), t)=0, \quad t\in I$$

Since $R(z(t),t)=0$, we have
$$\begin{align*}
c(z(t)) &= tAp\\
\Leftrightarrow\quad c_{i}(z(t))&=t \nabla c_{i}(x)^{T}p\\
&= t {\left\langle \nabla c_{i}(x),p \right\rangle}
\end{align*}$$
For $i\in \xi$ we have ${\left\langle \nabla c_{i}(x), p \right\rangle}=0$
$$\Rightarrow\quad c_{i}(z(t))=0$$
For $i\in \mathcal{I}$ we have ${\left\langle \nabla c_{i}(x), p \right\rangle}\ge 0$
$$\Rightarrow\quad c_{i}(z(t))\ge 0 \qquad t\ge 0$$
$$\Rightarrow\quad z(t)\in \Omega, \qquad t>0$$
And:
$$R(z(t), t) = 0 \text{ implies that}$$
$$J_{z}(R(z(t), t)) \cdot z'(t) + \partial_{t}R(z(t), t)=0$$
$$\Rightarrow\quad z'(t)=-J_{z}R(x,0)^{-1}\partial_{t} R(x,0)$$
Since $-J_{z}R(x,0)^{-1} = \begin{bmatrix}A \\ W^{T}\end{bmatrix}$ and $\partial_{t} R(x,0)= -\begin{bmatrix}Ap \\ W^{T}p\end{bmatrix}$
$$z'(t)=p$$
Choose $t_{k}>0, \quad t_{k}\rightarrow 0$ 
let $z_{k}=z(t_{k})$
$\Rightarrow\quad z_{k}\in \Omega, \quad z_{k}\rightarrow x$
and 
$$\stackrel{lim}{k \rightarrow \infty} \frac{z_{k}-x}{t_{k}}=\stackrel{lim}{k \rightarrow \infty} \frac{z(t_{k)}-x}{t_{k}}$$
$$=z'(0)=p \Rightarrow\quad p\in T_{\Omega}(x)\qquad \square$$


(break)


### Lemma
If $x^{*}$ is a local solution of $\min_{x\in \Omega}f(x)$ and LICQ holds at $x^{*}$, then
$${\left\langle \nabla f(x^{*}),p \right\rangle}\ge 0 \quad \forall p\in \mathcal{F}_\Omega(x^{*})$$
