### Transform to a reference element $\hat K$
![[Pasted image 20230412162711.png|500]]

Denote
$\vec{\xi }_{p}= (\xi _{p}, \eta _{p})$,  and $\vec{x}_{p}=(x_{p},y_{p})$.

Then, $$\begin{bmatrix}x \\ y\end{bmatrix}=\Phi \begin{bmatrix}\xi  \\ \eta \end{bmatrix}=\begin{bmatrix}x_{L} \\ y_{L}\end{bmatrix}+\begin{bmatrix}x_{m}-x_{l} & x_{N}-x_{L} \\ y_{M}-y_{L} & y_{N}-y_{L}\end{bmatrix}\begin{bmatrix}\xi  \\ \eta \end{bmatrix},$$
and 
$$\vec{x}=\Phi (\vec{\xi  })=\vec{x}_{L}+J_{K}\vec{\xi }$$
$$\vec{\xi }=\Phi ^{-1}(\vec{x})=J^{-1}_{K}(\vec{x}-\vec{x}_{L}).$$
And (direct computations). The jacobi matrix:
$$J_{k}=\nabla _\vec{\xi }\Phi _{R}=\begin{bmatrix}\partial_{\xi }x & \partial_{\eta }x  \\ \partial_{\xi }y & \partial_{\eta }y\end{bmatrix},\qquad J_{K}^{-1}=\nabla _{\vec{x}}\Phi _{K}^{-1}=\begin{bmatrix}\partial_{x} \xi  & \partial_{y}\xi  \\ \partial_{x} \eta  & \partial_{y}\eta \end{bmatrix}.$$
![[Pasted image 20230412162730.png|500]]

The area of $K$ is the half of parallepiped, or 
$$\begin{align*}
\lvert K \rvert&=  \frac{1}{2}\lvert (\vec{x}_{M}-\vec{x}_{L})\times (\vec{x}_{M}-\vec{x}_L) \rvert\\
&= \frac{1}{2}\text{det }J_{K}
\end{align*}$$
### Basis of $\mathbb{P}_{1}(\hat K)$
$\psi _{L}=1-\xi -\eta, \qquad \psi _{M}=\eta ,\qquad \psi _{N}=\eta,$  and $\vec{\psi }=\begin{bmatrix}\psi _{L} \\ \psi _{M} \\ \psi _{N}\end{bmatrix}$
and the jacobian of this vector is
$$J_{\psi }=\nabla _{\vec{\xi }}\vec{\psi }=\begin{bmatrix}-1 & -1 \\ 1 & 0 \\ 0 & 1\end{bmatrix}\tag{*}$$
### Basis of $\mathbb{P}_{1}(K)$
$$\phi _{P}(x)=\psi _{\hat P}(\Phi _{K}^{-1}(\vec{x}))=\psi _{\hat p}(\xi (x,y),\eta (x,y))$$
$$\partial_{x}\phi _{p}= \partial_{\xi } \psi _{\hat p} \cdot \partial_{x}\xi + \partial_{\eta }\psi _{\hat p}\cdot \partial_{x}\eta $$
$$\partial_{y}\phi _{p}= \partial_{\xi }\psi _{\hat p}\cdot  \partial_{y}\xi + \partial_{\eta }\psi _{\hat p}\cdot \partial_{y}\eta$$
Then the gradient becomes
$$\nabla _{\vec{x}}\phi _{p}(\vec{x})=J_{K}^{-T}\cdot (\nabla _{\vec{\xi }}\psi _{\hat p})(\Phi _{K}^{-1}(\vec{x})) \tag{**}$$

### Elemental matrices
Transform integral to reference element: $\text{ d}x \text{ d}y= \lvert J_{K} \rvert \text{ d}\xi \text{ d}\eta$,    where $\lvert J_{K} \rvert=\text{det } J$.

$$\begin{align*}
a^{K}(\phi _{P},\phi _{Q})&= \int_{K}\nabla \phi _{P}\cdot \nabla \phi _{Q}\text{ d}x \text{ d}y\\
		&= \int_{\hat K} (J_{K}^{-T}\cdot \nabla _{\vec{\xi }}\psi _{\hat P})\cdot (J_{K}^{-T}\nabla _{\vec{\xi }}\psi _{\hat Q} ) \cdot \lvert J_{K} \rvert \text{ d}\xi \text{ d}\eta ,
\end{align*}$$
where the first two terms are constant since the functions are linear. They can be taken out of the integral

$$=(J_{K}^{-T}\cdot \nabla _{\vec{\xi }}\psi _{\hat P})\cdot (J_{K}^{-T}\nabla _{\vec{\xi }}\psi _{\hat Q} )\cdot \lvert J_{K} \rvert \cdot \int_{\hat K}\text{ d}\xi \text{ d}\eta $$
and the area of the triangle is $\frac{1}{2}$,  and we have computed before that the area of $K = \frac{1}{2} \text{det }J_{K}$. So the expression simplifies to
$$(J_{K}^{-T}\cdot \nabla _{\vec{\xi }}\psi _{\hat P})\cdot (J_{K}^{-T}\nabla _{\vec{\xi }}\psi _{\hat Q} ) \cdot \text{area}(K).$$
The elemental matrix is
$$A^{K}=\begin{bmatrix}a^{K}(\phi _{L},\phi _{L}) & a^{K}(\phi _{M},\phi _{L}) & a^{K}(\phi _{N}, \phi _{L}) \\ \vdots & \ddots & \vdots \\ a^{K}(\phi _{L},\phi _{N})  & \dots & a^{K}(\phi _{N}, \phi _{N}) \end{bmatrix}.$$
Using $(*), (**)$ we obtain
$$A^{K}=(J^{-T}_{K}J^{T}_{\psi} )^{T}\cdot (J_{K}^{-T}J^{T}_\psi )\cdot \lvert K \rvert.$$
Denote $G:= J_{K}^{-T}\cdot J_{\psi} ^{T}$. Then
$G=J^{-T}_{K}\cdot \begin{bmatrix}-1 & 1 & 0 \\ -1 & 0 & 1\end{bmatrix}.$

### Elemental load vector
$$\begin{align*}
F^{K}(\phi _{P}) &= \int_{K}f \phi _{p}\text{ d}xdy \\
&≈Q(f \phi _{P},K)\\
&= Q(f(\Phi _{K})\cdot \psi _{\hat P},\hat K) \cdot \lvert J_{K} \rvert,
\end{align*}$$
where Q denotes a quadrature.
$$\vec{F}^{K}=\begin{bmatrix}F^{K}(\phi _{L})  \\ F^{K}(\phi _{M}) \\ F^{K}(\phi _{N}) \end{bmatrix}$$
### Example 1: Quadrature
Midpoint rule:
$$Q(g, K)= g\left( \frac{1}{3}(\vec{x}_{L}+\vec{x}_{M}+\vec{x}_{N}) \right) \cdot \lvert K \rvert$$
Trapezoidal:
$$Q(g, K)=  \frac{1}{3}(g(\vec{x}_{L}) + g(\vec{x}_{M}) + g(\vec{x_{N}})) \cdot \lvert K \rvert$$
These are second order methods, $\mathcal{O}(h^{2}), \qquad h=\max_\limits{}\{\lvert \vec{x_{M}}-\vec{x_{L}} \rvert ,\lvert \vec{x_{N}} -\vec{x_{L}} \rvert, \lvert \vec{x_{N}}-\vec{x_{M}} \rvert \}$.
And they integrate $g \in \mathbb{P}_{1}(K)$ exactly.