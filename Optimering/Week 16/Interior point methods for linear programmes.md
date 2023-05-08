Consider a linear programme in standard form, i.e.,
$$\min_\limits{}c^{T}x \qquad\text{s.t.}\quad Ax=b, \quad x\ge0.$$
Compute first the dual problem:
$$\mathcal{L}(x,\lambda ,s)= c^{T}x-\lambda ^{T}(Ax-b) -s^{T}x,$$
where $\lambda$ is for the equality constraints, $s$ is for the inequality constraints.

The dual cost function becomes
$$\begin{align*}
q(\lambda ,s)&= \min_\limits{x}\mathcal{L}(x,\lambda ,s)\\
&= \min_\limits{x}[c^{T}x-\lambda ^{T}(Ax-b) -s^{T}x]\\
&= \lambda ^{T}b+\min_\limits{x}[(c^{T}-\lambda ^{T}A -s^{T})x]\\
&=\lambda ^{T}b + \begin{cases}
0 & \quad\text{for }A^{T}\lambda +s=c\\
-\infty & \quad \text{else}
\end{cases}.
\end{align*}$$
$\implies\quad$ the dual problem becomes
$$\max_\limits{\lambda ,s} \lambda ^{T}b \qquad\text{s.t.}\quad A^{T}\lambda +s=c~~ \text{ and }~~s\ge0$$
	(or) 
$$\max_\limits{\lambda }\lambda ^{T}b \qquad\text{s.t.}\quad A^{T}\lambda \le c$$
	Interestingly: the lagrangian dual to this dual problem **is** the primal problem!

[[Duality theorem#Duality theorem|Strong duality theorem]] applies if [[Slater's constraint qualification]] holds, that is:
there exists a point $x$ with $Ax=b$ and $x\ge0$.
	That is, the primal problem is feasible
$\implies\quad$ the dual problem has a solution and the duality gap is zero, provided that the primal problem is bounded below.

But in this case, the primal problem has a solution as well. 
And one can show that the dual of the dual problem is the primal problem.
$\implies\quad$ There exists a primal-dual solution $(x^{*},\lambda ^{*},s^{*})$ such that
* $x^{*}$ solves the primal problem.
* $(\lambda ^{*},s^{*})$ solves the dual problem.
* $(\lambda ^{*},s^{*})$ is a Lagrange parameter for the primal problem.
* $x^{*}$ is a Lagrange parameter for the dual problem.

$(x^{*},\lambda ^{*},s^{*})$ is characterised by the [[KKT-conditions]]:
$$\begin{align*}
A^{T}\lambda ^{*}+s^{*}&= c\\
Ax^{*}&= b\\
x^{*}&\ge 0\\
s^{*}&\ge 0\\
x_{i}^{*}s_{i}^{*}&= 0 \quad\forall\quad i
\end{align*}$$

Now consider the logarithmic barrier problem:
$$B(x,\tau )=c^{T}x- \tau \sum\limits_{i}^{}\text{ ln }x$$
Now, let's minimise this
$$\min_\limits{x}B(x,\tau )\qquad\text{s.t.}\quad Ax=b,$$
where we assume that there exists some $x>0\qquad\text{s.t.}\quad Ax=b$.
Logarithm is concave $\quad\implies\quad -\sum\limits_{i}^{}\text{ ln}$ is strictly convex. $c^{T}x$ is linear.
$\implies\quad$ $B(x, \tau )$ is strictly convex function
$\implies\quad$ if a solution exists, it is unique, and uniquely characterised by the KKT conditions for this problem:
$$\begin{align*}
c_{i}- \frac{\tau}{x_{i}}-(A^{T}\lambda)_{i}&= 0 \quad\text{for }i =1,\dots,d\\
Ax&= b  \\
(x&> 0)
\end{align*}$$
Denote $s_{i}:= \frac{\tau }{x_{i}}$. Can rewrite
$$\begin{align*}
A^{T}\lambda +s&= c\\
Ax&= b\\
(x&> 0,s>0)\\
x_{i}s_{i}&= \tau \quad\forall\quad i
\end{align*}$$
$\implies\quad$ the optimality conditions for this problem is **almost** the same as for the original problem, we only have replaced $x_{i}s_{i}=0$ by $x_{i}s_{i}=\tau$.
Now we wish to apply Newton's method for this system. 
But first, some notation:
**Definition**
For $\tau >0$, we denote by $(x_{\tau },\lambda _{\tau },s_{\tau })$ the unique solution of the modified KKT system for the barrier
$$\begin{align*}
A^{T}\lambda _{\tau }+s_{\tau }&= c\\
Ax_{\tau }&= b\\
x_{\tau ,i}s_{\tau ,i}&= \tau \quad\text{for }i=1,\dots,d\\
(x_{\tau }>0&,s_{\tau }>0)
\end{align*}\tag{*}$$
Denote by $\{(x_{\tau },\lambda _{\tau },s_{\tau }):\quad \tau >0 \}$, the **central path** for the linear programme
$$\min_\limits{x}c^{T}x \qquad\text{s.t.}\quad Ax=b ~\text{ and }~x\ge0$$
#insert polyhedron

### Path following interior point methods
Idea:
* start with initial values $x^{(0)},\lambda ^{(0)},s^{(0)}$ with  $x^{(0)},s^{(0)}>0$
  and $Ax^{(0)}=b$
  and $A^{T}\lambda ^{(0)}+s^{(0)}=c$
  and $\tau _{0}>0$
* perform one step of Newton's method for $(*)$ and a step length $0<\alpha \le 1$ such that the next iterate stays "close" to the central path.
* Decrease $\tau$, iterate.

What means "close to the central path"?
	For that, denote by (average)
	$$\mu (x,s)= \frac{1}{d}\sum\limits_{i=1}^{d}x_{i}s_{i}$$
	the *duality measure*. 
		One can show: $d \mu (x,s)$ is the current duality gap
	If $x_{i}s_{i}=\mu (x,s)\quad\forall\quad i$, then $(x,\lambda ,s)$ is on the central path.

$\implies\quad$ define for $0<\gamma \le1$
$$\mathcal{N}(\gamma )=\{(x,\lambda ,s):\quad Ax=b, \quad A^{T}\lambda +s=c \quad x,s>0 \quad \text{ and }x_{i}s_{i}\ge \gamma \cdot \mu (x,s)\quad\forall\quad i\}$$
$\implies\quad \mathcal{N}(1)$ is the central path (where $x_{i}s_{i}=\text{const.} \quad\forall\quad i$)
$\implies\quad$ for $0<\gamma <1$, $\mathcal{N}(\gamma )$ is some neighborhood of the central path.

### "Long-step path following method".
Choose $(x^{(0)},\lambda ^{(0)},s^{(0)})\in \mathcal{N(\gamma )}$ for some $0<\gamma <1$.
And a contraction factor $0<\sigma <1$.
Iterate:
	Set $\tau =\sigma \mu (x^{(k)},s^{(k)})$ 
	Find Newton updates $(\Delta x^{(k)},\Delta \lambda ^{(k)},\Delta s^{(k)})$ for the system
	$\begin{align*}Ax &= b\\ A^{T}\lambda +s&= c\\ x_{i}s_{i}&= \tau \quad\text{for }i=1,\dots ,d\end{align*}$,
	starting from $(x^{(k)},\lambda ^{(k)},s^{(k)})$
	Find the largest $0<\alpha \le1 \qquad\text{s.t.}\quad (x^{(k)},\lambda ^{(k)},s^{(k)})+(\Delta x^{(k)},\Delta \lambda ^{(k)},\Delta s^{(k)})\in \mathcal{N(\gamma )}$
		 set $(x^{(k)},\lambda ^{(k)},s^{(k)})=(x^{(k)},\lambda ^{(k)},s^{(k)})+(\Delta x^{(k)},\Delta \lambda ^{(k)},\Delta s^{(k)})$
		 update $k=k+1$

Does it work?
### Theorem
There is a constant $\delta >0$ only depending on the chosen parameters $\gamma$ and $\sigma \qquad\text{s.t.}\quad$
$$\mu (x^{(k+1)},s^{(k+1)})\le \left(1- \frac{\delta }{d}\right)\cdot \mu (x^{(k)},s^{(k)})$$
Note:
	$\delta$ does not depend on $A,b,\text{ or }c$.

Linear complexity for the iterates + Cubic complexity for solving a linear system in each step $\quad\implies\quad$ quadratic complexity.