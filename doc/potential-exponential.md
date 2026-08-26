# Evaluation of Eigenvalues of the Schrödinger Equation with an Exponential Potential: A Review

## 1. Introduction and Scope

The family of "exponential-type" potentials occupies a special place in quantum mechanics because it interpolates between exactly solvable, quasi-exactly solvable, and genuinely non-solvable problems, while at the same time modelling real physical situations: repulsive molecular walls, screened Coulomb interactions in plasmas and solids, diatomic vibrational potentials (Morse, Hulthén, Woods–Saxon, Deng–Fan, Manning–Rosen, Rosen–Morse, Wood–Saxon-type nuclear mean fields), and confinement models in condensed-matter heterostructures. This review surveys the analytical, semi-analytical, and numerical machinery that has been developed to compute the eigenvalues (bound-state energies, resonances, and virtual-state poles) of the one-dimensional and radial Schrödinger equation with a purely or partly exponential potential, and situates the "pure" exponential potential

$$V(x) = -A e^{-\alpha x}, \qquad \psi''(x) + \left(E - A e^{-\alpha x}\right)\psi(x) = 0,\quad \psi(0)=0$$

within the broader landscape of exponential-type potentials used in the literature.

---

## 2. The Pure Exponential Potential: Exact Reduction to Bessel Functions

### 2.1 Reduction of the problem

The simplest and most studied member of the family is the one-sided exponential potential defined on the half-line $x\in[0,\infty)$ with a hard wall at the origin, $\psi(0)=0$. Rescaling $q=\alpha x$, $\epsilon = E/\alpha^2$, $\lambda = A/\alpha^2$ reduces the equation to a single-parameter form

$$\Phi''(q) + \left(\epsilon - \lambda e^{-q}\right)\Phi(q) = 0 .$$

A further substitution $z = 2\sqrt{-\lambda}\,e^{-q/2}$ transforms this exactly into **Bessel's equation**

$$z^2 Y''(z) + zY'(z) + (z^2-\nu^2)Y(z)=0, \qquad \nu^2=-4\epsilon,$$

so that the general solution satisfying the origin boundary condition is a combination of Bessel functions $J_{\pm\nu}(z)$ of the first kind. Demanding decay as $q\to\infty$ (bound states) forces the eigenvalue condition

$$J_{\nu}\!\left(2\sqrt{-\lambda}\right)=0, \qquad \mathrm{Re}(\nu)>0,$$

i.e. **the bound-state (and resonance/virtual-state) energies are given by the zeros of a Bessel function of order $\nu=2\sqrt{-\epsilon}$**. This is the classical result (traceable to early work on exponential/Morse-type molecular walls and later systematized for scattering theory) that reduces the entire eigenvalue problem to root-finding for Bessel functions, and the roots of this transcendental equation are simultaneously poles of the associated scattering amplitude. The same Bessel-function structure underlies the **repulsive exponential potential** $V=\lambda e^{-r}$ and the **exponential wall** $V=\lambda e^{r}$, whose *complex* eigenvalues (resonances) are obtained from the same equation analytically continued to complex $\nu$.

### 2.2 Numerical evaluation of the Bessel-zero condition

Because $J_\nu(2\sqrt{-\lambda})=0$ is transcendental in $\nu$ (equivalently in $\epsilon$) for generic $\lambda$, practical evaluation of eigenvalues still requires numerical root-finding or specialized series/continued-fraction techniques, particularly when $\nu$ (and hence $\epsilon$) is required to be complex, as happens for resonance and virtual states. Two complementary approaches dominate the literature:

- **Direct numerical solution of the Bessel zero condition** using asymptotic expansions or continued-fraction representations of $J_\nu$, valid for real bound states.
- **The Riccati–Padé Method (RPM)**, which avoids explicit reference to Bessel functions altogether and instead expands the logarithmic derivative of the wavefunction in a Taylor/Padé series about the origin. Substituting $f(q)=\Phi'(q)/\Phi(q) - 1/q$ into the Schrödinger equation yields a Riccati equation
$$f'(q) + \frac{2f(q)}{q} - f(q)^2 + \lambda e^{-q} - \epsilon = 0,$$
whose formal Taylor series $f(q)=\sum_j f_j q^j$ has coefficients that are polynomials in $\epsilon$. Padé approximants (specifically Hankel-determinant sequences) built from these coefficients converge to the exact complex eigenvalues, including resonance and antibound (virtual) states, with high accuracy and without needing to impose an asymptotic boundary condition numerically. This method has been shown capable of resolving subtleties that earlier applications of the same technique got wrong — the RPM's original treatment of the repulsive exponential potential produced *incorrect* resonance energies, later corrected by careful analytic continuation and comparison with the exact Bessel-zero solutions for both the repulsive potential and the exponential wall.

### 2.3 Key qualitative results

- For the repulsive exponential potential $\lambda e^{-r}$ ($\lambda>0$), complex "eigenvalues" correspond to resonance/antibound poles of the Bessel-function scattering amplitude; there are no genuine bound states since the potential is not confining.
- For the exponential *wall* $\lambda e^{r}$ ($\lambda>0$), which is confining, the discrete complex eigenvalues obtained by continuing the same formalism tend, in the limit $\lambda\to\infty$, either to the resonance energies of the repulsive exponential potential or to real rational numbers — a non-trivial asymptotic connection between the two problems that was only fully clarified in recent work reconciling earlier RPM calculations with the exact analytic structure.
- For the attractive pure exponential well $V=-ge^{-x}$, the negative (bound-state) eigenvalues for the $s$-wave ($l=0$) sector reduce exactly to the same Bessel-zero condition, $J_{2\sqrt{-\epsilon(g)}}(2\sqrt{g})=0$; however, this implicit relation is analytically "intractable" for practical spectroscopic use, motivating semi-analytical energy formulas valid for arbitrary radial and angular-momentum quantum numbers $(n,l)$ (see §4).

---

## 3. Exactly and Quasi-Exactly Solvable Exponential-Type Potentials Beyond the Pure Case

A large body of work extends the "pure exponential" case to richer exponential-type potentials that remain exactly or quasi-exactly solvable, generally by mapping the Schrödinger equation onto hypergeometric-, confluent-hypergeometric-, or Heun-type differential equations:

- **Morse potential** $V(r)=D\left(e^{-2a(r-r_e)}-2e^{-a(r-r_e)}\right)$: the archetypal exactly solvable exponential-type diatomic potential; for $l=0$ it reduces to the Coulomb-like/Laguerre problem exactly, while $l\neq0$ requires an approximation (typically the **Pekeris approximation**) to the centrifugal term, after which it remains exactly solvable in terms of Laguerre polynomials.
- **Hulthén potential** $V(r) = -Ze^2\alpha e^{-\alpha r}/(1-e^{-\alpha r})$ and its **generalized/deformed** and $\mathcal{PT}$-symmetric variants: exactly solvable for $l=0$; approximate for $l\neq0$ via Nikiforov–Uvarov (NU) or asymptotic-iteration-method (AIM) treatments (the two dominant modern semi-analytical frameworks, see §4).
- **Woods–Saxon potential** (and $q$-deformed, PT-/non-PT-symmetric, generalized versions): a smoothed exponential step used extensively in nuclear physics, solved via NU and AIM.
- **Exponential (and "general exponential") screened Coulomb potentials**, $V(r) \propto -\tfrac{1}{r}\left[1+(1+br)e^{-2br}\right]$: solved via NU method for arbitrary angular momentum, applied to diatomic molecules (N$_2$, CO, NO); it is explicitly noted in this literature that **no closed-form energy expression exists** for the general exponential screened Coulomb potential in the Schrödinger, Klein–Gordon, or Dirac cases — only numerically evaluated eigenvalues via the NU polynomial machinery.
- **Deng–Fan, Manning–Rosen, Rosen–Morse, Tietz–Hua, Frost–Musulin, Wei, and Kratzer-related exponential-type molecular potentials**: all treated by essentially the same toolkit (NU / AIM / SUSYQM / shifted large-$N$ expansion) to obtain approximate closed-form or numerically tabulated vibrational-rotational eigenvalues.
- **Confluent-hypergeometric and Heun-family exponential potentials (Ishkhanyan and collaborators)**: a systematic program constructing new *exactly integrable* potentials expressed through the Lambert-$W$ function, whose exact solutions are written in terms of Gauss hypergeometric, confluent hypergeometric, or (bi/double-)confluent Heun functions. These include:
  - the short-range exponential potential with inverse-square-root singularity at the origin (solved via Gauss hypergeometric functions; supports only a finite number of bound states, with an explicit transcendental spectrum equation);
  - the Lambert-$W$ step-potential and singular Lambert-$W$ potential (confluent hypergeometric solutions);
  - the "third" five-parametric hypergeometric quantum-mechanical potential, and related new hypergeometric potentials extending the classical Natanzon/Heun classification scheme of exactly solvable potentials to new exponential forms.
- **Non-analytic confining exponential potential** $V(x)=g^2 e^{2|x|}$: shown to be exactly Bessel-function solvable by parity decomposition, giving infinitely many discrete bound states indexed by node number, in contrast to the finite spectra of short-range exponential wells.
- **Conditionally exactly solvable (CES) exponential-type potentials** (López-Ortega and others): potentials of exponential form for which exact solvability holds only for special parameter relations, extending the CES program historically developed for other potential classes.

---

## 4. Semi-Analytical Methods for Approximate Eigenvalues

Because most physically motivated exponential-type potentials with $l\neq 0$ (angular momentum/centrifugal barrier included) are **not** exactly solvable, the literature has developed several standard semi-analytical techniques, applied almost interchangeably across the whole exponential-type potential family:

### 4.1 Nikiforov–Uvarov (NU) Method
Reduces the radial Schrödinger equation, after a suitable coordinate transformation (often $s=e^{-\alpha r}$), to a generalized hypergeometric-type equation solvable via Rodrigues-type formulas, yielding eigenvalues expressed through Jacobi polynomials. Its **parametric generalization** is now the most widely used variant, applied to the Hulthén, Woods–Saxon, exponential screened Coulomb, Deng–Fan, Manning–Rosen, Yukawa, Gaussian, and Mie-type exponential potentials, typically requiring the **Greene–Aldrich (Pekeris-type) approximation** to handle the centrifugal $1/r^2$ term for $l\neq0$.

### 4.2 Asymptotic Iteration Method (AIM)
Introduced by Çiftçi, Hall, and Saad for general second-order homogeneous linear ODEs, AIM converts the eigenvalue problem into an iterative termination condition on ratio sequences $\lambda_n(x)/s_n(x)$ derived from the equation's coefficients. It has been applied extensively to exponential-type potentials: the Morse and rotating Morse potential (including generalized $q$-deformed Morse forms applied to real diatomic molecules such as Li$_2$), the deformed/generalized Hulthén potential, the hyperbolical potential family, and singular potentials more broadly, with specific attention paid to selecting the correct exponentially-decaying asymptotic wavefunction ansatz to stabilize convergence. AIM results are consistently benchmarked against SUSYQM, shifted large-$N$ (SE/MSE), hypervirial perturbation, variational, exact quantization rule (EQR), and tridiagonal $J$-matrix methods, generally showing excellent agreement.

### 4.3 Supersymmetric Quantum Mechanics (SUSYQM) and Shape Invariance
Applied to Morse-type and Hulthén-type exponential potentials by constructing superpotentials whose shape-invariance property yields the bound-state spectrum algebraically; historically one of the earliest systematic routes to eigenvalues of exponential-type potentials beyond direct series solution.

### 4.4 Shifted (and Modified Shifted) $1/N$ Expansion
A large-order perturbative expansion in inverse powers of a shifted principal/angular quantum number, historically important for rotating Morse-type and exponential screened Coulomb potentials, and still used as a comparison benchmark for newer AIM/NU calculations.

### 4.5 Exact Quantization Rule (EQR)
A WKB-adjacent phase-integral method that expresses the eigenvalue condition through a quantum correction term; applied to the rotating Morse potential and other exponential-type molecular potentials with good numerical accuracy.

### 4.6 Auxiliary Field Method (AFM)
Maps the exponential-potential problem onto an auxiliary (typically harmonic-oscillator or Coulomb) problem with a principal quantum-number-dependent effective coupling, producing simple analytic (if approximate) closed-form energy formulas valid for arbitrary $n,l$ — explicitly constructed to overcome the intractability of the exact implicit Bessel-zero relation $J_{2\sqrt{-\epsilon(g)}}(2\sqrt g)=0$ for the pure exponential potential.

### 4.7 Direct Numerical Methods
- **Numerov / Runge–Kutta shooting methods** on the radial or one-dimensional equation, historically the default brute-force approach, still used for validating analytic approximations.
- **Spectral Integral Equation Method (S-IEM)**: an alternative to finite-difference (Numerov) integration based on Chebyshev-polynomial expansion of the equivalent Lippmann–Schwinger integral equation, with a re-scaling procedure specifically designed to compensate for exponential growth/decay of the negative-energy Green's function — demonstrated to reach 6-significant-figure accuracy on weakly bound systems (e.g. the He–He dimer) with modest mesh sizes.
- **Riccati–Padé Method (RPM)** (§2.2): Hankel-determinant/Padé resummation of a Taylor series generated from a Riccati equation for the logarithmic derivative; capable of yielding complex (resonance/virtual-state) eigenvalues to high precision, including for potentials with no genuine bound states.
- **Basis-set diagonalization** (harmonic-oscillator, Laguerre, or $B$-spline bases; tridiagonal $J$-matrix representation) for rotating Morse-type exponential potentials.

---

## 5. Complex Eigenvalues: Resonances and Virtual States

A recurring and technically delicate theme is the computation of **complex** eigenvalues of exponential potentials — resonance and virtual/antibound-state poles — as opposed to genuine real bound-state energies:

- For the **repulsive exponential potential** and the **exponential wall**, complex eigenvalues arise as poles of the Bessel-function scattering amplitude and can be obtained either from the exact analytic Bessel-zero condition (continued to complex order) or via the Riccati–Padé method.
- A key subtlety, only resolved in recent work, is that naive application of the RPM to the repulsive exponential potential previously produced *wrong* resonance energies; the correct behavior — including the limiting relationship between the exponential-wall spectrum and the repulsive-exponential-potential resonances as the coupling $\lambda\to\infty$ — required careful reconciliation with the exact analytic (Bessel) solution.
- More generally, the decay/growth structure of Schrödinger eigenfunctions for potentials bounded from below — the Agmon-type exponential decay estimates for eigenfunctions below the essential spectrum — underlies why exponential potentials are natural testbeds for resonance theory: they provide one of the few settings where the *exact* location of resonance poles is analytically known (via Bessel functions), enabling rigorous benchmarking of approximate numerical resonance-finding techniques (complex scaling, Padé, RPM, etc.).

---

## 6. Relativistic Extensions

The same exponential-type potentials (Hulthén, Woods–Saxon, Morse, exponential screened Coulomb, Deng–Fan, Manning–Rosen, Yukawa combinations) have been extensively re-solved for the **Klein–Gordon**, **Dirac**, **Duffin–Kemmer–Petiau (DKP)**, and **spinless Salpeter** equations, generally under spin-symmetry or pseudospin-symmetry assumptions ($S(r)=\pm V(r)$), using the same NU/AIM toolkit together with Pekeris-type approximations for the centrifugal/spin–orbit terms. These works consistently report that, as in the non-relativistic case, exact closed-form spectra exist only for special sub-cases (e.g. $l=0$ or specific screening-parameter values), with the general case requiring numerical evaluation of NU-generated implicit eigenvalue equations. The **Feinberg–Horodecki equation** — a time-like analogue of the spatial Schrödinger equation obtained from the relativistic Feinberg equation — has also been solved for improved deformed exponential-type (temporal) potentials, yielding quantized *momentum* eigenvalues by the same algebraic methods, with proposed applications extending to biological/DNA-type space-like models.

---

## 7. Summary Table of Methods

| Method | Typical potentials treated | Nature of result | Handles $l\neq0$? | Handles complex/resonance eigenvalues? |
|---|---|---|---|---|
| Exact Bessel-function reduction | Pure exponential $-Ae^{-\alpha x}$, exponential wall, non-analytic $e^{2|x|}$ | Exact implicit (Bessel-zero) equation | Only $l=0$ generally | Yes (analytic continuation) |
| Riccati–Padé Method (RPM) | Pure/repulsive exponential, exponential wall | Numerically converged (near-exact) | $l=0$ formulation | Yes — core strength |
| Nikiforov–Uvarov (NU) / parametric NU | Hulthén, Woods–Saxon, Morse, Deng–Fan, exponential screened Coulomb, Gaussian, Mie-type | Approximate closed form (Jacobi polynomials) | Yes, via Pekeris/Greene–Aldrich approx. | Rarely |
| Asymptotic Iteration Method (AIM) | Morse (incl. $q$-deformed), Hulthén, hyperbolical, singular potentials | Approximate/exact closed form or numeric roots | Yes | Occasionally (with modified ansatz) |
| SUSYQM / shape invariance | Morse, Hulthén | Algebraic closed form | Limited | No |
| Shifted $1/N$ expansion (SE/MSE) | Rotating Morse, exponential screened Coulomb | Perturbative closed form | Yes | No |
| Exact Quantization Rule (EQR) | Rotating Morse | Semi-analytic (WKB-like) | Yes | No |
| Auxiliary Field Method (AFM) | Pure exponential, generalized exponential | Simple analytic formula (approximate) | Yes | No |
| Confluent-hypergeometric/Heun exact methods (Ishkhanyan et al.) | Lambert-$W$, short-range inverse-square-root exponential, new 5-parameter hypergeometric potentials | Exact transcendental spectrum equation | Depends on potential | Occasionally |
| Numerov/Runge–Kutta shooting | General/benchmarking | Fully numerical | Yes | With complex-scaling extensions |
| Spectral Integral Equation Method (S-IEM) | Weakly bound systems (e.g. He–He dimer) | Fully numerical, high precision | Yes | No (bound states) |

---

## 8. List of Publications

1. Fernández, F. M. — *Accurate calculation of the complex eigenvalues of the Schrödinger equation with an exponential potential* (arXiv:0712.3375).
2. Garcia, J. — *On the complex solution of the Schrödinger equation with exponential potentials*, Phys. Scr. (2024), IOPscience, doi:10.1088/1402-4896/ad21c5.
3. Dong, Shishan; García-Ravelo, J.; Dong, Shi-Hai — *Analytical approximations to the $l$-wave solutions of the Schrödinger equation with an exponential-type potential*, Phys. Scr. 76 (2007), doi:10.1088/0031-8949/76/4/019.
4. Silvestre-Brac, B.; et al. — *Auxiliary field method and analytical solutions of the Schrödinger equation with exponential potentials* (arXiv:0811.0287).
5. Rawitscher, G.; Koltracht, I. — *An economical method to calculate eigenvalues of the Schrödinger Equation* (arXiv:physics/0606030).
6. Sasaki, R.; Znojil, M. — *One-dimensional Schrödinger equation with non-analytic potential $V(x)=g^2\exp(2|x|)$ and its exact Bessel-function solvability*, J. Phys. A 49, 445303 (2016) (arXiv:1611.02467).
7. Ahmed, Faizuddin — *Topological Effects With Inverse Quadratic Yukawa Plus Inverse Square Potential on Eigenvalue Solutions* (arXiv:2305.04823).
8. Ita, Benedict I.; Ekuri, P.; Isaac, Idongesit O.; James, Abosede O. — *Bound state solutions of Schrödinger equation for a more general exponential screened Coulomb potential via Nikiforov–Uvarov method*, Quim. Nova / SciELO Brazil.
9. Ita, B. I.; et al. — *The Nikiforov–Uvarov-Functional Analysis (NUFA) Method: A New Approach for Solving Exponential-Type Potentials*.
10. Various authors (compiled in NUFA review) — *Bound-states solutions of the radial Schrödinger equation for a Gaussian potential within the framework of the Nikiforov–Uvarov method*.
11. Ikhdair, S. M.; Sever, R. — *Improved analytical approximation to arbitrary $l$-state solutions of the Schrödinger equation for the hyperbolical potentials* (personal communication / related NU literature).
12. Berkdemir, C.; Han, J. — Chem. Phys. Lett. 409, 203–207 (2005) [exponential-type potential, NU method].
13. Şimşek, M.; Eğrifes, H. — *Bound-state solutions of the one-dimensional $\mathcal{PT}$-symmetric generalized Hulthén potential* (foundational NU work referenced across the Hulthén/Woods–Saxon literature).
14. Rao, N. A.; Kagali, B. A. — Relativistic bound states of the exponential-type screened Coulomb potential via the one-dimensional Klein–Gordon equation.
15. (Bound states of the Dirac equation for the $\mathcal{PT}$-symmetric generalized Hulthén potential by the Nikiforov–Uvarov method) — arXiv:quant-ph/0507165.
16. (Relativistic and nonrelativistic bound states of the isotonic oscillator by Nikiforov–Uvarov method) — arXiv:1203.1736.
17. (Bound-States of the Spinless Salpeter Equation for the $\mathcal{PT}$-Symmetric Generalized Hulthén Potential by the Nikiforov–Uvarov Method) — arXiv:quant-ph/0605045.
18. (Polynomial Solution of $\mathcal{PT}$-/Non-$\mathcal{PT}$-Symmetric and Non-Hermitian Generalized Woods–Saxon Potential via Nikiforov–Uvarov Method) — arXiv:quant-ph/0507272.
19. (Duffin–Kemmer–Petiau particle in a vector exponential-like decaying field with any arbitrary $l$-state) — arXiv:1212.1574.
20. Ikhdair, S. M.; Sever, R.; et al. — *Solutions of Schrödinger and Klein–Gordon equations with Hulthén plus Inversely Quadratic exponential Mie-type potential*, Phys. Sci. Int. J. 19, 1–27 (2018) [Okon, I. B.; Popoola, O.; Isonguyo, C. N.; Antia, A. D.].
21. Aygun, M.; Bayrak, O.; Boztosun, I. — *Solution of the radial Schrödinger equation for the potential family using the asymptotic iteration method*, J. Phys. B: At. Mol. Opt. Phys. 40, 537 (2007).
22. Bayrak, O.; Boztosun, I. — *Bound state solutions of the Hulthén potential by using the asymptotic iteration method*, Phys. Scr. 76, 92 (2007).
23. Bayrak, O.; Boztosun, I. — *Analytical solutions to the Hulthén and the Morse potentials by using the asymptotic iteration method*, ScienceDirect (2006).
24. Bayrak, O.; Boztosun, I. — *Arbitrary $l$-state solutions of the rotating Morse potential by the asymptotic iteration method*, J. Phys. A 39, 22 (2006) (arXiv:nucl-th/0604042).
25. Ciftci, H.; Hall, R. L.; Saad, N. — *Asymptotic iteration method for eigenvalue problems*, foundational AIM reference (J. Phys. A).
26. *Morse potential eigen-energies through the asymptotic iteration method* — Darboux-transformation-based AIM study (ResearchGate).
27. Jourdani, R.; et al. — *Exact solutions for vibrational states with generalized $q$-deformed Morse potential within the asymptotic iteration method*, applied to the lithium (Li$_2$) molecule A$^1\Sigma_u^+$ state.
28. Falaye, B. J. — *Arbitrary $l$-state solutions of the hyperbolical potential by the asymptotic iteration method*.
29. Okon, I. B.; et al. — *Non-relativistic molecular modified shifted Morse potential system*, Scientific Reports (2022), doi:10.1038/s41598-022-19179-4.
30. (Asymptotic Iteration Method for singular potentials) — arXiv:0802.2072.
31. (Asymptotic iteration method for the inverse power potentials) — Eur. Phys. J. Plus (2021), doi:10.1140/epjp/s13360-021-01647-x.
32. Ishkhanyan, A. M. — *Exact solution of the Schrödinger equation for a short-range exponential potential with inverse square root singularity*, Eur. Phys. J. Plus 133, 83 (2018), doi:10.1140/epjp/i2018-11912-5 (arXiv:1803.00565).
33. Ishkhanyan, A. M. — *A singular Lambert-W Schrödinger potential exactly solvable in terms of the confluent hypergeometric functions*, Phys. Scr. 90, 085202 (2015) (arXiv:1606.06383).
34. Ishkhanyan, A. M. — *The Lambert-W step-potential — an exactly solvable confluent hypergeometric potential*, Phys. Lett. A 380, 640–644 (2016).
35. Ishkhanyan, T. A.; Manukyan, V. A.; Harutyunyan, A. H.; Ishkhanyan, A. M. — *A new exactly integrable hypergeometric potential for the Schrödinger equation*, Mod. Phys. Lett. A.
36. Ishkhanyan, A. M. — *The Third Five-Parametric Hypergeometric Quantum-Mechanical Potential*, Advances in High Energy Physics (2018), doi:10.1155/2018/2769597.
37. Ishkhanyan, A. M. — *The third exactly solvable hypergeometric quantum-mechanical potential*, EPL 115, 20002 (2016).
38. Ishkhanyan, A.; Krainov, V. — *Discretization of Natanzon potentials*, Eur. Phys. J. Plus 131, 342 (2016).
39. Ishkhanyan, T. A.; Ishkhanyan, A. M. — *Solutions of the bi-confluent Heun equation in terms of the Hermite functions*, Ann. Phys. 383, 79–91 (2017).
40. López-Ortega, A. — *New conditionally exactly solvable potentials of exponential type*, arXiv:1602.00405 [math-ph].
41. López-Ortega, A. — *New conditionally exactly solvable inverse power law potentials*, Phys. Scr. 90, 085202 (2015).
42. Ishkhanyan, A. M. — Comment on *"Third-harmonic generation investigated by a short-range bottomless exponential potential well"* by Hu, M.; Guo, K.; Yu, Q.; Zhang, Z., Superlattices and Microstructures 122, 538–547 (2018); comment: arXiv:2008.01833.
43. Horodecki, R. — Foundational work on the *Feinberg–Horodecki equation* (time-like analogue of the Schrödinger equation).
44. (Feinberg–Horodecki exact momentum states of improved deformed exponential-type potential) — arXiv:2007.14789.
45. Frank, R. L. — *Exponential decay of Schrödinger eigenfunctions* (appendix), in *Two-Particle Bound States at Interfaces and Corners* (arXiv:2105.04874).
46. (Spectral properties of Schrödinger operators with decaying potentials) — mathematical-physics review, Duke University lecture notes.

---

## 9. Concluding Remarks

Three broad strategies define the field: (i) **exact reduction to special functions** — Bessel functions for the pure exponential well/wall/non-analytic double-exponential well, and Gauss/confluent hypergeometric or Heun functions for the newer Ishkhanyan-type exactly integrable exponential potentials; (ii) **algebraic semi-analytical approximations** — chiefly the Nikiforov–Uvarov and Asymptotic Iteration methods, supplemented by SUSYQM, shifted $1/N$ expansions, and the exact quantization rule, all of which require a Pekeris/Greene–Aldrich-type approximation of the centrifugal term for non-zero angular momentum and are validated by cross-comparison; and (iii) **numerical resummation and integral-equation techniques** — the Riccati–Padé method (uniquely capable of yielding complex resonance/virtual-state eigenvalues with high precision) and spectral/Numerov-type direct integration. A persistent theme across the literature is the tension between the *exact but analytically intractable* implicit spectral equations (Bessel zeros, hypergeometric connection coefficients) and the *approximate but explicit* closed-form energy expressions demanded by molecular and nuclear spectroscopy applications, which has driven continual refinement of both the exact solvability classification (Natanzon/Heun schemes) and the approximation toolkit (NU/AIM and successors) over the past several decades.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Exponential potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
