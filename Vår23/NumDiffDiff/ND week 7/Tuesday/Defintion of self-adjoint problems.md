 	Found online (chatgpt down). Complicated, haven't transcribed everything. https://mathworld.wolfram.com/Self-Adjoint.html
Consider the second order differential operator.
$${\mathcal{L}} u(x) := a u_{xx}+b u_{x}+c u$$
Where $u, a, b,c$ are real functions of $x$. The self adjoint operator is defined by.
$$\mathcal{L}^{\dagger}u(x):=(au)_{xx}- (bu)_{x}+cu$$
Then $\mathcal{L}$ is self-adjoint is 
$$\begin{align*}
\mathcal{L}&= \mathcal{L}^\dagger

\end{align*}$$
$\mathcal{L}^{\dagger}$  rewritten:
$$\begin{align*}
\mathcal{L}^{\dagger}u&= (a_{x}u+au_{x})_{x}-b_{x}u-bu_{x}+cu\\
&= a_{xx}u+a_{x}u_{x}+a_{x}u_{x}+au_{xx}-b_{x}u-bu_{x}+cu\\
&= au_{xx}+(2a_{x}-b)u_{x}+(a_{xx}-b_{x}+c)u
\end{align*}$$
And this should $=\mathcal{L}u$
$$au_{xx}+(2a_{x}-b)u_{x}+(a_{xx}-b_{x}+c)u=a u_{xx}+b u_{x}+c u$$
So 
$$2a_{x}-b=b \quad\Rightarrow\quad a_{x}=b$$
$$a_{xx}-b_{x}=0$$
