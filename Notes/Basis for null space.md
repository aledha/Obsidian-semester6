<div class="topSpace"></div>

Date Created: 13/04/2022 21:05:54
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Gaussian Elimination]], [[Dimension Theorem]], [[Rank of matrix in RREF is number of pivot columns of non-zero rows]], [[Spanning subset with same cardinality as dimension (finite) is a basis]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ be a field and consider a matrix $A\in\mat{m\times n}{K}$ with $r\coloneqq\rank A$ for some fixed $m,n,r\in\N^+$. Set $B\coloneqq\rref A$ and let each $k_i\in K$ denote the pivot column in $B$ corresponding to its $i^\textrm{\it{th}}$ row. Then there exists a set_ $\l\{\v{u}_1,\dots,\v{u}_{n-r}\r\}$_, called a set of **basic solutions of $A\v{x}=\v{b}$**, that forms a basis for $\nullsp A$._

```

_Proof_. For convenience, we shall denote
$$\begin{equation}
    \mc{K}\coloneqq\l\{k\in\N\mid k\textrm{ is a pivot column of }B\r\}\ \ \ \ \ \ \ \ \textrm{and}\ \ \ \ \ \ \ \ \mc{J}\coloneqq\l\{1,\dots,n\r\}\setminus\mc{K}.
\end{equation}$$
By Gaussian Elimination, there exist $t_j\in K$ for all $j\in\l\{1,\dots,n\r\}$ such that every solution $\v{s}\in\nullsp A$ can be expressed as
$$\begin{equation}
    \v{s}=\sum_{j\in\mc{J}}t_j\v{u}_j,
\end{equation}$$
where
$$\begin{equation}
    \l(\v{u}_j\r)_\alpha=
        \begin{dcases}
            -b_{ij} & \textrm{if }\ex i\in\l\{1,\dots,r\r\}:\alpha=k_i \\
            \frac{t_\alpha\delta_{\alpha j}}{t_j} & \textrm{else.}
        \end{dcases}\ \ \ \ \ \ \ \ \l(\alpha\in\l\{1,\dots,n\r\}\r)
\end{equation}$$
Thus the set $\l\{\v{u}_j\r\}_{j\in\mc{J}}$ spans $\nullsp A$. But since
$$\begin{equation}
    \begin{aligned}
        \dim\nullsp A&=n-\rank A && \textrm{Dimension Theorem} \\
        &=n-\l|\mc{K}\r| && \rank A\textrm{ is the number of pivot columns of }\rref A \\
        &=\l|\mc{J}\r|, && \textrm{Definition of $\mc{J}$}
    \end{aligned}
\end{equation}$$
those vectors form a basis for $\nullsp A$. The result follows after reindexing.<span style="float:right;">$\blacksquare$</span>
