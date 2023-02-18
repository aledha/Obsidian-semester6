<div class="topSpace"></div>

Date Created: 26/03/2022 14:26:12
Tags: #Proposition #Later/Linear_Algebra

Proved by: [[Matrix in RREF if augmented with tuple is in RREF]], [[Basis for column space]], [[Elementary matrices slash operations are rank-preserving]], [[Rank of matrix in RREF is number of pivot columns of non-zero rows]], [[Linearly dependent iff exists span redundant element]], [[Unique Representation Theorem (Basis)]]
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition.

_Let $K$ be a field and fix $m,n\in\N^+$. Then, for all $A\in\mat{m\times n}{K}$, there exists a unique reduced row-echelon matrix $B\in\mat{m\times n}{K}$ with $A\sim B$._

```

_Proof_. We proceed by induction on $n$.
* ($n=1$): If $A=0_{m\times1}$, it is in RREF and no elementary row operations can create a non-zero entry. Otherwise, we may use elementary row operations to bring a non-zero entry to the first row, divide it out to 1, and convert every non-zero entry below it to 0. No elementary row operations can destroy the 1, and any further non-trivial elementary row operations will bring the matrix out of RREF.

Assume now that the reduced row-echelon form of a matrix with $n$ columns is unique for some fixed $n\in\N^+$. Consider any $A\in\mat{m\times\l(n+1\r)}{K}$ and let $\v{a}$ be its last column, so the remaining $A'\in\mat{m\times n}{K}$ satisfies $A=\l[A'\mid\v{a}\r]$. Let $r\coloneqq\rank A$ and $r'\coloneqq\rank A'$. If $B\coloneqq\l[B'\mid\v{b}\r]$ is a reduced row-echelon form of $A$, then $B'$ is also in RREF and hence $B'$ is a reduced row-echelon form of $A'$; by our induction hypothesis, $B'$ is the unique such matrix. For all $i\in\l\{1,\dots,r'\r\}$, let $k_i$ denote the $i^\textrm{th}$ pivot column of $B'$ and consider the set $P'\coloneqq\l\{\v{a}_{k_1},\dots,\v{a}_{k_{r'}}\!\r\}$; observe that since $B'$ is unique, this set is uniquely determined. Since $P'$ is the set of all columns in $A'$ corresponding to the pivot columns of $B'$, it is a basis for $\col A'$. Let $P\coloneqq P'\cup\l\{\v{a}\r\}$.
* If $P$ is linearly independent, then $r=r'+1$, and since elementary row operations preserve rank, we have $\rank B=\rank B'+1$ too. Thus $\l\{\v{e}_1,\dots,\v{e}_{r'},\v{b}\r\}$ is linearly independent, and since the last $m-r$ rows of $B$ are zero, this forces $\v{b}=\v{e}_r$. Thus $B$ is uniquely determined.

* Otherwise, if $P$ is linearly dependent, then there exists a span-redundant element. Such an element must not be in $P'$, so $\v{a}\in\span P'\subseteq\col A'$. But since $P'$ is a basis for $\col A'$, there exists a unique representation of $\v{a}$ as a linear combination of vectors in $P'$, so the coefficients of $\v{b}=\sum_{i=1}^r\beta_i\v{e}_i$ are uniquely determined by those of $\v{a}$.

In both cases, $\v{b}$ is uniquely determined, and since $B'$ is unique, we see that $B=\l[B'\mid\v{b}\r]$ is the unique reduced row-echelon matrix such that $A\sim B$.<span style="float:right;">$\blacksquare$</span>
