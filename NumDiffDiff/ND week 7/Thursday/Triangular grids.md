Insert

$$-\int_{K_{P}}\mathcal{L}u \quad \text{d}x \text{d}y \stackrel{DT}{=}-\sum\limits_{i=1}^{s}\int_{\gamma_{i}}a \partial_{n} u \quad \text{d}s=\int_{K_{P}}f \quad \text{d}x \text{d}y$$
FDM/FVM:

$$\sum\limits_{i=1}^{s} a_{Q_{i}} \frac{l_{i}}{h_{i}A_{P}}(U_{Q_{i}}- U_{P})=f_{P}\quad \text{in }\mathbb{G}$$
## Remark 4
1. Complicated, but used.
2. Alternative: FEM.
	1. Not conservative


$$\begin{cases}
\mathcal{L}u=f & \text{in } \Omega \\
u=g  & \text{on } \partial \Omega
\end{cases}$$
Use $v=u-g$
$$\begin{cases}
\mathcal{L}v=f-\mathcal{L}g & \text{in } \Omega \\
v=0  & \text{on } \partial \Omega
\end{cases}$$
