<div class="topSpace"></div>

Date Created: 30/01/2022 19:17:19
Tags: #Proposition #Later/Set_Theory

Proved by: [[Transitive set iff every element is a subset]], [[Well-ordering well-orders subsets]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_The class of ordinal numbers $\ordinal$ is a transitive class. That is,_
$$\begin{equation}
    \fa z,\alpha:\l(z\in\alpha\land\alpha\in\ordinal\Rightarrow z\in\ordinal\r).
\end{equation}$$

```

_Proof_. Since $\alpha\in\ordinal$, it is a transitive set and thus $z\subseteq\alpha$. Also, since $\in$ well-orders $\alpha$, we see that $\in$ well-orders $z$ too. Hence it suffices to show that $z$ is a transitive set, so take sets $x$ and $y$ such that $x\in y$ and $y\in z$. Since $z\subseteq\alpha$, we see that $y\in\alpha$ and thus $y\subseteq\alpha$. It follows that $x\in\alpha$, so all $x,y,z\in\alpha$. Recall that $\in$ is a well-order on $\alpha$, so, in particular, it is a strict total order on $\alpha$ and hence it is transitive on $\alpha$; since $x\in y$ and $y\in z$ and all three are elements of $\alpha$, we see that $x\in z$ too.<span style="float:right;">$\blacksquare$</span>
