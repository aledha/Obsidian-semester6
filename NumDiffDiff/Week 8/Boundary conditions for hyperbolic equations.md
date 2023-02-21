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