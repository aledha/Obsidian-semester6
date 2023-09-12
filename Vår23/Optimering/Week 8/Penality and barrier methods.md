For inequality constraints.
For simplicity: **only** inequality constraints
$$\min_\limits{x}f(x)\quad\text{such that}\quad c_{i}(x)\ge0 \quad\forall\quad i\in \mathcal{I}$$
## Quadratic penalisation
(again)
Define 
$$c_{i}^{-}(x)=\begin{cases}
c_{i}(x) & c_{i}(x)<0 \\
0 & \text{else}
\end{cases}\quad (=\min_\limits{}\{c_{i}(x),0 \}$$
Then $$c_{i}(x)\ge0\quad\Leftrightarrow\quad c_{i}^{-}(x)=0$$
Obtain the problem
$$\min_\limits{x}f(x) \quad\text{such that}\quad c_{i}^{-}(x)=0\quad\forall\quad i\in \mathcal{I}$$
Can use the [[Quadratic penalty method]]
$$Q(x,\mu)=f(x)+ \frac{\mu}{2}\sum\limits_{i\in \xi}^{}c_{i}^{-}(x)^{2}$$
And minimize $Q$ for large $\mu$.
**Problem**: $c_{i}^{-}$ is (often) not differentiable in points where $c_{i}(x)=0$.
But $(c_{i}^{-})^{2}$ is actually $\mathcal{C}^{1}$ with
$$\nabla (c_{i}^{-})^{2}=2c_{i}^{-}(x)\cdot \nabla c_{i}^{-}(x)=\begin{cases}
2c_{i}(x)\nabla c_{i}(x) & \text{if } c_{i}(x)<0 \\
0 & \text{else}
\end{cases}$$
$(c_{i}^{-})^{2}$ is (mostly) **not** $\mathcal{C}^{2}$

Quadratic penalty method is applicable, but there might be issues since $Q$ is not $\mathcal{C}^{2}$

## Barrier methods
Idea: penalise $x$ if you are coming close to the boundary of the constrained set:
E.g.:
### Logarithmic barrier method
For $\beta>0$, define
$$B(x,\beta)=f(x)-\beta \sum\limits_{i\in \mathcal{I}}^{}\text{ ln}(c_{i}(x))$$
For $\beta\to0$, we get
$$B(x,\beta)\to\begin{cases}
f(x) & \text{if }c_{i}(x)>0\quad\forall\quad i\in \mathcal{I} \\
+\infty & \text{if } c_{i}(x)\le0\quad \text{for some }i\in \mathcal{I}
\end{cases}$$
And $B\in \mathcal{C}^{2}$ if $f\in \mathcal{C}^2$

One can show: 
Accumulation points of minimisers $x_{k}$ of $B(x,\beta_{k})$ with $\beta_{k}\to0,\quad \beta_{k}>0$ 
$\Downarrow$
Accumulation points are solutions of the constrained problem

And: problem becomse ill-conditioned as $\beta\to0$

## Differences
* Approximate solutions are strictly feasible
* $B$ is smooth
But:
* Evaluation of $B$ requires that $x$ is feasible.
	* $x_{0}$ **needs** to be feasible
	* If this is not possible, reformulate the problem as:
$$\min_\limits{x,s}f(x)\quad\text{s.t.}\quad \begin{cases}
c_{i}(x)=s_{i} & i\in \mathcal{I} \\
s_{i}\ge0 & i\in \mathcal{I}
\end{cases}$$
