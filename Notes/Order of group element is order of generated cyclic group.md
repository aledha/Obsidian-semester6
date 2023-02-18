---
mathLink: $\ord{g}=\ord{\cyclic{g}}$
---

<div class="topSpace"></div>

Date Created: 26/09/2022 17:57:49
Tags: #Proposition #Topics/Group_Theory

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $G$ be a group. Then, for all $g\in G$, we have $\ord{g}=\ord{\cyclic{g}}$._

```

**Remark.** For a finite group $G$, this shows that $G$ is cyclic iff there exists some $g\in G$ such that $\ord{g}=\ord{G}$.

* If $G$ is cyclic, then there exists some $g\in G$ such that $\cyclic{g}=G$. Thus $\ord{\cyclic{g}}=\ord{G}$, but since $\ord{g}=\ord{\cyclic{g}}$, we see that $\ord{g}=\ord{G}$.
* If $\ord{g}=\ord{G}$, then, since $\ord{g}=\ord{\cyclic{g}}$, we see that $\ord{\cyclic{g}}=\ord{G}$. Since $\cyclic{g}\subseteq G$ and $G$ have the same number of elements, they must coincide.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_. Consider the function $\phi:\cyclic{g}\to\l\{0,\dots,\ord{g}-1\r\}$ mapping $g^n\mapsto r$ where $0\leq r<n$ is the unique integer furnished by the Division Algorithm applied to $n$ and $\ord{g}$ such that $n=q\ord{g}+r$ for some unique $q\in\Z$. We claim that $\phi$ is a bijection, which proves that $\ord{\cyclic{g}}=\ord{g}$.
* (Injection): Take $g^n,g^m\in\cyclic{g}$ such that $\phi\l(g^n\r)=\phi\l(g^m\r)$. Then
$$\begin{equation}
    n=q_1\ord{g}+r\ \ \ \ \ \ \ \ \textrm{and}\ \ \ \ \ \ \ \ m=q_2\ord{g}+r
\end{equation}$$
for some unique $q_1,q_2\in\Z$, which implies that $n=q_1\ord{g}+m-q_2\ord{g}=\l(q_1-q_2\r)\l|g\r|+m$. Observe then that
$$\begin{equation}
    g^n=\l(g^\ord{g}\r)^{q_1-q_2}g^m=e^{q_1-q_2}g^m=g^m.
\end{equation}$$
* (Surjection): Take $r\in\l\{0,\dots,\ord{g}-1\r\}$ and observe that $r=0\ord{g}+r$. Thus, by the Division Algorithm, we see that $\phi\l(g^r\r)=r$.<span style="float:right;">$\blacksquare$</span>
