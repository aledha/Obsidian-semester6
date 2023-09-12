To model tensegrity structures, we will use a directed graph $\mathcal{G}$ with a vertex set $\mathcal{V}=\{1,\dots,N \}$ and an edge set $\mathcal{E} \subset \mathcal{V}\times\mathcal{V}$, where the vertices represent nodes and an edge $e_{ij}$ for $i<j$ represent a connection between node number $i$ and node number $j$. Furthermore, we denote the set of all cable connections as $\mathcal{C}$ and the set of all bar connections as $\mathcal{B}$. The position of node $i$ is denoted as $x^{(i)}=(x^{(i)}_{1}, x^{(i)}_{2}, x^{(i)}_{3} )\in \mathbb{R}^{3}$, and the collection of all nodes is in a large vector $X \in \mathbb{R}^{3N}$.

There are several energy components that we will consider. Suppose each node has an external load, we then can then model the gravitational potential energy as
\begin{equation}
    \label{ext}
    E_{ext}(X)= \sum\limits_{i=1}^{N} m_{i}g x_3^{(i)},
\end{equation}
where $m_{i}$ is the mass of the node and $g$ is the gravitational acceleration.

Consider a bar that connects the nodes $x^{(i)}$ and $x^{(j)}$, and denote the natural resting length of the bar as $l_{ij}>0$. We model the gravitational potential energy of such a bar as
\begin{equation}
    \label{barGrav}
    E_{grav}^{bar}(e_{ij})=\frac{\rho g l_{ij}}{2}(x_3^{(i)}+x_3^{(j)}),
\end{equation}
where $\rho>0$ is the line density of the bar.

Further, if the distance between the nodes is anything other than the natural resting length, then the the bar will have elastic potential energy. We model this with the quadratic model
\begin{equation}
    \label{barElast}
    E_{elast}^{bar}(e_{ij})= \frac{c}{2l_{ij}^2}(L(e_{ij})-l_{ij})^2=\frac{c}{2l_{ij}^2}(\Vert x^{(i)}-x^{(j)} \Vert-l_{ij})^2,
\end{equation}
where $c>0$ is a material parameter.

Cables will, however, not be compressed. We shall therefore model the elastic energy of the cables as
\begin{equation}
    \label{cableElast}
    E_{\text{elast}}^{\text{cable}}(e_{ij})= \begin{cases}\frac{k}{2l_{ij}^{2}}(\lVert x^{(i)}-x^{(j)} \rVert-l_{ij})^{2}  & \quad\text{for }\lVert x^{(i)}-x^{(j)}  \rVert> l_{ij}, \\0 &\quad\text{else,}
    \end{cases}
\end{equation}
where $k>0$ is also a material parameter.

We can now model the total energy of a given system as
\begin{equation}
    \label{1}
    E(X)= \sum\limits_{e_{ij} \in \mathcal{B}}^{}(E_{elast}^{bar}(e_{ij})+E_{grav}^{bar}(e_{ij}))+ \sum\limits_{e_{ij} \in \mathcal{C}}^{}E_{elast}^{cable}(e_{ij}) +E_{ext}(X).
\end{equation}

Mimimising such a system is problematic at the moment, since the functions $E_{ext}$ and $E^{bar}_{grav}$ are unbounded below. We must therefore introduce additional constraints. In this paper we explore two possibilities. The first possibility is fixing the position of the first $M$ nodes, 
\begin{equation}
    \label{2}
    x^{(i)}=p^{(i)}, \quad \text{for }i=1,\dots,M,
\end{equation}
which results in an unconstrained problem in $\mathbb{R}^{3(N-M)}$. The second possibility is constrained the system to be above ground, resulting in the following inequality constraints
\begin{equation}
    \label{3}
    x^{(i)}_3\ge 0, \quad \text{for }i=1,\dots,N. 
\end{equation}

