Then we define the functions $f: \mathbb{R}^{3(N-M)}\to \mathbb{R}$ and $\nabla f: \mathbb{R}^{3(N-M)}\to\mathbb{R}^{3(N-M)}$ such that $f(Y)=E(\left[P,Y  \right])$ and $\nabla f(Y)=\{\partial_{x_{k}} E(\left[P,Y \right]) \}_{k=3M+1}^{3N}$ , meaning that we only return the last $3(N-M)$ indices of the gradient. Then we use BFGS to minimize $f(Y)$, using $\nabla f(Y)$ as the gradient.


$\partial_{x^{(i)}}f_{3} \stackrel{\lVert x^{(i)}-x^{(j)} \rVert \to l_{ij}}{\to}0$


remind mar to switch from f_3 to E_cableelast

fix sub and domscript