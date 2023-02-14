Last topic: [[Self-adjoint problems]]
## Rectangular grid
![[Pasted image 20230214225940.png]]
Stencil:
![[Pasted image 20230214230006.png|500]]
Notation:
$$h_{Q}=|\vec{PQ}|\quad\forall\quad Q=E,S,N,W$$
Reduced order: (han skrev ikke faktisk some step, han skrev bare siste linje)
$$\begin{align*}
\partial_{y}(c \partial_{y}u_{P})&≈ \frac{1}{\text{some step}}\delta_{y}\left(c \frac{1}{\text{some step}}\delta_{y}u_{P}\right)\\
&= \frac{1}{\text{some step}} \delta_{y}\left(c \frac{1}{\frac{h_{N}}{2}+ \frac{h_{S}}{2}}(u_{N'}-u_{S'})\right)\\
&=\frac{1}{\frac{h_{N}+h_{S}}{2}} \cdot\frac{1}{\text{some step}}\delta_{y}(cu_{N'}-cu_{S'})\\
&= \frac{1}{\frac{h_{N}+h_{S}}{2}}\cdot \left[\frac{1}{h_{N}}(c_{N'}u_{N}- c_{S'}u_{P})- \frac{1}{h_{S}}(c_{N'}u_{P}-c_{S'}u_{S})\right]
\end{align*}$$
$$\partial_{y}(c \partial_{y}u_{P})= \frac{1}{\frac{h_{N}+h_{S}}{2}} \left(c_{N'} \frac{u_{N}-u_{P}}{h_{N}}-c_{S'} \frac{u_{P}-u_{S}}{h_{S}} \right)+O(h)$$
Where 
$$O(h)=O \left(\max_{Q=N,S}h_{Q} \right)$$(E,W) is ommited since we are looking in the y direction 
Irregular step size -> first order.

Next topic: [[Irregular grid]]