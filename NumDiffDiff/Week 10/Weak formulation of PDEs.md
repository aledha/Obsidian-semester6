## 1 dimension
1d poisson equation
$$-u_{xx}=f \qquad \text{in }(0,1)\tag{1}$$
with $u(0)=0=u(1)$.

$$\cdot v \text{  (smooth)} \qquad \Downarrow\qquad \int_{0}^{1}\text{ d}x$$

$$\int_{0}^{1}(-u_{xx})v \text{ d}x=\int_{0}^{1}fv \text{ d}x$$
Using integration by parts
$$\left[-u_{x}v \right]_{0}^{1}-\int_{0}^{1}(-u_{x})v_{x}\text{ d}x=\int_{0}^{1}fv \text{ d}x$$
$$\Updownarrow \quad \text{choosing  }v(0)=0=v(1)$$
$$\int_{0}^{1}u_{x}v_{x} \text{ d}x=\int_{0}^{1}fv \text{ d}x \tag{1}$$
### Observation 1
* $(2)$ is well-defined if the functions $u_{x}, v_{x},v,f\in L^{2}(0,1)$
	* i.e. $u,v\in H^{1}(0,1) =\{g:\quad g,g_{x}\in L^{2} \}$
	* (not $u\in C^{2}$)
* If $u\in C^{2}(0,1)\cap C(0,1]\cap H^{1}(0,1)$
  solves (1)
	* $\quad\Rightarrow\quad$ $u$ solves (2) $\quad\forall\quad v\in H^{1}_{0}(0,1)$
Where $H_{0}^{1}(0,1)=\{f\in H^{1}(0,1):f(0)=0=f(1) \}$

## Definion: Weak solution
$u\in H^{1}_{0}(0,1)$ is a *weak solution* of $(1)$ if
$$\int_{0}^{1}u_{x}v_{x}\text{ d}x=\int_{0}^{1}fv \text{ d}x \quad\forall\quad v\in H^{1}_{0}(0,1)\tag{3}$$
### Remark
* A classical solution is a weak solution (from observation 1, part 2)