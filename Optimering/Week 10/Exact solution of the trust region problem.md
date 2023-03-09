## Choice of $\Delta _{k}$ 
(Trust region radius)
In each step:
	Compute the expected decrease in function value $m_{k}(p_{k})-m_{k}(0)$
	Compare with the actual decrease $f(x_{k}+p_{k})-f(x_{k})$
	Compute
	$$\mathcal{S}_{k}= \frac{f(x_{k}+p_{k})-f(x_{k})}{m_{k}(p_{k})-m_{k}(0)}$$
	If $\mathcal{S_{k}}≈1$