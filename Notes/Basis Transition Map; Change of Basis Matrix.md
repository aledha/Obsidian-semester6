---
mathLink: Basis Transition Map/Matrix
---

<div class="topSpace"></div>

Date Created: 01/06/2022 15:30:57
Tags: #Definition #Topics/Linear_Algebra

Types: _Not Applicable_
Examples: _Not Applicable_
Constructions: [[Change of basis for linear maps]]
Generalizations: _Not Applicable_

Properties: _Not Applicable_
Sufficiencies: [[Basis transition map acts as left-multiplication by change of basis matrix]]
Equivalences: _Not Applicable_
Justifications: [[Linear isomorphism between finite-dim vector spaces and tuple spaces]], [[Isomorphism of objects is an equivalence relation]]

``` ad-Definition
title: Definition.

_Let $V$ be a finite dimensional vector space over some field $K$, say with $n\coloneqq\dim V$, and let $\mc{B}$ and $\mc{B}'$ be bases thereof. The **basis transition map from $\mc{B}$ to $\mc{B}'$** is the unique linear isomorphism_ $\psi:K^n\to K^n$ _such that the diagram_

<center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-06-01_153315/image.svg", width=145></center>

_commutes; that is,_ $\psi\coloneqq\phi_{\mc{B}'}\circ\phi_\mc{B}^{-1}$_._

```

**Remark.** The transition map can also be written as $\psi_{\mc{B}\to\mc{B}'}$ to emphasize the fact that $\psi\l(\l[v\r]_\mc{B}\r)=\l[v\r]_{\mc{B}'}$ for all $v\in V$; that is, it takes the coordinate representations of vectors in $\mc{B}$ and maps them to its corresponding representation in $\mc{B}'$.

Let $\mc{B}\coloneqq\l\{e_1,\dots,e_n\r\}$ and let $\mc{S}$ be the standard basis on $K^n$. Since $\l[\psi\r]_\mc{S}=\l[\id_V\r]_\mc{B}^{\mc{B}'}$, we can compute
$$\begin{equation}
    \begin{aligned}
        \l[v\r]_{\mc{B}'}=\psi\l(\l[v\r]_\mc{B}\r)&=\l[\psi\l(\l[v\r]_\mc{B}\r)\r]_\mc{S} && \psi\l(\l[v\r]_\mc{B}\r)\in K^n\textrm{; $\mc{S}$ standard} \\
        &=\l[\psi\r]_\mc{S}\l[\l[v\r]_\mc{B}\r]_\mc{S} && \textrm{Action of linear map} \\
        &=\l[\id_V\r]_\mc{B}^{\mc{B}'}\l[v\r]_\mc{B} && \textrm{Substitution; $\l[v\r]_\mc{B}\in K^n$; $\mc{S}$ standard} \\
    \end{aligned}
\end{equation}$$
by left-multiplying $\l[v\r]_\mc{B}$ by the **change of basis matrix**
$$\begin{equation}
    Q_{\mc{B}\to\mc{B}'}\!\coloneqq\l[\id_V\r]_\mc{B}^{\mc{B}'}=\l[\l[e_1\r]_{\mc{B}'}\ \ \cdots\ \ \l[e_n\r]_{\mc{B}'}\r].\exqedin
\end{equation}$$
