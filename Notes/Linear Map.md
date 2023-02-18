<div class="topSpace"></div>

Date Created: 01/04/2022 18:16:33
Tags: #Definition #Topics/Linear_Algebra

Types: [[Linear Isomorphism]], [[Linear Operator]]
Examples: [[Left-multiplication of Matrices]], [[Transposition (Matrix)]], [[Differentiable Function slash Derivative in Rn]]
Constructions: [[Matrix Representation of a Linear Map]], [[Kernel; Null Space]], [[Image; Column Space]], [[Dual Map]], [[Composition (Linear Map)]], [[Vector Space of Linear Maps]]
Generalizations: [[Multilinear Map]], [[Module Homomorphism]]

Properties: [[Linear map between vector spaces of same dimension is injective iff surjective]], [[Linear map is injective iff kernel vanishes]], [[Restriction on complement of kernel is injective]], [[Basic properties of linear maps]]
Sufficiencies: [[Existence of unique linear map via action on basis vectors]], [[Criteria for equality of linear maps via spanning set]]
Equivalences: [[Action of linear map repr under basis left-multiplication of matrix representation]]
Justifications: _Not Applicable_

``` ad-Definition
title: Definition.

_Let $V$ and $W$ be $K$-vector spaces. A **linear map from $V$ to $W$** is an additive group homomorphism $T:V\to W$ such that:_
$$\begin{equation}
    \fa\alpha\in K,\fa v\in V:T\l(\alpha v\r)=\alpha T\l(v\r).
\end{equation}$$

```

**Remark.** Equivalently, a function $T:V\to W$ is a linear map if
$$\begin{equation}
    \fa\alpha\in K,\fa v_1,v_2\in V:T\l(\alpha v_1+v_2\r)=\alpha T\l(v_1\r)+T\l(v_2\r).\exqedin
\end{equation}$$
