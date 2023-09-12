Is an acceleration of steepest descent.

## Choice of $p_{k}$
$p_{0}=r_{0}=b-Ax_{0}$
$$p_{k}=r_{k}+ \beta _{k-1}p_{k-1}\quad\text{for }k=1,2,\dots\tag{6}$$
where $\beta _{k}$ minimises $\phi (x_{k+2}(\beta ))$,
where $x_{k+2}=x_{k+1}+\alpha _{k+1}p_{k+1}(\beta _{k})$

### Observation
#### (a)
$p_{k}^{T}r_{k}\stackrel{(6)}{=} \lvert r_{k} \rvert^{2}+\beta _{k-1}p_{k-1}^{T}r_{k}$
from [[Line search methods#Lemma 1|Lemma 1a]]: $p_{k-1}^{T}r_{k}=0$, so
$$p_{k}^{T}r_{k}=\lvert r_{k} \rvert^{2}$$
#### (b)
From [[Line search methods#Lemma 1|Lemma 1b]]
$$\phi (x_{k+1})= \phi (x_{k})- \frac{1}{2}\frac{\lvert r_{k} \rvert^{2}}{p_{k}^{T}Ap_{k}}$$
$\min_\limits{\beta _{k}}\phi (x_{k+2})$equivalent to $\min_\limits{\beta _{k}}p_{k+1}^{T}Ap_{k+1}$ 