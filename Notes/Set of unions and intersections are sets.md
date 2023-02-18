<div class="topSpace"></div>

Date Created: 15/01/2022 17:21:16
Tags: #Proposition #Later/Set_Theory

Proved by: [[Axiom Schema of Specification]], [[Axiom of Extensionality]], [[Basic properties of unions, intersections, and power sets]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $v$ and $U$ be sets. Then there exists a unique set $z_1$ whose elements are exactly the sets $v\cup u$ for all sets $u\in U$. Similarly, there exists a unique set $z_2$ whose elements are exactly the sets $v\cap u$ for all sets $u\in U$. Formally, _
$$\begin{equation}
    \begin{gathered}
        \fa v\fa U\ex!z_1\fa x\l[x\in z_1\Leftrightarrow\l(\ex u\in U\r)x=v\cup u\r]\\
        \fa v\fa U\ex!z_2\fa x\l[x\in z_2\Leftrightarrow\l(\ex u\in U\r)x=v\cap u\r].
    \end{gathered}
\end{equation}$$

```

_Proof_. We shall prove the statement for $z_1$; the proof for $z_2$ is analogous. Let $\phi\l(x\r)$ denote the formula $\l(\ex u\in U\r)x=v\cup u$; we claim that
$$\begin{equation}
    \phi\l(x\r)\Rightarrow x\in\pow\l(v\cup\bigcup U\r).
\end{equation}$$
To this end, take a set $x$ with $x=v\cup u$ for some $u\in U$. Since $u\subseteq\bigcup U$, we have $v\cup u\subseteq v\cup\bigcup U$. By definition of the power set, we have $v\cup u\in\pow\l(v\cup\bigcup U\r)$, and so $x\in\pow\l(v\cup\bigcup U\r)$.<span style="float:right;">$\blacksquare$</span>
