<div class="topSpace"></div>

Date Created: 14/09/2022 19:47:03
Tags: #Definition #Topics/Ring_Theory

Types: _Not Applicable_
Examples: _Not Applicable_
Constructions: [[Content slash primitive polynomials]]
Generalizations: _Not Applicable_

Properties: _Not Applicable_
Sufficiencies: [[GCDs exist in UFDs]], [[Bezout's Identity]], [[Euclidean Algorithm]]
Equivalences: _Not Applicable_
Justifications: [[GCD exists implies unique up to a unit]], [[Basic properties of divisibility and associates]]

``` ad-Definition
title: Definition.

_Let $R$ be a integral domain and fix $a,b\in R\comp\l\{0\r\}$. An element $d\in R\comp\l\{0\r\}$ is said to be a **greatest common divisor (GCD) of $a$ and $b$** if_
* _$d$ is a common divisor of $a$ and $b$; that is, if $d\divides a$ and $d\divides b$, and_
* _for all common divisors $d'$ of $a$ and $b$, $d'\divides d$._

_The greatest common divisor of $a$ and $b$ is, up to a unit, unique; write $\gcd\l(a,b\r)\coloneqq d$ and let the **GCD ideal of $a$ and $b$** be $\ideal{d}$._

```

**Remark.** Rephrasing in terms of ideals, $d$ is a greatest common divisor of $a$ and $b$ iff $\ideal{a,b}\subseteq\ideal{d}$ and $\ideal{d}\subseteq\ideal{d'}$ for any ideal $\ideal{d'}$ containing $\ideal{a,b}$.<span style="float:right;">$\blacklozenge$</span>
