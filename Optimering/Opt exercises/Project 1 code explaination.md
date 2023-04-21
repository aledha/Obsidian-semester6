Then we define the functions $f: \mathbb{R}^{3(N-M)}\to \mathbb{R}$ and $\nabla f: \mathbb{R}^{3(N-M)}\to\mathbb{R}^{3(N-M)}$ such that $f(Y)=E(\left[P,Y  \right])$ and $\nabla f(Y)=\{\partial_{x_{k}} E(\left[P,Y \right]) \}_{k=3M+1}^{3N}$ , meaning that we only return the last $3(N-M)$ indices of the gradient. Then we use BFGS to minimize $f(Y)$, using $\nabla f(Y)$ as the gradient.


$\partial_{x^{(i)}}f_{3} \stackrel{\lVert x^{(i)}-x^{(j)} \rVert \to l_{ij}}{\to}0$


remind mar to switch from f_3 to E_cableelast

fix sub and domscript $\infty$

$$\partial_{x_{1}^{(i)}}f_3  = - \partial_{x_{1}^{(j)}}f_{3} ,\quad 
    \partial_{x_{2}^{(i)}}f_{3} = - \partial_{x_{2}^{(j)}}f_{3} ,\quad 
    \partial_{x_{3}^{(i)}}f_{3} = - \partial_{x_{3}^{(j)}}f_{3}\quad \text{, and }
     \partial_{x_{1}^{(i)}}f_{3} =\frac{k\left(x_1^{(i)}-x_1^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right).$$

increase number of subsections


$$\partial_{x^{(i)}}E = \begin{pmatrix}\frac{k\left(x_1^{(i)}-x_1^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right) \\ \frac{k\left(x_2^{(i)}-x_2^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right) \\\frac{k\left(x_3^{(i)}-x_3^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right)+m_ig \end{pmatrix}^{T}=\begin{pmatrix}0 \\ 0 \\ 0\end{pmatrix}$$

$$ \frac{\partial E }{\partial x_1^{(i)}} =\frac{k\left(x_1^{(i)}-x_1^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right)=0,$$
    $$ \frac{\partial E }{\partial x_2^{(i)}} =\frac{k\left(x_2^{(i)}-x_2^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right)=0,$$
    $$ \frac{\partial E }{\partial x_3^{(i)}} =\frac{k\left(x_3^{(i)}-x_3^{(j)}\right)}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert} \left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right)+m_ig=0,$$
    where $i,j=M+1,...,N$ for  $i<j$.