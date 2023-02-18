---
mathLink: Linear system $A\v{x}=\v{b}$ consistent $\Leftrightarrow$ $\rank A=\rank\l[A\mid\v{b}\r]$
---

<div class="topSpace"></div>

Date Created: 06/06/2022 01:11:59
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Column space is spanned by columns of matrix]], [[Dimension of subspace]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $A\v{x}=\v{b}$ be an $m\times n$ linear system of equations over some field $K$. Then the system is consistent iff $\rank A=\rank\l[A\mid\v{b}\r]$._

```

_Proof_. Let $\v{a}_1,\dots,\v{a}_n$ be the columns of $A$ and observe that
$$\begin{equation}
    \begin{aligned}
        A\v{x}=\v{b}\textrm{ is consistent}&\Leftrightarrow\ex\v{s}\in K^n:A\v{s}=\v{b} && \textrm{Definition of consistency} \\
        &\Leftrightarrow\ex\v{s}\in K^n:L_A\l(\v{s}\r)=\v{b} && \textrm{Definition of $L_A$} \\
        &\Leftrightarrow\v{b}\in\im L_A && \textrm{Definition of image} \\
        &\Leftrightarrow\v{b}\in\span\l\{\v{a}_1,\dots,\v{a}_n\r\}, && \textrm{Column space is spanned by columns} \\
    \end{aligned}
\end{equation}$$
so it suffices to show that this is equivalent to $\rank A=\rank\l[A\mid\v{b}\r]$. Note that
$$\begin{equation}
    \span\l\{\v{a}_1,\dots,\v{a}_n\r\}\subseteq\span\l\{\v{a}_1,\dots,\v{a}_n,\v{b}\r\}\cref{\ast}
\end{equation}$$
and observe that the converse inclusion holds iff $\v{b}\in\span\l\{\v{a}_1,\dots,\v{a}_n\r\}$. But equality in $\ref{\ast}$ is equivalent to
$$\begin{equation}
    \dim\span\l\{\v{a}_1,\dots,\v{a}_n\r\}=\dim\span\l\{\v{a}_1,\dots,\v{a}_n,\v{b}\r\};\cref{\diamond}
\end{equation}$$
the forward direction is trivial, and the backwards direction follows since if the inclusion in $\ref{\ast}$ is strict, then $\ref{\diamond}$ would be an inequality. Observe that this is equivalent to
$$\begin{equation}
    \dim\im L_A=\dim\im L_{\l[A\mid\v{b}\r]}
\end{equation}$$
from which is result follows.<span style="float:right;">$\blacksquare$</span>
