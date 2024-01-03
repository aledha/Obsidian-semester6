To construct ordinary differential equations (o.d.e) with flows that have non-empty, compact limit sets containing one, two, three, or four fixed points, you can use polar coordinates \((r, \theta)\). In polar coordinates, \( r \) represents the radial distance from the origin, and \( \theta \) represents the angle with respect to the positive x-axis. The idea is to create a system of o.d.e that controls the behavior of both \( r \) and \( \theta \) to achieve the desired number of fixed points.

### General Approach

1. **Single Fixed Point**: To have a single fixed point, usually at the origin, you can design the system so that all trajectories eventually converge to this point. An example is:
   \[ \begin{align*}
   \dot{r} &= -r \\
   \dot{\theta} &= \omega
   \end{align*} \]
   Here, \( \dot{r} \) is negative for \( r > 0 \), ensuring that all trajectories move towards the origin, and \( \dot{\theta} = \omega \) gives a constant angular velocity.

2. **Two Fixed Points**: For two fixed points, you might design a system where one point is a stable equilibrium and the other an unstable one. This can be achieved by manipulating the radial component to grow in one region and decay in another. An example is:
   \[ \begin{align*}
   \dot{r} &= r(1 - r)(r - a) \\
   \dot{\theta} &= \omega
   \end{align*} \]
   With \( 0 < a < 1 \), you have two fixed points at \( r = 0 \) and \( r = 1 \), with different stability characteristics.

3. **Three Fixed Points**: To construct a system with three fixed points, you can extend the previous idea by adding another term to the radial equation. For instance:
   \[ \begin{align*}
   \dot{r} &= r(a - r)(r - b)(r - c) \\
   \dot{\theta} &= \omega
   \end{align*} \]
   Here, \( 0 < a < b < c \) gives three fixed points with alternating stability.

4. **Four Fixed Points**: Similarly, for four fixed points, add an additional term to the radial equation:
   \[ \begin{align*}
   \dot{r} &= r(a - r)(r - b)(r - c)(r - d) \\
   \dot{\theta} &= \omega
   \end{align*} \]
   Choose \( 0 < a < b < c < d \) for four fixed points.

### Notes
- The angular component \( \dot{\theta} \) is often kept simple (like a constant \( \omega \)) to focus on the radial dynamics.
- The values of \( a, b, c, d \) and their order determine the position and stability of the fixed points.
- These are just simple examples. More complex behaviors can be designed by varying \( \dot{r} \) and \( \dot{\theta} \) in more intricate ways.