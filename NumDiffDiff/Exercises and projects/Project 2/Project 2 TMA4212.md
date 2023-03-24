# Task 1
## 1a)
Consider the stationary model,
$$-\partial_{x}(\alpha (x)\partial_{x}u)+\partial_{x}(b(x)u)+c(x)u=f \quad\text{on }\Omega =(0,1).$$
Now, we can apply the Galerkin method, by multiplying both sides with a test function $v\in H^{1}_{0}$, and integrating $x$ from $0$ to $1$,
$$\int_{0}^{1}-(\alpha u_{x})_{x}v+ (bu)_{x}v+cuv \text{ d}x=\int_{0}^{1}fv \text{ d}x.$$
Using integration by parts, we obtain
$$-\left\{\left[\alpha u_{x} v \right]_{0}^{1}-\int_{0}^{1}\alpha u_{x}v_{x}\text{ d}x \right\}+\left\{\left[buv \right]_{0}^{1}-\int_{0}^{1}buv_{x}\text{ d}x \right\}+ \int_{0}^{1}cuv \text{ d}x=\int_{0}^{1}fv \text{ d}x.$$
Since $v\in H^{1}_{0} \quad\implies\quad v(0)=0=v(1)$, such that the equation becomes
$$\int_{0}^{1}(\alpha u_{x}v_{x} -buv_{x}+cuv ) \text{ d}x=\int_{0}^{1}fv \text{ d}x.$$
Thus, 
$$a(u,v)= \int_{0}^{1}(\alpha u_{x}v_{x} -buv_{x}+cuv ) \text{ d}x, \qquad F(v)=\int_{0}^{1}fv \text{ d}x.$$
Since our only constriction on $v$ was that it was in the space $H_{0}^{1}$, any classical solution $u$ would fulfill
$$a(u,v)=F(v)\quad\forall\quad v\in V,\tag{1}$$
where for now $V=H^{1}_{0}$.


# Task 2
## 2a
To actually compute and find a solution numerically, we need to approximate the infinite dimensional function space $V$ with some finite dimensional space $V_{h}$. This can be done by taking an arbitrary grid on $(0,1)$, and setting $V_{h}=X^{1}_{h}\cap H^{1}_{0}$. That is, the space of continuous functions with zero bondary values at $x=0,x=1$, that also are piecewise linear on our grid.

Since $V_{h}$ is now finite dimensional, we can set a basis. We choose the simple solution of a basis $\{\phi _{i}(x) \}$ defined as
$$\phi _{i}(x)=\begin{cases}
\frac{x-x_{i-1}}{h_{i}}, & \quad\text{for }x\in[x_{i-1},x_{i}), \\
\frac{x_{i+1}-x}{h_{i+1}}, & \quad\text{for }x\in[x_{i},x_{i+1}), \\
0,  & \quad \text{elsewhere},
\end{cases}$$
where $x_{i}$ is nodal point number $i$, and $h_{i}=x_{i}-x_{i-1}$.

Can write this as a linear system, since any solution would be a linear combination of the basis, i.e. $u_{h}=\sum\limits_{i=0}^{M}U_{i}\phi _{i}(x)$.
$$A \vec{U}=\vec{F},\qquad U_{0}=0,\quad U_{M}=0,$$
where $\vec{U}=\left[U_{0},\dots,U_{M} \right]^{T},\qquad A_{ij}=a(\phi _{j},\phi _{i}), \qquad F_{j}=F(\phi _{j})$.

For ease of implementation, we will build the matrix $A$ and vector $\vec{F}$ element by element. More specifically,
$$A_{ij}=\sum\limits_{K\in \mathcal{T}_{h}}^{}\int_{K}(\alpha \phi_{j}'\phi_{i}' -b \phi_{j}  \phi_{i}'+c \phi_{j} \phi_{i}  ) \text{ d}x=:\sum\limits_{K \in \mathcal{T}_{h}}^{}a^{K}(\phi _{j},\phi _{i}),$$
$$F_{j}=\sum\limits_{K\in \mathcal{T}_{h}}^{}\int_{K}f \phi  _{j}=:\sum\limits_{K \in \mathcal{T_{h}}}^{}F^{K}(\phi _{j}).$$
Now define the elemental stiffness matrix and the elemental load vector as
$$A^{K_{i}}=\begin{bmatrix}a^{K_{i}}(\phi _{i-1},\phi _{i-1}) & a^{K_{i}}(\phi _{i-1},\phi _{i}) \\ a^{K_{i}}(\phi _{i},\phi _{i-1}) & a^{K_{i}}(\phi _{i},\phi _{i})\end{bmatrix}, \qquad \qquad F^{K_{i}}=\begin{bmatrix}F^{K_{i}}(\phi _{i-1}) \\ F^{K_{i}}(\phi _{i})\end{bmatrix}.$$
Computing the first index,
$$\begin{align*}
a^{K_{i}}(\phi _{i-1},\phi _{i-1})&= \int_{x_{i-1}}^{x_{i}}\alpha \left(- \frac{1}{h_{i}}\right)^{2}-b \cdot \frac{x_{i}-x}{h_{i}}\cdot \left(- \frac{1}{h_{i}}\right)+c \left(\frac{x_{i}-x}{h_{i}} \right)^{2}\text{ d}x\\
&= \frac{1}{h_{i}}\alpha + \frac{1}{2}b + \frac{1}{3}c h_{i}.
\end{align*}$$
Similarly for the other indices, we get
$$\begin{align*}
a^{K_{i}}(\phi _{i},\phi _{i-1})&=  -\frac{1}{h_{i}}\alpha - \frac{1}{2}b + \frac{1}{6}c h_{i},\\
a^{K_{i}}(\phi _{i-1},\phi _{i})&=  -\frac{1}{h_{i}}\alpha + \frac{1}{2}b + \frac{1}{6}c h_{i},\\
a^{K_{i}}(\phi _{i},\phi _{i})&=  \frac{1}{h_{i}}\alpha - \frac{1}{2}b + \frac{1}{6}c h_{i}.
\end{align*}$$
And for the elemental load vecter we get
$$F^{K_{i}}=\begin{bmatrix}\int_{K_{i}}f \phi _{i-1}\text{ d}x \\\int_{K_{i}}f \phi _{i}\text{ d}x \end{bmatrix},$$
which we will compute by using quadrature functions from SciPy. 

Let's look at some results. We use the analytical solutions $u(x)=x(1-x)$  and $u(x)=\text{ sin}(3\pi x)$.
We will need to compute $f$ from the model.
(insert ole gunnar computations)

We now obtain these results,
(insert results)

## 2b)
How good are these results? We compute convergence plots numerically by computing the solution and corresponding $L^{2}$ and $H^{1}$ errors, i.e., $\lVert u-u_{h} \rVert_{L^{2}}$ and $\lVert u-u_{h} \rVert_{H^{1}}$.

(insert first convergence plots)

## 2d)
It could be interesting to explore how our method handles non-differentiable functions. Let's take a look at the following
$$w_{1}(x)=\begin{cases}
2x & \quad\text{for }x\in\left(0, \frac{1}{2}\right) \\
2(1-x) & \quad\text{for }x\in\left( \frac{1}{2},1\right)
\end{cases},\qquad \quad w_{2}(x)=x-\lvert x \rvert^{\frac{2}{3}}.$$
The derivatives are
$$w'_{1}(x)=\begin{cases}
2 & \quad\text{for }x\in\left(0, \frac{1}{2}\right) \\
-2 & \quad\text{for }x\in\left( \frac{1}{2},1\right)
\end{cases},\qquad \quad w'_{2}(x)=1- \frac{2}{3}\lvert x \rvert^{-\frac{1}{3}}.$$
For a function $f$ to be in $H^{1}(0,1)$, we need that $f\in L^{2}(0,1), \nabla f\in L^{2}(0,1)$
So for compute
$$\begin{align*}
\int_{0}^{1}|w_{1}(x)|^{2}\text{ d}x&= \int_{0}^{\frac{1}{2}}4x^{2}\text{ d}x+\int_\frac{1}{2} ^{1}(2-2x)^{2}\text{ d}x<\infty \quad&\implies\quad w_{1} \in L^{2},\\
\int_{0}^{1}|w'_{1}(x)|^{2}\text{ d}x&= \int_{0}^{\frac{1}{2}}4\text{ d}x+\int_\frac{1}{2} ^{1}4\text{ d}x<\infty \quad&\implies\quad w'_{1} \in L^{2},\\
\int_{0}^{1}|w_{2}(x)|^{2}\text{ d}x&= \int_{0}^{1}x-x^{\frac{2}{3}}\text{ d}x=\left[\frac{1}{2}x^{2}- \frac{3}{5}x^{\frac{5}{3}} \right]_{0}^{1}<\infty \quad&\implies\quad w_{2}\in L^{2}\\
\int_{0}^{1}|w'_{2}(x)|^{2}\text{ d}x&= \int_{0}^{1}1- \frac{2}{3}x^{-\frac{1}{3}}\text{ d}x=\left[x-x^{\frac{2}{3}} \right]_{0}^{1}<\infty \quad&\implies\quad w_{2}\in L^{2}
\end{align*}$$
#show that they are not in H2
$w'_{1}$ is not continuous at $x=\frac{1}{2}$, and $w'_{2}$ is not defined at $x=0$.


Since these two functions are not second differentiable, we must use integration by parts to remove the $w''$ term.
$$\begin{align*}
F^{K_{i}}(\phi _{j})&= \int_{K_{i}}f \phi _{j} \text{ d}x= \int_{K_{i}}-\alpha w''(x)\phi _{j}+bw'(x)\phi _{j} +cw(x)\phi _{j}\text{ d}x\\
	&\stackrel{\text{I.B.P}}{=}-\alpha \left[ w' \phi _{j}\right]_{x_{i-1}}^{x_{i}}+\int_{K_{i}}\alpha w'\phi' _{j} + \phi _{j}(bw'+cw) \text{ d}x.
\end{align*}$$
There are two cases where $F^{K_{i}}(\phi _{j})≠0$, namely when $j=i-1, \quad j=i$.
For $j=i-1$:
$$\begin{align*}
F^{K_{i}}(\phi _{i-1})&= -\alpha (w'(x_{i})\cdot 0-w'(x_{i-1})\cdot 1)+\int_{K_{i}}\alpha w' \cdot \left(- \frac{1}{h_{i}}\right)+ \frac{x_{i}-x}{h_{i}}(bw'+cw) \text{ d}x\\
&= \alpha w'(x_{i-1})+\int_{K_{i}}- \frac{\alpha}{h_{i}} w' \cdot + \frac{x_{i}-x}{h_{i}}(bw'+cw) \text{ d}x
\end{align*}$$
For $j=i$:
$$\begin{align*}
F^{K_{i}}(\phi _{i})&= -\alpha (w'(x_{i})\cdot 1-w'(x_{i-1})\cdot 0)+\int_{K_{i}}\alpha w' \cdot \frac{1}{h_{i}}+ \frac{x_{i}-x}{h_{i}}(bw'+cw) \text{ d}x\\
&= -\alpha w'(x_{i-1})+\int_{K_{i}} \frac{\alpha}{h_{i}} w' \cdot + \frac{x-x_{i-1}}{h_{i}}(bw'+cw) \text{ d}x
\end{align*}$$
Which again, we will compute numerically.




## 2e)
$f(x)=x^{- \frac{1}{4}}$
$$\begin{align*}
\int_{0}^{1}|x^{- \frac{1}{4}}|^{2}\text{ d}x&=  \int_{0}^{1}x^{- \frac{1}{2}}\text{ d}x\\
&= \left[2x^{\frac{1}{2}} \right]_{0}^{1}= 2<\infty\\
&\implies\quad f\in L^{2}(0,1)
\end{align*}$$