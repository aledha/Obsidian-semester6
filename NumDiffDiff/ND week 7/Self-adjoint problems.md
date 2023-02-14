* Last topic: [[Neumann, Robin, mixed BCs]]

$$-Lu=f \qquad Lu = \partial_{x}(a \partial_{x}u)+\partial_{y}(c \partial_{y} u)$$
![[Pasted image 20230214225902.png|400]]. 
We have P, N, W, S, E. Introduce midpoints W', N', E', S'
More notation:
$$Q'=P+ \frac{1}{2}\vec{PQ} \quad\forall\quad Q=N,E,S,W$$
Consider the stencil above and do a central difference approximation:
$$\begin{align*}
\partial_{y}(c \partial_{y}u)&=  \frac{1}{h^{2}}\delta_{y}(c \delta_{y}u)\\
&= \frac{1}{h^{2}}\left( \delta_{y}c \left({u_{N'}-u_{S'}}\right) \right)\\
&= \frac{1}{h^{2}}\left(\delta_{y}cu_{N'} -\delta_{y}cu_{S'}\right)\\
&= \frac{1}{h^{2}}((c_{N'}u_{N}-c_{S'}u_{P}) -(c_{N'}u_{P}-c_{S'}u_{S}))\\
&=  \frac{1}{h^{2}}\left(c_{N'}(u_{N}-u_{P})-c_{S'}(u_{P}-u_{S})) \right)
\end{align*}$$
Han hoppet over de tre midterste linjene over:( 

Not a part of the lecture, but here is the [[Defintion of self-adjoint problems]]


* Next time: [[Variable step size]]