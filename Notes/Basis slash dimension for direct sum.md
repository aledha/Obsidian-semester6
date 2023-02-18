---
mathLink: auto
---

<div class="topSpace"></div>

Date Created: 16/01/2023 11:50:16
Tags: #Proposition #Topics/Linear_Algebra

Proved by: [[Unique Representation Theorem (Direct Sum)]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let_ $\l\{U_i\r\}_{i\in I}$ _be an indexed family of distinct linear subspaces of a vector space $V$ over some field $K$, and, for all $i\in I$, let $\mc{B}_i$ be a basis for $U_i$. Then_ $\mc{B}\coloneqq\coprod_{i\in I}\mc{B}_i$ _is a basis for_ $U\coloneqq\bigoplus_{i\in I} U_i$_. In particular, if $I=\l\{1,\dots,n\r\}$ for some $n\in\N^+$, we have_
$$\begin{equation}
    \dim\bigoplus_{i=1}^nU_i=\sum_{i=1}^{n}\dim U_i.
\end{equation}$$

```

**Remark.** We thus obtain a basis $\mc{B}$ of $U$ by $\textrm{`}$glueing$\textrm{'}$ together bases for each $U_i$.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_. Clearly $\span\mc{B}=U$, so it suffices to show that $\mc{B}$ is linearly independent. Indeed, suppose that $\sum_{b\in\mc{B}}\alpha_b b=0$ where $\alpha_b\in K$ is such that $\alpha_b=0$ for all but finitely-many $b\in\mc{B}$. Note that $\mc{B}=\coprod_{i\in I}\mc{B}_i$, so we may write this as
$$\begin{equation}
    \sum_{i\in I}\l(\sum_{b\in\mc{B}_i}\alpha_bb\r)=0.
\end{equation}$$
But $\sum_{b\in\mc{B}_i}\alpha_bb\in\span\mc{B}_i=U_i$, and since $0$ admits only the trivial representation of a sum of vectors in $\l\{U_i\r\}$, we see that
$$\begin{equation}
    \sum_{b\in\mc{B}_i}\alpha_bb=0
\end{equation}$$
for all $i\in I$. The result follows since each $\mc{B}_i$ is linearly independent, so $\alpha_b=0$ for all $b\in\mc{B}$.<span style="float:right;">$\blacksquare$</span>
