Model problem (a>0)
$$\begin{cases}
u_t+au_x=0 & \text{in }(0,1)\times(0,T) \\
u(x,0)=u_0(x)  & \text{IC}\\
u(0,t)= g(t) & \text{inflow B.C}
\end{cases}$$
Solution from last time
$$u(x,t) = \begin{cases}
u_0 (x-at) & x\ge at \\
g(t-x/a) & x<at 
\end{cases}$$
### Hyperbolic maximum principle
$$u_t+au_x\le0 \quad (0,1)\times (0,T)$$
$$\Rightarrow \quad \max_\limits{(0,1)\times(0,T)} u(x,t)\le \max_\limits{x=0\text{ or }t=0} u(x,t)$$
LHS is $\Omega$, RHS is $\partial \Omega$ 

### Positive coefficient schemes
satisfies hyperbolic discrete maximum principle:
$-\mathcal{L}_{h}U_{p}\le0\quad \text{in }\mathbb{G}$
$\quad\Rightarrow\quad \max_\limits{P\in \overline{\mathbb{G}}}U_{P}\le \max_\limits{P\in \partial_{\text{in}} \mathbb{G}}(0,U_{P})$
Where $\partial_{\text{in}}$ denotes inflow nodes

### Error analysis
As for parabolic problems.
1. Consistency, stability, error equation
	$\quad\Rightarrow\quad ||\vec{e_{h}}||_{\infty}\le C||\vec{\tau_{h}}||_{\infty}$
2. Stability: positive coefficients, DMP, supersolution

## Numerical schemes
$a>0$,  $r=a \frac{k}{h}$

### (a) Forward difference in space
$$\frac{1}{k}\Delta_{t}U_{M}^{n}+a \frac{1}{h}\Delta_{x}U_{m}^{n}=0$$
$$U^{n+1}_{m}-U^{n}_{m}+a \frac{k}{h}(U_{m+1}^{n}-U_{m}^{n})=0\tag{FS}$$
$$U^{n+1}_{m}-(1+r)U_{m}^{n}+rU_{m+1}^{n}=:-\mathcal{L}_{h}U_{m}^{n+1}=0$$
Does not have positive coefficients since $r>0$
### (b) Backward differences in space
$$U_{m}^{n+1}-U_{m}^{n}+r(U_{m}^{n}-U_{m-1}^{n})=0\tag{BS}$$
Positive coefficient form:
$$U_{m}^{n+1}-(1-r)U_{m}^{n}-rU_{m-1}^{n}=:-\mathcal{L}_{h}U_{m}^{n+1}=0$$
### (c) Central difference in space
$$U_{m}^{n+1}-U_{m}^{n}+ \frac{r}{2}(U_{m+1}^{n}-U_{m-1}^{n})=0\tag{CS}$$
Positive coefficient form
$$U_{m}^{n01}-U_{m}^{n}+ \frac{r}{2}U_{m+1}^{n}- \frac{r}{2}U_{m-1}^{n}=: \mathcal{L}_{h}U_{m}^{n+1}=0$$
### (d) Upwind scheme 
(ok for any coefficient $a\in \mathbb{R}$)
$$U_{m}^{n+1}-Um ^{n}+ r^{+}(U_{m}^{n}-U_{m-1}^{n})-r^{-}(U_{m+1}^{n}-U_{m}^{n})=0 \tag{UW}$$
$$U_{m}^{n+1}-(1-r^{+}+r^{-})U_{m}^{n}-r^{+}U_{m-1}^{n}-r^{-}U_{m+1}^{n}:=-\mathcal{L}_{h}U_{m}^{n+1}=0$$
Where 
$$r^{+}=\max_\limits{}(0,r)\qquad r^{-}=(-r)^{+}$$
Note:
$$r=r^{+}-r^{-} \qquad |r|=r^{+}+r^{-}$$

#### Observation
$$au_{x}=a^{+} \frac{1}{h}\nabla _{h}u-a^{-} \frac{1}{h}\Delta_{h}u+\mathcal{O}(h)$$
If $a>0$ then (UW) = (BS)

## Consistent schemes
(FS), (BS), (UW) have
$$\tau_{m}^{n}=\mathcal{O}(h+k)$$
(CS):
$$\tau_{m}^{n}=\mathcal{O}(h^{2}+k)$$

## Positive coeffiecients
Never (FS), (CS)
For (BS), (UW):
	Conditionial when $1-|r|\ge 0$.  CFL condition


## CFL conditions
Conditions to have positive coefficients or von Neumann stability

## Von Neumann stability
For this problem: same as for positive coefficients.

$$U_{m}^{n}=\xi^{n}e^{i \beta x_{m}}\qquad \beta\in \mathbb{R},\quad  x_{m}=m \cdot h$$
Inserted in (FS)
$$\xi^{n+1}e^{i \beta x_{m}}=\xi^{n}e^{i \beta x_{m}}-r(\xi^{n}e^{i \beta x_{m+1}}-\xi^{n}e^{i \beta x_{m}})$$
Simplified:
$$\xi=1-r(e^{i \beta h}-1)= (1-r)-re^{i \beta h}$$
$$|\xi|^{2}=Re \xi^{2}+Im \xi^{2}=\dots$$
$$\dots=1+2r(r+1)(1-\text{cos}\beta h)$$
We want $|\xi|^{2}\le1$:
$$\Rightarrow\quad r(r+1)\le0$$
But $r$ is positive, so $|\xi|^{2}>1$, so (FS) is von Neumann **unstable**.

Similarly for (BS), (UW), we eventually get
$$|\xi|^{2}=1+2r(r-1)(1-\text{cos}\beta h)$$
$$\Rightarrow\quad |\xi|\le1 \quad\Leftrightarrow\quad r(r-1)\le0$$
$$\quad\Leftrightarrow\quad r\ge0,\quad r\le1$$
So CFL condition is $r\le1$, implies von Neumann stability (in this case, same as positive coefficients)