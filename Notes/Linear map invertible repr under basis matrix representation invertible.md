---
mathLink: auto
---

<div class="topSpace"></div>

Date Created: 28/05/2022 17:05:24
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Linearly isomorphic iff dimensions coincide (finite-dim.)]], [[Identity function repr under basis by identity matrix]], [[Composition of linear maps repr under basis matrix product of representations]], [[Linear isomorphism between linear maps and matrices]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $V$ and $W$ be finite-dimensional $K$-vector spaces with bases $\mc{B}$ and $\mc{C}$, respectively, and consider a linear map $T:V\to W$. Then $T$ is invertible iff_ $\l[T\r]_\mc{B}^\mc{C}$ _is invertible, in which case_ $\l(\l[T\r]_\mc{B}^\mc{C}\r)^{-1}=\l[T^{-1}\r]_\mc{C}^\mc{B}$_._

```

_Proof_.
* ($\Rightarrow$): Since $T:V\to W$ is an invertible linear map, we see that $V\iso W$ and thus $n\coloneqq\dim V=\dim W$. Observe then that
$$\begin{equation}
    \begin{aligned}
        I_n&=\l[\id_V\r]_\mc{B} \\
        &=\l[T^{-1}\circ T\r]_\mc{B} \\
        &=\l[T^{-1}\r]_\mc{C}^\mc{B}\l[T\r]_\mc{B}^\mc{C}
    \end{aligned}\ \ \ \ \ \ \ \ \textrm{and}\ \ \ \ \ \ \ \ 
    \begin{aligned}
        I_n&=\l[\id_W\r]_\mc{C} && \textrm{$I$ is represented by $\id$} \\
        &=\l[T\circ T^{-1}\r]_\mc{C} && \textrm{Definition of $T^{-1}$} \\
        &=\l[T\r]_\mc{B}^\mc{C}\l[T^{-1}\r]_\mc{C}^\mc{B}. && \textrm{$\circ$ is represented by $\times$}
    \end{aligned}
\end{equation}$$

* ($\Leftarrow$): Conversely, if $A\coloneqq\l[T\r]_\mc{B}^\mc{C}$ is invertible, then $n\coloneqq\dim V=\dim W$ by definition. Let $B\in\mat{n\times n}{K}$ be the inverse of $A$ and let $U:W\to V$ be the unique linear map such that $\l[U\r]_\mc{C}^\mc{B}=B$. It suffices to show that $U=T^{-1}$. Observe that
$$\begin{equation}
    \begin{aligned}
        \l[U\circ T\r]_\mc{B}&=\l[U\r]_\mc{C}^\mc{B}\l[T\r]_\mc{B}^\mc{C} \\
        &=BA \\
        &=I_n \\
        &=\l[\id_V\r]_\mc{B}
    \end{aligned}\ \ \ \ \ \ \ \ \textrm{and}\ \ \ \ \ \ \ \ 
    \begin{aligned}
        \l[T\circ U\r]_\mc{C}&=\l[T\r]_\mc{B}^\mc{C}\l[U\r]_\mc{C}^\mc{B} && \textrm{$\circ$ is represented by $\times$} \\
        &=AB && \textrm{Substitution} \\
        &=I_n && B=A^{-1} \\
        &=\l[\id_W\r]_\mc{C}, && \textrm{$I$ is represented by $\id$}
    \end{aligned}
\end{equation}$$
so, since $\l[\slot\r]_\mc{B}$ and $\l[\slot\r]_\mc{C}$ are injective, we see that $U\circ T=\id_V$ and $T\circ U=\id_W$.<span style="float:right;">$\blacksquare$</span>
