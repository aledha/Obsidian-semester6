>Formally, a topological space is defined as a set $X$ together with a collection $\tau$ of subsets of $X$, satisfying certain axioms. The elements of $\tau$ are called open sets.

*A topological space is a fundamental concept in topology* 
### Formal Definition
A pair $(X, \tau)$ is called a topological space if:
1. The empty set $\emptyset$ and the entire set $X$ are both elements of $\tau$.
2. The intersection of any finite number of sets in $\tau$ is also in $\tau$.
3. The union of any number of sets in $\tau$ is also in $\tau$.
### Examples
1. **Discrete Topology**: For any set $X$, the power set of $X$ (i.e., the set of all subsets of $X$) can serve as $\tau$, making $(X, \tau)$ a topological space. This is called the discrete topology on $X$.
2. **Standard Topology on $\mathbb{R}$**: In the real numbers $\mathbb{R}$, the standard topology is generated by the set of all open intervals $(a, b)$, where $a < b$.
3. **Cofinite Topology**: For a non-empty set $X$, the cofinite topology consists of the empty set and all subsets of $X$ whose complements in $X$ are finite. This forms a topological space $(X, \tau)$.
4. **Product Topology**: If $(X_1, \tau_1)$ and $(X_2, \tau_2)$ are topological spaces, then their Cartesian product $X_1 \times X_2$ can be endowed with a product topology.
### Importance
The notion of a topological space serves as a foundational concept for various areas of mathematics including geometry, analysis, and algebra. It generalizes many concepts like convergence, continuity, and compactness, and provides a framework for studying them in a highly abstract setting.