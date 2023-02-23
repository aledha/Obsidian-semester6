---
mathLink: auto
---

<div class="topSpace"></div>

Date Created: 19/09/2022 23:07:24
Tags: #Theorem #Topics/Number_Theory

Proved by: [[Bezout's Identity]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: [[Prime Element]]

``` ad-Theorem
title: Theorem (Euclid$\textrm{'}$s Lemma).

_Let $a,b\in\Z$ and let $p$ be a prime number. If $p\divides\!\l(ab\r)$, then either $p\divides a$ or $p\divides b$._

```

_Proof_. Since $p\divides\!\l(ab\r)$, there exist $k\in\Z$ such that $kp=ab$. If $p\divides a$, we are done. Otherwise, suppose that $p\ndivides a$. Then $\gcd\l(a,p\r)=1$, so , by B$\acute{\textrm{e}}$zout$\textrm{'}$s Identity, there exist $m_1,m_2\in\Z$ such that $am_1+pm_2=1$. Observe then that
$$\begin{equation}
    \begin{aligned}
        b&=b\l(am_1+pm_2\r) && am_1+pm_2=1 \\
        &=abm_1+bpm_2 && \textrm{Distribution} \\
        &=kpm_1+bpm_2 && ab=kp \\
        &=\l(km_1+bm_2\r)p, && \textrm{Distribution}
    \end{aligned}
\end{equation}$$
so $p\divides b$.<span style="float:right;">$\blacksquare$</span>