$$Ax^{*}=b \tag{P}$$
$$\Downarrow \quad A \in \mathbb{R}^{n \times n} \text{ is SPD}$$
$$x^{*}\text{ minimises }\phi (x) = \frac{1}{2}x^{T}Ax-b^{T}x \tag{M}$$
Iteration to solve $(M)$:
	1. choose start $\overline{x}$ and search direction $p$
	2. set $x_{new}=x(\alpha ^{*}):=\overline{x}+\alpha ^{*}p$
		1. where $\alpha =\alpha ^{*}\min_\limits{}\phi (x(\alpha ))$.
	3. Set $\overline{x}=x_{new}$, choose $p$, iterate

**Observation 1**
 (a) $$\begin{align*}
\phi (x(\alpha ))&=  \frac{1}{2} (\overline{x}+ \alpha p)^{T}A(\overline{x}+\alpha p)-b^{T}(\overline{x }+\alpha p)\\
&\stackrel{A=A^{T}}{=} \frac{1}{2}\alpha ^{2}p^{T}Ap+\alpha p^{T}(A \overline{x}-b)+ \phi (\overline{x}) \tag{2}
\end{align*}$$
Denote $-\overline{r}:=A \overline{x}-b$.

(b) Minimising
$$0=\partial_{\alpha }\phi (x(\alpha ))=\alpha p^{T}Ap-p^{T}\overline{r}$$
$$\implies\quad \alpha ^{*}=\frac{p^{T}\overline{r}}{p^{T}Ap}$$
## Generic line search
Choose $x_{0},p_{0}$
$r_{0}=b-Ax_{0}$
for $k=0,1,2,\dots$:
	$$\alpha _{k}= \frac{p_{k}^{T}r_{k}}{p_{k}^{T}Ap_{k}}\tag{4}$$
	$x_{k+1}=x_{k}+ \alpha _{k}p_{k}$
	$r_{k+1}=b-Ax_{k+1}=r_{k}-A(x_{k+1}-x_{k})=r_{k}-\alpha_{k}Ap_{k}$.
	**choose** $p_{k+1}$

### Lemma 1
(a) $\begin{align*}\phi (x_{k+1})&= \phi (x_{k})- \frac{1}{2} \frac{(p_{k}^{T}r_{k})^{2}}{p_{k}^{T}Ap_{k}}\\ &\stackrel{A SPD}{\le}\phi (x_{k}) \end{align*}$

(b) $p_{k}^{T}r_{k+1}=0$

**Proof**
(a): Relation (2) with $\overline{x}=x_{k},\quad \alpha =\alpha _{k},\quad \overline{r}=r_{k}$
(b):
$$p_{k}^{T}r_{k+1}=p_{k}^{T}(r_{k}-\alpha _{k}Ap_{k})=p_{k}^{T}\left(r_{k}-\frac{p_{k}^{T}r_{k}}{p_{k}^{T}Ap_{k}}Ap_{k}\right)$$
$$=p_{k}^{T}r_{k}- \frac{p_{k}^{T}r_{k}}{p_{k}^{T}Ap_{k}}\cdot p_{k}^{T}Ap_{k}=0 \qquad \square$$

### Remark 1
(a) $p_{k}^{T}r_{k}≠0 \quad\Leftrightarrow\quad  \alpha _{k}≠0 \quad\implies\quad \{\phi (x_{k}) \}_{k}$ is strictly decreasing.

(b) $$p_{k}^{T}r_{k}=0 \quad\Leftrightarrow\quad \begin{cases}
r_{k}=0 & (\Leftrightarrow\quad x_{k}=x^{*}) \\
r_{k}≠0 &  \text{Want to avoid}
\end{cases}$$
### Choice of $p_{k}$
##### (i) Steepest descent
$p_{k}=r_{k}$
$\quad\implies\quad p_{k}^{T}r_{k}=\lvert r_{k} \rvert^{2},\qquad \alpha _{k}= \frac{\lvert r_{k} \rvert^{2}}{r_{k}^{T}Ar_{k}}$
This method will converge when $A$ is SPD

#### (ii) Conjugate gradient
$p_{k}= r_{k}+ \dots$
[[Conjugate Gradient]]