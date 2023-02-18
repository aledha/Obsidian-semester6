---
mathLink: auto
---

<div class="topSpace"></div>

Date Created: 27/01/2022 12:42:19
Tags: #Proposition #Later/Set_Theory/Choice

Proved by: [[Exists function in relation iff Choice]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $f:X\to Y$ with $X\neq\em$. Then $f$ is right-invertible iff $f$ is surjective._

```

_Proof_. ($\Rightarrow$): Let $h:Y\to X$ be a right-inverse of $f$. Then, for any $y\in Y$, we have
$$\begin{equation}
    \begin{alignedat}{2}
        y&=\id_Y\l(y\r)&&\textrm{Definition of the identity function}\\
        &=\l(f\circ h\r)\l(y\r)\ \ \ \ \ \ \ \ &&h\textrm{ is a right-inverse of }f\\
        &=f\l(h\l(y\r)\r).&&\textrm{Definition of composition of functions}
    \end{alignedat}
\end{equation}$$
Since $h\l(y\r)\in X$, we see that $f$ is a surjection.

($\Leftarrow$): Assume that $f$ is a surjection, so for all $y\in Y$, there exists $x\in X$ such that $y=f\l(x\r)$; such an $x$ is generically not unique since $f$ need not be an injection. Using Choice, let $h\subseteq f^{-1}$ be a function with $\dom h=\dom f^{-1}=Y$; here, $f^{-1}$ is the inverse of the relation $f$. Since $h$ is function, we see that for all $y\in Y$, there exists a unique $x$ such that $\tpl{y,x}\in h$. This implies that $\tpl{y,x}\in f^{-1}$ and thus $\tpl{x,y}\in f$. Since $x=h\l(y\r)$, we see that $f\l(h\l(y\r)\r)=y$; this holds for all $y\in Y$, so $h$ is a right-inverse of $f$.<span style="float:right;">$\blacksquare$</span>

---

**Remark.** The backwards direction, $f\textrm{ is surjective }\Rightarrow f\textrm{ has a left-inverse}$, implies the Axiom of Choice. To see this, 
