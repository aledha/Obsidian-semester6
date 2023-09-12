Last topic: [[Variable step size]]
	potato
![[Pasted image 20230214230139.png|300]]

$$\overline{\mathbb{G}}=(P)=(x_{i},y_{j})= \mathbb{G}\cup \partial\mathbb{G}$$
$$-\mathcal{L} u =-au_{xx}-2bu_{xy}-cu_{yy}-du_{x}-eu_{y}-lu=f \quad \quad \text{in } \Omega\tag{P}$$
### FDM in $P\in \mathbb{G}:$
	Method of undetermined coefficients

#### Choose a stencil for every point:
	s neighbors

![[Pasted image 20230214230205.png]]
Now all neighbors are in random directions. When we choose an $h$, we choose a radius of which points are included as neighbors.
$$Q_{i}=P+h(\xi_{i}, \eta_{i})\in\overline{\mathbb G}$$
where $h>0$ is the step size. $\xi_{i}, \eta_{i}\in[0,1]$.  
$(\xi_{i}, \eta_i)$ is a vector
![[Pasted image 20230214230237.png]]
Now we can write a 

##### **Difference approximation of $\mathcal{L}$**
$$-\mathcal{L}_{h}U_{P}= \alpha_{PP}U_{P}- \sum\limits_{i=1}^{s}\alpha_{PQ _{i}}U_{Q_{i}}$$
Want this to be an approx of (P).
**Taylor:**
$$-\mathcal{L}_{h}u_{P}=\alpha_{PP}u_{P}-\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}u(P+h(\xi_{i},\eta_{i}))$$
$$=\alpha_{PP}u_{P}-\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\left(u_{P}+ h(\xi_{i}u_{x}+\eta_{i}u_{y})_{P} + \frac{1}{2}h^{2}(\xi_{i}^{2}u_{xx}+2\eta_{i}\xi_{i}u_{xy}+\eta_{i}^{2}u_{yy})_{P}\right)+ O(h^{3})\tag{*}$$

### System of equations for irregular grids
To have $\mathcal{L}_{h}u_{P}=\mathcal{L}u_{P}+ O(h^{r})$ need $r$ of the following equations to be true:
(1) Coefficients for $h^{0}u_{P}$ in $(*)$ = Coeffs in (P)
$$\alpha_{PP}-\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}=-l_{P}$$
(2) $h^{1}u_{x}$:
$$-h \sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\xi_{i}=-d_{P}$$
(3) $h^{1}u_{y}$:
$$-h\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\eta_{i})=-e_{P}$$
(4) $h^{2}u_{xx}$
$$- \frac{h^{2}}{2}\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\xi_{i}^{2}=-a_{P}$$
(5) $h^{2}u_{xy}$ 
$$-h^{2}\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\xi_{i}\eta_{i}=-2b_{P}$$
(6) $h^{2}u_{yy}$
$$- \frac{h^{2}}{2}\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\eta_{i}^{2}= -c_{P}$$
Solving these equations for the different $\alpha$
$$-\mathcal{L}_{h}U_{P}=f_{P} \quad \text{in }\mathbb{G} \tag{Ph}$$
If BCs are implemented $\Rightarrow\quad A \vec{U}=\vec{c}$

#### Remarks
1. 6 equations, need  6 $\alpha$'s $\Rightarrow\quad s\ge 5$  (larger stencil than before)
2. $s=5 \quad\Rightarrow\quad O(h^{1})$     (unless $\mathbb{G}$ is symmetric)
3. $O(h^{r}), \quad r\ge1 \quad\Rightarrow\quad s>5$  and you will need more equations:
$$\sum\limits_{i=1}^{s}\alpha_{PQ_{i}}\xi_{i}^{l}\eta_{i}^{q-l}=0 \quad$$
$$\text{for}\quad q=3,\dots,r+2i \quad \text{and } l=0,\dots,q$$
4. $A$ sparse, invertible  $\quad\Leftrightarrow\quad A$ weakly chained diagonally dominant.

### Example 1. Beehive grid, Poisson
	Hexagonal grid: Angles 120 degrees. Three points stencil

![[Pasted image 20230214230405.png|300]]
Poisson equation:
$$-\mathcal{L}u=-u_{xx}-u_{yy}=f$$
Stencil:
![[Pasted image 20230214230515.png|300]]
Geometry:
$$\begin{align*}
Q_{1}&= P+h(1,0)\\
Q_{2}&= P + h\left(- \frac{1}{2}, - \frac{1}{2}\sqrt{3}\right)\\
Q_{3}&= P+h(- \frac{1}{2}, \frac{1}{2}\sqrt{3})
\end{align*}$$
$$-\mathcal{L}_{h}u_{P}= \alpha_{0}u_{P}-\sum\limits_{i=1}^{3}\alpha_{i}u_{Q_{i}}$$
(Where we write $\alpha_{0}=\alpha_{PP}$ and $\alpha_{i}=\alpha_{PQ_{i}}$ for simplicty)
$$=-\mathcal{L}u_{P}-\tau_{P}$$
Systems of eq to satisfy error. Using the [[#System of equations for irregular grids|system of equations]] above: (chk.)
1. No $u$ terms:
$$\alpha_{0}-\alpha_{1}-\alpha_{2}-\alpha_{3}=0$$
2. $u_{x}$
   $$-\alpha_{1}+ \frac{1}{2}\alpha_{2}+ \frac{1}{2}\alpha_{3}=0$$
3. $u_{y}$
$$\frac{1}{2}\sqrt{3}\alpha_{2}- \frac{1}{2}\sqrt{3} \alpha_{3}=0$$
4. $u_{xx}$
$$-\alpha_{1}- \frac{1}{4}\alpha_{2}- \frac{1}{4}\alpha_{3}=- \frac{2}{h^{2}}$$
Solving the system we get
$$\begin{align*}
\alpha_{0}&= \frac{4}{h^{2}}\\
\alpha_{1}&= \frac{4}{3h^{2}}\\
\alpha_{2}=\alpha_{3}&= \alpha_{1}
\end{align*}$$
$$-\mathcal{L}_{h}u_{P}= \frac{1}{h^{2}}\left(4u_{P}- \frac{4}{3}(u_{Q_{1}}+ u_{Q_{2}}+ u_{Q_{3}})\right)=-\mathcal{L}u_{P}+O(h)$$

