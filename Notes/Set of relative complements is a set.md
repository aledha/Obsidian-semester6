<div class="topSpace"></div>

Date Created: 18/01/2022 16:08:40
Tags: #Proposition #Later/Set_Theory

Proved by: [[Axiom Schema of Specification]], [[Axiom of Extensionality]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $v$ and $U$ be sets. Then there exists a unique set $z$ whose elements are exactly the sets $v\comp u$ for all sets $u\in U$. Formally,_
$$\begin{equation}
    \fa v\fa U\ex!z\fa x\l[x\in z\Leftrightarrow\l(\ex u\in U\r)x=v\comp u\r].
\end{equation}$$

```

_Proof_. Let $\phi\l(x\r)$ denote the formula $\l(\ex u\in U\r)x=v\comp u$; we claim that
$$\begin{equation}
    \phi\l(x\r)\Rightarrow x\in\pow v.
\end{equation}$$
To this end, take a set $x$ with $x=v\comp u$ for some $u\in U$. Since $v\comp u\subseteq v$, we have, by definition of the power set, $v\comp u\in\pow v$. Thus $x\in\pow v$.<span style="float:right;">$\blacksquare$</span>