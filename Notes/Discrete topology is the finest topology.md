<div class="topSpace"></div>

Date Created: 25/01/2022 11:58:09
Tags: #Proposition #Later/Topology

Proved by: [[Discrete topology (basis)]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $X$ be a set. The discrete topology is the finest topology on $X$._

```

_Proof_. Let $\mc{T}$ be any topology on $X$ and take $U\in\mc{T}$. Recall that we have
$$\begin{equation}
    U=\bigcup\limits_{x\in U}\l\{x\r\}=\bigcup\underbrace{\l\{\l\{x\r\}\in\pow\l(x\r)\mid x\in U\r\}}_{\mathclap{\subseteq\mc{B}_\textrm{discrete}}}\in\mc{T}_\textrm{discrete}
\end{equation}$$
where the last inclusion follows from $\axitop[2]$ of $\mc{T}_\textrm{discrete}$. It follows that $\mc{T}\subseteq\mc{T}_\textrm{discrete}$.<span style="float:right;">$\blacksquare$</span>
