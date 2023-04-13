Let $A \in \mathbb{R}^{n \times n}$ be symmetric and positive definite (SPD):
	(i) Symmetric $A=A^{T}$
	(ii) Positive definite $x^{T}Ax >0 \quad\forall\quad x \in \mathbb{R}^{n}, x≠0$

**Remark 2**
(a) $A$ symmetric, then:
	(i) A strictly diagionally dominant with positive diagonal $\quad \implies\quad$ A positive definite.
	(ii) All eigenvalues $\lambda (A)>0 \quad\Leftrightarrow\quad A$ positive definite
(b) $A$ is symmetric and positive definite, then:
	(i) A invertible
	(ii) $A^{-1}$ is symmetric positive definite
(c) $A$ symmetric positive definite
	(i) $\exists \quad  B = A^{\frac{1}{2}}$  and $B$ is symmetric positive definite
		$B B=A$
		{Spectral theorem: $A=\sum\limits_{i=1}^{n}\lambda _{i}y_{i}y_{i}^{T}$ ,    where $Ay_{i}= \lambda _{i}y_{i}, \quad \lvert y_{i} \rvert=1$
		$\implies\quad A^{\frac{1}{2}}=\sum\limits_{i=1}^{n}\lambda _{i}^{\frac{1}{2}}y_{i}y_{i}^{T}$   }

#### Lemma 1
Any matrix $A$ which is SPD defines an inner product and norm:
	$\left\langle x \text{ , } y \right\rangle_{A}:=x^{T}Ay$
	$\lVert x \rVert^{2}_{A}:= \left\langle x \text{ , } x \right\rangle_{A}= \lvert A^{\frac{1}{2}}x \rvert^{2}$.

Need to show that $\lVert x \rVert_{A}^{2}=0 \quad\Leftrightarrow\quad x=0$.
$A^{\frac{1}{2}}$ is invertible, so
$x=0$ is the only solution of $A^{\frac{1}{2}}x=0$
$x=0$ is the only solution of $\lVert x \rVert_{A}^{2}=0$. 

Other inner product conditions are easier to check.


## Variational form
$$Ax^{*}=b \tag{P}$$
$$\textbf{Find minimiser }x^{*} \textbf{ of }\phi (x)= \frac{1}{2}x^{T}Ax-x^{T}b \tag{M}$$
### Theorem 2
(a) $x^{*}=A^{-1}b$   is a unique solution of (P)
(b) $x^{*}=A^{-1}b$  is a unique solution of (M)

#### Corallary 1
$A$ SPD:
$x^{*}$ solves (P) $\quad\Leftrightarrow\quad$ $x^{*}$ solves (M)
(M) is the **Variational form** of (P)

### Proof of (b)
Strategy: use $\tilde{\phi }(x)$ where $x^{*}$ is obviously a unique minimiser, and show that this is equivalent to $\phi (x)$.
1)
	$x^{*}$ is a unique minimizer of $\tilde{\phi }(x)= \frac{1}{2}\lVert x-x^{*} \rVert^{2}_{A}$
	since $\tilde{\phi}(x)>0 \quad\forall\quad x≠x^{*}$ 
	and $\tilde{\phi }(x^{*})=0$.
2)
	$2 \tilde{\phi }(x)=(x-x^{*})^{T}A(x-x^{*})$
	$=x^{T}Ax- x^{T}Ax^{*}-(x^{*})^{T}Ax+(x^{*})^{T}Ax^{*}$
	$=x^{T}Ax- b-b^{T}x+(x^{*})^{T}Ax^{*}$                                            since $Ax^{*}=b$    and    $(x^{*})^{T}A=(x^{*})^{T}A^{T}=b^{T}$
	$\stackrel{\text{def }\phi }{=} 2\phi + \text{constant}$
3) $x^{*}$ unique minimiser of $\phi (x))$
	by 1) and 2).