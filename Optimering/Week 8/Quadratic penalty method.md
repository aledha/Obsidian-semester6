Specifically for equality constraints. Generally equality constraints are easier than inequality constraints.
Consider the problem
$$\min_{}f(x)\quad \text{such that}\quad c_{i}(x)=0\quad i\in \xi$$

## Definition: Penalty function
For some $\mu>0$, define the *penalty function*
$$Q(x,\mu)=f(x)+ \frac{\mu}{2}\sum\limits_{i\in \xi}c_{i}(x)^{2}$$
$\Rightarrow\quad$Minimize $Q$ instead of $f$, without any constraints, e.g. $\Omega=\mathbb{R}^{d}$.

### Example 1
$$\stackrel{\min}{x,y} \quad xy \quad \text{such that}\quad x^{2}+y^{2}=1$$
$\Rightarrow\quad$ KKT conditions read
$$\begin{align*}
y&= 2 \lambda x\\
x&= 2\lambda y\\
x^{2}+y^{2}&= 1
\end{align*}$$
We obtain the points
$$(x,y)= \frac{1}{\sqrt{2}} (1,1)\qquad (x,y)= -\frac{1}{\sqrt{2}}(1,1)$$
(maximum points). and
$$(x,y)= \frac{1}{\sqrt{2}} (1,-1)\qquad (x,y)= \frac{1}{\sqrt{2}}(-1,1)$$
(minimum points)

With quadratic penalisation
$$Q(x,y,\mu)=xy + \frac{\mu}{2}\cdot(x^{2}+y^{2}-1)^{2}$$
$\Rightarrow\quad$ Optimality conditions are (set $\nabla Q=0$)
$$\begin{align*}
y+\mu(x^{2}+y^{2}-1)\cdot2x&= 0\\
x+\mu(x^{2}+y^{2}-1)\cdot2y&= 0
\end{align*}$$
Obtain solutions
$$\begin{align*}
(x,y)&=  \sqrt{\frac{1}{2}+ \frac{1}{4\mu}}(1,-1)\\
(x,y)&=  \sqrt{\frac{1}{2}+ \frac{1}{4\mu}}(-1,1)
\end{align*}$$
(+ saddle point, maxima)

### Example 2
$$\min_{} \quad -x^{4} \quad \text{such that}\quad x=0$$
$$Q(x,\mu)=-x^{4} + \frac{\mu}{2}x^{2}$$
$\Rightarrow\quad$ this is unbounded below
$\Rightarrow\quad$ $Q(x,\mu)$ has no global solutions

## Theorem: Convergence of quadratic penalty method
Assume that $f$ is coercive and continuous, and that 
$c_{i}\quad i\in \xi$    are continuous.
there exists $\hat x\in \mathbb{R}^{d}$ such that $c_{i}(\hat x)=0\quad i\in \xi$
Let $\mu_{k}\to \infty$ and let $x_{k}$ be a gloval solution of $$\min_{x_{k}\in \mathbb{R}^{d}} Q(x,\mu_{k})$$
Then the sequence $x_{k}$ is bounded (it has a converging subsequence).
Every accumulation point is a solution of $\text{min} f$ such that $c_{i}(x)=0\quad i\in \xi$.

### Proof
$f$ is coercive and continuous. 
$c_{i}$ are continuous.
$$\Rightarrow\quad x_{k}\quad \text{exists}$$
and: there exists a solution $\tilde x$ of 
$$\min_{x}f(x)\quad\text{such that}\quad c_{i}(x)=0\quad\forall\quad i$$
Thus 
$$f(x_{k})\le f(x_{k}) + \frac{\mu_{k}}{2}\sum\limits_{i\in \xi}c_{i}(x_{k})^{2}\tag{*}$$
$$=Q(x_{k},\mu_{k})\le Q(\tilde x, \mu_{k})$$
$$=f(\tilde x)+ \frac{\mu_{k}}{2} \sum\limits_{i\in \xi}c_{i}(\tilde x)^{2}=f(\tilde x)$$
$$\Rightarrow\quad f(x_{k})\le f(\tilde x)\quad\forall\quad k$$
$f$ is coercive $\quad\Rightarrow\quad$ the sequence $x_{k}$ is bounded $\quad\Rightarrow\quad$ every bounded sequence has an accumulation point.
Let $y$ be an accumulation point of the sequence $x_{k}$.
Without loss of generality we can assume that 
$$x_{k}\stackrel{k\to \infty}{\to} y$$
Thus 
$$\begin{align*}
f(x_{k})&\to f(y)\\
c_{i}(x_{k})&\to c_{i}(y)
\end{align*}$$
In particular,
$$f(y)<\lim_{k\to \infty} f(x_{k})\le f(\tilde x)$$
We only have to show that $y$ satisfies the constraints.
We have from ($*$)
$$f(x_{k})+ \frac{\mu_{k}}{2}\sum\limits_{i\in \xi}c_{i}(x_{k})^{2}\le f(\tilde x)$$
$$\Rightarrow\quad \sum\limits_{i\in \xi}c_{i}(x_{k})^{2}\le \frac{2}{\mu_{k}}(f(\tilde x)-f(x_{k}))$$
When $k\to \infty$:
$$\le 0 \cdot(f(\tilde x)-f(y))$$
Therefore,
$$\sum\limits_{i\in \xi}c_{i}(y)^{2}= \lim_{k\to \infty}\sum\limits_{i\in \xi}c_{i}(x_{k})^{2}=0$$
$$\Rightarrow\quad c_{i}(y)=0 \quad\forall\quad i\in \xi$$
$\Rightarrow\quad$ $y$ solves the $\min_{x}f(x)\quad\text{such that}\quad c_{i}(x)=0\quad i\in \xi$

## In practice
Choose $\mu_{0}>0$ and $x_{0}$.
For $k=0,1,2,\dots$ {
use an unconstrained optimization method with initialization $x_{k}$ on the problem
$$\min_{x\in \mathbb{R}^{d}}Q(x,\mu_{k})$$
$\Rightarrow\quad$ solution $x_{k+1}$
Increase $\mu_{k+1}>\mu_{k}$
}

## Accuracy
Assume that $x^{*}$ is a KKT-point such that LICQ holds at $x^{*}$, 
and let $x_{\mu}$ is a local solution of $\min_{x}Q(x,\mu)$ 
and close to $x^{*}$.
Also assume that $c_{i}\in \mathcal{C}^{2}\qquad f\in \mathcal{C}^{1}$

Approach: Linearization
KKT conditions:
$$\nabla f(x^{*})=\sum\limits_{i\in \xi} \lambda_{i}^{*}\cdot \nabla c_{i}(x^{*})$$
Taylor:
$$≈\sum\limits_{i\in \xi} \lambda^{*}_{i}\nabla c_{i}(x_{\mu})+\mathcal{O}(||x_{\mu}-x^{*}||)$$
Optimality condition for $Q(\cdot,\mu)$
$$0=\nabla f(x_{\mu})+\mu \sum\limits_{i\in \xi}c_{i}(\mu)\cdot \nabla c_{i}(x_\mu)$$
$$=\nabla f(x^{*}) + \mu \sum\limits_{i\in \xi} c_{i}(x_{\mu})\nabla c_{i}(x_{\mu}) +\mathcal{O}(||x_{\mu}-x^{*}||)$$
$$\Rightarrow\quad \sum\limits_{i\in \xi}(\lambda_{i}^{*}+\mu c_{i}(x_\mu))\cdot \nabla c_{i}(x_{\mu})=\mathcal{O}(||x_{\mu}-x^{*}||)$$
LICQ $\quad\Rightarrow\quad$ $\nabla c_{i}(x^{*})$ are linearly independant $\quad\forall\quad i\in \xi$.
$\Rightarrow\quad$ for $x_{\mu}$ close to $x^{*}$, the vectors $\nabla c_{i}(x_{\mu})$ are also linearly independant. Remember defintion of [[Linear Independance]]
$$\Rightarrow\quad \lambda_{i}^{*}+\mu c_{i}(x_{u})=\mathcal{O}(||x_{\mu}-x^{*}||)$$
If $\lambda_{i}^{*}≠0$, then $\mu c_{i}(x_{\mu})≈-\lambda_{i}^{*}$.
or 
$$c_{i}(x_{\mu})≈- \frac{\lambda_{i}^{*}}{\mu}$$
Remember that the constraints should be $c_{i}(x^{*})=0$
$$c_{i}(x_{\mu})\sim \frac{1}{\mu}$$
$\Rightarrow\quad$ the accuracy of the solution is of order $\frac{1}{\mu}$
If we want $||x_{\mu}-x^{*}||< \epsilon$, we need
$$\mu\le  \frac{1}{\epsilon}$$
## Condition of the problem
$$\min_{x}Q(x,\mu)$$
is the condition number of
$$H_{Q}(x_{\mu},\mu)$$
$$\nabla Q(x,\mu)=\nabla f(x)+\mu \sum\limits_{i\in \xi}c_{i}(x)\nabla  c_{i}(x)$$
$$H_{Q}(x,\mu)=H_{f}(x)+\mu \sum\limits_{i\in \xi}(c_{i}(x)\cdot H_{c_{i}}(x) +\nabla c_{i}(x)\cdot \nabla c_{i}(x)^{T})$$
$$H_{Q}(x_{\mu}, \mu)≈H_{f}(x_{\mu})- \sum\limits_{i\in \xi}\lambda_{i}^{*}H_{c_{i}}(x_{\mu})+\mu \sum\limits_{i\in \xi}\nabla c_{i}(x_{\mu})\cdot \nabla c_{i}(x_{\mu})^T$$
What are the singular values of this matrix?
$\Rightarrow\quad$ have singular values of order $\mu$ from the term $\mu \sum\limits_{i\in \xi} \nabla c_{i}(x_{\mu})\nabla c_{i}(x_{\mu})^{T}$ 
and singular values of order 1 from the term $H_{f}(x_{\mu})-\sum\limits_{i\in \xi}\lambda_{i}^{*}H_{c_{i}}(x_{\mu})$
$$\Rightarrow\quad \text{cond}(H_{Q}(x_{\mu},\mu))\sim \mu$$
Horrible with gradient descent method!
Problem: we need to increase $\mu$ for accuracy, decrease $\mu$ for well-conditioned.