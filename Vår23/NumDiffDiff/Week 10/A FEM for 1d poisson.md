$$u_{xx}=f \quad \text{in }(0,1)$$
$u(0)=0=u(1)$

The bilinear form is
$$a(u,v)=\int_{0}^{1}u_{x}v_{x}\text{ d}x$$
$$F(v)=\int_{0}^{1}fv \text{ d}x$$
$V=H_{0}^{1}(0,1)$
$V_{h}=\{v_{h}\in X^{1}_{h}: \quad v_{h}(0)=0=v_{h}(1) \}$

*Gelerkin formulation:*
Find $u_{h}\in V_{h}\quad\text{s.t.}\quad$
$$a(u_{h},v_{h})=F(v_{h})\quad\forall\quad v_{h}\in V_{h}$$
$$\text{see (1)}\quad \Updownarrow \quad u_{h}=\sum\limits_{}^{}c_{i}\phi _{i}$$
$$A \vec{c}=\vec{F}$$
#### Computin A
$$\{A \}_{ij}=a(\phi _{j},\phi _{i})=\int_{0}^{1}\phi _{i}'\phi _{j}'\text{ d}x$$
$$=\sum\limits_{K\in \tau _{h}}^{}\int_{K}\phi _{i}'\phi _{j}'\text{ d}x$$
$\phi _{i}$ piecewise linear $\quad\implies\quad \phi _{i}'$   pieciewise constant on (most) $K$ 

#### Computing $\vec{F}$
$$F_{i}=\int_{0}^{1}f \phi _{i}\text{ d}x=\dots$$
$$=\left(\int_{K_{i}}+\int_{K_{i+1}} \right)f \phi _{i}\text{ d}x$$
Where usually numerical quadrature is needed for the integration (not in this case though)

# $X^{1}_{h}$ in multi dimensions
Subdivision/triangulation of $\Omega$:
$$\tau _{h}=\{K_{j} \}_{j}\quad\text{s.t.}\quad \overline{\Omega }=\overline{\mathop{\cup}\limits_{K\in \tau_{h} } K}$$
![[Pasted image 20230425193418.png|300]] 

$N_{h}=\{x_{i} \}_{i}$ :  the vertex points
$$X_{h}^{1}=\{v_{h}\in C(\overline{\Omega }):\quad v_{h}|_{K}\in \mathbb{P}_{1} \}$$

Basis functions: one per vertex $x_{i}$
![[Pasted image 20230425193438.png|300]]

### Observation 2
$\phi _{i}(x_{j})=\delta _{ij}$
$\phi _{i}=0$ outside of neighborhood around $x_{i}$.