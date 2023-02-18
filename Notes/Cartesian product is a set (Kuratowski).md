<div class="topSpace"></div>

Date Created: 21/01/2022 17:33:37
Tags: #Proposition #Later/Set_Theory

Proved by: [[Axiom Schema of Specification]], [[Axiom of Extensionality]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $X$ and $Y$ be sets. Then there exists a unique set $z$ whose elements are exactly the sets $u$ for which there exists $x$ in $X$ and $y$ in $Y$ such that $u=\tpl{x,y}$. Formally,_
$$\begin{equation}
    \fa X\fa Y\ex!z\l[u\in z\Leftrightarrow\ex x\in X,\ex y\in Y:u=\tpl{x,y}\r].
\end{equation}$$

```

_Proof_. Let $\phi\l(u\r)$ denote the formula $\l[u\in z\Leftrightarrow\ex x\in X,\ex y\in Y:u=\tpl{x,y}\r]$; we claim that
$$\begin{equation}
    \phi\l(u\r)\Rightarrow u\in\pow \pow\l(X\cup Y\r).
\end{equation}$$
To this end, assume that there exist $x\in X$ and $y\in Y$ such that $u=\tpl{x,y}=\l\{\l\{x\r\},\l\{x,y\r\}\r\}$. Observe that $\l\{x\r\}\subseteq X\subseteq X\cup Y$ and $\l\{x,y\r\}\subseteq X\cup Y$, and thus $\l\{x\r\},\l\{x,y\r\}\in\pow\l(X\cup Y\r)$. It follows then that $u=\tpl{x,y}=\l\{\l\{x\r\},\l\{x,y\r\}\r\}\subseteq\pow\l(X\cup Y\r)$ and thus $u\in\pow \pow\l(X\cup Y\r)$.<span style="float:right;">$\blacksquare$</span>
