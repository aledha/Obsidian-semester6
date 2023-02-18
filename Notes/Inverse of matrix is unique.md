<div class="topSpace"></div>

Date Created: 07/04/2022 07:22:22
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Basic properties of matrix operations]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ be a field and fix $n\in\N^+$. Then, for all invertible matrices $A\in\mat{n}{K}$, its inverse is unique._

```

_Proof_. Suppose both $B,C\in\mat{n}{K}$ are inverses of $A$, so, in particular, we have that
$$\begin{equation}
    CA=I_n=AB.
\end{equation}$$
Observe then that
$$\begin{align}
    B&=I_nB && \textrm{Identity matrix is the identity of matrix multiplication} \\
    &=\l(CA\r)B && \textrm{Substitution} \\
    &=C\l(AB\r) && \textrm{Associativity of matrix multiplication} \\
    &=CI_n && \textrm{Substitution} \\
    &=C. && \textrm{Identity matrix is the identity of matrix multiplication}\qedin
\end{align}$$
