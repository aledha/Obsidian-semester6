Only boundary conditions at **inflow** boundaries!
(No conditions at **outflow**!)

What is inflow?
	Where $x$-characteristic curves go **into** domain.
What is outflow?
	Not inflow (duh)

## Example 6
$$u_{t}+au_{x}=0\quad \text{in}\quad (0,1)$$
$$u(x,0)=u_{0}(x),\qquad a>0$$
With boundary conditions.
x-characterstics:
$$x(t) \stackrel{\text{example 5}}{=}x_{0}+a(t-t_{0})$$
(insert sylinder)

Then the boundary conditions becomes:
$$\begin{align*}
u(0,t)&= g_{0}(t)\\
\end{align*}$$
No condition at x=1
Characteristics starting from $x=0$:
$$x(t)=a(t-t_{0}) \quad\Rightarrow\quad t_{0}=t- \frac{x}{a}$$
$$z(t) \stackrel{\text{Ex. 5}}{=}u(x_{0},t_{0}) \stackrel{x_{0}=0}{=}g_{0}(t_{0})$$
$$\Rightarrow\quad u(x,t)=z=g_{0}\left(t- \frac{x}{a}\right)$$
Characteristics starting from $t=0$:
$$\text{Example 5} \quad\Rightarrow\quad u(x,t)=u_{0}(x-at)$$
Solution:
(insert)

Need to have starting points on a large curve such that the solution fills the whole space.
Think: tube of water.
	Cannot impose conditions on what goes out. Can control what goes in.

### Example 1
$a>0, b\ge0$
$$\vec{u}_{t}+\begin{pmatrix}a & b \\ b & a\end{pmatrix}\vec{u_{x}}=\vec{0}\quad \text{in}\quad (0,1)\times(0,T)\tag{1}$$
Observation: eigenvalues are $\lambda_{\pm}=a\pm b\in\mathbb{R} \quad\Rightarrow\quad$ hyperbolic!
Diagonalise:
$$\begin{align*}
A&= P \Lambda P^{T}\\
P= P^{T}&= \frac{1}{\sqrt{2}}\begin{pmatrix}1 & 1 \\
1 & -1 \end{pmatrix}
\end{align*}$$
$\vec{v}=P^{T}\vec{u}$    satisfies
$$\vec{v}+\begin{pmatrix}a+b & 0 \\ 0 & a-b\end{pmatrix}\vec{v_x}=\vec{0}\tag{2}$$
#### Charcteristic equations: 
($\lambda_{1}=\lambda_{+}=a+b,\quad \lambda_{2}=\lambda_{-}=a-b$) 
$$v_{t}^{i}+\lambda_{i}v^{i}_{x}=0 \quad\Rightarrow\quad \dot{x_{i}}=\lambda_{i}\quad\text{for }i=1,2$$
(decoupled)

#### Boundary conditions for $v_{i}$:
$x=0$: 
inflow when $\lambda_{i}>0$
(insert)

$x=1$:
inflow when $\lambda_{i}<0$
(insert)

3 cases ($a>b,\quad a<b, \quad a=b$)
	(i) $\lambda_{1},\lambda_{2}>0 \quad\Rightarrow\quad$
		$v_{1},v_{2} \text{ B.C. at } x=0$
	(ii) $\lambda_{1}>0,\lambda_{2}<0 \quad\Rightarrow\quad v_{1} \text{ BC at } x=0$
		$v_{2}$ B.C at $x= 1$
	(iii) $\lambda_{1}>0,\lambda_{2}=0$
		$v_{1}$ BC at $x=0$
		$v_{2}$ no BC!

##### Case (i):
(insert)
Boundary conditions,  $\vec{v_{0}}=\vec{g_{0}}$$\quad\Leftrightarrow\quad \vec{u}(0)=P \vec{g_{0}}$
**or** $\vec{u}(0)= \vec{\phi_{0}}\quad\Leftrightarrow\quad \vec{v}(0)=P^{T}\vec{\phi_{0}}$
Can choose $\vec\phi_{0}$ freely

##### Case (ii):
(insert)
Bondary conditions:
$v_{1}=g_{0}\quad \vec v_{2}(1)=\vec g_{1}$
Using $\vec{u}=P^{T}\vec{v}$:

$$1/\sqrt{2} (u_1 +u_2)(0)=g_0, \quad 1/\sqrt{2}(u_1 -u_2)(1)=g_1$$
BC at both sides, must satisfy (3)



