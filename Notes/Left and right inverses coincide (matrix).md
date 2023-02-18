<div class="topSpace"></div>

Date Created: 07/04/2022 09:17:55
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Basic properties of matrix operations]], [[Homogeneous linear system with more unknowns than equations has non-trivial solutions]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: [[Left and right inverses coincide (function)]]

``` ad-Proposition
title: Proposition.

_Let $K$ be a field and fix $m,n\in\N^+$. Then, for all left and right invertible matrices $A\in\mat{m\times n}{K}$ with one-sided inverses $B,C\in\mat{m\times n}{K}$, respectively, we have that $B=C$. Furthermore, this forces $m=n$ and thus $A$ is invertible._

```

_Proof_. We shall first prove that $B=C$. To this end, observe that
$$\begin{equation}
    BA=I_n\ \ \ \ \ \ \ \ \textrm{and}\ \ \ \ \ \ \ \ AC=I_m,
\end{equation}$$
and compute
$$\begin{equation}
    \begin{aligned}
        B&=BI_m && \textrm{Identity matrix is the identity of matrix multiplication} \\
        &=B\l(AC\r) && \textrm{Substitution} \\
        &=\l(BA\r)C && \textrm{Associativity of matrix multiplication} \\
        &=I_nC && \textrm{Substitution} \\
        &=C. && \textrm{Identity matrix is the identity of matrix multiplication}
    \end{aligned}
\end{equation}$$
We now claim that $BA=I_n$ implies $m\geq n$. To this end, consider the $m\times n$ homogeneous linear system $A\v{x}=\v{0}$. Observe that
$$\begin{equation}
    \v{x}=I_n\v{x}=\l(BA\r)\v{x}=B\l(A\v{x}\r)=B\l(\v{0}\r)=\v{0},
\end{equation}$$
so all solutions thereof are forced to be trivial. Thus it must be the case that $m\geq n$, for if not then $A\v{x}=\v{0}$ would have a non-trivial solution. Similarly, the fact that $AC=I_m$ forces $n\geq m$, and we obtain the desired result.<span style="float:right;">$\blacksquare$</span>
