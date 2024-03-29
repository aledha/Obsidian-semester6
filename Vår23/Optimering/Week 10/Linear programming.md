## Linear constraints and linear programming
Linear programme: linear constrains+linear problem
Consider linear programmes of the form
$$\min_\limits{x}c^{T}x \quad\text{s.t.}\quad Ax\ge b$$
	$x\in \mathbb{R}^{d}, \quad c\in \mathbb{R}^{d}, \quad A\in \mathbb{R}^{m \times d}, \quad b\in \mathbb{R}^{m}$
	Where $Ax\ge b$ means that $(Ax)_{i}\ge b_{i}\quad\forall\quad i \quad\Leftrightarrow\quad a_{i}x\ge b_{i}$    for all rows $a_{i}$ of $A$.

### Definition: Polyhedron
A set of the form
	$P:=\{x\in \mathbb{R}^{d}: \quad Ax\ge b \}$
is called a *polyhedron*.
#insert 

A bounded polyhedron is called a *polytope*.


### Definition: Hyperplane
Given $\xi \in \mathbb{R}^{d}$ and $s\in \mathbb{R}$, we denote the *hyperplane* by 
$H(\xi ,s):=\{x\in \mathbb{R}^{d}: \quad \xi ^{T}x=s \}.$

#### Definition: Supporting hyperplane
Assume that $P\subset \mathbb{R}^{d}$ is a polyhedron.
We say that $H(\xi ,s)$ is a *supporting hyperplane* for $P$, if
$$\xi ^{T}x\ge s \quad\forall\quad x\in P$$
and $H(\xi ,s)\cap P≠0$.


#### Definition: Face
A set $F\subset \mathbb{R}^{d}$ is called a *face* of the polyhedron $P$, if it is of the form
$$F=P\cap H(\xi ,s)$$
Where $H(\xi ,s)$ is a supporting hyperplane.

#### Definition: Minimal face and vertex
A face $F$ of a polyhedron $P$ is called *minimal*, if it does not contain any other face.
It is called a *vertex* if it consists of a single point.

##### Example
$P=\{(x,y)\in \mathbb{R}^{2}:\quad 0\le x\le1 \}$
#insert 
$P$ has no vertices, but minimal faces 
$F=\{(0,y), y\in \mathbb{R} \}\cup \{(1,y), y\in \mathbb{R} \}$

### Theorem
Consider the linear programme 
$$\min_\limits{x}c^{T}x \quad\text{s.t.}\quad Ax\ge b$$
and denote $P=\{x:\quad Ax\ge b \}$.

Then either:
* $P=Ø$
	* Problem is infeasible
* Problem is unbounded.
	* $\inf_\limits{x\in P}c^{T}x=-\infty$
* There exists a solution
	* There also exists a *minimal face* $F$ of $P$ such that every point in $F$ is a solution.
	* If $P$ has any vertex, then there exists a vertex that solves the problem.

## Lemma
A point $x$ is a vertex of $P=\{\hat x \in \mathbb{R}^{d}: \quad A\hat x=b \}$ 
$\Updownarrow$
$Ax\ge b$ and there exists an index set $B\subset \{1,\dots,m \}$
with $\lvert B \rvert=d \quad\text{s.t.}\quad$ 
the rows $a_{i}\in B$ of the matrix are linearly independant and
$a_{i}x=b \quad\forall\quad i \in B$.

Put differently,
denote $A_{B}:=\{a_{i} \}_{i\in B}$ and  $b_{B}=\{b_{i} \}_{i\in B}$.
The vertices of $P$ are on the form
$$x_{B}:=A_{B}^{-1}b_{B}$$
and satisfy $Ax_{b}\ge b$.

## Definition: Standard form
A linear programme is in *standard form* if it is of the form
$$\min_\limits{}c^{T}x \quad\text{s.t.}\quad \begin{align*}
Ax&=  b\\
x&\ge 0
\end{align*}
$$
Note: If we have a problem in standard form, then the feasible polyhedron cannot contain any lines
$\quad\implies\quad$ all the minimal faces are vertices.
$\quad\implies\quad$ If the problem has a solution, there exists a vertex that is a solution.

One can show that every linear programme can be rewritten in standard form (possibly by increasing the number of variables).

### Example
Continuing the same problem, e.g. for $A\in \mathbb{R}^{d \times m}$
$$\min_\limits{x}c^{T}x \quad\text{s.t.}\quad Ax\ge b$$
First, introduce slack variable $s\in \mathbb{R}^{m}\quad\implies\quad$ rewrite 
$$Ax\ge b \quad \to \quad \begin{align*}
Ax-s&= b\\
s&\ge 0
\end{align*}$$
Then write $x= x^{+}-x^{-}$, with $\begin{cases}x^{+}\ge0 \\ x^{-}\ge0\end{cases}$
$$\implies\quad c^{T}x=c^{T}x^{+}-c^{T}x^{-}$$
And $Ax=Ax^{+}-Ax^{-}$. The problem then becomes
$$\min_\limits{x^{+},x^{-},s}c^{T}x^{+}-c^{T}x^{-} \quad\text{s.t.}\quad \begin{align*}
Ax^{+}-Ax^{-}-s&= b\\
s,x^{+},x^{-}\ge0
\end{align*}$$
Rewrite for simplicity, 
$$\min_\limits{\hat x}\hat c^{T}\hat x \quad\text{s.t.}\quad \begin{align*}
\hat A\hat x&= b\\
\hat x&\ge 0
\end{align*}$$
With $\hat x =\begin{bmatrix}x^{+} \\ x^{-} \\ s & \end{bmatrix}\in \mathbb{R}^{2d+ m}$
$\hat c= \begin{bmatrix}c \\ -c \\ 0\end{bmatrix}\in \mathbb{R}^{2d + m}$  and
$\hat A = \begin{bmatrix}A & -A & -I\end{bmatrix}$
