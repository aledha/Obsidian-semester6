Let $\tilde{A}=0\in \mathbb{R}^{\overline M \times \overline M},\qquad \vec{\tilde{b}}=0 \in \mathbb{R}^{\overline M}$ 

Algorithm:

for $k \in \mathcal{T}_{h}$:
	for $P=L,M,N$:
		$i=\theta (P,K)$
		for $Q=L,M,N$:
			$j=\theta (Q,K)$
			$\tilde{A}_{ij} =\tilde{A}_{ij}+A^{K}_{PQ}$
		end
		$\tilde b_{i}=\tilde{b}_{i}+b_{P}^{K}$
	end
end 