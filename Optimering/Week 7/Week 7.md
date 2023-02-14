[First slide](https://wiki.math.ntnu.no/_media/tma4180/2023v/lecture11.pdf)
From week 6:
![[Pasted image 20230213151855.png|700]]
## Definition: Constraint space $\Omega$
Let $\Omega\subset \mathbb{R}^{d}$ be defined by
$$x\in \Omega \quad\Leftrightarrow\quad \begin{cases}
c_{i}(x)=0 & i\in \xi \\
c_{i}(x)\ge0 & i\in \mathcal{I}
\end{cases}$$

## Definition: Tangent cone
$p\in T_\Omega(x)$ if
$$p = \\lim_{k \to \infty} \frac{z_{k}-x}{t_{k}} \qquad \text{for some}\quad  \begin{cases}
z_{k}\in \Omega,  &  z_{k}\to x \\
t_{k}>0 & t_{k}\to0
\end{cases}$$

## Definition: Linearized feasible directions
$p\in \mathcal{F}_\Omega(x)$ if
$$\begin{cases}
{\left\langle \nabla c_{i}(x),p \right\rangle}=0 & i\in \xi \\
{\left\langle \nabla c_{i}(x),p \right\rangle}\ge0 & i\in \mathcal{I} \text{ with } c_i(x)=0
\end{cases}$$


Warning: this will be a heavy lecture

[[Constraint qualifications]]   
	-   ▶  When does the equality $T_Ω(x) = F_Ω(x)$ hold?
	-  ▶  Linear independence constraint qualification (LICQ).
[[LICQ]]   
[[Farkas' Lemma]]   
[[KKT-conditions ]]  
[[Slater's constraint qualification]]   
[[Second order necessary and sufficient conditions]]

