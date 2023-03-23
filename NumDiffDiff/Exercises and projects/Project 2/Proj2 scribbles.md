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
$$a(u,v)=F(v)\quad\forall\quad v\in V,$$
where for now $V=H^{1}_{0}$.

**TODO:** show that a(u,v) is a bilinear and continuous form (function) on H1 ×H1, and that F(v) is a linear continuous (bounded) functional on H1. 

## 2a)
To actually compute and find a solution numerically, we need to approximate the infinite dimensional function space $V$ with some finite dimensional space $V_{h}$. This can be done by taking an arbitrary grid on $(0,1)$, and setting $V_{h}=X^{1}_{h}\cap H^{1}_{0}$. That is, the space of continuous functions with zero bondary values at $x=0,x=1$, that also are piecewise linear on our grid.

Since $V_{h}$ is now finite dimensional, we can set a basis. We choose the simple solution of a basis $\{\phi _{i}(x) \}$ defined as
$$\phi _{i}(x)=\begin{cases}
\frac{x-x_{i-1}}{h_{i}} & \quad\text{for }x\in[x_{i-1},x_{i}) \\
\frac{x_{i+1}-x}{h_{i+1}} & \quad\text{for }x\in[x_{i},x_{i+1}] \\
0  & \quad \text{elsewhere},
\end{cases}$$
where $x_{i}$ is nodal point number $i$, and $h_{i}=x_{i}-x_{i-1}$.


