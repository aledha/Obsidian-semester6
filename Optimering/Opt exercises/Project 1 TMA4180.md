Ole Gunnar Røsholt Hovland
Alexander Edward Hatle
Mar González Alonso
## P1

To show this we want to use the "existence of minimizers" theorem from the lectures. For the theorem to hold, i.e. for a global solution to exist, our function must be lower semi continuous, coercive and the space we operate in must be closed and non-empty.


$\mathcal{B}$ and $\mathcal{C}$ can only shrink/stretch around their respective tetherpoints whitch is continous. The only worrisome point is if to points ar exatly on top of eachother, where the energy explode to infinity and then to zero, but this point is still lower continuous. Since all the terms are at least lower continuous, their sum is as well. 

  

Let us first look at type (1) constraints. In the $x$- and $y$ direction, the only terms they apply in are the elastic energy in $\mathcal{B}$ and $\mathcal{C}$. Increasing these variables to $\pm\infty$ will increase $E(X)$ to $+\infty$. Now for the z-direction: for non-negative $z$ , all terms grow to $+\infty$. The negative direction is a little more work. The only terms that apply here are:

$$\begin{align*}

E_{\text{elast}}^{\text{bar}},E_{\text{elast}}^{\text{cable}}&\sim z^{2},\\

E_{\text{grav}}^{\text{bar}},E_{\text{ext}}&\sim z.

\end{align*}$$

This means that when $z\rightarrow-\infty$, $E_{\text{grav}}^{\text{bar}}$ and $E_{\text{ext}}$ become neglegable and $E(X)\rightarrow+\infty$. 

  

Now for the (2) constraint type. Since $z$ cannot be negative, and the set is closed, there are not any peoblems in this direction. The tricky part here is that if we move all the points to $\pm\infty$ in the $x$- or $y$ direction, then $E(X)$ does not tend to infinity, but remain constant! To fix this problem we can define the origo for (only) the  $x$- or $y$ axis to be in one of the points (the easisiest would be in $x^{(1)}$). In other words, the $x$- and $y$ coordinates are defined in relation to their distance to the "fixed" node. Coercivity in $x$- and $y$ direction is then introduced, and our problem admits a global solution.

  


$\textbf{P2: Show that the function E defined in (4) is C1, but typically not C2.}$

First of all we know that the sum of $C^1$ functions is $C^1$, so we just need to check each
term separately. To verify that the functions are $C^1$ we will proof that the partial derivates
of the functions are continuous.

For $E_{elast}^{cable}(e_{ij}) = E_{elast}^{cable}(x_1^{(i)}, x_2^{(i)}, x_3^{(i)}, x_1^{(j)},x_2^{(j)}, x_3^{(j)})$, we define the term $\frac{k}{2l_{ij}^{2}}(\Vert x^{(i)}-x^{(j)} \Vert- l_{ij})^2= f_3$ we have that, by symmetry
$$\frac{\partial f_3 }{\partial x_1^{(i)}} = - \frac{\partial f_3 }{\partial x_1^{(j)}} $$
$$\frac{\partial f_3 }{\partial x_2^{(i)}} = - \frac{\partial f_3 }{\partial x_2^{(j)}} $$
$$\frac{\partial f_3 }{\partial x_3^{(i)}} = - \frac{\partial f_3 }{\partial x_3^{(j)}}$$
and
$$ \frac{\partial f_3 }{\partial x_1^{(i)}} =\frac{k\left(x_1^{(i)}-x_1^{(j)}\right)}{l_{ij}^2\Vert
x^{(i)}-x^{(j)} \Vert ^{2}}\left( \Vert x^{(i)} - x^{(j)} \Vert -l_{ij}\right)$$

and when $\Vert x^{(i)}-x^{(j)} \Vert = l_{ij}$ then $\frac{\partial f_3 }{\partial x_1^{(i)}} = 0$.
Also, a potential issue with every $\frac{\partial f_3 }{\partial x^{(i)}}$ would be when $\Vert x^{(i)}-x^{(j)} \Vert=0$ (and hence a 0 in the denominator), but in this case, by definition
$0\lt l_{ij}$ so the function and its derivative are equal to 0.
Then $$ \frac{\partial f_3 }{\partial x_1^{(i)}}$$ is continuous. The same can be done for the
other coordinates of $x^{(i)}$.
Hence $E_{elast}^{cable}(e_{ij})$ is $C^1$.
If we compute $\frac{\partial^2 f_3 }{\partial x_1^{(i)^2}}$ we get $$\frac{\partial^2 f_3
}{\partial x_1^{(i)^2}}=\frac{(x_1^{(i)}-x_1^{(j)})}{l_{ij}^2}\left[ x_1^{(i)}-2\sqrt[3]{l_{ij}^{2}} x_1^{(j)}
\right]$$then $$\frac{\partial^2 f_3 }{\partial x_1^{(i)^2}}=0 \Leftrightarrow x_{1}^{(i)}-
2\sqrt[3]{l_{ij}^{2}} x_1^{(j)}=0\Leftrightarrow l_{ij}=\left( \frac{x_1^{(i)}}{2x_1^{(j)}}\right)^{\frac{2}{3}}
$$ or $$\frac{\partial^2 f_3 }{\partial x_1^{(i)^2}}=0 \Leftrightarrow x_{1}^{(i)}=x_1^{(j)}$$
which is not necessary the case. Hence it is typically not $C^2$.

The term $E_{ext}(X)$ is clearly $C^1$ as $E_{ext}(X)= \sum\limits_{i=1}^{N} E_{ext}(m_i,x^{(i)})= \sum\limits_{i=1}^{N}f_{i_4}$ where $E_{ext}(m_i, x^{(i)})= m_i g x_3^{(i)}=f_{i_4}$ is
clearly $C^1$ as $\frac{\partial f_{i4} }{\partial x_3^{(i)}} = m_ig$ is constant, and so
continuous.

$\textbf{P3: Show that the problem (4) is convex. Is the problem strictly convex? Do we necessarily have a unique solution?}$
$$\min_\limits{X}E(X)=\sum\limits_{e_{ij}\in \xi }^{}E^{\text{cable}}_\text{elast} (e_{ij})+E_\text{ext}(X),\tag{4}$$
such that $x^{(i)}=p^{(i)}\quad\forall\quad i=1,\dots M$.

Let's first explore $E_{ext}(X)=\sum\limits_{i=1}^{N}m_{i}gx_{3}^{(i)}$.
With our constraints, we have
$$E_{ext}(X)=\sum\limits_{i=1}^{M}m_{i}gp_{3}^{(i)}+\sum\limits_{i=M+1 }^{N}m_{i}gx^{(i)}_3.$$
$E_{ext}(X)$ is convex $\quad\Leftrightarrow\quad E_{ext}(tX+(1-t)Y)\le tE_{ext}(X)+(1-t)E_{ext}(Y) \quad\forall\quad 0\le t\le1$.
$$\begin{align*}
E_{ext}(tX+(1-t)Y)&= \sum\limits_{i=1}^{M}m_{i}gp_{3}^{(i)}+\sum\limits_{i=M+1 }^{N}m_{i}g(tx_{3}^{(i)}+(1-t)y_{3}^{(i)})\\
&= (1-t+t)\sum\limits_{i=1}^{M}m_{i}gp_{3}^{(i)}+t\sum\limits_{i=M+1 }^{N}m_{i}gx_{3}^{(i)}+(1-t)\sum\limits_{i=M+1 }^{N}m_{i}gy_{3}^{(i)}\\
&= tE_{ext}(X)+(1-t)E_{ext}(Y).
\end{align*}$$
So $E_{ext}(X)$ is convex.

Now let's explore if $\sum\limits_{e_{ij}\in \xi }^{}E^{\text{cable}}_\text{elast} (e_{ij})=\sum\limits_{e_{ij}\in \xi }\begin{cases}\frac{k}{2l_{ij}^{2}}(\lVert x^{(i)}-x^{(j)} \rVert-l_{ij})^{2}  & \quad\text{for }\lVert x^{(i)}-x^{(j)}  \rVert> l_{ij}, \\0 &\quad\text{else,} \end{cases}$
is convex.

The sum of convex functions is convex and a convex function multiplied by a constant is also convex, so we need only show that
$\begin{cases}(\lVert x^{(i)}-x^{(j)} \rVert-l_{ij})^{2}  & \quad\text{for }\lVert x^{(i)}-x^{(j)}  \rVert> l_{ij}, \\0 &\quad\text{else,} \end{cases}$ 
is convex.
The squared of a non-negative convex function is also convex, and
$$g(X):=\begin{cases}\lVert x^{(i)}-x^{(j)} \rVert-l_{ij}  & \quad\text{for }\lVert x^{(i)}-x^{(j)}  \rVert> l_{ij}, \\0 &\quad\text{else,} \end{cases}$$
is non-negative, so we need only show that $g(X)$ is convex.
We have
$$\begin{align*}
g(tX+(1-t)Y)&= \lVert t(x^{(i)}-x^{(j)})+(1-t)(y^{(i)}-y^{(j)}) \rVert-l_{ij}\\
&\stackrel{\text{Triangle ineq.}}{\le}t \lVert x^{(i)}-x^{(j)} \rVert+(1-t)\lVert y^{(i)}-y^{(j)} \rVert -(1-t+t)l_{ij}\\
&= tg(X)+(1-t)g(Y).
\end{align*}$$
So $g$ is convex, and by extension $\sum\limits_{e_{ij}\in \xi }^{}E^{\text{cable}}_\text{elast} (e_{ij})$ is convex.

Again, the sum of of convex functions is also convex, so
$$\min_\limits{X}E(X)=\sum\limits_{e_{ij}\in \xi }^{}E^{\text{cable}}_\text{elast} (e_{ij})+E_\text{ext}(X),\tag{4}$$
is convex.

Note that since 
$$E_{ext}(tX+(1-t)Y)=tE_{ext}(X)+(1-t)E_{ext}(Y),$$
$E_{ext}(X)$ is not strictly convex. However, this is not sufficient to conclude weather $E(X)$ is strictly convex or not.

$\textbf{P4: Formulate the necessary and sufficient optimality conditions for (4).}$
We have a free optimization problem and our function $E(X)$ is convex and $C^1$ for this
case. Hence we know that our necessary and sufficient optimality conditions are $\nabla E(X)=0$. More specifically

$$\nabla E(X) =\sum\limits_{i,j=M+1, i<j}^{N} \frac{k}{l_{ij}^2}(\Vert x^{(i)}-x^{(j)} \Vert-l_{ij})\begin{bmatrix}
\frac{x_1^{(i)}-x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{x_2^{(i)}-x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{x_3^{(i)}-x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + \frac{m_ig}{2(\Vert x^{(i)}-
x^{(j)} \Vert-l_{ij}) }\\
\frac{-x_1^{(i)}+x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{-x_2^{(i)}+x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{-x_3^{(i)}+x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + \frac{m_jg}{2(\Vert x^{(i)}-
x^{(j)} \Vert-l_{ij}) }
\end{bmatrix} $$
or the same written differently:
$$\nabla  E(X) =\sum\limits_{i,j=M+1, i<j}^{N} \frac{k(\Vert x^{(i)}-x^{(j)} \Vert-
l_{ij})}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert}\begin{bmatrix}
x_1^{(i)}-x_1^{(j)} & x_2^{(i)}-x_2^{(j)} & x_3^{(i)}-x_3^{(j)} + \frac{l_{ij}^2m_{ig}\Vert x^{(i)}-
x^{(j)} \Vert}{k(\Vert x^{(i)}-x^{(j)} \Vert-l_{ij}) }\\
-x_1^{(i)}+x_1^{(j)} & -x_2^{(i)}+x_2^{(j)} & -x_3^{(i)}+x_3^{(j)} + \frac{l_{ij}^2m_{jg}\Vert
x^{(i)}-x^{(j)} \Vert}{k(\Vert x^{(i)}-x^{(j)} \Vert-l_{ij}) }
\end{bmatrix} $$

$\textbf{P6: Show that the function E in (5) is typically not differentiable.}$
$\textbf{Discuss why the lack of differentiability should in practical situations pose no problem.}$

The problem that we face in (5) lies in having the cables. What happens is that by the
definition of $E_{elast}^{cable}$, there is no restriction on the values $x^{(i)}$ and $x^{(j)}$ can
take, so we could have indeed the possibility of $x^{(i)}=x^{(j)}$. For the cables we found that by
the definition of their energy, there was no problem with having a hypotetical case were
$x^{(i)}=x^{(j)}$ because their energy would be 0, and so its derivative. But for the bars we
have that
$$\nabla E_{elast}^{bar}(X) =\sum\limits_{e_{i,j}\in \mathcal{B}, i,j=M+1, i\le j}^{N} \frac{c(\Vert
x^{(i)}-x^{(j)} \Vert-l_{ij})}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert}\begin{bmatrix}
x_1^{(i)}-x_1^{(j)} & x_2^{(i)}-x_2^{(j)} & x_3^{(i)}-x_3^{(j)} \\
-x_1^{(i)}+x_1^{(j)} & -x_2^{(i)}+x_2^{(j)} & -x_3^{(i)}+x_3^{(j)}
\end{bmatrix}$$
where if $x^{(i)}=x^{(j)}$ then this it is not differentiable.

Using any reasonable algorithm, the nodes connected by bars will not coincide, since the energy would grow fast as the points come closer. 

$\textbf{P7: Formulate the necessary optimality conditions for (5).}$ $\textbf{Are they also sufficient for a local minimum?}$
We can treat problem (5) as differentiable because in reality we are not going to have the case
where the function is not differentiable. As the function is not convex (see problem 8), we can
only formulate the necessary optimality conditions. These are $\nabla E(X)=0$. The function is
not twice differentiable (the same issue as in Problem 2), so we cannot formulate the second
order optimality conditions.

$$\sum\limits_{e_{i,j}\in \mathcal{B}, i\lt;j}^{} \left( \frac{c(\Vert x^{(i)}-x^{(j)} \Vert-
l_{ij})}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert}\begin{bmatrix}
x_1^{(i)}-x_1^{(j)} & x_2^{(i)}-x_2^{(j)} & x_3^{(i)}-x_3^{(j)}\\
-x_1^{(i)}+x_1^{(j)} & -x_2^{(i)}+x_2^{(j)} & -x_3^{(i)}+x_3^{(j)}
\end{bmatrix} + \begin{bmatrix}
0 & 0 & \frac{\rho g l_{ij} }{2}+m_ig \\
0 & 0& \frac{\rho g l_{ij} }{2}+m_jg
\end{bmatrix} \right)$$
$$+\sum\limits_{e_{i,j}\in \mathcal{C}, i\lt;j}^{} \left( \frac{k(\Vert x^{(i)}-x^{(j)} \Vert-
l_{ij})}{l_{ij}^2\Vert x^{(i)}-x^{(j)} \Vert}\begin{bmatrix}
x_1^{(i)}-x_1^{(j)} & x_2^{(i)}-x_2^{(j)} & x_3^{(i)}-x_3^{(j)}\\
-x_1^{(i)}+x_1^{(j)} & -x_2^{(i)}+x_2^{(j)} & -x_3^{(i)}+x_3^{(j)}
\end{bmatrix} + \begin{bmatrix}

0 & 0 & m_ig \\
0 & 0& m_jg
\end{bmatrix} \right)=0$$


In reality we have that every cable matters, in the sense that the cable is going to be tense and
not loose (compressed), so we are always going to be in the non-zero term for the bars. That is
why in the first summary there are no 0 terms.

¿LOCAL MINIMA?

In practice, the function is $C^1$ and hence continuous, and also coercive as shown in
Problem 1.
Is this enough for local minima?

$\textbf{P10: Formulate the first order optimality conditions (i.e., KKT-conditions) for(6).}$ $\textbf{Are they sufficient or necessary for a local solution?}$
$\textbf{What can be said about constraint qualifications?}$

There is only one constrain $c_1^{(i)}(x^{(i)})=x_{3}^{(i)}\geq 0$, $i=1,...,N$ and $\nabla c_1^{(i)}(x^{(i)})=(0,0,1)$, which is linearly independent as it is non-zero. Then for every point 
LICQ holds, and we can formulate the KKT-conditions.
When the constraint is active, $c_1^{(i)}(x^{(i)})=x_{3}^{(i)}= 0$ for every i, it does not make
physical sense for us, because it would mean that our whole structure is on the floor.

There may be some equal to zero.

Then we will consider the inactive case, when $c_1^{(i)}(x^{(i)})=x_{3}^{(i)}> 0$.
$\mathcal{L}(X, \lambda)= E(X)-\sum\limits_{i=1}^{N}\lambda _{i}c_1(x^{(i)})$
KKT conditions establish:
$\nabla_{x} E(X)=\sum\limits_{i=1}^{N}\lambda_i(0,0,1)$
If $c_1(x^{(i)})>0$, inactive, $\Rightarrow \lambda _i=0$.
If $c_1(x^{(i)})=0$, active, $\Rightarrow \lambda _i>0$.
$$\begin{align*}
\sum\limits_{i,j \in \mathcal{B}, i<j}^{} \begin{bmatrix}

\frac{x_1^{(i)}-x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{x_2^{(i)}-x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{x_3^{(i)}-x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + \frac{\rho g l_{ij} }{2}+m_ig-
\lambda_i \\
\frac{-x_1^{(i)}+x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{-x_2^{(i)}+x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{-x_3^{(i)}+x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + \frac{\rho g l_{ij}
}{2}+m_jg - \lambda_j
\end{bmatrix}\\
+\sum\limits_{i,j \in \mathcal{C}, i<j}^{} \begin{bmatrix}
\frac{x_1^{(i)}-x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{x_2^{(i)}-x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{x_3^{(i)}-x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + m_ig - \lambda_i\\
\frac{-x_1^{(i)}+x_1^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} & \frac{-x_2^{(i)}+x_2^{(j)}}{\Vert x^{(i)}-
x^{(j)} \Vert} & \frac{-x_3^{(i)}+x_3^{(j)}}{\Vert x^{(i)}-x^{(j)} \Vert} + m_jg - \lambda_j
\end{bmatrix}=0
\end{align*}$$ 

On the other hand, $c_1(x^{(i)})=x_{3}^{(i)} \ge 0$ is concave (not strictly concave),
$c_1((1-\alpha)x^{(i)}+\alpha x^{(j)})=~~~~~~(1-\alpha)x_{3}^{(i)} +\alpha x_3^{(j)}~~~~~~~~=(1-\alpha)c_1(x^{(i)})+\alpha c_1(x_3^{(j)})$,
$\Omega = \left\lbrace x^{(i)}: c_1(x^{(i)}) \ge 0 \right\rbrace$, and if there exists $\tilde{x} \in \Omega$ s.t. $c_1(\tilde{x})>0$ 
(this is going to happen since not all the points are going to
stay on the floor), then Slater´s constraint qualification holds and so KKT conditions are
necesssary optimality conditions.

As the energy function is not convex if there are bars ($\mathcal{B} \neq \emptyset$), we
cannot say anything about the KKT points being a local solution of our problem. Hence KKT
conditions are not sufficient, only necessary.
If there are no bars $(\mathcal{B} = \emptyset)$, then as shown in Problem 8, the function is
convex an so KKT conditions are sufficient optimality conditions and every KKT point is a global
solution of our problem.

Some side ideas:
Even though the Hessian is not positive definite, it could be positive definite where we need.
If LICQ holds at X (the solution), and the matrix $H_{\mathcal{L}}(X,\lambda)$ is pos definitive
on $ker(A(X)) \in \mathcal{R}^{(3N-M) \times \mathcal{A}}$ (Jacobian of $c_1(x^{(i)})$), then
we will have local convergence.


## P11

This problem is adressed in P1, and the way we handled the issue there is an easely applicable strategy to adress this issue in our numerical solvers as well.
