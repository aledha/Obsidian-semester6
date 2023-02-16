$$-\mathcal{L}u=f \quad \text{in } \Omega \tag{P}$$
$$-\mathcal{L}_{h}U_{P}=f_{P} \quad \text{in } \mathbb{G}\tag{Ph}$$
Local truncation error
$$\tau_{P}=\mathcal{L}u_{P}-\mathcal{L}_{h}u_{P}\quad \text{in }\mathbb{G}\tag{C}$$
$$e_{p}=u_{P}-U_{P}$$
$$-\mathcal{L}_{h}e_{P}=-\tau_{P}\quad \text{in }\mathbb{G}\tag{E}$$
$$e_{p}=0\quad \text{in }\mathbb{\partial G}$$
$\mathcal{L}_{h}$ positive coefiicients, boundary connected. DMP:
$$-\mathcal{L}_{h}V_{P}\le 0 \quad \text{in }\mathbb{G}$$
$$\quad\Rightarrow\quad \max_{\mathbb{G}}V_{P}\le \max_{\partial \mathbb{G}}(V_{P},0)$$
Find supersolution:
$$\phi\ge0, \quad -\mathcal{L}_{h}\phi\ge 1\quad \text{in }\mathbb{G}\tag{phi}$$
(DMP) + ($phi$) $\quad\Rightarrow\quad$ max norm stable:
$V$ solves $P_{h,f}$.   (($P_{h}$) with $V_{h}=0$ on $\partial \mathbb{G}$)
$$\Rightarrow\quad -\mathcal{L}_{h}(V_{P}-||\vec{f}||_{\infty}\phi_{P}) \stackrel{(P_{h})}{=}f_{p}-||\vec{f}||_{\infty}(-\mathcal{L}_{h})\phi_{p}\le 0$$
$$\begin{align*}
\stackrel{DMP}{\Rightarrow}\quad V_{P}-||\vec{f}||_{\infty} \phi_{P}&\le  \max_{\partial \mathbb{G}}(V_{P}-||\vec{f}||_{\infty}\phi_{P},\quad 0)\\
&= 0
\end{align*}$$
Since $V_{P}=0$. We then get
$$V_{P}\le C||\vec{f}||_{\infty}, \quad \quad C=\max_{\Omega}\phi$$
Since also $-V_{P}$ is a solution, we can bound it from below as well.
$$-V_{P}\le C||-\vec{f}||_\infty$$
$$\Rightarrow\quad \text{max} |V_{P}|\le C||\vec{f}||_\infty\tag{S}$$

## Error estimation
(E)+(S) $\quad\Rightarrow\quad$ $$||\vec{e}_{h}||_{\infty}\le C||\vec{\tau}_{h}||_\infty$$
Convergent if consistent:
$$||\vec{\tau}_{h}||_{\infty}\to 0, \quad h\to0$$

### Remark 1:
1. Finding $\phi$ can be difficult
2. $\mathcal{L}=\Delta$ on $(0,1)^{2}$: can use $\phi= \frac{1}{2}x(1-x)$
3. $\mathcal{L}u=au_{xx}+bu_{xy}+\dots -\lambda u$ for  $\lambda>0$
	Can use $\phi=\frac{1}{\lambda} \quad\Rightarrow\quad -\mathcal{L}\phi=1$
4. Parabolic ($-\mathcal{L}\to \partial_{t}-\mathcal{L}$)
	Can use $\phi=t \quad$ if $\lambda=0$ in (3)
	or $\phi=\frac{1}{\lambda}\quad$  if $\lambda>0$ in (3)
	($(\partial_{t}-\mathcal{L})\phi=+1$)