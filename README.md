---
layout: default
title: "Algebraic Derivation of the Scalar Propagator in Spontaneously Broken Gauge Theories via the Woodbury Matrix Identity"
---
#### 1. Introduction
In spontaneously broken gauge theories, deriving the scalar field propagator in the generalized $R_\xi$ gauge (renormalizable $\xi$-gauge) often involves cumbersome calculations. This difficulty arises because the contribution introduced to the scalar fields to cancel the cross terms from the gauge-fixing term manifests as an off-diagonal, low-rank correction to the mass matrix.

Standard textbooks (e.g., Weinberg [1]) typically rely implicitly on the method of undetermined coefficients, assuming the final form of the propagator and solving a system of equations component by component. In this note, however, we demonstrate that by employing the **Woodbury matrix identity** from linear algebra, one can directly incorporate the consequences of the Nambu-Goldstone theorem, allowing for a highly transparent and rigorous derivation of the propagator.

#### 2. Formulation
Let $D(k)$ be the quadratic operator for the scalar field $\phi'$ in momentum space. The desired propagator $\Delta(k)$ is defined as its inverse matrix, $\Delta(k) = D^{-1}(k)$. From the Lagrangian, the operator is given by:

$$ D(k) = k^2 I + M^2_{\text{full}} \quad (1) $$

where the full mass matrix $M^2_{\text{full}}$ is decomposed into a term originating from the scalar potential, $\tilde{M}^2$, and a contribution from the gauge-fixing term:

$$ M^2_{\text{full}} = \tilde{M}^2 - \xi F F^T \quad (2) $$

The components of these matrices are defined as 

$$v\tilde{M}^2_{nm} = \partial^2 P / \partial\phi_n\partial\phi_m |_{\phi=v}v$$

 and 
 
 $F_{\alpha n}= (t_{\alpha}v)_n \quad$.

Due to spontaneous symmetry breaking, these matrices are subject to the following crucial physical properties:


1. **Nambu-Goldstone Theorem:** The curvature of the potential is zero along the directions of the broken generators, $F$.

   $$\tilde{M}^{2}F = 0 \quad (3)$$

2. **Vector Boson Mass Matrix:** Due to the anti-Hermitian nature of the generators, the vector boson mass matrix $\mu^2$ is given by:

   $$F^{T}F=-{\mu}^{2} \quad (4)$$

#### 3. Application of the Woodbury Matrix Identity
From Eqs. (1) and (2), the inverse matrix to be evaluated is $\Delta(k) = (k^2 I + \tilde{M}^2 - \xi F F^T)^{-1}$. Since this operator possesses the structure of a "base full-rank matrix" plus a "low-rank update term," the Woodbury matrix identity can be naturally applied.

The Woodbury identity reads:

$$ (A + U C V)^{-1} = A^{-1} - A^{-1} U (C^{-1} + V A^{-1} U)^{-1} V A^{-1} \quad (5) $$

In our system, we identify the associated matrices as follows:

$$ A = k^2 I + \tilde{M}^2, \quad U = F, \quad V = F^T, \quad C = -\xi I \quad (6) $$

First, we evaluate $A^{-1} F$ appearing on the right-hand side of Eq. (5). Utilizing the property in Eq. (3) ($\tilde{M}^2 F = 0$), we have $AF = (k^2 I + \tilde{M}^2)F = k^2 F$, which immediately yields:

$$ A^{-1} F = \frac{1}{k^2} F \quad (7) $$

(Similarly, $F^T A^{-1} = \frac{1}{k^2} F^T$.)
Through this step, the typically complex product of $A^{-1}$ and the vector space is drastically and algebraically simplified, owing entirely to the properties of the Goldstone modes.

Next, we evaluate the inverse matrix block in the parentheses of Eq. (5), $(C^{-1} + V A^{-1} U)$. Substituting Eq. (7) and Eq. (4) ($F^T F = -\mu^2$), we obtain:

$$ C^{-1} + F^T (A^{-1} F) = -\frac{1}{\xi}I + \frac{1}{k^2}F^T F = -\frac{1}{\xi}I - \frac{1}{k^2}\mu^2 \quad (8) $$

Factoring out the common terms, this simplifies to:

$$ = -\frac{1}{\xi k^2} (k^2 I + \xi \mu^2) \quad (9) $$

#### 4. Conclusion
We substitute the results of Eqs. (7) and (9) into the identity (5):

$$ \Delta(k) = A^{-1} - \left( \frac{1}{k^2} F \right) \left[ -\xi k^2 (k^2 I + \xi \mu^2)^{-1} \right] \left( \frac{1}{k^2} F^T \right) \quad (10) $$

The scalar factors $k^2$ and the minus signs cancel out, yielding the final matrix representation of the scalar field propagator:

$$ \Delta(k) = (k^2 I + \tilde{M}^2)^{-1} + \xi F \frac{1}{k^2} (k^2 I + \xi \mu^2)^{-1} F^T \quad (11) $$

Written in terms of matrix components, this result perfectly matches Eq. (21.2.21) in Weinberg. 

This derivation demonstrates that the non-trivial correction to the propagator arising from the gauge-fixing term is, mathematically, nothing but the inverse problem of a matrix perturbed by a low-rank update. By applying the Woodbury matrix identity, one achieves a highly transparent derivation without obscuring any of the beautiful algebraic structures inherent in the Nambu-Goldstone theorem.

**References**  
[1] S. Weinberg, *The Quantum Theory of Fields*, Vol. 2: Modern Applications (Cambridge University Press, 1996), Section 21.2.  
[2] [Woodbury matrix identity](https://en.wikipedia.org/wiki/Woodbury_matrix_identity)   
	