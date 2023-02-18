<div class="topSpace"></div>

Date Created: 11/02/2022 11:45:28
Tags: #Definition #Later/Topology

Types: _Not Applicable_
Examples: _Not Applicable_
Constructions: [[Topological Subspace]]
Generalizations: _Not Applicable_

Properties: [[Open set in open subspace is open]], [[Subspace topology of subspace topology is subspace topology]], [[Product and subspace topologies on subsets coincide]], [[Restricted order topology subset of subspace topology]], [[Restricted order and subspace topologies coincide for convex sets]]
Sufficiencies: _Not Applicable_
Equivalences: [[Subspace topology (basis)]], [[Subspace topology (subbasis)]]
Justifications: [[Subspace topology is a topology]]

``` ad-Definition
title: Definition.

_Let $\tpl{X,\mc{T}}$ be a topological space and fix a subset $Y\subseteq X$. Then the **subspace topology on $Y$ inherited from $X$ w.r.t. $\mc{T}$** is the topology_
$$\begin{equation}
    \l.\mc{T}\r|_Y\coloneqq\l\{V\in\pow\l(Y\r)\mid\ex U\in\mc{T}:V=U\cap Y\r\}.
\end{equation}$$

```

**Remark.** The subspace topology on $Y$ can be visualized by the following diagram:

<center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-02-11_115828/image.svg", width=260></center>

The thick intervals $V_1$ and $V_2$ are open in $\l.\mc{T}\r|_Y$ since $V_1=U_1\cap Y$ and $V_2=U_2\cap Y$.<span style="float:right;">$\blacklozenge$</span>
