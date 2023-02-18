<div class="topSpace"></div>

Date Created: 16/09/2022 12:00:27
Tags: #Theorem #Later/Ring_Theory

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: [[Ring of integers is a EUD]]

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Theorem
title: Theorem (Euclidean Algorithm).

_Let $a,b\in\Z\comp\l\{0\r\}$ and consider the sequence of divisions as shown below:_
$$\begin{equation}
    \begin{aligned}
              a&=q_0b+r_0 \\
              b&=q_1r_0+r_1 \\
            r_0&=q_2r_1+r_2 \\
               &\vdotswithin{=} \\
        r_{i-2}&=q_ir_{i-1}+r_i \\
               &\vdotswithin{=}
    \end{aligned}
\end{equation}$$
_Then there exists some $n\in\N$ such that_ $r_{n-1}\neq0$ _and $r_n=0$, which which case_ $\gcd\l(a,b\r)=r_{n-1}$_._

```

**Remark.** This shows that $\gcd\l(a,b\r)$ exists and provides an algorithm to compute it.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_. The existence and uniqueness of the integers $q_0,q_1,\dots$ and $r_0,r_1,\dots$ are guaranteed by the Division Algorithm. Note that
$$\begin{equation}
    b>r_0>r_1>\cdots\geq0,
\end{equation}$$
and since all remainders are integers, there must exist some $n\in\N$ such that $r_n=0$. Thus the process ends with the last two divisions being
$$\begin{equation}
    \begin{aligned}
        r_{n-3}&=q_{n-1}r_{n-2}+r_{n-1} \\
        r_{n-2}&=q_nr_{n-1}.
    \end{aligned}
\end{equation}$$
We first prove the fact that for all $a,b\in\Z$ whose division yields $q,r\in\Z$ such that $a=qb+r$, we have $\gcd\l(a,b\r)=\gcd\l(b,r\r)$. It suffices to show that $g\coloneqq\gcd\l(a,b\r)$ is the greatest common divisor of $\gcd\l(b,r\r)$.
* (proof that $g\divides b$ and $g\divides r$): Since $g=\gcd\l(a,b\r)$, there exist $k,l\in\mb{Z}$ such that $a=kg$ and $b=lg$. Together with $r=a-qb$, we obtain $r=kg-q\l(lg\r)=\l(k-ql\r)g$, so $g\divides r$.

* (proof that $g$ is the greatest such common divisor): Let $d\in\mb{Z}\setminus\l\{0\r\}$ be a common divisor of $b$ and $r$, so there exist $k,l\in\mb{Z}$ such that $b=kd$ and $r=ld$. Since $a=qb+r$, we have $a=q\l(kd\r)+ld=\l(qk+l\r)d$, so $d\divides a$. Together with $d\divides b$ and the fact that $\gcd\l(a,b\r)$ is the greatest common divisor of $a$ and $b$, we see that $d\divides\!\gcd\l(a,b\r)$.

We can then apply this fact to the entire sequence to obtain
$$\begin{equation}
    \gcd\l(a,b\r)=\gcd\l(b,r_0\r)=\gcd\l(r_0,r_1\r)=\cdots=\gcd\l(r_k,r_{k+1}\r)=\cdots=\gcd\l(r_{n-2},r_{n-1}\r).
\end{equation}$$
But $r_{n-2}=q_nr_{n-1}$, so $r_{n-1}\divides r_{n-2}$. It follows then that $\gcd\l(r_{n-2},r_{n-1}\r)=r_{n-1}$, so we are done.<span style="float:right;">$\blacksquare$</span>
