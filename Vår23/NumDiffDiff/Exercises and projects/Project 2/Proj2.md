Let us consider a one-dimensional domain $\Omega = [x_i, x_{i+1}]$ and divide it into $n$ equally spaced elements. Let $u(x)$ be the approximation of the solution $u(x)$ on the element $\Omega$. We can represent $u(x)$ as a linear combination of shape functions $\phi_i(x)$ as follows:

$$u(x) = \sum_{j=1}^n u_j \phi_j(x), \quad x\in \Omega$$

where $u_j$ are the nodal values of $u(x)$ at the nodes of the element.

We can then substitute this representation of $u(x)$ into the differential equation $-\alpha u_{xx} + bu_x + cu = f$ to obtain:

$$-\sum_{j=1}^n u_j \alpha \phi_j''(x) + \sum_{j=1}^n u_j b\phi_j'(x) + \sum_{j=1}^n u_j c\phi_j(x) = f(x), \quad x\in \Omega$$

We can then apply the Galerkin finite element method by multiplying this equation by a test function $\phi_i(x)$ and integrating over the element $\Omega$. Integrating by parts and using the fact that the test function $\phi_i(x)$ is zero at the boundary of the element, we obtain:

$$-\int_{\Omega} \phi_i(x) \alpha \phi_j''(x),dx + \left[\phi_i(x) \alpha \phi_j'(x)\right]_{x_i}^{x_{i+1}} + \int_{\Omega} \phi_i(x) b\phi_j'(x),dx + \int_{\Omega} \phi_i(x) c\phi_j(x),dx = \int_{\Omega} \phi_i(x) f(x),dx$$

Simplifying and rearranging, we get:

$$\int_{\Omega} \left(a\phi_i'(x)\phi_j'(x) + b\phi_i(x)\phi_j'(x) + c\phi_i(x)\phi_j(x)\right),dx = \int_{\Omega} \phi_i(x) f(x),dx + \left[\phi_i(x) a\phi_j'(x)\right]_{x_i}^{x_{i+1}}$$



## 2d)

$$w_{1}=\begin{cases}
2x & \quad\text{for }x \in \left(0, \frac{1}{2}\right) \\
2(1-x)  & \quad\text{for }x \in \left(\frac{1}{2},1\right)
\end{cases}$$
$$\begin{align*}
f&= -aw_{xx}+bw_{x}+cu\\
&= \begin{cases}
2b+2cx & \quad\text{for }x \in \left(0, \frac{1}{2}\right)\\
-2b +2c(1-x) & \quad\text{for }x\in \left(\frac{1}{2},1\right)
\end{cases}
\end{align*}$$



## gpt
Let us consider a one-dimensional domain $\Omega = [x_i, x_{i+1}]$ and divide it into $n$ equally spaced elements. Let $u(x)$ be the approximation of the solution $u(x)$ on the element $\Omega$. We can represent $u(x)$ as a linear combination of shape functions $\phi_i(x)$ as follows:

$$u(x) = \sum_{j=1}^n u_j \phi_j(x), \quad x\in \Omega$$

where $u_j$ are the nodal values of $u(x)$ at the nodes of the element.

We can then substitute this representation of $u(x)$ into the differential equation $-au_{xx} + bu_x + cu = f$ to obtain:

$$-\sum_{j=1}^n u_j a\phi_j''(x) + \sum_{j=1}^n u_j b\phi_j'(x) + \sum_{j=1}^n u_j c\phi_j(x) = f(x), \quad x\in \Omega$$

We can then apply the Galerkin finite element method by multiplying this equation by a test function $\phi_i(x)$ and integrating over the element $\Omega$. Integrating by parts and using the fact that the test function $\phi_i(x)$ is zero at the boundary of the element, we obtain:

$$-\int_{\Omega} \phi_i(x) a\phi_j''(x),dx + \left[\phi_i(x) a\phi_j'(x)\right]_{x_i}^{x_{i+1}} + \int_{\Omega} \phi_i(x) b\phi_j'(x),dx + \int_{\Omega} \phi_i(x) c\phi_j(x),dx = \int_{\Omega} \phi_i(x) f(x),dx$$

Simplifying and rearranging, we get:

$$\int_{\Omega} \left(a\phi_i'(x)\phi_j'(x) + b\phi_i(x)\phi_j'(x) + c\phi_i(x)\phi_j(x)\right),dx = \int_{\Omega} \phi_i(x) f(x),dx + \left[\phi_i(x) a\phi_j'(x)\right]_{x_i}^{x_{i+1}}$$

Let $K_{ij}$ be the elemental stiffness matrix defined as:

$$K_{ij} = \int_{\Omega} \left(a\phi_i'(x)\phi_j'(x) + b\phi_i(x)\phi_j'(x) + c\phi_i(x)\phi_j(x)\right),dx$$

Then, the above equation can be written in matrix form as:

$$\mathbf{K}\mathbf{u} = \mathbf{f_e} + \mathbf{b_e}$$

where $\mathbf{u}$ is the vector of nodal values of $u(x)$, $\mathbf{f_e}$ is the element load vector defined as:

$$(\mathbf{f_e})_i = \int_{\Omega} \phi_i(x) f(x),dx$$

and $\mathbf{b_e}$ is the element boundary vector defined as:
$$\mathbf{b_e}=\begin{bmatrix} \phi_1(x_i)a\phi_1'(x_i) & 0 & \cdots & 0 \ 0 & \phi_2(x_i)a\phi_2'(x_i) & \cdots & 0 \ \vdots & \vdots & \ddots & \vdots \ 0 & 0 & \cdots & \phi_n(x_i)a\phi_n'(x_i) \end{bmatrix} - \begin{bmatrix} \phi_1(x_{i+1})a\phi_1'(x_{i+1}) & 0 & \cdots & 0 \ 0 & \phi_2(x_{i+1})a\phi_2'(x_{i+1}) & \cdots & 0 \ \vdots & \vdots & \ddots & \vdots \ 0 & 0 & \cdots & \phi_n(x_{i+1})a\phi_n'(x_{i+1}) \end{bmatrix}$$

The elemental stiffness matrix $\mathbf{K}$ is symmetric, positive definite, and can be computed analytically. The element load vector $\mathbf{f_e}$ and element boundary vector $\mathbf{b_e}$ can be computed numerically.

The overall stiffness matrix $\mathbf{K}$ and load vector $\mathbf{f}$ for the entire domain can be obtained by assembling the elemental stiffness matrices and load vectors, respectively. This can be done by adding the corresponding entries of each elemental matrix and vector to the corresponding entries of the global matrix and vector, respectively.

Once the system of equations is solved for the nodal values of $u(x)$, we can obtain the approximate solution $u(x)$ by substituting the nodal values into the shape function representation:

$$u(x) = \sum_{j=1}^n u_j \phi_j(x), \quad x\in \Omega$$

This completes the derivation of the elemental stiffness matrix for the differential equation $-au_{xx} + bu_x + cu = f$.