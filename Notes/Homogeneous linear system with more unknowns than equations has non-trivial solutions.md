---
mathLink: Homogeneous $m\times n$ linear system with $n>m$ has non-trivial solutions
---

<div class="topSpace"></div>

Date Created: 28/03/2022 15:32:39
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Linear map to a lower dimensional space is not injective]], [[Linear map is injective iff kernel vanishes]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ be an field and take $A\in\mat{m\times n}{K}$ with $n>m$. Then the homogeneous linear system $A\v{x}=\v{0}$ has a non-trivial solution._

```

**Remark.** That is, a homogeneous linear system with more unknowns than equations are underdetermined, so it has non-zero solutions.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_. Since $n>m$, the linear map $L_A:K^n\to K^m$ is not injective, and hence $\nullsp A=\ker L_A\neq\l\{\v{0}\r\}$. Thus there exists some $\v{s}\neq\v{0}$ in $K^n$ such that $A\v{s}=\v{0}$; that is, the system has a non-trivial solution.<span style="float:right;">$\blacksquare$</span>
