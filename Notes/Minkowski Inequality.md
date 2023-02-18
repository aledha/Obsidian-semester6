<div class="topSpace"></div>

Date Created: 16/02/2023 10:42:25
Tags: #Theorem #Courses/MATH255

Proved by: [[Holder's Inequality]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Theorem
title: Theorem (Minkowski Inequality).

_Fix $n\in\N^+$ and take $\v{x}\coloneqq\tpl{x_1,\dots,x_n}$ and $\v{y}\coloneqq\tpl{y_1,\dots,y_n}$ in $\R^n$. For all $p\geq1$, we have_
$$\begin{equation}
    \l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1/p}\leq\l(\sum_{i=1}^{n}\l|x_n\r|^p\r)^{1/p}\!+\l(\sum_{i=1}^{n}\l|y_n\r|^p\r)^{1/p}=\|\v{x}\|_p+\|\v{y}\|_p.
\end{equation}$$

```

_Proof_. First, observe that the case for $p=1$ is trivial. For $p>1$, let $1<q<+\infty$ be its conjugate exponent. Observe that
$$\begin{equation}
    \sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p=\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l(\l|x_n\r|+\l|y_n\r|\r)=\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l|x_n\r|+\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l|y_n\r|.
\end{equation}$$
Applying Hölder$\textrm{'}$s Inequality, we see that
$$\begin{equation}
    \sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l|x_n\r|\leq\l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{\l(p-1\r)q}\r)^{1/q}\l(\sum_{i=1}^{n}\l|x_n\r|^p\r)^{1/p}.
\end{equation}$$
But $p$ and $q$ being conjugate exponents imply that $p=q\l(p-1\r)$, so we have
$$\begin{equation}
    \sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l|x_n\r|\leq\l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1/q}\l(\sum_{i=1}^{n}\l|x_n\r|^p\r)^{1/p}.
\end{equation}$$
Similarly, Hölder$\textrm{'}$s Inequality on the second factor gives
$$\begin{equation}
    \sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^{p-1}\l|y_n\r|\leq\l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1/q}\l(\sum_{i=1}^{n}\l|y_n\r|^p\r)^{1/p},
\end{equation}$$
so we have
$$\begin{equation}
    \sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\leq\l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1/q}\l[\l(\sum_{i=1}^{n}\l|x_n\r|^p\r)^{1/p}+\l(\sum_{i=1}^{n}\l|y_n\r|^p\r)^{1/p}\r].
\end{equation}$$
Diving, we obtain
$$\begin{equation}
    \l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1/p}=\l(\sum_{i=1}^{n}\l(\l|x_n\r|+\l|y_n\r|\r)^p\r)^{1-\frac{1}{q}}\leq\l(\sum_{i=1}^{n}\l|x_n\r|^p\r)^{1/p}+\l(\sum_{i=1}^{n}\l|y_n\r|^p\r)^{1/p}.\qedin
\end{equation}$$
