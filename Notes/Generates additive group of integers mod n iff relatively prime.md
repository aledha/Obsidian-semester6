---
mathLink: $\Z_n=\cyclic{m}$ $\Leftrightarrow$ $m\perp n$
---

<div class="topSpace"></div>

Date Created: 27/09/2022 18:26:12
Tags: #Proposition #Topics/Group_Theory

Proved by: [[Order of power of element]], [[Order of additive group of integers mod n is n]], [[Order of group element is order of generated cyclic group]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Fix $n\in\N^+$ and some $m\in\Z$. Then $\l[m\r]$ generates $\Z_n$ iff $\gcd\l(m,n\r)=1$._

```

_Proof_. Note that
$$\begin{equation}
    \ord{\l[m\r]}=\ord{\l[m\cdot1\r]}=\ord{m\l[1\r]}=\frac{\ord{\l[1\r]}}{\gcd\l(\ord{\l[1\r]},m\r)}=\frac{n}{\gcd\l(n,m\r)},
\end{equation}$$
so $\gcd\l(m,n\r)=1$ iff $\ord{\l[m\r]}=n=\ord{\Z_n}$. But since $\Z_n$ is finite, this is equivalent to $\Z_n=\cyclic{\l[m\r]}$.<span style="float:right;">$\blacksquare$</span>
