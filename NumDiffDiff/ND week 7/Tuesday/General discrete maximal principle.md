	For irregular grids (rather general)
Last topic: [[Variable step size]]

$$-\mathcal{L}_{h}V_{P}= \alpha_{PP}V_{P}- \sum\limits_{Q≠P}\alpha_{PQ}V_{Q}\qquad \text{for }P\in \mathbb{G}, Q\in \overline{\mathbb{G}}$$
Assume:
1. (A1) **Positive coefficients** scheme
$$\alpha_{PQ}\ge0,\qquad \alpha_{PP}\ge \sum\limits_{Q≠P}\quad\forall\quad P\in \mathbb{G}, Q\in\overline{\mathbb{G}}$$
2. (A2) **Boundary connected**
For each $P\in \mathbb{G}$ there exists $Q\in \partial^{*}\mathbb{G}$ and $P_{1},\dots, P_{k}\in \mathbb{G}$ such that
$$\alpha_{PP_{1}}, \alpha_{P_{1}P_{2}}\dots, \alpha_{P_{k}Q}≠0$$
(where $\partial^{*}\mathbb{G}\subset \partial \mathbb{G}$) 
A2 will hold for all scenarios in this course.
Intuitively: it is possible to "walk along stencils" to a boundary.

## Theorem: DMP
$$-\mathcal{L}_{h}V_{h}\le 0 \quad \text{in }\mathbb{G}$$
$$\Rightarrow\quad \max_{P\in\overline{\mathbb{G}}}V_{P}\le \max_{P\in \partial^{*}\mathbb{G}}V_P$$
## Theorem: Monotone
$-\mathcal{L}_{h}$ is **monotone** if DMP holds and (A1) and (A2) holds

## Proof
![[Pasted image 20230214115854.png|1000]]
![[Pasted image 20230214115913.png|700]]