# Evaluation of Eigenvalues of the Schrödinger Equation with the Manning–Rosen Potential: An Exhaustive Review

## 1. Introduction

The Manning–Rosen (MR) potential is one of the most widely used short-range, exponential-type molecular potentials in quantum mechanics. It was originally introduced to model the vibrational and rotational structure of diatomic molecules, and it has since become a standard testbed for approximate analytical methods used to solve the radial Schrödinger equation (and its relativistic counterparts, the Klein–Gordon and Dirac equations) for arbitrary orbital angular momentum quantum number $\ell$.

The potential is attractive to researchers for two main reasons:

1. It reduces, in various limits, to several other important potentials (Hulthén, Coulomb, Yukawa, Kratzer), making it a convenient "umbrella" model.
2. Unlike the exactly solvable $s$-wave ($\ell = 0$) case, the full $\ell \neq 0$ radial equation contains a centrifugal term $\ell(\ell+1)/r^2$ that cannot be handled exactly when combined with the MR potential's exponential form — this has driven decades of methodological development around *approximation schemes for the centrifugal term* and *exact solution techniques* for second-order differential equations of hypergeometric type.

This review surveys the mathematical formulation of the problem, the principal solution techniques used to evaluate the energy eigenvalues, the main results obtained, extensions to relativistic wave equations and other combined potentials, and a representative bibliography of the literature.

---

## 2. Definition of the Manning–Rosen Potential

The Manning–Rosen potential is commonly written as

$$V_{MR}(r) = \frac{\hbar^2}{2\mu b^2}\left[\frac{\alpha(\alpha-1)e^{-2r/b}}{\left(1-e^{-r/b}\right)^2} - \frac{A\, e^{-r/b}}{1-e^{-r/b}}\right]$$

where:
- $\mu$ is the reduced mass of the diatomic system,
- $b$ is a range (screening) parameter related to the equilibrium bond length,
- $\alpha$ is a dimensionless parameter,
- $A$ is a potential-depth parameter, often related to the dissociation energy.

An equivalent, frequently used two-parameter exponential form is

$$V_{MR}(r) = -A_1\,\frac{e^{-\alpha r}}{1-e^{-\alpha r}} + A_2\,\frac{e^{-2\alpha r}}{\left(1-e^{-\alpha r}\right)^2}.$$

Depending on the choice of $\alpha(\alpha - 1)$ and $A$, the MR potential reduces to:
- the **Hulthén potential** (when the quadratic exponential term vanishes),
- the **Yukawa (screened Coulomb) potential** in appropriate limits,
- the **Kratzer/Coulomb-like potential** for small $r/b$.

---

## 3. The Radial Schrödinger Equation

Separating the three-dimensional time-independent Schrödinger equation in spherical coordinates via $\psi(r,\theta,\phi) = r^{-1}R_{n\ell}(r)Y_{\ell m}(\theta,\phi)$ gives the radial equation

$$\frac{d^2 R_{n\ell}(r)}{dr^2} + \left[\frac{2\mu}{\hbar^2}\Big(E_{n\ell} - V_{MR}(r)\Big) - \frac{\ell(\ell+1)}{r^2}\right]R_{n\ell}(r) = 0.$$

- For **$\ell = 0$ (s-wave)**, the equation is exactly solvable in closed form, and $R_{n0}(r)$ can be expressed via hypergeometric functions.
- For **$\ell \neq 0$**, the presence of $1/r^2$ alongside the exponential MR terms prevents an exact analytic solution. The equation is only solvable after the centrifugal term is approximated by a function of the same exponential variable $x = e^{-r/b}$ (or $e^{-\alpha r}$), so that the whole equation can be cast into a Gauss-type hypergeometric (or generalized hypergeometric) differential equation.

---

## 4. Approximation Schemes for the Centrifugal Term

Since the crux of the $\ell$-wave problem is handling $\ell(\ell+1)/r^2$, the literature has developed a family of related approximations, all expanding $1/r^2$ in powers of $e^{-r/b}$:

| Scheme | Approximate form | Notes |
|---|---|---|
| **Greene–Aldrich approximation** | $\dfrac{1}{r^2}\approx \dfrac{1}{b^2}\dfrac{e^{-r/b}}{(1-e^{-r/b})^2}$ (or similar) | The earliest and most widely used scheme (1976), valid for short-range potentials ($r/b \ll 1$). |
| **Pekeris-type approximation** | Expansion around the potential minimum via a different exponential ansatz | Improves accuracy at larger $\ell$ and $\alpha$. |
| **Improved (Ikhdair–Sever) scheme** | A refined combination that better reproduces $1/r^2$ over a wider $r$ range | Reported to significantly increase numerical agreement with exact numerical integration, especially for larger $n$ and $\ell$. |
| **Combined Greene–Aldrich/Pekeris scheme with tunable parameters $\lambda,\nu$** | Interpolates between the two classical schemes | Recovers both limiting cases for special parameter choices; used in recent (2020s) ro-vibrational studies. |

The accuracy of the eigenvalues obtained by any exact-solution method (NU, AIM, SUSYQM, etc.) is therefore *entirely contingent* on the quality of the chosen centrifugal approximation; much of the comparative literature is devoted to benchmarking these schemes against numerical (shooting-method) solutions of the exact radial equation.

---

## 5. Principal Analytical Methods Used to Evaluate the Eigenvalues

### 5.1 Nikiforov–Uvarov (NU) Method
The dominant technique in this literature. The radial equation, after the centrifugal approximation and a change of variable $x=e^{-r/b}$, is transformed into the generalized hypergeometric-type equation

$$\psi''(x) + \frac{\tilde\tau(x)}{\sigma(x)}\psi'(x) + \frac{\tilde\sigma(x)}{\sigma^2(x)}\psi(x)=0,$$

which is solved using the NU algebraic machinery (parametric NU method), yielding closed-form quantized energy expressions and wavefunctions expressed in terms of **Jacobi polynomials** or hypergeometric functions ${}_2F_1$.

### 5.2 Asymptotic Iteration Method (AIM)
An alternative to NU that iterates a linear second-order ODE until a "termination" (quantization) condition is met. Widely used by Ikhdair and co-workers to cross-check NU results for the MR potential; typically implemented with several Pekeris-type approximation variants for benchmarking.

### 5.3 Supersymmetric Quantum Mechanics (SUSYQM) / Shape Invariance
The effective potential is factorized using superpotentials $W(r)$ satisfying the Riccati equation, and the shape-invariance condition is exploited to generate the energy spectrum algebraically. Produces eigenvalue formulas identical to NU/AIM results (a useful consistency check), and naturally extends to constructing ladder operators and (in select works) coherent states.

### 5.4 Exact/Series and Tridiagonal (Recursion) Methods
- **Exact $\ell=0$ solution**: hypergeometric-function closed form without any centrifugal approximation.
- **Tridiagonal representation approach** (Alhaidari and co-workers): represents the wave operator in a square-integrable basis so that the recursion relation for expansion coefficients is a three-term relation, and diagonalizes it to obtain the exact discrete spectrum; wavefunctions again expressed via Jacobi polynomials.
- **WKB / improved quantization rule**: semiclassical evaluation of eigenvalues, useful as an independent, non-algebraic check, and effective at higher quantum numbers.

### 5.5 Other/Numerical Methods
- Direct numerical integration (shooting method) of the exact ($\ell\neq0$) radial equation, used almost universally as a benchmark against which all approximate analytic eigenvalue formulas are validated.
- Extended/generalized methods such as the "functional analysis method," proper quantization rule, and formula method, each reproducing the standard energy expression via different formal routes.

---

## 6. Representative Structure of the Eigenvalue Formula

Across the NU/AIM/SUSYQM derivations (using the Pekeris-type or Greene–Aldrich centrifugal approximation), the bound-state energies take the generic closed form:

$$E_{n\ell} = \Big[\alpha(\alpha-1)+A\Big]\frac{\hbar^2}{2\mu b^2} \;-\; \frac{\hbar^2}{8\mu b^2}\,\frac{\Big[\big(n+\tfrac12\big)+\tfrac12\sqrt{1+4\alpha(\alpha-1)+4\zeta(\ell)}\,\Big]^2+\alpha(\alpha-1)+A}{\Big[\big(n+\tfrac12\big)+\tfrac12\sqrt{1+4\alpha(\alpha-1)+4\zeta(\ell)}\,\Big]^2}$$

where $\zeta(\ell)$ is a function of $\ell(\ell+1)$ that depends on which centrifugal approximation scheme was adopted (it reduces to $\ell(\ell+1)$ itself in the exact $s$-wave limit). Different papers present algebraically equivalent but notationally distinct versions of this expression, depending on the definition of the potential parameters and the specific approximation used.

Key qualitative features consistently reported:
- Energies are discrete and negative for bound states (as expected for a short-range attractive well), becoming less negative (approaching the dissociation limit) with increasing $n$ and $\ell$.
- Numerical eigenvalues for real diatomic molecules (HCl, CH, LiH, CO, H₂, ScH, TiH, VH, CrH, etc.) are typically tabulated and compared against experimental/other-method values, generally agreeing to 4–5 decimal digits for small $\ell$ and short potential range, with growing discrepancy for large $\ell$ or large screening parameter $\alpha$ — this discrepancy is a direct diagnostic of the underlying centrifugal-term approximation's accuracy.

---

## 7. Extensions and Combined Potentials

The MR-potential eigenvalue problem has been extended in numerous directions:

**A. Relativistic wave equations**
- **Klein–Gordon equation** with MR (scalar/vector) potentials, including MR-plus-Yukawa and MR-plus-Coulomb-like mixtures, solved via parametric NU with Pekeris-like approximation of the Coulomb-type term.
- **Dirac equation** with MR-type potentials under spin and pseudospin symmetry, often combined with a Coulomb-like or Hulthén-like tensor interaction, solved via NU or SUSYQM.

**B. Potential combinations ("superposition" potentials)**
- Manning–Rosen **plus Hulthén** potential.
- Manning–Rosen **plus (shifted) Deng–Fan** potential.
- Manning–Rosen **plus Yukawa** / **class of Yukawa** potentials (including inversely quadratic Yukawa).
- Manning–Rosen **plus ring-shaped** (non-central) potentials — extends the problem to include an angle-dependent term, requiring separate treatment of the angular equation.
- **Schioberg plus Manning–Rosen** potential.
- **q-deformed / Pöschl–Teller plus Manning–Rosen** non-central potentials in D dimensions.

**C. Higher-dimensional (D-dimensional) treatments**
Several works generalize the radial equation to arbitrary spatial dimension $D$, recovering the standard 3D results as a special case and studying the dimensional dependence of the spectrum.

**D. Thermodynamic and information-theoretic applications**
Once the energy spectrum $E_{n\ell}$ is known in closed form, it is used to construct the partition function $Z(\beta)=\sum_n e^{-\beta E_n}$ and derive thermodynamic functions (vibrational mean energy, free energy, entropy, specific heat) for diatomic molecules, as well as Fisher information and Shannon-entropy measures characterizing the localization of the corresponding eigenstates.

**E. Position-dependent mass formulations**
Some studies solve the MR-potential problem with a spatially varying (position-dependent) mass $m(r)$, relevant to semiconductor heterostructure and effective-mass modeling contexts.

---

## 8. Summary Table of Methods

| Method | Type of solution | Typical output form | Cross-checked against |
|---|---|---|---|
| Exact solution ($\ell=0$) | Exact | Hypergeometric function | — |
| Nikiforov–Uvarov (NU) | Approximate ($\ell\neq0$) | Jacobi polynomials / ${}_2F_1$ | AIM, SUSYQM, numerical |
| Asymptotic Iteration Method (AIM) | Approximate | Closed-form recursion termination | NU, numerical |
| SUSYQM / shape invariance | Approximate | Same algebraic form as NU | NU, AIM |
| Tridiagonal (Alhaidari) representation | Quasi-exact | Jacobi polynomial expansion, diagonalized recursion | Numerical |
| WKB / quantization rule | Semiclassical | Bohr–Sommerfeld-type quantization integral | Exact/NU at large $n$ |
| Direct numerical integration (shooting) | Numerical | Tabulated $E_{n\ell}$ | Used as ground truth |

---

## 9. Conclusion

Sixty-plus years after Manning and Rosen first proposed the potential to model diatomic vibrational spectra, the eigenvalue problem for the Manning–Rosen potential remains a fertile and still-active area of mathematical and molecular physics research. The central technical obstacle — the non-separability introduced by the centrifugal term for $\ell \neq 0$ — has motivated an entire ecosystem of complementary techniques (NU, AIM, SUSYQM, tridiagonal/recursion methods, WKB), all of which converge on structurally similar closed-form eigenvalue expressions once a centrifugal approximation is chosen. Ongoing work continues to refine the approximation schemes themselves, extend the potential to relativistic wave equations and multi-term potential combinations, and exploit the resulting spectra for thermodynamic and information-theoretic characterization of diatomic molecules.

---

## 10. List of Publications

Below is a representative (non-exhaustive) bibliography of key publications on the evaluation of eigenvalues of the Schrödinger (and related relativistic) equations for the Manning–Rosen potential and its variants.

### Foundational / Original Potential
1. Manning, M. F., & Rosen, N. (1933). A potential function for the vibrations of diatomic molecules. *Physical Review*, 44, 953.
2. Greene, R. L., & Aldrich, C. (1976). Variational wave functions for a screened Coulomb potential. *Physical Review A*, 14, 2363.

### Nikiforov–Uvarov Method Applications
3. Ikhdair, S. M., & Sever, R. (2008). An improved approximation to *l*-wave bound states of the Manning-Rosen potential by Nikiforov-Uvarov method. *arXiv:0807.2085*.
4. Ikhdair, S. M. (2011). Approximated *l*-states of the Manning-Rosen potential by Nikiforov-Uvarov method. *arXiv:1110.3153*.
5. Ikhdair, S. M. (2011/2018). On the bound-state solutions of the Manning-Rosen potential including improved approximation to the orbital centrifugal term. *arXiv:1104.0301*.
6. Ikhdair, S. M. (2012). Approximate *l*-States of the Manning-Rosen Potential by Using Nikiforov-Uvarov Method. *International Scholarly Research Notices (ISRN Mathematical Physics)*, 2012, Article 201525.
7. Diaf, A., & Chouchaoui, A. (2011). *L*-states of the Manning-Rosen potential with an improved approximate scheme and Feynman path integral formalism. *Physica Scripta*, 84(1), 015004.
8. Qiang, W. C., & Dong, S. H. (2009). The Manning–Rosen potential studied by a new approximate scheme to the centrifugal term. *Physica Scripta*, 79, 045004.
9. Wei, G. F., Long, C. Y., & Dong, S. H. (2008). The scattering of the Manning-Rosen potential with centrifugal term. *Physics Letters A*, 372(15), 2592–2596.
10. (2021). Ro-vibrational energy analysis of Manning-Rosen and Pöschl-Teller potentials with a new improved approximation in the centrifugal term. *European Physical Journal Plus*, 136, 449; also *arXiv:2205.10313*.
11. Analytical solutions of the Klein–Gordon equation for Manning–Rosen potential with centrifugal term through Nikiforov–Uvarov method. *(Journal article, ResearchGate record)*.

### Asymptotic Iteration Method (AIM)
12. Bound state solutions of the Manning-Rosen potential (via AIM). *arXiv:1207.5135*.

### Exact / Semiclassical / Series Methods
13. Exact Solution to the Schrödinger Equation with Manning-Rosen Potential via WKB Approximation Method. *(Conference/journal paper, Academia.edu record)*.
14. Min-Cang, Z., & Bo, A. (2010). Analytical Solutions of the Manning-Rosen Potential in the Tridiagonal Program. *Chinese Physics Letters*, 27(11), 110301.
15. Exact Quantized Momentum Eigenvalues and Eigenstates of a General Potential Model (including time-dependent Manning-Rosen potential). *arXiv:2007.13836*.
16. PT/Non-PT Symmetric and Non-Hermitian Pöschl-Teller-Like Solvable Potentials via Nikiforov-Uvarov Method (includes generalized Manning-Rosen form). *arXiv:quant-ph/0610260*.

### Supersymmetric Quantum Mechanics (SUSYQM)
17. Qiang, W.-C., et al. (2009). Solutions of the Schrödinger equation for the Manning–Rosen potential via supersymmetric shape invariance approach. *Modern Physics Letters A*, 24(4).
18. Analytical Solutions of the Schrödinger Equation for the Manning-Rosen plus Hulthén Potential Within SUSY Quantum Mechanics. *Journal of Physics: Conference Series*, 965, 012001 (2018).

### Relativistic (Klein–Gordon / Dirac) Extensions
19. Ita, B. I., et al. (2017). Bound State Solutions of the Klein-Gordon Equation with Manning-Rosen Plus Yukawa Potential Using Pekeris-Like Approximation of the Coulomb Term and Parametric Nikiforov-Uvarov. *Physical Science International Journal*, 15(3), 1–6.
20. Bound State Solutions of the Schrödinger's Equation with Manning-Rosen Plus a Class of Yukawa Potential Using Pekeris-like Approximation and Parametric Nikiforov-Uvarov. *(Journal article, Academia.edu record)*.
21. Solutions to the Dirac Equation for Manning-Rosen Plus Shifted Deng-Fan Potential and Coulomb-Like Tensor Interaction Using Nikiforov-Uvarov Method. *(Journal article, Academia.edu record, 2018)*.
22. Maghsoodi, E., Hassanabadi, H., & Zarrinkamar, S. (2012). Spectrum of Dirac equation under Deng-Fan scalar and vector potentials and a Coulomb tensor interaction by SUSYQM. *Few-Body Systems*, 53(3-4), 525–538. (Methodologically parallel to MR-potential treatments.)
23. D-dimensional Dirac equation of q-deformed modified Pöschl-Teller plus Manning-Rosen non-central potential solved using SUSYQM. Suparmi, A., Cari, C., & Pratiwi, B. N. *(Conference proceedings)*.

### Combined / Generalized Potentials and Applications
24. Eigen Solution and Thermodynamic Properties of Manning Rosen Plus Exponential Yukawa Potential. *arXiv:2304.08219*.
25. Thermomagnetic properties and its effects on Fisher entropy with Schioberg plus Manning-Rosen potential (SPMRP) using Nikiforov-Uvarov functional analysis (NUFA) and SUSYQM methods. *(PMC open-access article)*.
26. Thermodynamics properties study of diatomic molecules with q-deformed modified Pöschl-Teller plus Manning-Rosen non-central potential in D dimensions using SUSYQM approach. Suparmi, A., Cari, C., & Pratiwi, B. N.
27. Oyewumi, K. J., Oluwadare, O. J., Sen, K. D., & Babalola, O. A. (2013). Bound state solutions of the Deng-Fan molecular potential with the Pekeris-type approximation using the Nikiforov–Uvarov (N–U) method. *Journal of Mathematical Chemistry*, 51(3), 976–991. (Comparative reference potential in the same solution family.)

> **Note on sourcing:** Several entries above are drawn from preprint servers (arXiv), aggregator/repository copies (Academia.edu, ResearchGate), and abstracting services (ADS, PMC); where a formal journal citation could be independently verified it is given, otherwise the accessible record is cited. Readers should verify final published versions (volume/page/DOI) via the journal's official site before formal citation.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Manning–Rosen potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
