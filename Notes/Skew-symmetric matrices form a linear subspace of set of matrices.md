---
mathLink: $\Skew_n\!\l(K\r)\subseteq\mat{n}{K}$ is a linear subspace
---

<div class="topSpace"></div>

Date Created: 09/05/2022 18:18:04
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Transposition is a linear map]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ be a field and fix $n\in\N^+$. Then $\Skew_n\!\l(K\r)\subseteq\mat{n}{K}$ is a linear subspace._

```

_Proof_. It suffices to show that $0_n\in\Skew_n\!\l(K\r)$ and, for every $\alpha\in K$ and $A,B\in\Skew_n\!\l(K\r)$, that $\alpha A+B\in\Skew_n\!\l(K\r)$.
* ($0_n\in\Skew_n\!\l(K\r)$): This follows readily since $0_n^\trans=0_n=-0_n.$

* ($\alpha A+B\in\Skew_n\!\l(K\r)$): The result follows from the following computation:
$$\begin{align}
    \l(\alpha A+B\r)^\trans&=\l(\alpha A\r)^\trans+B^\trans && \textrm{Transposition respects matrix addition} \\
    &=\alpha A^\trans+B^\trans && \textrm{Transposition respects scalar multiplication} \\
    &=\alpha\l(-A\r)+\l(-B\r) && A,B\in\Skew_n\!\l(K\r) \\
    &=-\l(\alpha A+B\r). && \textrm{Arithmetic}\qedin
\end{align}$$
