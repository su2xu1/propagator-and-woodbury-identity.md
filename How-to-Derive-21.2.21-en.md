## Weinberg QFT: Step-by-Step Derivation of Eq. (21.2.21) from Eq. (21.2.14)
I will explain the step-by-step procedure to derive the scalar field propagator $\Delta_{nm}(k)$ in Eq. (21.2.21) from the Lagrangian in Eq. (21.2.14).


$$
\begin{aligned}
L_{QUAD}={}&
-\frac{1}{4}\sum_\alpha({\partial^\mu}{A_\alpha^\nu}-{\partial^\nu}{A_\alpha^\mu})({\partial_\mu}{A_{\alpha\nu}}-{\partial_\nu}{A_{\alpha\mu}})\\
&-\frac{1}{2}\sum_{\alpha\beta}\mu^2_{\alpha\beta}A_\alpha^{\mu}A_{\beta\mu}
-\frac{1}{2\xi}\sum_\alpha({\partial_\mu}{A_\alpha^\mu})({\partial_\nu}{A_\alpha^\nu})\\
&-\frac{1}{2}\sum_n{\partial_{\mu}\phi^{'}_n}{\partial^{\mu}\phi^{'}_n}
-\frac{1}{2}\sum_{nm}M^2_{nm}{\phi^{'}_n}{\phi^{'}_m}\\
&- {\overline\Psi}({\gamma_\mu}{\partial^\mu} +m)\Psi\\
&-\partial_\mu\omega_\alpha^*\partial^\mu\omega_\alpha
- \xi\sum_{\alpha\beta}\mu^2_{\alpha\beta}\omega^*_\alpha\omega_\beta\\
&+ \text{total derivatives},\quad (21.2.14)
\end{aligned}
$$


$$
\phi: \Delta_{nm}(k)= (k^2+M^2)^{-1}_{nm}+\xi\sum_{\alpha\beta}(t_\alpha{v})_n(t_\alpha{v})_m(k^2)^{-1}(k^2+\xi\mu^2)^{-1}_{\alpha\beta}\quad (21.2.21)
$$


### Step 1: Identifying the momentum space operator $D(k)$ for the scalar field Extract the quadratic terms for the scalar field $\phi'_n$ (denoted as $L_{\phi'}$) from Eq. (21.2.14).


$$
L_{\phi'}=-\frac{1}{2}\sum_n \partial_\mu \phi'_n \partial^\mu \phi'_n - \frac{1}{2}\sum_{n,m} M^2_{\text{full}, nm} \phi'_n \phi'_m
$$

By integrating by parts ($\partial_\mu \phi' \partial^\mu \phi' \to -\phi' \Box \phi'$), we obtain:

$$
L_{\phi'} = -\frac{1}{2}\sum_{n,m} \phi'_n \left( -\Box \delta_{nm} + M^2_{\text{full}, nm} \right) \phi'_m
$$

Following the textbook's convention, transforming to momentum space ($\partial_\mu \to ik_\mu, \Box \to -k^2$) turns the propagator into the inverse matrix $\Delta(k) = D^{-1}(k)$ of the operator $D(k)$:
$$D(k) = k^2 I + M^2_{\text{full}}$$

### Step 2: Decomposition of the mass matrix and its properties
From the context of Eqs. (21.2.16) and (21.2.19), the full mass matrix $M^2_{\text{full}}$ can be separated into a "potential-derived term" and a "gauge-fixing derived term." (*Note: There is a typo in Eq. (21.2.16) of the textbook with a coefficient of $1/2$, but it must correctly be $\xi$ to be consistent with the eigenvalue equation (21.2.19)*).
$$M^2_{\text{full}} = \tilde{M}^2 - \xi F F^T$$
Here, the matrix components are defined as follows:
*   $\tilde{M}^2_{nm} = \frac{\partial^2 P(\phi)}{\partial\phi_n\partial\phi_m}\big|_{\phi=v}$
*   $F_{n\alpha} = (t_\alpha v)_n$

From Eqs. (21.2.15) and (21.2.18), these have the following important properties:
1.  **Zero eigenvalues:** $\tilde{M}^2 F = 0$ (along the Nambu-Goldstone boson directions)
2.  **Vector boson mass:** $(F^T F)_{\alpha\beta} = \sum_n (t_\alpha v)_n (t_\beta v)_n = -\mu^2_{\alpha\beta}$  (Since $t_\alpha$ is anti-Hermitian, the sum)


### Step 3: Calculating the inverse matrix using the Woodbury matrix identity
The propagator we want to find is $\Delta(k) = (k^2I+\tilde{M}^2-{\xi}FF^T)^{-1}$.
We apply the **Woodbury matrix identity** to this:

$$
(A + U C V)^{-1} = A^{-1} - A^{-1} U (C^{-1} + V A^{-1} U)^{-1} V A^{-1}
$$

We assign each matrix as follows:
*   $A = k^2 I + \tilde{M}^2$
*   $U = F, \quad V = F^T$
*   $C = -\xi I$

** ① Calculating $A^{-1} F$:**
Since $\tilde{M}^2F= 0$, $AF=(k^2I+\tilde{M}^2)F=k^2 F$.
Thus, multiplying both sides by $A^{-1}$ gives $A^{-1} F = \frac{1}{k^2} F$.
(Similarly, $F^T A^{-1} = \frac{1}{k^2} F^T$)

**② Calculating the bracketed term $(C^{-1} + V A^{-1} U)$:**
$C^{-1} + F^T (A^{-1} F) = -\frac{1}{\xi}I + \frac{1}{k^2} F^T F$
Substituting the property $F^T F = -\mu^2$ and simplifying:
$$= -\frac{1}{\xi}I - \frac{1}{k^2}\mu^2 = -\frac{1}{\xi k^2} (k^2 I + \xi \mu^2)$$

**③ Finalizing the propagator $\Delta(k)$:**
The inverse matrix of ② is $- \xi k^2 (k^2 I + \xi \mu^2)^{-1}$. Substituting this into the identity:
$$ \Delta(k) = A^{-1} - \left(\frac{1}{k^2}F\right) \left[ - \xi k^2 (k^2 I + \xi \mu^2)^{-1} \right] \left(\frac{1}{k^2}F^T\right) $$
The minus signs and $k^2$ cancel out, yielding:
$$\Delta(k) = A^{-1} + \xi F \frac{1}{k^2} (k^2 I + \xi \mu^2)^{-1} F^T$$

## Conclusion
Writing down the obtained matrix expression component by component, we get:
$$\Delta_{nm}(k) = (k^2 + \tilde{M}^2)^{-1}_{nm} + \xi \sum_{\alpha\beta}(t_\alpha v)_n (t_\alpha v)_m (k^2)^{-1} (k^2 + \xi \mu^2)^{-1}_{\alpha\beta}$$
*Note: The $M^2$ in the first term of Eq. (21.2.21) in the text specifically refers only to the potential-derived mass matrix $\tilde{M}^2 = \frac{\partial^2 P}{\partial\phi^2}$. With this understood,* **Eq. (21.2.21) is fully derived**.
 
#### Why was the Woodbury matrix identity used?

In the context of **deriving this propagator (Eq. 21.2.21)**, there are three main reasons for using the Woodbury matrix identity:

**1. To naturally deduce the structure of the target Eq. (21.2.21) (a sum of two terms)**
Eq. (21.2.21) takes the form of a sum of a "physical mass term (1st term)" and a "gauge-fixing correction term (2nd term)." The Woodbury identity, $(A+UCV)^{-1} = A^{-1} + (\text{correction term})$, directly yields this separated structure.

**2. To dramatically leverage the property of Goldstone bosons ($\tilde{M}^2 F = 0$)**
In applying the formula, the calculation $(k^2 I + \tilde{M}^2)^{-1} F$ arises. By employing the physical property that "there is no mass in the Goldstone direction ($\tilde{M}^2 F = 0$)", the complex matrix inversion is instantly simplified to just $\frac{1}{k^2}F$. Trying to compute the inverse matrix directly makes it difficult to incorporate this property effectively.

**3. The matrix took the form of "Base Matrix + Outer Product Term"**
The operator we wanted to invert, $k^2 I + \tilde{M}^2 - \xi F F^T$, was precisely in the standard form to which the Woodbury identity can be applied (a matrix $A$ plus an outer product $F F^T$ of vectors/matrices).

### Are there other examples where the Woodbury identity is applied to derive a propagator?

Yes, in Quantum Field Theory and Condensed Matter Physics, there are several instances where the Woodbury matrix identity (or its special case, the Sherman-Morrison formula) is used to compute propagators (Green's functions).

In physics, this identity appears not merely as a mathematical trick, but as a natural algebraic structure that describes **"how the entire system responds when a specific interaction or constraint is applied to a free state (base system)."**

Here are some representative examples:

#### 1. Derivation of Vector (Gauge) Field Propagators
The closest analogue to this scalar field example is the calculation of the photon or weak boson propagator in general gauges (such as the $R_\xi$ gauge).
The kinetic term in the Lagrangian usually has the structure $-(g_{\mu\nu}k^2 - k_\mu k_\nu)$, to which the gauge-fixing term $-\frac{1}{\xi} k_\mu k_\nu$ is added.
$$ D_{\mu\nu}^{-1}(k) = -(g_{\mu\nu}k^2 - k_\mu k_\nu) - \frac{1}{\xi} k_\mu k_\nu $$
The term $k_\mu k_\nu$ here is an outer product (tensor product) of the vector $k$ with itself, making it a **rank-1 matrix**. The process of finding its inverse $D_{\mu\nu}(k)$ to derive the propagator is mathematically a direct application of the Woodbury identity (Sherman-Morrison formula).

#### 2. Impurity Scattering and the T-matrix
This frequently appears in Condensed Matter Physics (solid-state electron theory) when determining the electron propagator $G$ in a clean crystal with a single impurity (potential $V$).
If the base free-electron propagator is $G_0$, the Dyson equation is written in matrix form as:
$$ G = G_0 + G_0 V G $$
If the impurity potential $V$ is localized to specific sites (i.e., the matrix $V$ is low-rank), this equation can be solved analytically to yield:
$$ G = G_0 + G_0 T G_0 \quad \left( T = V(1 - G_0 V)^{-1} \right) $$
This expression using the T-matrix structurally matches the Woodbury identity perfectly.

#### 3. Dyson Equation and Self-Energy (Separable Potentials)
In general, the propagator $G$ of an interacting system is written using the free propagator $G_0$ and the self-energy $\Sigma$ as $G^{-1} = G_0^{-1} - \Sigma$.
If the self-energy $\Sigma$ takes a "separable" form, meaning it can be written as an outer product of vector functions like $\Sigma = \lambda |u\rangle \langle v|$ (often seen in effective interactions in nuclear physics),
$$G = G_0 + G_0 |u\rangle \frac{\lambda}{1 - \lambda \langle v | G_0 | u \rangle} \langle v | G_0$$
This allows the exact propagator to be written down explicitly using the Woodbury identity.

#### 4. Random Phase Approximation (RPA) and Dielectric Function Calculations
In many-body electron systems, when summing up Coulomb interactions infinitely (summation of ring diagrams) via RPA, this matrix inversion formula is utilized in the process of calculating the effective propagator (effective interaction). Here again, the identity is applied in the form of "Base response function" + "Correction due to Coulomb interaction (which also features an outer product structure)."



**Summary**
In Quantum Field Theory, scenarios where "a part of a matrix takes the form of a vector outer product (tensor product)" arise frequently in situations like:
*   **Gauge-fixing terms** (manipulating a specific direction = longitudinal components only)
*   **Localized interactions** (occurring only between specific sites or states)
*   **Specific symmetry breakings in mass matrices** (the Goldstone boson direction in this context)

When analytically decoupling these to compute propagators, the Woodbury matrix identity serves as a highly powerful and natural tool.

---
- Woodbury matrix identity
https://en.wikipedia.org/wiki/Woodbury_matrix_identity#cite_note-higham-5
