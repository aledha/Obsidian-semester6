## 1a)
Let $x \in S^c$ be arbitrary. We want to find an open ball around $x$ that is completely contained in $S^c$. Let $\epsilon = ||x||_{\infty} - 1 > 0$. Then, consider the open ball $B_{\epsilon}(x)$ centered at $x$ with radius $\epsilon$ with respect to the $\ell_{\infty}$ norm, i.e., $$ B_{\epsilon}(x) = { y \in \mathbb{R}^d : ||y - x||_{\infty} < \epsilon }. $$ Now, let $y \in B_{\epsilon}(x)$ be arbitrary. Then, $$ ||y||_{\infty} \geq ||x||_{\infty} - ||y - x||_{\infty} > ||x||_{\infty} - \epsilon = 1, $$ so $y \in S^c$. Therefore, $B_{\epsilon}(x) \subseteq S^c$, which means that $S^c$ is open.

Since the complement of $S$ is open, $S$ must be closed. Therefore, the set $S = { x \in \mathbb{R}^d : ||x||_{\infty} \leq 1 }$ is closed.

To show that the set $S = { x \in \mathbb{R}^d : ||x||_{\infty} \leq 1 }$ is convex, we need to show that for any $x, y \in S$ and $t \in [0,1]$, the point $tx + (1-t)y$ is also in $S$.

Let $x, y \in S$ be arbitrary, and let $t \in [0,1]$ be arbitrary as well. Then, we have
$$\begin{align*} ||(tx + (1-t)y)||_{\infty} &= \max_{1 \leq i \leq d} |(tx + (1-t)y)_i| \\ &= \max_{1 \leq i \leq d} |tx_i + (1-t)y_i| \\ &\leq \max_{1 \leq i \leq d} (|tx_i| + |(1-t)y_i|) \quad \text{(triangle inequality)} \\ &= \max_{1 \leq i \leq d} (t|x_i| + (1-t)|y_i|) \\ &\leq t \max_{1 \leq i \leq d} |x_i| + (1-t) \max_{1 \leq i \leq d} |y_i| \\ &\leq t \cdot 1 + (1-t) \cdot 1 = 1, \end{align*}$$ where we used the fact that $|x_i| \leq 1$ and $|y_i| \leq 1$ for all $i$, since $x, y \in S$.

Therefore, $tx + (1-t)y \in S$, which shows that $S$ is convex.