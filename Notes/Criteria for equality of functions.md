<div class="topSpace"></div>

Date Created: 27/01/2022 10:54:11
Tags: #Proposition #Topics/Set_Theory

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $f$ and $g$ be functions. If $\dom f=\dom g$ and $f\l(x\r)=g\l(x\r)$ for all $x$ in their common domain, then $f=g$._

```

_Proof_. Take $\tpl{x,y}\in f$, so $x\in\dom f$ and thus $x\in\dom g$. Hence there exists a unique $y'$ such that $\tpl{x,y'}\in f$. Since $y=f\l(x\r)=g\l(x\r)=y'$, we see that $\tpl{x,y}\in g$ too and thus $f\subseteq g$. Similarly, we have $g\subseteq f$ and thus $f=g$.<span style="float:right;">$\blacksquare$</span>
