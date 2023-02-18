<div class="topSpace"></div>

Date Created: 14/05/2022 13:39:47
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Linear map is injective iff kernel vanishes]], [[Dimension of vector space is zero iff it is the zero vector space]], [[Dimension Theorem]], [[Dimension of subspace]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $V$ and $W$ be finite-dimensional $K$-vector spaces with $\dim V>\dim W$. Then no linear map $T:V\to W$ is injective._

```

_Proof_. It suffices to show that $\ker T\neq\l\{0\r\}$, or, equivalently, that $\dim\ker T\neq0$. The result follows from the following computation:
$$\begin{align}
    \dim\ker T&=\dim V-\dim\im T && \textrm{Dimension Theorem} \\
    &\geq\dim V-\dim W && \im T\subseteq W \\
    &>0. && \textrm{Hypothesis}\qedin
\end{align}$$
