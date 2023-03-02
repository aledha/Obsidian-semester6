Transport equation:
$$u_{t}+au_{x}=0, \qquad a>0$$
## Implicit upwinding
$$U_{m}^{n+1}=U_{m}^{n}-r(U_{m}^{n+1}-U_{m-1}^{n+1}) \tag{IU}$$
Where $r=a \frac{k}{h}$

Stencil: (Where the circled point is $n+1,m$)
![[Pasted image 20230302122518.png]]
$\tau_{m}^{n}=\mathcal{O}(h+k)$ and positive coefficients when $a>0$. 
Respects inflow boundary conditions.

## Wendroff
$$U_{m+1}^{n+1}+\gamma U_{m}^{n+1}=\gamma U_{m+1}^{n}+U_{m}^{n}\tag{W}$$
Where $\gamma= \frac{1-r}{1+r}$
Want to calculate the value at $n+1,m+1$
![[Pasted image 20230302122808.png|700]]
$\mathcal{O}(h^{2}+k^{2})$, not positive coefficients.
Unconditionally von Neumann stable.
Respects the inflow boundary conditions.