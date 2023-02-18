---
mathLink: Hölder$\textrm{'}$s Inequality
---

<div class="topSpace"></div>

Date Created: 14/02/2023 11:03:20
Tags: #Theorem #Courses/MATH255

Proved by: [[Young's Inequality for Products]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Theorem
title: Theorem (Hölder$\textrm{'}$s Inequality).

_Fix $n\in\N^+$ and take $\v{x}\coloneqq\tpl{x_1,\dots,x_n}$ and $\v{y}\coloneqq\tpl{y_1,\dots,y_n}$ in $\R^n$. Letting $1<p,q<+\infty$ be conjugate exponents, then_
$$\begin{equation}
    \sum_{i=1}^{n}\l|x_i\r|\l|y_i\r|\leq\l(\sum_{i=1}^{n}\l|x_i\r|^p\r)^{1/p}\l(\sum_{i=1}^{n}\l|y_n\r|^q\r)^{1/q}=\|\v{x}\|_p\|\v{y}\|_q.
\end{equation}$$

```

_Proof_. Let $A\coloneqq\l(\sum_{i=1}^{n}\l|x_i\r|^p\r)^{1/p}$ and $B\coloneqq\l(\sum_{i=1}^{n}\l|y_n\r|^q\r)^{1/q}$, and assume, w.l.o.g., that $A,B>0$. For each $i\in\N^+$, let $a_i\coloneqq\l|x_i\r|/A$ and $b_i\coloneqq\l|y_i\r|/B$. Applying Young$\textrm{'}$s Inequality for Products, we obtain
$$\begin{equation}
    \frac{\l|x_i\r|}{A}\frac{\l|y_i\r|}{B}\leq\frac{1}{p}\frac{\l|x_i\r|^p}{A^p}+\frac{1}{q}\frac{\l|y_i\r|^q}{B^q}.
\end{equation}$$
Summing $i$ from $1$ to $n$, we obtain
$$\begin{equation}
    \sum_{i=1}^{n}\frac{\l|x_n\r|}{A}\frac{\l|y_n\r|}{B}\leq\frac{1}{pA^p}\sum_{i=1}^{n}\l|x_n\r|^p+\frac{1}{qB^q}\sum_{i=1}^{n}\l|y_n\r|^q=\frac{1}{p}+\frac{1}{q}=1.
\end{equation}$$
Multiplying by $AB$ gives the desired result.<span style="float:right;">$\blacksquare$</span>
