<div class="topSpace"></div>

Date Created: 03/01/2023 22:52:08
Tags: #Theorem #Topics/Group_Theory

Proved by: [[Universal Property of Quotient Groups]], [[Basic properties of cosets]], [[Canonical Decomposition of Functions]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Theorem
title: Theorem (Canonical Decomposition of Group Homomorphisms).

_Let $G$ and $H$ be groups and consider a group homomorphism $\phi:G\to H$. Then the following diagram commutes:_
<center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2023-01-03_225322/image.svg", width=280></center>

```

**Remark.** In other words, every homomorphism $\phi:G\to H$ can be decomposed into $\phi=\iota\circ\tilde{\phi}\circ\pi$ for $\pi$ a surjective homomorphism, $\tilde{\phi}$ a (unique) isomorphism, and $\iota$ an injective homomorphism.<span style="float:right;">$\blacklozenge$</span>

---

_Proof_. Let $\phi':G\to\im\phi:g\mapsto\phi\l(g\r)$. By universality of $\pi:G\to G/\ker\phi$, there exists a unique homomorphism $\tilde{\phi}:G/\ker\phi\to\im\phi$ such that $\phi'=\tilde{\phi}\circ\pi$. But $\phi=\iota\circ\phi'$, so it suffices to show that $\tilde{\phi}$ is an isomorphism. Indeed, observe that $G/\ker\phi=G/\!\sim$ where $\sim$ is the equivalence relation on $G$ defined by
$$\begin{equation}
    g_1\sim g_2\ \ \ \ \ \ \ \ \,\colon\!\Leftrightarrow\ \ \ \ \ \ \ \ g_1\ker\phi=g_2\ker\phi\ \ \ \ \ \ \ \ \Leftrightarrow\ \ \ \ \ \ \ \ g_1^{-1}g_2\in\ker\phi\ \ \ \ \ \ \ \ \Leftrightarrow\ \ \ \ \ \ \ \ \phi\l(g_1^{-1}g_2\r)=e\ \ \ \ \ \ \ \ \Leftrightarrow\ \ \ \ \ \ \ \ \phi\l(g_1\r)=\phi\l(g_2\r),
\end{equation}$$
so, by the Canonical Decomposition of Functions, $\tilde{\phi}$ is a bijection.<span style="float:right;">$\blacksquare$</span>
