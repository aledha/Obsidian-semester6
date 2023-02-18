<div class="topSpace"></div>

Date Created: 24/03/2022 14:51:51
Tags: #Proposition #Later/Linear_Algebra

Proved by: _Not Applicable_
References: _Not Applicable_
Justifications: _Not Applicable_

Specializations: _Not Applicable_
Generalizations: _Not Applicable_

``` ad-Proposition
title: Proposition (Gaussian Algorithm).

_Let $K$ be a field and fix $m,n\in\N^+$. Then every matrix $A\in\mat{m\times n}{K}$ is row-equivalent to a matrix $R\in\mat{m\times n}{K}$ in reduced row-echelon form._

```

_Proof_. We shall algorithmically construct $R$ from $A$.
* _Step 1: (Create a leading 1 in the first row)$\bf{.}$_ If $A=0_{m\times n}$, stop. For all non-zero rows $i\in\l\{1,\dots,m\r\}$, let $k_i\coloneqq\min\l\{j\in\l\{1,\dots n\r\}\mid a_{ij}\neq0\r\}$ be the column with its leading entry. Let $l$ be any row such that $k\coloneqq k_l\leq k_i$ for all $i\in\l\{1,\dots,m\r\}$. Perform the type 3 elementary row operation
  <center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-03-24_185733/image.svg", width=500></center>
which moves said row on top, followed by the type 1 elementary row operation
  <center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-03-24_201822/image.svg", width=525></center>
* _Step 2: (Create zeros below the leading 1)$\bf{.}$_ This is done by performing the type 2 elementary row operations
  <center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-03-24_203210/image.svg", width=525></center>

  for all $i\in\l\{2,\dots,m\r\}$.
* _Step 3: (Repeat for all green submatrices)$\bf{.}$_ Let $A'$ be the matrix obtained after Step 2 and let $A_g$ be the green $\textrm{`}$submatrix$\textrm{'}$ shown above; that is, let $A_g$ be the $m_g\times n_g$ matrix defined, formally, as
$$\begin{equation}
    A_g:\l\{1,\dots,m_g\r\}\times\l\{1,\dots,n_g\r\}\to K\ \ \ \ \ \ \ \ \textrm{mapping}\ \ \ \ \ \ \ \ \tpl{i,j}\mapsto a'_{1+i,k+j}
\end{equation}$$
where $m_g\coloneqq m-1$ and $n_g\coloneqq n-k$. If $m_g\neq0$, repeat steps 1 and 2 with $A_g$, $m_g$, and $n_g$ in place of $A$, $m$, and $n$, respectively; note that all the elementary row operations performed in those steps do not affect any of the columns preceding and including $k$. Otherwise, move on to Step 4; this stopping condition will always occur as $m_g$ strictly decreases after each loop.

Steps 1 to 3 constitute the **forward pass** which ensure that all zero-rows are at the bottom and that the resulting matrix is in an upper-triangular $\textrm{`}$staircase$\textrm{'}$ form. As such, the zero-rows will not be typesetted; similarly for all zero-columns on the left since they will not be affected by any further elementary row operations.
* _Step 4: (Create zeros above the last leading 1)$\bf{.}$_ Let $l$ be the last non-zero row of the resulting matrix $U$ and let $k$ be its corresponding pivot column. Perform the type 2 elementary row operation
  <center><img src="app://local/home/zhao/Dropbox/MathWiki/Images/2022-06-07_044007/image.svg", width=750></center>

  for all $i\in\l\{1,\dots,l-1\r\}$ which create zeros above the leading 1.
* _Step 5: (Repeat for all green submatrices)$\bf{.}$_ Let $U'$ be the matrix obtained after Step 4 and let $U_g$ be the green $\textrm{`}$submatrix$\textrm{'}$ shown above; that is, let $U_g$ be the $m_g\times n_g$ matrix defined, formally, as
$$\begin{equation}
    U_g:\l\{1,\dots,m_g\r\}\times\l\{1,\dots,n_g\r\}\to K\ \ \ \ \ \ \ \ \textrm{mapping}\ \ \ \ \ \ \ \ \tpl{i,j}\mapsto u'_{ij}
\end{equation}$$
where $m_g\coloneqq l-1$ and $n_g\coloneqq k-1$. If $m_g\neq1$, repeat Step 5 with $U_g$, $m_g$, and $n_g$ in place of $U$, $m$, and $n$, respectively; again, note that all the elementary row operations performed do not affect any rows after $l$. Otherwise, stop.

Steps 4 and 5 constitute the **backward pass** which ensure that every pivot column contains only its leading 1. Let $R$ be the resulting matrix; observe that it is in reduced row-echelon form and that only elementary row operations were used to obtain $R$ from $A$.<span style="float:right;">$\blacksquare$</span>
