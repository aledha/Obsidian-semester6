<div class="topSpace"></div>

Date Created: 01/02/2022 16:28:32
Tags: #Proposition #Later/Set_Theory

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $\leq$ and $\preceq$ be partial orders on the sets $X$ and $Y$, respectively. Then the binary relation defined by_
$$\begin{equation}
    \tpl{x_1,y_1}\sqsubseteq\tpl{x_2,y_2}\ \ \ \ \Leftrightarrow\ \ \ \ \l[x_1<x_2\lor\l(x_1=x_2\land y_1\preceq y_2\r)\r]
\end{equation}$$
_for all $x_1,x_2\in X$ and $y_1,y_2\in Y$ is the reflexive closure of the strict lexicographical order $\sqsubset$ on $X\times Y$._

```

_Proof_. We shall show that $\sqsubseteq\,=\rfcl\sqsubset=\,\sqsubset\cup\id_{X\times Y}$.
* ($\subseteq$): Take $\tpl{x_1,y_1},\tpl{x_2,y_2}$ such that $\tpl{x_1,y_1}\sqsubseteq\tpl{x_2,y_2}$.
    * If $x_1<x_2$, then $\tpl{x_1,y_1}\sqsubset\tpl{x_2,y_2}$ follows immediately.
    * If $x_1=x_2\land y_1\preceq y_2$, then either $x_1=x_2\land y_1\prec y_2$ from which we have $\tpl{x_1,y_1}\sqsubset\tpl{x_2,y_2}$, or $x_1=x_2\land y_1=y_2$ from which we have $\tpl{\tpl{x_1,y_1},\tpl{x_2,y_2}}\in\id_{X\times Y}$.

* ($\supseteq$): Take $\tpl{x_1,y_1},\tpl{x_2,y_2}$ such that either $\tpl{x_1,y_1}\sqsubset\tpl{x_2,y_2}$ or $\tpl{x_1,y_1}=\tpl{x_2,y_2}$.
    * If $x_1<x_2$, then $\tpl{x_1,y_1}\sqsubseteq\tpl{x_2,y_2}$ follows immediately.
    * If $x_1=x_2\land y_1\prec y_2$, then $y_1\preceq y_2$ too and thus $\tpl{x_1,y_1}\sqsubseteq\tpl{x_2,y_2}$.
    * If $\tpl{x_1,y_1}=\tpl{x_2,y_2}$, then $x_1=x_2$ and $y_1=y_2$. Observe that $y_1\preceq y_2$ too and thus $\tpl{x_1,y_1}\sqsubseteq\tpl{x_2,y_2}$.<span style="float:right;">$\blacksquare$</span>
