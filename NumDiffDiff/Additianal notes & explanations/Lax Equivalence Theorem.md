The theorem helps us understand the conditions under which a consistent numerical scheme for a PDE converges to the solution of that PDE.

---
<u>Consistensy</u>: *A difference method is* **consistent** *(with the differential equation) if*
$$\tau _{m}^{n}\rightarrow0,\quad \text{for all} \quad m,n \quad\text{when}\quad h \rightarrow 0,k \rightarrow 0.$$

---
<u>Lax Equivalence Theorem</u>: *A* **consistent** *difference scheme is* **convergent** *if and only if it is* **stable**.

---


# GPT:
<u>Lax Equivalence Theorem</u>: *Let $u(t,x)$ be a solution of an initial value problem for a hyperbolic system of conservation laws with smooth solutions and bounded total variation. Suppose that $u_h$ is the approximate solution obtained from a numerical scheme. If the numerical scheme is consistent and stable, then it is convergent. In other words, as the grid spacing $h$ approaches 0, $u_h$ approaches $u$ in a certain norm.*

Let's break this theorem down:

1. **Consistent:** A numerical scheme is consistent with the differential equation it is approximating if the local truncation error goes to zero as the step sizes go to zero. Formally, if our numerical scheme represents the PDE as $L_h(u_h) = 0$, where $L_h$ is the differential operator of the numerical scheme, and $L$ is the differential operator of the PDE, then the scheme is consistent if:
$$\lim_{{h\to 0}} \sup_{{t,x}} |L_h(u) - L(u)| = 0$$
Here, $u$ is the exact solution of the PDE.

2. **Stable:** A numerical scheme is stable if the solution does not blow up as we evolve the system in time. Formally, if $||u_h(t)||$ is a norm of the solution at time $t$, then the scheme is stable if for every T, there exists a constant $C(T)$ such that:
$$||u_h(t)|| \leq C(T) \text{ for all } t \in [0, T]$$
3. **Convergent:** A numerical scheme is convergent if the solution of the numerical scheme converges to the solution of the exact equation as the step size goes to zero. Formally, if $u$ is the exact solution and $u_h$ is the numerical solution, then the scheme is convergent if:
  $$\lim_{{h\to 0}} \sup_{{t,x}} |u_h(t,x) - u(t,x)| = 0$$
Lax's theorem essentially states that for linear hyperbolic PDEs, consistency and stability together imply convergence. This is a significant result as it tells us that we only need to check two properties (consistency and stability) to ensure our scheme will be successful (convergent).