## 1d:
$$-u_{xx}= f \quad\text{on }(0,1), \qquad u(0)=0, \quad u_{x}(1)=\beta $$
$$\Downarrow \cdot v\in H^{1}, \quad \int \text{ d}x, \quad \text{i.b.p.}$$
$$\int_{0}^{1}u_{x}v_{x}\text{ d}x- \left[u_{x}v \right]_{0}^{1}=\int_{0}^{1}fv \text{ d}x$$
Idea: make test function "kill" the boundary at x=0, not x=1.
$$\Downarrow v \in V:=H^1 _{\Gamma }=\{v \in H^{1}:\quad v(0)=0 \}$$
$$\begin{align*}
\int_{0}^{1}u_{x}v_{x}\text{ d}x&= \int_{0}^{1}fv \text{ d}x+ \beta v(1)\\
	&= :\tilde{F}(v)
\end{align*}$$
## Multi-d:
$$-\Delta u=f \quad\text{on }\Omega , \quad \begin{cases}
\partial_{n}u=h  & \text{on }\Gamma \\
u=0  & \text{on }\partial_{}\Omega \backslash \Gamma 
\end{cases} $$
$$\Downarrow v\in V\in H^{1}_{\Gamma }=\{v\in H^{1}:\quad v=0 \quad\text{on }\partial_{} \Omega \backslash \Gamma \}$$
$$\int_{\Omega }\nabla u \cdot \nabla v-\int_{\partial \Omega }\nabla u \cdot v \cdot \vec{n}\text{ d}s=\int_{\Omega }fv \text{ d}x$$

$$\begin{align*}
a(u,v)&= \int _{\Omega }\nabla u \cdot \nabla v\\
	\int_{\partial \Omega } \nabla u \cdot v \cdot \vec{n} \text{ d}s &= \int_{\Gamma } \partial_{n}u \cdot v \text{ d}S + \int_{\partial \Omega \backslash \Gamma }\partial_{n}u \cdot v \text{ d}S\\\\
&\stackrel{v=0 \text{ on }\partial \Omega }{=} \int_{\Gamma } \partial_{n}u \cdot v \text{ d}S
\end{align*}$$
So 
$$\tilde{F}(v)=\int_{\Omega }fv \text{ d}x+\int_{\Gamma }h \cdot v ds$$
Where $h= \partial_{n}u$.
