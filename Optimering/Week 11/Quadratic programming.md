Consider a *quadratic programme*, that is a quadratic optimization problem with linear constraints, say
$$\min_\limits{x} \frac{1}{2}{\left\langle x \text{ , } Gx \right\rangle} + {\left\langle c \text{ , } x \right\rangle} \qquad\text{s.t.}\quad \begin{align*}
	{\left\langle a \text{ , } x \right\rangle}&= b_{i}, \quad\text{for }i\in \xi \\
	 {\left\langle a \text{ , } x \right\rangle}&\ge b_{i}\quad\text{for }i\in \mathcal{I}
\end{align*}.$$
Here: $G\in \mathbb{R}^{d\times d}$ is symmetric, $c\in \mathbb{R}^{d}$, $a_{i} \in \mathbb{R}^{d}$  and $b_{i}\in \mathbb{R}$.

If $G$ is positive definite $\quad\implies\quad$ problem is convex (with linear constraints)
$\implies\quad$ if the problem is feasible, we have a unique solution characterised by the [[KKT-conditions]].

Else: existence is not guaranteed, KKT-conditions are necessary, not sufficient. We can have local minimisers.

We restrict ourselves to the positive definite case.
	Rather, we only need positive definite on the equality constraints
	${\left\langle p \text{ , } Gp \right\rangle}>0 \quad\forall\quad p\in \mathbb{R}^{d}\backslash \{0 \}$
	$\quad\text{s.t.}\quad {\left\langle a_{i} \text{ , } p \right\rangle} =0\quad\forall\quad i\in \xi$.

## Only equality constraints
$$\min_\limits{x} \frac{1}{2} {\left\langle x \text{ , } Gx \right\rangle}+{\left\langle c \text{ , } x \right\rangle} \qquad\text{s.t.}\quad {\left\langle a_{i} \text{ , } x \right\rangle}= b_{i} \quad\forall\quad i\in \xi $$
Where ${\left\langle a_{i} \text{ , } x \right\rangle}= b_{i} \quad\forall\quad i\in \xi$  is equivalent to
	$Ax =b$      with the rows of $A=a_{i}$

The [[KKT-conditions]] reads:
$$\begin{align*}
Gx+c=\sum\limits_{i}^{}\lambda _{i}a_{i}&= A^{T}\lambda \\
Ax&= b
\end{align*}$$
Have a linear system in $(x,\lambda )$, e.g.
$$\begin{bmatrix}G & -A^{T} \\ A & 0 \end{bmatrix}\begin{bmatrix}x \\ \lambda \end{bmatrix}=\begin{bmatrix}-c \\ b\end{bmatrix}.\tag{*}$$
$\implies\quad$ solutions of $(*)$ are the solutions of the quadratic programme.
The system is indefinite $\quad\implies\quad$ Cholesky decomposition and conjugate gradient method will fail.

## Equality and inequality constraints
$$\min_\limits{x} \frac{1}{2}{\left\langle x \text{ , } Gx \right\rangle} + {\left\langle c \text{ , } x \right\rangle} \qquad\text{s.t.}\quad \begin{align*}
	{\left\langle a_{i} \text{ , } x \right\rangle}&\ge b_{i}\quad\text{for }i\in \xi \\
	{\left\langle a_{i} \text{ , } x \right\rangle}&= b_{i}\quad\text{for }i\in \mathcal{I}
\end{align*}$$
	And $G$ is positive definite.

KKT-conditions are necessary and sufficient:
$$\begin{align*}
	Gx+c&= \sum\limits_{i\in \xi \cup \mathcal{I}}^{} \lambda _{i}a_{i},\\
	{\left\langle a_{i} \text{ , } x \right\rangle}&= b_{i} \quad\text{for } i\in \xi, \\
{\left\langle a_{i} \text{ , } x \right\rangle}&\ge b_{i} \quad\text{for }i\in \mathcal{I},\\
\lambda _{i} &\ge 0 \quad\text{for }i\in \mathcal{I}.
\end{align*}$$
If $\lambda _{i}>0\quad\implies\quad {\left\langle a_{i} \text{ , } x \right\rangle}=b_{i}\quad\text{for }i\in \mathcal{I}$.
**If** we would know the correct active set $\mathcal{A}(x)$, we would obtain  the equality constrained problem of
$$\min_\limits{x} \frac{1}{2} {\left\langle x \text{ , } Gx \right\rangle}+{\left\langle c \text{ , } x \right\rangle} \qquad\text{s.t.}\quad {\left\langle a_{i} \text{ , } x \right\rangle}=b_{i}\quad\text{for }i\in\mathcal{A}(x),$$
which we already know how to solve.



**Idea**: find the active set $\mathcal{A}(x)$ in a systematic manner
	Start with a guess
	"Working set"
	$W_{0}\supset \xi$   
	And add/remove indicies until we have found the solution
Algorithm in [[Active set method]]
