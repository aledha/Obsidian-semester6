<div class="topSpace"></div>

Date Created: 09/01/2023 15:58:47
Tags: #Proposition #Topics/Ring_Theory #Courses/MATH457

Proved by: [[Integral domain iff cancellable]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $R$ be a commutative ring and take $a,a_1,a_2,b\in R$ with $b\neq0$. Then the following properties hold._
* _$b\divides a_1$ and $b\divides a_2$ implies $b\divides\!\l(a_1\pm a_2\r)$._
* _$b\divides a$ implies $b\divides\!\l(ra\r)$ for any $r\in R$._
* _$1\divides a$ and $b\divides0$._
* _$u\divides a$ for all $u\in R^\times$._
* _$b\divides a$ iff $a\in\ideal{b}$ iff $\ideal{a}\subseteq\ideal{b}$._
* _$a\sim b$ iff $\ideal{a}=\ideal{b}$._
* _If $a=bu$ for some $u\in R^\times$, then $a\sim b$. The converse holds if $R$ is an integral domain._

```

_Proof_. The first four are easy: write $a_1=bk_1$ and $a_2=bk_2$ for some $k_1,k_2\in R$ and observe that $a_1\pm a_2=bk_1\pm bk_2=b\l(k_1\pm k_2\r)$; write $a=bk$ for some $k\in R$ and observe that $ar=\l(bk\r)r=b\l(kr\r)$; observe that $a=1a$ and $0=0b$; observe that $a=u\l(u^{-1}a\r)$.
* Observe that $b\divides a$ iff $a=kb$ for some $k\in R$ iff $a\in\ideal{b}$. Now, for all $x\in\ideal{a}$, $x=ar$ for some $r\in R$ and hence $b\divides a$ implies $b\divides x$. Thus $x=bk$ for some $k\in R$ and hence $x\in\ideal{b}$. The converse is easy.
* This follows directly from the above.
* If $a=bu$, then $b\divides a$. But since $u\in R^\times$, we have that $b=au^{-1}$, so $a\divides b$ and hence $a\sim b$. Conversely, write $a=bk$ and $b=al$ for some $k,l\in R$. Then $a=\l(al\r)k=a\l(lk\r)$, so, since $R$ is an integral domain, we see that $lk=1$. In particular, $u\coloneqq k\in R^\times$.<span style="float:right;">$\blacksquare$</span>
