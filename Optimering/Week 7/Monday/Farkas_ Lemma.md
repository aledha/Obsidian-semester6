Let $a_{i} \quad i\in \xi$ and $b_{i} \quad i\in \mathcal{I}$ be vectors in $\mathbb{R}^d$ and let
$$g\in \mathbb{R}^{d}$$
Then precisely one of the two following statements holds.
(1):
$$\text{There exists }p\in \mathbb{R}^{d} \text{ such that}$$
$$\begin{align*}
{\left\langle g, p \right\rangle}&\le 0\\
{\left\langle p,a_{i} \right\rangle} &=0, \quad i\in \xi\\
{\left\langle p,b_{i} \right\rangle} &\ge 0, \quad i\in \mathcal{I}
\end{align*}$$
(2):
We can write $$g=\sum\limits_{i\in \xi} \alpha_{i}a_{i}+\sum\limits_{i\in \mathcal{I}}\beta_{i}b_{i}$$
with $\alpha_{i}\in \mathbb{R}$ and $\beta_{i}\ge 0$.

We will not cover this proof, see NW.

## Usage in optimization
Given an optimization problem 
$$\min_{x}f(x) \quad \text{s.t.} \begin{cases}
c_{i}(x) = 0 \quad\forall i\in \xi \\
c_{i}(x)\ge0 \quad\forall i\in \mathcal{I}
\end{cases}\tag{P}$$
we define the Lagrangian $\mathcal{L}:\mathbb{R}^{d}\times \mathbb{R}^{\xi \cup \mathcal{I}}\to \mathbb{R}$ 
$$\mathcal{L}(x,\lambda)=f(x)- \sum\limits_{i\in \xi \cup \mathcal{I}}\lambda_{i}c_{i}(x)$$
Continuation: [[KKT-conditions]]
