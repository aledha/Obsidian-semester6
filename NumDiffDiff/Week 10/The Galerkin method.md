All finite element methods are Galerkin.
PDE:
Find $u\in V \quad\text{s.t.}\quad$ 
$$a(u,v)=F(v)\quad\forall\quad v\in V \tag{P}$$
	Example $V=H^{1}_{0}(0,1)$ 

Now we want to approximate $u\in V$ by 
$u_{h}\in V_{h}\subset V, \quad dim(V_{h})=n$  (finite dimensional)
which solves
Find $u_{h}\in V_{h} \quad\text{s.t.}\quad$
$$a(u_{h},v_{h})=F(v_{h})\quad\forall\quad v_{h}\in V_{h}\tag{Ph}$$
This was cut off by recording:
	We want $\{V_{h} \}_{h>0}$ to approximate $V$:
	$\quad\forall\quad u\in V, \quad \exists \quad u_{h}\in V_{h}, \quad h>0 \quad\text{s.t.}\quad$
:(

If $V_{h}$ is a vector space with bases
$\phi_{1}(x),\ldots, \phi _{n}(x)$, then
$$u_{h}(x)=\sum\limits_{j=0}^{n}c_{j}\phi _{j}(x)$$
$$a(u_{h},v_{h})=\sum\limits_{j=1 }^{n}c_{j}a(\phi _{j},v_{h})$$
Then since $v_{h}\in \text{span}\{\phi _{i} \}_{i=1}^{n}$
(Ph) becomes
Find $c_{1},\ldots,c_{n} \quad\text{s.t.}\quad$ 
$$\sum\limits_{j=1 }^{n}a(\phi _{j},\phi _{i})c_{j}=F(\phi _{i}) \quad\forall\quad i=1,\ldots,n \tag{Ph}$$
$$\text{Finite dimension}\quad \Updownarrow \quad \text{Linear system}$$
$$A \vec{c}=\vec{F} \tag{1}$$
Where we call
	$A$: stiffness matrix
	$F:$ load vector

### Example 1: Spectral methods for 1d Poisson
$$-u_{xx}=f \quad \text{in } (0,1)$$
with B.C.s $u(0)=0=u(1)$
$V=H^{1}_{0}$,     $V_{h}=\text{span}\{\text{ sin}(i \pi x) \}_{i=1}^{n}, \quad h= \frac{1}{n}$
	Linear independant, orthogonal.
	$V_{h}$ forms an orthogonal basis
	$V_{h}\subset V=H_{0}^{1}(0,1)$ 
		Differentiable
		Sinuses satisfy the boundary conditions
	Computing $a(\phi _{j},\phi _{i})$:
	$$\begin{align*}
	a(\phi _{j},\phi _{i})&= \int_{0}^{1}\phi _{j}'\phi _{i}' \text{ d}x\\
	&=  \int_{0}^{1}j \pi \text{ cos}(j \pi x) i \pi \text{ cos}(i \pi x)\text{ d}x\\
	&= \begin{cases}
	j^{2}\pi ^{2} \cdot \frac{1}{2 \pi }  & \text{for }i=j\\
	0 & \text{else}
	\end{cases}
	\end{align*}$$
	And
	$F(\phi _{i})=\int_{0}^{1}f \phi_{i}\text{ d}x$
$$(P_{h})\quad\Leftrightarrow\quad c_{i}= \frac{2}{\pi ^{2}i^{2}}\int_{0}^{1}f \text{ sin}(i \pi x)\text{ d}x \quad\forall\quad i=1,\dots , n$$
Approx: $V_{h}\stackrel{h<<1}{≈} H_{0}^{1}(0,1)$
	Truncated Fourier series $≈$ Full Fourier series


### Example 2
A $\mathbb{P}_{1}$ FEM for 1d poisson
$V=H_{0}^{1}(0,1)$
$V_{h}=X^{1}_{h} \quad \text{with } 0 \text{ boundary conditions}$
Where $X^{1}_{h}=\{\text{pieciewise linear functions on subdivision } \tau _{h} \text{ of }(0,1) \}$
Need a more precise definition of $X_{h}^{1}$ and a basis to use $(1)$.

## The space $X_{h}^{1}(\Omega )$
We use now $\Omega =[0,1]$
#insert subdivision
![[Pasted image 20230308132750.png|700]]
Partition: $0=x_{0},x_{1}<\dots<x_{M}=1$
$h_{i}:= x_{i}-x_{i-1}$
Element: $K_{i}:=(x_{i-1},x_{i}), \quad i=1,\dots,M$
Subdivision/triangulation: $\tau _{h}=\{K_{i}  \}_{i=1}^{n}$
	Observation: $\overline{\left[\mathop{\cup}\limits_{K\in \tau _{h}}K\right]}=\overline \Omega$ 
	Meaning: the (closure of the) union of all subdivisions is equal to (the closure of) the whole space
Restriction of $v$ to $K$: $v|_{K}$
	$v|_{K}: K\to R \quad\text{s.t.}\quad v|_{K}=v \text{ on } K$ 
Space of piecewise polynomials of order 1 associated to $\tau _{h}$
	$$X_{h}^{1}=\{v\in C(\overline \Omega ): \quad v_{h}|_{K}\in \mathbb{P}_{1}\quad\forall\quad K\in \tau _{h} \}$$
	where $\mathbb{P}_{1}$ is the space of first order polynomials
	Note: $X_{h}^{1}$ is a vector space.
		$u_{h}+v_{h}\in X_{h}^{1}\quad\implies\quad au_{h}+bv_{h}\in X_{h}^{1}$

### Basis of $X_{h}^{1}$
#insert subdivision triangle hats
$$\phi _{i}(x)=\begin{cases} 
\frac{x-x_{i-1}}{h_{i}} & x\in[x_{i-1},x_{i}) \\
\frac{x_{i+1}-x}{h_{i+1}} & x\in (x_{i},x_{i+1}] \\
0 & \text{else}
\end{cases}$$
for $i=1,\dots M-1$
$$\phi _{0}(x)=\begin{cases}
\frac{x_{1}-x}{h_{1}} & x\in[0,x_{1}] \\
0 & \text{else}
\end{cases}$$
$$\phi _{M}(x)=\begin{cases}
\frac{x-x_{M-1}}{h_{M}} & x\in[x_{M-1},x_{M}] \\
0 & \text{else}
\end{cases}$$
#### Observation 1
$\phi _{j}(x_{i})=\begin{cases} 1 & i=j \\ 0 & i≠j\end{cases}$
and $\phi _{i}\ge0$,   and $\phi _{i}=0$  for $x\notin[x_{i-1},x_{i+1}]$ 
$\implies\quad \text{supp }\phi _{i}=\{\overline{x: \phi _{i}≠0}\}\subset [x_{i-1},x_{i+1}]$ 

### Lemma 1
$$v_{h}\in X_{h}^{1}\quad\Leftrightarrow\quad v_{h}=\sum\limits_{i=1}^{M}c_{i}\phi _{i}(x)$$
Where $c_{i}=v_{h}(x_{i})$.

Proof:
	Define $w_{h}(x):=\sum\limits_{i=1}^{M}v_{h}(x_{i})\phi _{i}(x)$
	Then
	$w_{h}(x_{k})=0+\dots+v_{h}(x_{k})\cdot 1+0=v_{h}(x_{k})\quad\forall\quad k$
	$\quad\implies\quad w_{h}(x)=v_{h}(x)\quad\forall\quad x\in[0,1]$ since both piecewise linear. $\square$ 

### Observation 2
* $X_{h}^{1}\subset H^{1}(\Omega )$     ($v_{h}$ bounded, $\in L^{2}$,   $\nabla v_{h}$ piecewise constant, $\in L^{2}$)
* $v_{h}\in X^{1}_{h}$,      $v_{h}(0)=0=v_{h}(1) \quad\implies\quad c_{0}=0=c_{M}$  
	* $\quad\implies\quad v_{h}\in H_{0}^{1}(\Omega )$

