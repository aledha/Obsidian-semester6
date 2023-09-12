> When we want to perform a $2^{k}$ factorial experiment, we may not be able to perform all experiments, and therefore we rather perform a *fractional* experiment.
---

First, how to compute interactions:
$$AB= A \cdot B \qquad ABC=AB \cdot AC\cdot BC \qquad ABDC=\dots$$
For example, say that $A=1, B=-1, C=1$. Then,
$$AB=1 \cdot (-1) = -1, \qquad AC=1 \cdot 1=1 \qquad BC=(-1) \cdot 1=-1 $$
and $ABC =(-1)\cdot 1 \cdot (-1)=1$.

---
Keywords: 
* generator(s)=how to generate the design,  
* defining relation(s), found from the generators,  
* resolution=length of shortest defining relation,  
* alias structure=confounding pattern, found by multiplying each effect of interest with the defining relation.

When we perform a fractional $2^{k}$ experiment, we must first choose a fraction, where the most common choice is $\frac{1}{2}$. 

## Example- 2014 exam problem
![[Pasted image 20230522175906.png|500]]
**What type of experiment is this?**  
We see that we have a full factorial design in the factors A, B, C, but there is a fourth factor D added. This is a half fraction of a $2^{4}$ design, also called a $2^{4-1}$design.

**What is the generator and the defining relation for the experiment?**  
The generator for the design is D=AB. The defining relation is then I=ABD. This can be seen by calculating the interaction $AB$ and see that this equals $D$ in each experiment.

**What is aliasing?**
Aliasing is when a main effect confounds with an interaction. For example, if we observe a significant effect when changing A from -1 to +1, we cannot determine whether it is due to the main effect of A or the confounded BC interaction.

**What is the resolution of the experiment?**  
The resolution of the design equals the number of letters in the defining relation, thus the resolution is 3. We want it high to avoid aliasing between main effects and low-order inter- actions.

**Write down the alias structure of the experiment**. 
A=BD, B=AD, C=ABCD, D=AB  
AC=BCD, BC=ACD, CD=ABC  
I=ABD