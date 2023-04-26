## Rectangular domain
Ex: $\vec{n}=-\vec{e}_{x}$

i.
$$\frac{\partial u_{p}}{\partial n}=-\partial_{{x}}u_{p}= -\frac{u_{E}-u_{P}}{h} + O(h )$$
Never use this since this is first order. Rather, we should use
(ii) Fictitious node
$$\frac{\partial u_{p}}{\partial n}=-\partial_{{x}}u_{p}=- \frac{u_{E}-u_{W}}{2h}+O(h^{2})+\text{ FDM at P}$$
## Irregular domain
Notation: $d(P,Q)=d$  and  $d(Q,S)=h'$  and  $d(P,S)=k'$. 
(insert picture)
### (i)
$$\frac{\partial u_{p}}{\partial n}= \frac{u_{P}-u_{Q}}{d}+O(d)$$
where 
$$u_{Q}=u_{R} \frac{h'}{h}+u_{S}\left(1- \frac{h'}{h}\right)+O(h^{2})$$
^ is linear interpolation of Q between the points R and S: $O(d+ \frac{h^{2}}{d})$ method
### (ii) Complicated..

* Next topic: [[Self-adjoint problems]]