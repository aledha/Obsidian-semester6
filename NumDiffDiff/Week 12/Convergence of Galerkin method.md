23.04.2023
Ceas lemma:
	$\lVert u-v_{h} \rVert_{V}\le \frac{M}{\alpha }\inf_\limits{v_{h}\in V_{h}}\lVert u-v_{h} \rVert_{V}$,
Let us define the approximation error,
$$E_{h}(u):=\inf_\limits{v_{h}\in V_{h}}\lVert u-v_{h} \rVert_{V}.$$

Convergence:
$u_{h}\stackrel{h\to 0}{\to}u \quad \text{in }V \text{ if }\quad  E_{h}(u)\to0$.
So $E_{h}(u)=$ "how well $u \in V$ can be approximated by $u_{h}\in V_{h}$".

# Approximation error for $\mathbb{P}_{1}$ FEM in 1d
Let $V=H_{0}^{1}(0,1)$, and
triangulation $\mathcal{T}_{h}=\{K_{i} \}_{i=1}^{M}$,
and let our approximation space be
$V_{h}=X^{1}_{h}(0,1)\cap V$.
#insert sketch of space

### Linear interpolation
Let the interpolant $I_{h}$ be defined by
$$I_{h}u(x)=\sum\limits_{i=0}^{M}u(x_{i})\phi _{i}(x),$$
where $\phi _{i}$ is the $i$-th basis function.
#insert interpolation

**Observation**
* $u \in H^{1} \quad\implies\quad u \text{ continuous (in 1d)}.$
	$\quad\implies\quad I_{h}u \in X^{1}_{h} \text{ is well defined}$.
* $u\in H^{1}_{0}\quad\implies\quad I_{h}u \in X^{1}_{h}\cap H^{1}_{0}$
	  and 
	  $$E_{h}(u)\le \lVert u-I_{h}u \rVert_{H^{1}}=:\tilde{E}_{h}(u),$$
	  where $E_{h}(u)$ is the approximation error, and
	  $\tilde{E}_{h}(u)$ is the interpolation error.

### Estimate $\tilde{E}_{h}$ for $v \in H^{2}\subset H^{1}$
Denote $e=v-I_{h}v$.
Then,
$$\tilde{E}_{h}(v)^{2}=\lVert e \rVert^{2}_{H^{1}}=\lVert e \rVert^{2}_{L^{2}}+\lVert e' \rVert^{2}_{L^{2}}.$$

**Observation**
	$e(x_{i})=0 \quad\text{for }i=0,\dots,M$.

**Mean value theorem**
	There exists $\xi _{i}\in K_{i}=(x_{i-1},x_{i})$ such that
	$e'(\xi _{i})=0$.
	Note: not illegal
		$e'|_{K_{i}}$ is continuous since $v' \in H^1$.

**Fundemental theorem of calculus**
	$e'(x)=e'(\xi _{i})+\int_{\xi _{i}}^{x}e''(s)\text{ d}s$,
	for $x\in K_{i}$

And $e''=v''-(I_{h}v)''$
Inside every element the linear interpolant is zero:
$e''=v''$.

So combining these we get,
$$\begin{align*}
\lvert e'(x) \rvert^{2}&\le  \left(\int_{K_{i}}\lvert e''(s) \rvert \text{ d}s \right)^{2}\\
&= \left(\int_{K_{i}}1\cdot \lvert v''(s) \rvert \text{ d}s\right)^{2}\\
\text{(*)}\qquad &\stackrel{\text{Cauchy Sch}}{\le}\int_{K_{i}}1^{2}\text{ d}s \cdot \int_{K_{i}}\lvert v''(s) \rvert^{2} \text{ d}s\\
&= (x_{i}-x_{i-1})\int_{K_{i}}\lvert v''(s) \rvert^{2} \text{ d}s\\
&= h\int_{K_{i}}\lvert v''(s) \rvert^{2} \text{ d}s
\end{align*}$$
Integrate over $x \in (0,1)$, then we get
$$\begin{align*}
\lVert e' \rVert^{2}_{L^{2}(0,1)}&= \sum\limits_{i}^{}\int_{K_{i}}\lvert e'(x) \rvert^{2}\text{ d}x\\
		&\le \sum\limits_{i}^{}\left(h_{i}\int_{K_{i}}\lvert v''(s) \rvert^{2}\text{ d}s \right)\int_{K_{i}}\text{ d}x\\
\text{Setting }h=\max_\limits{i}h_{i}\quad \qquad &\le h^{2} \sum\limits_{i}^{}\int_{K_{i}}\lvert v'' \rvert^{2}\text{ d}s\\
\lVert e' \rVert^{2}_{L^{2}(0,1)}&\le h^{2}\lVert v'' \rVert^{2}_{L^{2}(0,1)}\tag{1}
\end{align*}$$
So far we have computed $\lVert e' \rVert^{2}_{L^{2}(0,1)}$. 
Now we need to compute $\lVert e \rVert^{2}_{L^{2}(0,1)}$.
As before, we obtain
$$\lvert e(x) \rvert^{2}\stackrel{x\in K_{i}}{\le}h_{i}\int_{K_{i}}\lvert e'(s) \rvert^{2}\text{ d}s.$$
Using $(*)$:
$$\le h_{i}\left(h_{i}\int_{K_{i}}\lvert v'' \rvert^{2}\text{ d}s\right)\int_{K_{i}}\text{ d}x$$
$$\le h^{3}\int_{K_{i}}\lvert v''(s) \rvert^{2}\text{ d}s$$
$$\implies\quad \lVert e \rVert^{2}_{L^{2}(0,1)}=\sum\limits_{i}^{}\int_{K_{i}} \lvert e(s) \rvert^{2}\text{ d}s$$
$$\le \sum\limits_{i}^{}\left(h^{3}\int_{K_{i}}\lvert v''(s) \rvert^{2}\text{ d}s\right)\int_{K_{i}}\text{ d}x$$
$$\lVert e(x) \rVert^{2}_{L^{2}(0,1)}\le h^{4}\lVert v'' \rVert^{2}_{L^{2}(0,1)}\tag{2}$$
### Conclusion

$$\lVert v-I_{h}u \rVert_{L^{2}}+h\lVert (v-I_{h})' \rVert_{L^2} \stackrel{(1)+(2)}{\le}2h^{2}\lVert v'' \rVert_{L^2}$$
$$\begin{align*}
\tilde{E}_{h}(v)^{2}&= \lVert e \rVert^{2}_{H^{1}}=\lVert e \rVert^{2}_{L^{2}}+\lVert e' \rVert^{2}_{L^{2}}\\
	\tilde{E}_{h}(v)&\le 2h \lVert v'' \rVert_{L^{2}(0,1)}\tag{3}
\end{align*}$$
## Error bound and convergence for $\mathbb{P}_{1}$ FEM
Error in $H^{1}$:
$$\lVert u-u_{h} \rVert_{H^{1}}\stackrel{\text{Cea}}{\le } \frac{M}{\alpha }\inf_\limits{v_{h}\in X^{1}_{h}\cap H^{1}_{0}}\lVert u-v_{h} \rVert_{H^{1}}$$
$$\stackrel{I_{h}u\in X^{1}_{h}\cap H^{1}_{0}}{\le } \frac{M}{\alpha }\lVert u-I_{h}u \rVert_{H^{1}}$$
$$\stackrel{(3)}{\le} \frac{2M}{\alpha }\lVert u'' \rVert_{L^{2}(0,1)}\cdot h$$
**Remark 1**
* Last time: Example where we computed explicit $M, \alpha$.
* $\lVert u-u_{h} \rVert_{L^{2}}\le C \lVert v'' \rVert_{L^{2}(0,1)}h^{2}$.
* Second order method in $L^{2}$.
	  First order in $H^{1}$.
* $f \in  L^{2}\quad\implies\quad u \in H^{2}=\{f:\quad f,f',f'' \in L^{2} \}$
	in 1d: ok since $u_{xx}=f \in L^{2}$


