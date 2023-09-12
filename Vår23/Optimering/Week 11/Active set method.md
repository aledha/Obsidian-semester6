**Idea**: find the active set $\mathcal{A}(x)$ in a systematic manner
	Start with a guess
	"Working set"
	$W_{0}\supset \xi$   
	And add/remove indicies until we have found the solution


More precisely:
def equation_fixer(k):
	Choose some feasible point    $x_{0}\in \mathbb{R}^{d}\qquad\text{s.t.}\quad {\left\langle a_{i} \text{ , } x_{0} \right\rangle}=b_{i} \quad\text{for }i\in \xi$  and ${\left\langle a_{i} \text{ , } x_{0} \right\rangle}\ge b_{i}\quad\text{for }i\in \mathcal{I}$,
	and set $W_{0}=\{i: \quad {\left\langle a_{i} \text{ , } x_{0} \right\rangle}=b_{i} \}$
	In step k:
		Compute the solution of
		$\min_\limits{p} \frac{1}{2}{\left\langle x_{k}+p \text{ , } G(x_{k}+p) \right\rangle}+{\left\langle c \text{ , } x_{k}+p \right\rangle}$  $\quad\text{s.t.}\quad {\left\langle a_{i} \text{ , } p \right\rangle}=0\quad\forall\quad i\in W_{k}$
			(where ${\left\langle a_{i} \text{ , } p \right\rangle}=0\quad\forall\quad i\in W_{k} \quad\Leftrightarrow\quad {\left\langle a_{i} \text{ , } x_{k}+p \right\rangle}=b_{i}$)
		obtain $p_{k}$
		if $p_{k}≠0$:
			if $x_{k}+p_{k}$ is feasible, meaning
			if ${\left\langle a_{i} \text{ , } x_{k}+p_{k} \right\rangle}\ge b_{i}\quad\forall\quad i\notin W_{k}$:
				define $x_{k+1}=x_{k}+p_{k}$
				and set $W_{k+1}=\{i: \quad {\left\langle a_{i} \text{ , } x_{k+1} \right\rangle} =b_{i}\}$
			else, if $x_{k}+p_{k}$ is infeasible:
				choose the largest $\alpha _{k}>0$ such that
				$x_{k}+\alpha _{k}p_{k}$ is still feasible.
				Set $x_{k+1}=x_{k}+\alpha _{k}p_{k}$ 
				and $W_{k+1}=\{i:\quad {\left\langle a_{i} \text{ , } x_{k+1} \right\rangle} =b_{i}\}$.
		else if $p_{k}=0$:
			$x_{k}$ solves the problem:
			**$(P_{k})$**
				$\min_\limits{x} \frac{1}{2}{\left\langle x \text{ , } Gx \right\rangle}+ {\left\langle c \text{ , } x \right\rangle}$
				such that ${\left\langle a_{i} \text{ , } x \right\rangle}=b_{i}\quad\text{for }i\in W_{k}$
			And ${\left\langle a_{i} \text{ , } x_{k} \right\rangle}>b_{i}\quad\text{for }i\in W_{k}$
			Since $x_{k}$ solves this $(P_{k})$, there exists a Lagrange multiplier $\hat \lambda \in \mathbb{R}^{W_{k}}$
			such that
			$Gx_{k}+c=\sum\limits_{i\in W_{k}}^{}\hat \lambda _{i}a_{i}$.
			If $\hat\lambda _{i}\ge0\quad\forall\quad i\in W_{k}\cap \mathcal{I}$,
				then we can extend $\hat \lambda$ to a Lagrange multiplier for the original problem, with
				$\lambda _{i}=0 \quad\text{for }i\notin W_{k}$
				$\implies\quad$ we have found a solution
			Else, there exists $i\in W_{k}\cap \mathcal{I}$  such that $\hat \lambda _{i}<0$:
				$\implies\quad$ if we replace the condition that
				${\left\langle a_{i} \text{ , } x \right\rangle}=b_{i}$ by ${\left\langle a_{i} \text{ , } x \right\rangle}= b_{i}+\epsilon$,
				the function value decreases.
					Because of negative Lagrange multiplier
				$\implies\quad$ choose $i\in W_{k}\cap \mathcal{I}$ such that
				$\hat \lambda _{i}<0$ is the smallest,
				and set $W_{k+1}=W_{k}\backslash \{i \}$.

## Theorem
This algorithm finds a solution in finitely many steps.

### Proof:
Adding indices can be done finitely many times, after that we have found the solution on some face of the feasible polyhedron. In each step the function value decreases, which means that we can't get back to the same face. $\square$
