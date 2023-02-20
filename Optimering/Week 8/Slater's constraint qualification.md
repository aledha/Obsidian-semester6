Consider the case 
$$\Omega=\begin{cases}
x\in \mathbb{R}^{d}:\quad c_{i}(x)\ge0, \quad i\in \mathcal{I}
\end{cases}$$
and that the functions $c_{i}:\mathbb{R}^{d}\to \mathbb{R}$ are concave 
($c_{i}$ concave $\quad\Leftrightarrow\quad -c_{i}$ is convex).

The set $\Omega$ is convex.
## Defintion
We say that Slaters constraint qualifications are satisfied if
$c_{i}\quad i\in \mathcal{I}$ are concave, where $\Omega=[x:\quad c_{i}(x)\ge0 \quad i\in \mathcal{I}$.
And there exists $\hat x\in \Omega$ such that 
$$c_{i}(\hat x)> 0 \quad\forall\quad i\in \mathcal{I}$$


One can show:
If Slaters constraint qualifications holds, then 
$$T_\Omega(x)=\mathcal{F}_{\Omega}(x)\quad\forall\quad x\in \Omega$$
([[LICQ]] only tells us that this is true for one point, Slaters tells us for all points in $\Omega$)

In particular, the [[KKT-conditions]] are necessary optimality conditions.

If, in addition, $f$ is convex, then every KKT-point is a global solution.