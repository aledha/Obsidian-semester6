### Detour: plane waves
$$u(x,t)=e^{i(\omega t+ \beta x)}$$
Where $\omega$ is the angular frequency, $\omega=2\pi f$,    where $f$ is the frequency
And $\beta$ is the wave number. $\beta=\frac{2\pi}{\lambda}$,   where $\lambda$ is the wavelength

Wave speed: 
$v=\lambda \cdot f= \frac{\omega}{\beta}$ 

## Dispersion
$v=v(\beta)= \frac{\omega(\beta)}{\beta}$ 
Which is not constant $\quad\Rightarrow\quad$ waves of different lengths have different speeds.

## Dissipation
Damped plane wave:
$$u(x,t)= e^{-Dt} e^{i(\omega t + \beta x)}$$
This is *dissipative* if $D>0$
(wave loses amplitude $\quad\Leftrightarrow\quad$ $\int_{0}^{1}u^{2}(x,t)\text{ d}x \stackrel{t\to \infty}{\to} 0$)

## General wave solution
=superposition of damped plane waves
$$u(x,t)=\sum\limits_{k=-\infty}^{\infty}a_{k}e^{-D_{k}t}e^{i(\omega_{k} t + k x)}$$
or on the whole line:
$$u(x,t)=\int a_{\beta}e^{D_{\beta}t}e^{i(\omega_{\beta} t + \beta x)} \text{ d}\beta$$

### Example 1
Heat equation with a transport term
$$u_{t}+au_{x}=c^{2}u_{xx}$$
$$\Downarrow \quad u=e^{-Dt}e^{i(\omega t + \beta x)}$$
$$(-D+i \omega)u+a (i \beta)u =c^{2}(-\beta^{2})u$$
$$\Downarrow$$
$$\begin{cases}
\text{Real part} & -D=-c^{2}\beta^{2} \\
\text{Imaginary}  & \omega+a \beta=0
\end{cases}$$
Dissaptive since $D=c^{2}\beta^{2}<0$
Non-dispersive: $v=\frac{\omega}{\beta}=-a=\text{const}$

### Example 2
$$u_{t}+au_{x}+bu_{xxx}=0$$
$$\Downarrow \qquad u=e^{-Dt}e^{i(\omega t + \beta x)}$$
$$\begin{cases}
\text{Real} & & -D=0 \\
\text{Imaginary} &  & \omega+a \beta-b \beta^{3}=0
\end{cases}$$
Non-dissipative:  $D=0$
Dispersive: $v=\frac{\omega}{\beta}=-a+b \beta^{2}$

# In numerical schemes
Damped plane wave
$$U_{m}^{n}= \rho^{n}e^{i(\omega t_{n} + \beta x_{m})},\qquad \rho\ge0$$
Where $t_{n}=nk,\quad x_{m}=mh$
## Remark 1
$$U_{m}^{n}=\xi^{n}e^{i \beta x_{m}}$$$\qquad \text{with }\xi=\rho e^{i \omega k}$      (polar form)
Von Neumann stable if $|\xi|=\rho\le1$

_Dissipative_ for numerical solution if $\rho<1$
*Dissipative of order $s$* 
	if there is $k_{0}>0, \quad \sigma>0 \quad\text{s.t.}\quad$
	$$\rho\le1-\sigma(\beta h)^{2s}\qquad\text{for }k\le k_{0}, \quad |\beta h|\le \pi$$
	Interpretation: how much lower than 1 for one wavelength
*Dispersive* if $v= \frac{\omega(\beta)}{\beta}$ not constant.

### Example 3: Upwind
$$U_{m}^{n+1}=U_{m}^{n}-r(U_{m}^{n}-U_{m-1}^{n})$$
Where $r=\text{const}\ge0$
$$U_{m}^{n}= \rho^{n}e^{i(\omega t_{n} + \beta x_{m})}\quad \Downarrow \quad  \text{divide by common factor}$$
$$\rho e^{i\omega k}=1-r(1- e^{-i \beta h})$$
$$\begin{align*}
&= 1-r(1-\text{ cos}(\beta h))- ir \text{ sin}(\beta h)\\
&= \text{Re } + \text{ Im}\\
\rho^{2}&= \text{Re}^{2} + \text{ Im}^{2}\\
&= \dots\\
&= 1-4r(1-r)\text{ sin}^{2}\left(\frac{\beta h}{2} \right)
\end{align*}$$
Where the dots represent completing the squares and lots of trig identities.
$$\Downarrow \qquad \text{ sin}^{2}\left(\frac{\beta h}{2} \right)\ge0$$

*Dissipative*: when       $\rho\le1 \qquad \text{when } r<1$
*Dissipative of order $s$*:

For $|\beta h|\le \pi$:
	$\text{ sin}^{2}( \frac{\beta h}{2})\ge \frac{1}{6}(\frac{\beta h}{2})^{2}$
	"Proof by sketch"
	#scetch
	$\rho^{2}\le 1- \frac{1}{6}r(1-r)(\beta h)^{2}$
Another inequality:
$$\sqrt{1-x}\le1- \frac{x}{2}$$
#### Miniproof
$$1-x\le 1-x+ \frac{x^{2}}{4}=\left(1- \frac{x}{2}\right)^{2}$$
So we get
$$\rho\le 1- \frac{1}{12}r(1-r)(\beta h)^{2}$$
Hence, when $r\le1 \quad\Rightarrow\quad$ dissipation of order $s=1$
	look at exponent

Also *dispersive*: 
$$\omega k=\text{arg}(\text{Re}+i \text{ Im})=\text{arctan } \frac{\text{Im}}{\text{Re}}$$
This is not linear in $\beta h$
$\Rightarrow\quad \frac{\omega}{\beta}$ is not linear in $\beta$.

Point being that the transport equation is not dispersive or dissapative, while our discretisation *is*
