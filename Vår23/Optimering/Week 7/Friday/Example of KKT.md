Problem: minimize
$$f(x,y)=-(x-1)^{2}-(y+1)^{2} \quad \text{such that}$$
$$\begin{align*}
x^{2}&\le  y^{3}\\
x^{2}+y^{2}&\le 2
\end{align*}$$
Where the first condition can be written as
$$y\ge |x|^{\frac{2}{3}}$$
![[Pasted image 20230218125613.png|800]]

$$\begin{align*}
c_{1}(x,y)&= y^{3}-x^{2}&\ge 0\\
c_{2}(x,y)&= 2-x^{2}-y^{2}&\ge 0
\end{align*}$$

The optimality conditions state that possible candidates for solutions $(x^{*},y^{*})$ are
* points where [[KKT-conditions]] holds OR
* points where LICQ fails

Let's start with the second possibility, LICQ:
## LICQ
$$\nabla c_{1}(x,y)=\begin{pmatrix}-2x  \\ 3y^{2}\end{pmatrix}$$
$$\nabla c_{2}(x,y)=\begin{pmatrix}-2x \\ -2y\end{pmatrix}$$
LIQC holds at $(x,y)$ $\quad\Leftrightarrow\quad$ gradients $\nabla c_{i}(x,y)$  of active constraints are linearly independant
## Different possibilities:
### Both constraints are active
$c_{1}(x,y)=0=c_{2}(x,y)$
These points are $(-1,1)$ and $(1,1)$.

For $(1,1)$
$$\nabla c_{1}(1,1)=\begin{pmatrix}-2 \\ 3\end{pmatrix} \qquad \nabla c_{2}(1,1)=\begin{pmatrix}-2 \\ -2\end{pmatrix}$$
Those are linear independant $\Rightarrow$ LICQ holds here
For $(-1,1)$
$$\nabla c_{1}(-1,1)= \begin{pmatrix}2 \\ 3\end{pmatrix} \quad \quad \nabla c_{2}(-1,1)=\begin{pmatrix}2 \\ -2\end{pmatrix}$$
Those are linear independant $\Rightarrow$ LICQ holds here

### $c_{1}$ is active, $c_{2}$ inactive
$c_{1}(x,y)=0, \quad c_{2}(x,y)>0$
$$\nabla c_{1}(x,y)=\begin{pmatrix}-2x \\ 3y^{2}\end{pmatrix}$$
Recall [[Linear Independance]]:

The only way a single vector can be linearly dependant is if the vector is zero.
$$\begin{pmatrix}-2x \\ 3y^{2}\end{pmatrix}=\begin{pmatrix}0 \\ 0\end{pmatrix} \quad\Leftrightarrow\quad x,y=0 \quad\Rightarrow\quad \text{LICQ doesn't hold}$$
So LICQ holds for all $(x,y)≠(0,0)$

### $c_{1}$ is inactive, $c_{2}$ is active
$c_{1}(x,y)\ge0,\quad c_{2}(x,y)=0$
$$\nabla c_{2}(x,y)=\begin{pmatrix}-2x \\ -2y\end{pmatrix}=0 \quad\Leftrightarrow\quad (x,y)=(0,0)$$
But $c_{2}(0,0) =2≠0$. 
i.e. $c_{2}$ is **inactive** at $(0,0)$.

In this case, LICQ holds always.

### LICQ holds
For all $(x,y)\in \Omega\backslash(0,0)$.

## KKT-conditions
$$\nabla f(x,y)=\lambda_{1}\nabla c_{1}(x,y)+\lambda_{2}\nabla c_{2}(x,y)$$
$$\Leftrightarrow\quad \begin{pmatrix}-2(x-1) \\ -2(y+1)\end{pmatrix}=\begin{pmatrix}\lambda_{1}(-2x)+\lambda_{2}(-2x) \\ \lambda_{1}(3y^{2})+\lambda_{2}(-2y) \end{pmatrix}$$
With the conditions
$$
\begin{align*}
y^{3}&\ge  x^{2} \\
x^{2}+y^{2}&\le 2\\
\lambda_{1}&\ge 0,\quad \lambda_{2}\ge0  

\end{align*}$$
Reformulation of last KKT-condition:
If $y^{3}>x^{2}$, then $\lambda_{1}=0$.
If $x^{2}+y^{2}<2$, then $\lambda_{2}=0$.

Look at at all possibilities where constraints can be active:
### No constraints are active
-Strict inequalities

$$\lambda_{1}=0,\quad \lambda_{2}=0$$
Then 
$$\begin{align*}
-2(x-1)&= 0\\
-2(y+1)&= 0
\end{align*}$$
$\Rightarrow\quad (x,y)=(1,-1)$
But $(1,-1)\notin \Omega$.

### $c_{1}$ is active, $c_{2}$ is inactive
$y^{3}=x^{2}, \quad \lambda_{2}= 0$

$$\begin{align*}
-2(x-1)&= -2x \lambda_{1}\\
-2(y+1)&= 3y^{2}\lambda_{1}
\end{align*}$$
And $\lambda_{1}\ge0$.
$$\begin{align*}
-2(y+1)&\ge 0\\
\Rightarrow\quad y&\le -1\\
\Rightarrow\quad &\text{no feasible points}
\end{align*}$$
### $c_{1}$ is inactive, $c_{2}$ is active
$y^{3}>x^{2},\quad x^{2}+y^{2}=2$
$\lambda_{1}=0$
Need that
$$\begin{align*}
-2(x-1)&= -2x \lambda_{2}\\
-2(y+1)&= -2y \lambda_{2}
\end{align*}$$
With $\lambda_{2}\ge0$
First equation: 
$$\begin{align*}
x-1&= x \lambda_{2}\\
\quad\Leftrightarrow\quad 1&= x-x \lambda_{2}=x(1- \lambda_{2})
\end{align*}$$
With $1-\lambda_{2}\le0$
$$\Rightarrow\quad x\ge1$$
Which is not feasible.

### $c_{1}$ and $c_{2}$ are active
$(x,y)=(-1,1)\quad \text{or}\quad (x,y)=(1,1)$
With $\lambda_{1},\lambda_{2}\ge0$
(1,1):
$$\begin{align*}
0&= -2\lambda_{1}-2\lambda_{2}\\
-4 &= 3\lambda_{1}-2\lambda_{2}
\end{align*}$$
Which results in $\lambda_{1}+\lambda_{2}=0$, which implies that $\lambda_{1}=\lambda_{2}=0$
For the second equation we then get $-4=0 \quad\Rightarrow\quad$ contradiction.

(-1,1):
$$\begin{align*}
4&= 2\lambda_{1}+2\lambda_{2}\\
-4 &= 3\lambda_{1}-2\lambda_{2}
\end{align*}$$
$$\begin{align*}
\Rightarrow\quad \lambda_{1}&= 0\\
\lambda_{2}&= 2
\end{align*}$$
We then got the only KKT point 
$$(-1,1),\quad \text{with} \quad \lambda_{1}=0,\quad \lambda_{2}=2$$
And also remember the point $(0,0)$ where LICQ fails.
These two are the only possible points that can be a minimiser.