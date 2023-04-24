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

### ChatGPT
The Karush-Kuhn-Tucker (KKT) conditions are a set of necessary conditions for a solution to be optimal in a constrained optimization problem. They provide a way to incorporate the constraints into the problem while still searching for the optimal solution. The KKT conditions are especially useful in nonlinear programming, and they help generalize the concept of optimality.

To build intuition, let's first consider the unconstrained optimization problem:

$$
\text{minimize } f(x)
$$

In this case, we know that a necessary condition for optimality is that the gradient of the objective function is zero:

$$
\nabla f(x^*) = 0
$$

Now, let's move to a constrained optimization problem:

$$
\begin{aligned}
&\text{minimize } && f(x) \\
&\text{subject to } && g_i(x) \leq 0, \; i = 1,\dots,m \\
& && h_j(x) = 0, \; j = 1,\dots,p
\end{aligned}
$$

The KKT conditions consist of the following five conditions:

1. **Stationarity condition**: This condition generalizes the idea that the gradient should be zero. It states that a linear combination of the gradients of the objective function and the constraints should be zero. Mathematically:

$$
\nabla f(x^*) + \sum_{i=1}^m \lambda_i^* \nabla g_i(x^*) + \sum_{j=1}^p \mu_j^* \nabla h_j(x^*) = 0
$$

where $\lambda_i^*$ and $\mu_j^*$ are the Lagrange multipliers associated with the inequality and equality constraints, respectively.

2. **Primal feasibility**: The optimal solution must satisfy the constraints of the problem:

$$
\begin{align*}
g_i(x^*) \leq 0, \; i = 1,\dots,m \\
h_j(x^*) = 0, \; j = 1,\dots,p
\end{align*}
$$

3. **Dual feasibility**: The Lagrange multipliers associated with the inequality constraints must be non-negative:

$$
\lambda_i^* \geq 0, \; i = 1,\dots,m
$$

4. **Complementary slackness**: This condition enforces that if an inequality constraint is not active (i.e., not tight) at the optimal solution, the corresponding Lagrange multiplier must be zero:

$$
\lambda_i^* g_i(x^*) = 0, \; i = 1,\dots,m
$$

5. **Linear Independence Constraint Qualification (LICQ)**: As previously discussed, the gradients of active inequality constraints and equality constraints must be linearly independent at the optimal solution.

Intuitively, the KKT conditions combine the information from the objective function and the constraints to form a unified set of conditions that must be satisfied for a solution to be optimal. When the problem is convex, and the LICQ is satisfied, the KKT conditions are not only necessary but also sufficient for optimality, which means that if a point satisfies the KKT conditions, it is guaranteed to be a global optimum.