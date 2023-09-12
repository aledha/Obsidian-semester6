$$\begin{cases}
u_{t}+au_{x}=0  & \quad \text{in }(0,1)\times(0,\infty) \\
u(x,0)=u_{0}(x) \\
u(0,t)=g(t)\tag{P}
\end{cases}$$
Where $a>0$
# Explicit schemes

## Lax-Friedrich
Central space 
$$\begin{align*}
\frac{1}{k}\Delta_{t}U_{m}^{n}+a \frac{1}{2h}\delta_{2h}U_{m}^{n}&=  0\\
\frac{1}{k}(U_{m}^{n+1}-U_{m}^{n})+ \frac{a}{2h} (U_{m+1}^{n}-U_{m-1}^{n})&= 0\\
r=a \frac{k}{h}\quad\Rightarrow\quad U_{m}^{n+1}=U_{m}^{n}- \frac{r}{2}(U_{m+1}^{n}-U_{m-1}^{n})
\end{align*}$$
Now using central space on $U_{m}^{n}≈ \frac{1}{2}(U_{m+1}^{n}+U_{m-1}^{n})$:
$$\begin{align*}
U_{m}^{n+1} &=  \frac{1}{2}(U_{m+1}^{n}-U_{m-1}^{n})- \frac{r}{2}(U_{m+1}^{n}-U_{m-1}^{n})\\
U_{m}^{n+1}&= \frac{1-r}{2}(U_{m+1}^{n}-U_{m-1}^{n})\\
\end{align*}$$
### Truncation error
$$\tau_{m}^{n}= \frac{1}{2}k u_{tt}(x_{m},\xi_{n})+ \frac{1}{6}h^{2}u_{xxx}(\tilde{\eta}_{m},t_{n}) + \frac{1}{2} \frac{h^{2}}{k}u_{xx}(\eta_{m},t_{n})$$
Conditional *consistent*: need $\frac{h^{2}}{k}\to0$

<u>Positive coefficients</u> if $1-|r|\ge0$ 
	CFL condition: $|r|\le1 \quad\Leftrightarrow\quad k\le \frac{h}{|a|}$

<u>Von Neumann stable</u> if $|r|\le1$
$$\begin{align*}
U_{m}^{n}&= \xi^{n}e^{i \beta x_{m}}\\
\text{chk}\quad\Rightarrow\quad \xi&= \text{ cos}\beta h+ir \text{ sin}\beta h\\
|\xi|^{2}&= 1+(r^{2}-1)\text{ sin}\beta h
\end{align*}$$
So $|\xi |\le1\quad\Leftrightarrow\quad r^{2}\le1$
