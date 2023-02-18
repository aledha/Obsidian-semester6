<div class="topSpace"></div>

Date Created: 21/01/2022 18:23:06
Tags: #Proposition #Later/Set_Theory

Proved by: [[Axiom Schema of Specification]], [[Axiom of Extensionality]], [[Cartesian product is monotone w.r.t. subsets]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $X$ and $Y$ be sets. Then there exists a unique set $z$ whose elements are exactly the functions from $X$ into $Y$. Formally,_
$$\begin{equation}
    \fa X\fa Y\ex!z:\l(f\in z\Leftrightarrow f:X\to Y\r).
\end{equation}$$

```

_Proof_. Let $\phi\l(f\r)$ denote the formula $f:X\to Y$; we claim that
$$\begin{equation}
    \phi\l(f\r)\Rightarrow x\in\pow\l(X\times Y\r).
\end{equation}$$
To this end, take a function $f:X\to Y$. By definition, we have that $f$ is a binary relation with $\dom f=X$ and $\ran f\subseteq Y$. Observe that
$$\begin{equation}
    f\subseteq\dom f\times\ran f\subseteq X\times Y,
\end{equation}$$
and thus $f\subseteq X\times Y$. It follows that $f\in\pow\l(X\times Y\r)$.<span style="float:right;">$\blacksquare$</span>
