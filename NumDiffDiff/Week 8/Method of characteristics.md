$$u_{t}+a(t,x,u)u_{x}=b(t,x,u)\tag{2}$$
Solution method for (2).
## Idea:
Solve $u$ along a curve $x(t)$:
$$z(t):=u(x(t),t)$$
$$\dot{z}=u_{t}+u_{x}\dot{x}\stackrel{\text{if }\dot{x}=a}{=}b$$
We then get two **characteristic** equations
$$\begin{align*}
	\dot{x}&= a(x,t,z)\\
\dot{z} &= b(x,t,z)\tag{4}
\end{align*}$$
Need initial/boundary conditions
$$\begin{align*}
x(t_{0})&= x_{0}\\
z(t_{0})&= u(x(t_{0}),t_{0})=u(x_{0},t_{0})
\end{align*} \tag{5}$$
If solvable for all $(x_{0},t_{0})\in \Sigma$   where $\Sigma$ is a curve
$$\begin{align*}
x(t)&= X(t;x_{0},t_{0})\\
z(t) &= Z(t;x_{0},t_{0})
\end{align*}$$
And if $X:(x_{0},t_{0})\to(x,t)$   is invertible, then
$$u(x,t)=z(t;X^{-1}(x,t))$$
![[Pasted image 20230426134513.png|700]]

## Remark 2
* Data/information **flows** from $\Sigma$ to $(x,t)$
	* $\Sigma$=inflow boundary

## Special cases
1. 
   $$b=b(x,t) \stackrel{(4)}{\quad\Rightarrow\quad} z(t)=z(t_{0})=\int_{t_{0}}^{t}b(x(s),s)\text{d}s$$ 
2. 
$$b=0 \quad\Rightarrow\quad z(t)=z(t_{0})\stackrel{(5)}{=}u(x_{0},t_{0})$$

### Example 4
$$u_{t}+e^{-x}u_{x}=0$$
$$x(x,0)=x_{0}(x)$$
So $a=e^{-x},\quad b=0$
$$\frac{\text{d}x}{\text{d}t}=a=e^{-x} \stackrel{\text{seperable}}{\quad\Rightarrow\quad }\int_{x_{0}}^{x}e^{x}\text{d}x=\int_{0}^{t}dt $$
$$\text{I.C.s}\Rightarrow\quad e^{x}-e^{x_{0}}=t$$
Where we need $e^{x}>t$  since we are substracting $e^{x_{0}}>0$.
$$\text{invertible}\quad\Rightarrow\quad x_{0}=ln(e^{x}-t)\quad (=X^{-1})$$
$$\Rightarrow\quad u(x,t)=Z(t;X^{-1}(x,t))=u(X^{-1}(x,t))$$
$$\begin{align*}
u(x,t)&= u(\ln(e^{x}-t),0)\\
u(x,t)&= u_{0}(\ln(e^{x}-t))\quad\text{for }e^{x}>t
\end{align*}$$
![[Pasted image 20230426134657.png|600]]

### Example 5: Transport equation
$$u_{t}+au_{x}=0\quad \quad u(x,0)=u_{0}(x)$$
Where $a>0$
$$\dot{x}=a \quad \stackrel{I.C, (5)}{\Rightarrow}\quad x(t)=x_{0}+a(t-t_{0})$$
$$\dot{z}=0 \quad\Rightarrow\quad z(t)=z(t_{0})\stackrel{\text{def }z}{=}u(x_{0},t_{0})$$
$$\quad \stackrel{t_{0}=0}{\Rightarrow}\quad u(x,t)=u(x_{0},0)=u_{0}(x_{0})$$
$$u(x,t)\stackrel{x_{0}=x-at}{=}u_{0}(x-at)$$
![[Pasted image 20230426134712.png|600]]

