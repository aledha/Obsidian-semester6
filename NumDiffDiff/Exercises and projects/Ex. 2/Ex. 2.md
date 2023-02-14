Using initial solution

$$
u(x,0)=\begin{cases} 2x & 0\le x\le 0.5\\
2(1-x) & 0.5\le x\le 1\end{cases}
$$
And $M=20$,  $N=400$ and $T=0.5$ 

Now with same initial solution but with $N=395$ instead.

since 
$$
r = \frac{k}{h^{2}}= \frac{T/N}{1/M^2} =\frac{M^2T}{N}
$$
Earlier we had
$$
r= \frac{20^{2}\cdot 0.5}{400}=0.5
$$
Which satisfies the stability condition.
Now though,
$$
r= \frac{20^{2}\cdot 0.5}{395}> 0.5
$$
Which does _not_ satisfy the stability condition, as seen in the result.

## 1c)
We want to solve the heat equation for
$$\begin{align*}
u_{t}&=u_{xx}\\
u(x,0) &= \text{sin}(\pi x)\\
\end{align*}$$
We assume that 
$$u(x,t)= G(t)\text{sin}(\pi x)$$
Then
$$\begin{align*}
u_{t}&= G'(t)\text{sin}(\pi x)\\
=u_{xx}&= -\pi^{2}G(t)\text{sin}(\pi x)\\
G'(t)&= -\pi^{2}G(t)\\
G(t)&= Ce^{-\pi^{2}t}\\
u(x,t) &= Ce^{-\pi^{2}t}\text{sin}(\pi x)
\end{align*}$$
Using $u(x,0)=\text{sin}(\pi x)$ we get that $C=1$ and
$$u(x,t)=e^{-\pi^{2}t}\text{sin}(\pi x)$$


## 1d) Neumann
Now we have the heat equation
$$u_{t}=u_{xx}$$
With initial conditions
$$
u(x,0) = \text{cos}(\pi x)
$$
With Neumann conditions
$$u_{x}(0,t)=\alpha=u_{x}(1,t)$$
Discretizing, we get:
$$\frac{1}{k}\Delta_{t}U_{m}^{n}- \frac{1}{h^{2}}\delta_{x}^{2}U_{m}^{n}=0$$
for the boundary, using fictitious nodes:
$$\delta_{2h,-1}U_{0} =\frac{U_{1}^{n}-U_{-1}^{n}}{2h}=\alpha$$
$$\frac{1}{k}\Delta_{t}U_{0}^{n}- \frac{1}{h^{2}}\delta_{x}^{2}U_{0}^{n}=0$$
With $r= \frac{k}{h^{2}}$ 
$$U_{-1}^{n}=U_{1}^{n}-2h\alpha$$
$$U_{0}^{n+1}=U_{0}^{n}+2r(U_{1}^{n}-U_{0}^{n}-h \alpha)$$
unsure about^ do the same for $U_{M}$!

