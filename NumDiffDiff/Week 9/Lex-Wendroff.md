For system
$$u_{t}+Au_{x}=f(x,t)\tag{1}$$
$$\vec{U}_{m}^{n+1}=\vec{U}_{m}^{n} - \frac{1}{2}p A \delta_{2h}\vec{U_{m}^{n}}+ \frac{1}{2}p^{2}A^{2} \delta_{x}^{2}\vec{U}_{m}^{n}$$
Where $p= \frac{k}{h}$
If $A=A(x,t) \quad\Rightarrow\quad$ use $A\to A_{m}^{n+1/2}$ in (LW)

Von Neumann stable if
$$U_{m}^{n}=G^{n}e^{i \beta x_{m}}U_{0}$$
solves (LW) with $\rho(G)\le1$
Check:
$$G\stackrel{(LW)}{=} I-ipA \text{ sin}(\beta h) + p^{2}A^{2}(\text{ cos}(\beta h)-1)$$
$$\Downarrow \lambda_{i},x_{i}\quad \text{eigen-pair for }A$$
$$\begin{align*}
Gx_{i}&= \left[1-ip \lambda_{i}\text{ sin}(\beta h) + p^{2}\lambda_{i}^{2}(\text{ cos}(\beta h)-1) \right]x_{i}\\
&= \lambda_{G,i}x_{i}
\end{align*}$$
BO p. 87:
$$|\lambda_{G,i}|=1-r_{i}^{2}(1-r_{i}^{2})\text{ sin}^{4}\left(\frac{\beta h}{2} \right)$$
Where $r_{i}=\lambda_{i}p$
Hence 
$$\rho(G)\le1 \quad\Leftarrow\quad r_{i}^{2}\le1\quad\forall\quad i$$
$$\Leftrightarrow\quad k\le \frac{h}{\min_\limits{i}|\lambda_{i}|}$$
Which is the CFL-condition.