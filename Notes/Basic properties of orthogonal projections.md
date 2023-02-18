<div class="topSpace"></div>

Date Created: 29/06/2022 10:06:15
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Basic properties of orthogonal complements]], [[Equivalences for projections]], [[Pythagorean Theorem]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ denote either $\R$ or $\C$ and let $V$ be an inner product space over $K$. If $U$ is a finite-dimensional linear subspace of $V$, then the following algebraic identities hold:_
* _$\proj_U\!:V\to V$ is a linear operator._
* _$\proj_U^2=\proj_U$._
* _$\im\proj_U=U$ with $\proj_U\!\l(u\r)=u$ for all $u\in U$._
* _$\ker\proj_U=U^\perp$._
* _$\l\|\proj_U\l(v\r)\r\|\leq\|v\|$ for all $v\in V$._

```

_Proof_. 
* Take $v_1,v_2\in V$ and $\alpha\in K$, so there exist unique vectors $u_1,u_2\in U$ and $w_1,w_2\in U^\perp$ such that $v_1=u_1+w_1$ and $v_2=u_2+w_2$. Observe then that
$$\begin{equation}
    \alpha v_1+v_2=\l(\alpha u_1+u_2\r)+\l(\alpha w_1+w_2\r),
\end{equation}$$
and since both $U$ and $U^\perp$ are linear subspaces of $V$, we have
$$\begin{equation}
    \begin{aligned}
        \proj_U\!\l(\alpha v_1+v_2\r)&=\alpha u_1+u_2 && \textrm{Definition of $\proj_U$} \\
        &=\alpha\proj_U\!\l(v_1\r)+\proj_U\!\l(v_2\r). && v_i=u_i+w_i\textrm{ uniquely}
    \end{aligned}
\end{equation}$$

* The next three properties holds since $V=U\oplus U^\perp$, so, by definition of $\proj_U$, it is a projection on $V$ (in the sense that $\proj_U^2=\proj_U$).
* Take $v\in V$, so $v=u+w$ with $u\in U$ and $w\in U^\perp$. Observe then that
$$\begin{align}
    \l\|\proj_U\!\l(v\r)\r\|&=\|u\| && \textrm{Definition of $\proj_U$} \\
    &\leq\|u\|+\|w\| && \|w\|\geq0 \\
    &=\|u+w\| && u\perp w\textrm{; Pythagoras} \\
    &=\|v\|. && \textrm{Substitution}\qedin
\end{align}$$
