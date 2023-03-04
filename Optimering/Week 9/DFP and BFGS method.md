A [[Quasi-Newton methods]]
The idea again is to define $B_{k+1}$ by changing $B_{k}$ as little as possible such that
$$B_{k+1}s_{k}=y_{k}$$
Remember that $s_{k}:=x_{k+1}-x_{k}$        and         $y_{k}:=\nabla f(x_{k+1})-\nabla f(x_{k})$

Recall that [[SR1-method]] requires that $B_{k+1}-B_{k}$ has rank 1.


## Extrapolating the method
Define $B_{k+1}$ as the solution of 
$$\underset{B\in \mathbb{R}^{d \times d}}{\text{argmin}} ||B-B_{k}||$$
Such that $Bs_{k}=y_{k}$   and    $B=B^{T}$.  
If differentiation is needed:
$$\underset{B\in \mathbb{R}^{d \times d}}{\text{argmin}} \frac{1}{2}||B-B_{k}||^{2}$$
<u>Goal:</u> Method should resemble Newtons method, as in having quadratic convergence.
$\quad\Rightarrow\quad$ should choose a norm according to this goal.

Newtons method has a nice <u>invariant</u> property:
	Assume $A\in \mathbb{R}^{d\times d}$ is non-singular and
$$f(x)=\tilde{f}(Ax),$$
	and denote $\tilde{x}=Ax$. If we apply Newton's method to $\min_\limits{x}f(x)$ and $\min_\limits{\tilde{x}}\tilde{f}(\tilde{x})$ with initialisations $x_{0}, \tilde{x_{0}}$ such that
	$Ax_{0}=\tilde{x_{0}}$, then  $\tilde{x}_{k}=Ax_{k}$ holds for all $k$.

The reason for this is $H_{f}(x)=A^{T}H_{\tilde{f}}(\tilde{x})A$.
We want this same property for the Quasi-Newton methods, so we have to define $||\cdot||$ in a suitable manner

### One possibility
Define $G$ as the average of Hessian between two iterates,
$$G:=\int_{0}^{1}H_{f}(x_{k}+\tau \alpha _{k}p_{k})\text{ d}\tau ,$$
and assume $G$ is positive definite (and therefore invertible).
Let $W:= G^{-1}$, and define $\left\lVert A \right\rVert_{W}=\left\lVert W^{\frac{1}{2}} AW^{\frac{1}{2}}\right\rVert_F$
where $\lVert\cdot\rVert _{F}$ is the Frobernius norm.
Now define $B_{k+1}$ as the solution of
$$\underset{B}{\text{argmin}} \frac{1}{2}\left\lVert B-B_{k} \right\rVert_{W}^{2}$$
such that $Bs_{k}=y_{k}$ and $B=B^{T}$
<u>Note</u>:
	$$\begin{align*}
Gs_{k}&= G(x_{k+1}-x_{k})\\
&= G(\alpha _{k}p_{k})\\
	&= \int_{0}^{1}H_{f}(x_{k}+\tau \alpha _{k}p_{k})\alpha _{k}p_{k}\text{ d}\tau \\
&\mathop{=}\limits^{\text{chain}}_{\text{rule}} \left[\nabla f(x_{k}+\tau \alpha _{k}p_{k}) \right]_{\tau =0}^{1}\\
	&= \nabla f(x_{k}+\alpha _{k}p_{k})-\nabla f(x_{k})\\
&= \nabla f(x_{k+1}) -f(x_{k}=y_{k})
\end{align*}$$
	So $Gs_{k}=y_{k} \quad \stackrel{W=G^{-1}}{\Rightarrow}\quad Wy_{k}=s_{k}$ 

# DFP method
Assume that $W\in \mathbb{R}^{d\times d}$ is symmetric and satisfies $Wy_{k}=s_{k}$.
Then the solution of 
$$\underset{B\in \mathbb{R}^{d\times d}}{\text{argmin}} =\frac{1}{2}\left\lVert B-B_{k} \right\rVert^{2}\quad\text{s.t.}\quad Bs_{k}=y_{k} \quad \text{and} \quad  B=B^{T}$$
is
$$B_{k+1}=(I-\mathcal{S}_{k}y_{k}\otimes s_{k})B_{k}(I-\mathcal{S}_{k}s_{k}\otimes y_{k}),$$
where $\mathcal{S}_{k}= \frac{1}{{\left\langle s_{k} \text{ , } y_{k} \right\rangle}}$
	Proof is doable but tedious. Will not do it.
Alternatively, with $H_{k}=B^{-1}_{k}$, we get
$$H_{k+1}=H_{k}- \frac{(H_{k}y_{k})\otimes (H_{k}y_{k})}{{\left\langle y_{k} \text{ , } H_{k}y_{k} \right\rangle}}+ \frac{s_{k}\otimes s_{k}}{{\left\langle y_{k} \text{ , } s_{k} \right\rangle}}\tag{*}$$
This is very nice! We can do even better, though.

## BFGS method
Do everything with $H$ instead. Meaning, we define $H_{k+1}$ as 
$$H_{k+1}= \underset{H\in \mathbb{R}^{d\times d}}{\text{argmin}} \frac{1}{2}\left\lVert  H-H_{k}\right\rVert^{2}_{W^{-1}} \quad\text{s.t.}\quad Hy_{k}=s_{k}\quad \text{and}\quad H=H^{T}.$$
So, we obtain
$$H_{k+1}=(I-\mathcal{S_{k}}s_{k}\otimes y_{k})H_{k}(I-\mathcal{S_{k}}y_{k}\otimes s_{k})+\mathcal{S_{k}}s_{k}\otimes s_{k},\tag{**}$$
where $\mathcal{S}_{k}= \frac{1}{{\left\langle s_{k} \text{ , } y_{k} \right\rangle}}$


<u>One can show that</u> (for DFP and BFGS):
* If $H_{k}$ is positive definite and ${\left\langle s_{k} \text{ , } y_{k} \right\rangle}>0\quad\Rightarrow\quad H_{k+1}$ is positive definite as well.
* If $f$ is strictly convex, then ${\left\langle s_{k} \text{ , } y_{k} \right\rangle}>0$
	* Proof, next exercise. Hint: treat as Newton method
* If $\alpha _{k}$ is chosen acording to Wolfe line search, then ${\left\langle s_{k} \text{ , } y_{k} \right\rangle}>0$.
	* Use Wolfe!!
* Under restrictive conditions, both methods converge **superlinearly**.
	* Conditions: convex $f$ and $f\in \mathcal{C}^{3}$ or something (??)

## Initialisation
Start with gradient step + line search. Then define
$$\frac{{\left\langle y_{0} \text{ , } s_{0} \right\rangle}}{{\left\langle y_{0} \text{ , } y_{0} \right\rangle}}\cdot I=H_{0}$$
And compute $H_{1},\dots$

For BFGS we rewrite $(**)$ as
$$\begin{align*}
H_{k+1}&= (I-\mathcal{S_{k}}s_{k}\otimes y_{k})H_{k}(I-\mathcal{S_{k}}y_{k}\otimes s_{k})+\mathcal{S_{k}}s_{k}\otimes s_{k}\\
	&= H_{k}-\mathcal{S_{k}}(s_{k}\otimes y_{k})H_{k}-\mathcal{S_{k}}H_{k}(y_{k}\otimes s_{k})
+ \mathcal{S_{k}}^{2}(s_{k}\otimes y_{k})H_{k}(y_{k}\otimes s_{k})+\mathcal{S_{k}}(s_{k}\otimes s_{k})\\
&= H_{k}-\mathcal{S_{k}}\big[s_{k}\otimes (H_{k}y_{k})+(H_{k}y_{k})\otimes s_{k}\big]
	+\big[\mathcal{S_{k}}^{2} {\left\langle y_{k} \text{ , } H_{k}y_{k} \right\rangle}+\mathcal{S_{k}}\big]s_{k}\otimes s_{k}
\end{align*}$$
Now the computations are easier for a computer to compute ($d^{2}$ operations at most). Calculating $H_{k}y_{k}$ is the most expensive.