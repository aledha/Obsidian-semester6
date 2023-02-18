<div class="topSpace"></div>

Date Created: 11/01/2023 15:53:00
Tags: #Proposition #Topics/Ring_Theory

Proved by: [[Basic properties of divisibility and associates]], [[Integral domain iff cancellable]]
References: [[Maximal implies prime]]
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $R$ be an integral domain and let $a\in R\comp\l\{0\r\}$. Then the following properties hold._
* _$a$ is prime iff $\ideal{a}$ is a prime ideal._
* _$a$ is irreducible iff $\ideal{a}$ is maximal in the set of all proper principal ideals of $R$._
* _$a$ is prime implies $a$ is irreducible._

```

**Remark.** In particular, this proves that $a$ is prime iff $a$ is irreducible in a PID. The forwards direction always holds, so let $a$ be irreducible. Then $\ideal{a}$ is maximal (since $R$ is a PID), so $\ideal{a}$ is a prime ideal. Hence $a$ is prime.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_.
* Observe that
$$\begin{equation}
    \begin{aligned}
        a\textrm{ is prime}&\Leftrightarrow a\not\in R^\times\land\fa b,c\in R:a\divides\!\l(bc\r)\Rightarrow\l(a\divides b\lor a\divides c\r) \\
        &\Leftrightarrow\ideal{a}\neq R\land\fa b,c\in R:bc\in\ideal{a}\Rightarrow\l(b\in\ideal{a}\lor c\in\ideal{a}\r) \\
        &\Leftrightarrow\ideal{a}\textrm{ is a prime ideal}.
    \end{aligned}
\end{equation}$$

* For the forwards direction, say $b\in R$ is such that $\ideal{a}\subseteq\ideal{b}\subset R$. Since $\ideal{a}\subseteq\ideal{b}$, we see that $b\divides a$ and hence $a=bc$ for some $c\in R$. But $a$ is irreducible, so either $b\in R^\times$ or $c\in R^\times$. Note that $\ideal{b}\neq R$, so $c\in R^\times$. Thus $a\sim b$, so $\ideal{a}=\ideal{b}$. Conversely, Take $b,c\in R$ such that $a=bc$. Then $b\divides a$, so $\ideal{a}\subseteq\ideal{b}$ and thus either $\ideal{a}=\ideal{b}$ or $\ideal{b}=R$. In the latter case, $b\in R^\times$. In the former, we see that $a\sim b$ and hence $a=bu$ for some $u\in R^\times$. Then $bc=bu$, so $c=u\in R^\times$.
* Write $a=bc$ for some $b,c\in R$, so, since $a$ is prime, either $a\divides b$ or $a\divides c$. W.l.o.g., assume $a\divides b$, so $b=ad$ for some $d\in R$. Then $a=bc=acd$, so $cd=1$ and hence $c\in R^\times$.<span style="float:right;">$\blacksquare$</span>
