<div class="topSpace"></div>

Date Created: 22/01/2022 09:39:56
Tags: #Proposition #Later/Set_Theory

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $R$ be a binary relation. Then_
$$\begin{equation}
    \dom R^{-1}=\ran R\ \ \ \ \textrm{\it{and}}\ \ \ \ \ran R^{-1}=\dom R.
\end{equation}$$

```

_Proof_. Simply compute:
$$\begin{gather}
    \dom R^{-1}=\l\{y\mid\ex x:yR^{-1}x\r\}=\l\{y\mid\ex x:xRy\r\}=\dom R\\
    \ran R^{-1}=\l\{x\mid\ex y:yR^{-1}x\r\}=\l\{x\mid\ex y:xRy\r\}=\dom R.\qedin
\end{gather}$$
