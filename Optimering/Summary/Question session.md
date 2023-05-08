## Necessary/sufficient optimality conditions
### Necessary
* $x^{*}$ is a KKT point or $\mathcal{F}(x^{*})≠\mathcal{T}(x^{*})$
* $x^{*}$ is a KKT point or LICQ fails at $x^{*}$
* $x^{*}$ is a KKT point and the second order optimality conditions holds or LICQ fails

## Sufficient
* $x^{*}$ is a KKT point and the Hessian of the Lagrangian is strictly positive definite.

If the inequality constraints are concave or linear and equality constraints are linear:
	If Slaters fulfilled, then $\mathcal{T}(x)=\mathcal{F}(x)\quad\forall\quad x$
	Then the **neccesary condition** is
	$x^{*}$ is a KKT point.

If Slaters fulfilled and $f$ is convex, then
* $x^{*}$ is a KKT point $\quad\Leftrightarrow\quad$ $x^{*}$ is a global solution.


## Pareto optimality
Problem 3, exercise sheet 11

$f_{1}(x)=x^{2},\quad f_{2}(x)= (x^{2}-1)^{2}$

Find pareto-optimal solutions of $\min_\limits{x}(f_{1}(x),f_{2}(x))$.
	(**Pareto optimality:** $x^{*}$ is pareto-optimal if: 
	there does not exist $\hat x$ such that
	$f_{i}(\hat x)\le f_{i}(x^{*})\quad\forall\quad i$
	$f_{i}(\hat x)\le f_{i}(x^{*})$ for some $i$
	Meaning: if $\hat x$ such that $f_{i}(\hat x)<f_{i}(x^{*})$ then there exists some $j≠i$ such that $f_{j}(\hat x)>f_{j}(x^{*})$)
	if we decrease one function some, other function is increased.

Here:
$x^{*}$ is Pareto optimal if
$\quad\forall\quad \hat x$ with $f_{1}(\hat x)<f_{1}(x^{*})$ we have
$\quad f_{2}(\hat x)>f_{2}(x^{*})$
And visa-versa.