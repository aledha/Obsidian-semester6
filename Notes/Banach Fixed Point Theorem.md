<div class="topSpace"></div>

Date Created: 09/02/2023 10:46:58
Tags: #Theorem #Topics/Analysis

Proved by: [[Contractive implies Cauchy]], [[Sequential slash functional limit characterizations of continuity]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Theorem
title: Theorem (Banach Fixed Point Theorem).

_Let $\tpl{X,d}$ be a (non-empty) complete metric space and consider a contractive map $f:X\to X$. Then there exists a unique fixed point $x\in X$; that is, there exists a unique $x\in X$ such that $f\l(x\r)=x$._

_Furthermore, $x$ can be found as the limit of any sequence $\tpl{x_n}$ defined by_ $x_n\coloneqq f\l(x_{n-1}\r)$ _for all $n\geq1$._

```

_Proof_. Since $f$ is contractive, there exists some $\alpha\in\l(0,1\r)$ such that $d\l(f\l(x\r),f\l(y\r)\r)\leq\alpha d\l(x,y\r)$ for all $x,y\in X$. Thus $f$ is $\alpha$-Lipschitz, so it is uniformly continuous and hence continuous on $X$. Consider any sequence $\tpl{x_n}$ defined by $x_n\coloneqq f\l(x_{n-1}\r)$ for all $n\geq1$. Then $\tpl{x_n}$ a contractive sequence, so it is Cauchy and hence converges to some $x\in X$ since $X$ is complete. Indeed, $x$ is a fixed point of $f$ since
$$\begin{equation}
    x=\lim\limits_{n\to\infty}x_n=\lim\limits_{n\to\infty}f\l(x_{n-1}\r)=f\l(\lim\limits_{n\to\infty}x_{n-1}\r)=f\l(x\r).
\end{equation}$$
Lastly, such a fixed point is unique, for suppose that $f\l(y\r)=y$ for some $y\in X$. Then
$$\begin{equation}
    d\l(x,y\r)=d\l(f\l(x\r),f\l(y\r)\r)\leq\alpha d\l(x,y\r),
\end{equation}$$
so, if $x\neq y$, then $\alpha\geq1$. This contradicts the assumption that $f$ is a contraction.<span style="float:right;">$\blacksquare$</span>
