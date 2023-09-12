![[Pasted image 20230216163519.png|700]]
![[Pasted image 20230216163537.png|700]]

$$\begin{align*}
\int_{K_{p}} f \quad \text{d}x \text{d}y &\stackrel{A=aI}{=}-\int_{\partial K_{P}}a \frac{\partial u}{\partial n} \quad \text{d}s\\
&= -\sum\limits_{Q=E,N,S,W}\oint_{\gamma_{Q}}a \frac{\partial u}{\partial n} \quad \text{d}s
\end{align*}$$
Approximate: (using central difference approximation on curve going through $N'$)
$$\oint_{\gamma_{N}}a\frac{\partial u}{\partial n} \quad \text{d}s ≈ a_{N'} \frac{u_{N}-u_{P}}{h_{N}} \cdot \frac{h_{E}+h_{W}}{2}$$
where the last term is the length of the boundary. $\text{length}(\gamma_{N})=:l_{N} \quad \quad (=l_{S})$
$$\int_{\gamma_{E}}\dots \text{d}s ≈ a_{E'} \frac{u_{E}-u_{P}}{h_{E}}\cdot \frac{h_{N}+h_{S}}{2} $$
$\frac{h_{N}+h_{S}}{2}=:l_{E}\quad \quad (=l_{W})$
$$\vdots$$
$$\int_{K_{P}}f \quad \text{d}x \text{d}y≈ f_{P} \cdot \frac{h_{E}+h_{W}}{2}\cdot \frac{h_{S}+h_{N}}{2}=:f_{P}A_{P}$$
Where we define $A_{P}$ as the area of $K_{P}$.

**End result:**
$$-\sum\limits_{Q=N,S,E,W}a_{Q'} \frac{l_{Q}}{A_{P}h_{Q}}(U_{Q}-U_{P})=f_{P} \quad \quad \text{in }\mathbb{G}$$
$$\quad\Leftrightarrow\quad \alpha_{PP}U_{P}-\sum\limits_{Q=N,S,E,W}\alpha_{PQ}U_{Q}-f_{P} \qquad \text{in }\mathbb{G}$$
Where 
$$\alpha_{PQ}=a_{Q'} \frac{l_{Q}}{A_{P}h_{Q }} \quad , \qquad \alpha_{PP}= \sum\limits_{Q=N,S,E,W} \alpha_{PQ}$$

### Remark 3
1. Posetive coefficients! DMP! Conservative! 
	1. Check
2. Central difference approximation
	1. $O(h^{2})$ in interior
3. Neumann B.C.s or other 
	1. Need equations for $U_{P}, \quad p\in \partial\mathbb{G}$
	2. See figure:
![[Pasted image 20230216163606.png|400]]

$$\partial_{n}u+\alpha u=g \quad \text{in } \partial \Omega$$
$$\begin{align*}
\int_{\gamma_{1}}a \partial_{n} u \quad \text{d}y&=  \int_{\gamma_{1}}a(g-\alpha u)\quad \text{d}s\\
&≈ l_{1}a_{P}(g_{P}-\alpha_{P}u_{P})
\end{align*}$$
$$-l_{1}a_{P}(g_{P}-\alpha_{P}u_{P})-\sum\limits_{i=2 }^{4}a_{Q_{i}} \frac{l_{i}}{h_{i}}(U_{Q_{i}}-U_{P})=f_{P}\cdot A_{P,E}$$
Where the sum are the other boundaries