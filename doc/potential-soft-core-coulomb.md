# Evaluation of Eigenvalues of the Schrödinger Equation with the Soft-Core Coulomb Potential: A Review

## 1. Introduction and Motivation

The soft-core (also called "truncated" or "regularized") Coulomb potential is a family of central potentials that mimic the $-1/r$ Coulomb interaction at large distance while remaining finite at $r=0$. The most widely used member of the family is

$$
V_q(r) = -\frac{Z}{\left(r^q+\beta^q\right)^{1/q}}, \qquad Z>0,\ \beta>0,\ q\ge 1,
$$

with the two physically important special cases $q=1$,

$$
V_1(r) = -\frac{Z}{r+\beta},
$$

and $q=2$,

$$
V_2(r) = -\frac{Z}{\sqrt{r^2+\beta^2}}.
$$

As $\beta \to 0$ both reduce to the pure Coulomb potential $-Z/r$, while for $\beta \neq 0$ the singularity at the origin is removed ("softened" or "smeared"). The radial Schrödinger equation for the reduced wavefunction $\phi(r) = rR(r)$ reads (atomic units, $\hbar=m=1$)

$$
-\frac{1}{2}\frac{d^2\phi}{dr^2} + \left[\frac{\ell(\ell+1)}{2r^2} + V_q(r)\right]\phi(r) = E\,\phi(r), \qquad \phi(0)=0,\ \phi(\infty)=0,
$$

and the central problem addressed by the literature reviewed here is the **accurate evaluation of the discrete eigenvalues** $E_{n\ell}(Z,\beta,q)$ (bound states) as functions of the coupling $Z$, the softening/cutoff parameter $\beta$, the power $q$, and (in generalized studies) the spatial dimension $d$.

### 1.1 Why the potential matters

- **Smeared/extended nuclear charge and mesonic atoms.** $V_1$ represents the potential produced by a smeared (non-pointlike) charge distribution and is used to model mesonic atoms.
- **Strong-field / intense-laser atomic physics.** In simulations of atoms in intense laser fields (above-threshold ionization, high-harmonic generation), the true 3-D Coulomb singularity is numerically problematic on a spatial grid; replacing $-1/r$ by $-1/\sqrt{r^2+\beta^2}$ (or its 1-D reduction $Z/\sqrt{2Z^{-2}+x^2}$) regularizes the grid while preserving an infinite Rydberg series and the correct asymptotic behavior. $\beta$ in the range $20$–$40$ (a.u.) is quoted as covering typical experimental laser-field strengths in the reduced-dimensionality models used for laser–atom interaction.
- **Quantum-dot and confinement physics**, dense-plasma-embedded atoms, and Rydberg atoms near metal surfaces, where the singular Coulomb potential is replaced by a softened one to model screening or extended-charge effects.
- **Mathematical physics interest.** The potential is one of the best-studied examples connecting a physically motivated Schrödinger problem to Heun-type differential equations, quasi-exact solvability, and the Bethe-ansatz method, making it a benchmark for testing new analytic and semi-analytic eigenvalue techniques (variational methods, the Asymptotic Iteration Method, Nikiforov–Uvarov method, envelope theory, etc.).

### 1.2 Scope of this review

This review focuses specifically on **methods for computing/evaluating the eigenvalues** $E_{n\ell}$ of the non-relativistic (and, where relevant, relativistic) Schrödinger/Klein–Gordon/Dirac problem with soft-core Coulomb potentials, covering:

1. Exact/quasi-exact analytic approaches (reduction to Heun-type equations, Bethe ansatz, polynomial solutions).
2. The Asymptotic Iteration Method (AIM) as the dominant semi-analytic tool in this literature.
3. Envelope theory / operator-inequality spectral bounds.
4. Algebraic approaches (Nikiforov–Uvarov method, supersymmetric QM).
5. Purely numerical approaches (shooting/Numerov, finite-difference, generalized pseudospectral methods) used as benchmarks or for confined/relativistic extensions.
6. Extensions: arbitrary dimension $d$, spatial confinement (impenetrable boxes, harmonic/linear confinement), and relativistic generalizations (Klein–Gordon, Dirac, spinless Salpeter equations).

---

## 2. The Model Potential and Its General Properties

### 2.1 Scaling and monotonicity

A key structural result established for the general family $V_q(r) = -Z/(r^q+\beta^q)^{1/q}$ is a **scaling law** relating eigenvalues at different $(Z,\beta)$: because $V_q$ depends on $Z$ and $\beta$ only through specific combinations, an eigenvalue computed for one parameter pair can be mapped onto another via a simple algebraic rescaling, which is numerically valuable because it allows eigenvalues computed at moderate $\beta$ to be used to infer eigenvalues at large $\beta$, where the levels of different $\ell$ become nearly degenerate and direct numerical methods (including the AIM) lose accuracy.

It has also been shown analytically that, for the whole family, the potential itself and the eigenvalues $E_{\nu\ell}$ are **monotonic functions of each of the parameters** $Z$, $\beta$, and $q$. This monotonicity underlies the use of **envelope theory** (Section 4) to bound the true eigenvalues using the known exact spectra of pure power-law potentials.

### 2.2 Level crossings

Because softening the Coulomb singularity redistributes probability density away from the origin, states with different $(\nu,\ell)$ quantum numbers that are degenerate or ordered a certain way in the pure Coulomb problem can **cross** as $\beta$ increases. Extensive numerical work (see Section 5) established the empirical/conjectural crossing condition between a pair of states $(\nu,\ell)$ and $(\nu',\ell')$: crossing occurs when $\nu' \ge \nu+1$ and $\ell' \ge \ell+3$. This is qualitatively different from the level-ordering behavior seen for the hydrogen atom confined in an impenetrable sphere, providing a way to physically distinguish the two types of "softening" of the Coulomb problem.

### 2.3 General spectral (operator) bounds

Using the operator inequality $-\Delta \ge 1/(4r^2)$, a general lower bound on the spectrum can be derived,

$$
E \;>\; \min_{r>0}\left[\frac{P^2}{2r^2} + V_q(r)\right], \qquad P=\tfrac12,
$$

and, combined with envelope theory, both upper and lower estimates for every discrete eigenvalue can be constructed in closed form for suitable choices of the comparison exponent $P$.

---

## 3. Exact and Quasi-Exact Analytic Solutions

### 3.1 Reduction to Heun's equation ($q=1$) and generalized Heun equation ($q=2$)

The landmark result in this literature (Hall, Saad & Sen, *J. Math. Phys.* **51**, 022107, 2010) is that the radial Schrödinger equation for $V_1(r)=-Z/(r+\beta)$ reduces exactly to the **confluent Heun equation**, while for $V_2(r) = -Z/\sqrt{r^2+\beta^2}$ it reduces to the **generalized (bi-confluent-type) Heun equation**. In a formulation with the correct asymptotic behavior built in, the eigenfunctions are written as a known asymptotic factor multiplying an unknown function that, for special (quantized) values of the energy, **terminates as a polynomial**. The **Asymptotic Iteration Method** is then the tool used both (i) to identify exactly those special parameter combinations for which the solution is an exact polynomial (yielding closed-form eigenvalues), and (ii) to generate highly accurate approximations to the eigenvalues in the generic (non-terminating) case.

### 3.2 The $d$-dimensional problem and the generalized confluent Heun equation

A systematic generalization to arbitrary spatial dimension $d$ was carried out by constructing the general theory of polynomial solutions of the differential equation

$$
(\alpha_2 r^2+\alpha_1 r)\,y'' + (\beta_2 r^2 + \beta_1 r + \beta_0)\,y' - (\varepsilon_1 r + \varepsilon_0)\,y = 0
$$

in $d$-dimensional space. Necessary and sufficient conditions for the existence of polynomial solutions are derived, together with a three-term recurrence relation generating the polynomial coefficients explicitly. A remarkable by-product is that, in the ordinary 3-dimensional case with $v \equiv \beta e^2 Z$ chosen so that $2(n+1)\mathcal{E}=v$, the eigenvalues of the softcore problem

$$
\left[-\frac{d^2}{dr^2}-\frac{v}{r+1}\right]\psi_{n k}(r) = -\mathcal{E}^2\,\psi_{n k}(r)
$$

turn out to be **exactly the roots of the (generalized) Laguerre polynomials** $L_n^{(1)}(2\mathcal{E})=0$. This links the special, exactly solvable, subset of the soft-core Coulomb spectrum directly to a well-known classical orthogonal polynomial family, and the resulting polynomial solutions are shown to be sources of finite sequences of orthogonal polynomials, with associated recurrence relations, Christoffel–Darboux formulas, and explicit moments of the weight function.

### 3.3 Confined soft-core Coulomb potential: biconfluent Heun equation

When the softcore Coulomb interaction $a/(r+\beta)$ is supplemented by additional linear and/or harmonic-oscillator confinement terms — relevant to quarkonium spectroscopy and to modeling pressure/confinement effects — the radial equation reduces instead to a **biconfluent Heun equation**. Polynomial solution methods analogous to those above were developed, subject to additional constraints among the potential parameters, and "hard confinement" by an impenetrable spherical box was treated as a complementary limiting case. The resulting spectra combine oscillator-like and Coulomb-like structure.

### 3.4 Quasi-exact solvability via the Bethe ansatz

A separate line of work (Agboola & Zhang, and related studies) shows that the soft-core Coulomb potential belongs to a broader class of **quasi-exactly solvable (QES)** problems — together with the singular anharmonic oscillator, the generalized quantum isotonic oscillator, and the non-polynomially modified oscillator — all reducible to the same basic second-order ODE. This basic equation is solved in closed form via the **Bethe ansatz method**, yielding explicit expressions for a finite subset of the energies and the constraints on the potential parameters for which those energies are exact, with wavefunctions expressed via the roots of a system of Bethe ansatz equations. This QES structure has been extended to the **relativistic** Klein–Gordon and Dirac equations with soft-core Coulomb potentials, where the same underlying ODE reappears and quasi-exact polynomial solutions are obtained for both $q=1$ and $q=2$.

### 3.5 Related exactly solvable special cases

Earlier and more limited exact treatments (prior to the systematic Heun-equation approach) obtained bound-state solutions of $V_1$ only for a restricted set of low angular-momentum states ($\ell = 0,\dots,3$) using ad hoc factorization of infinite Hill determinants or recursive-relation methods; the $q\ge 2$ case had not been treated analytically before the Heun-equation reduction was introduced.

---

## 4. The Asymptotic Iteration Method (AIM) as the Central Semi-Analytic Tool

The AIM is, by a wide margin, the most used technique in this specific literature for **evaluating** (not merely classifying) the eigenvalues, because it naturally accommodates both the exactly solvable and the generic (non-terminating) regimes.

### 4.1 Method outline

Given a second-order homogeneous linear ODE of the form $y'' = \lambda_0(r) y' + s_0(r) y$, AIM generates, by repeated differentiation, a sequence of coefficient pairs $(\lambda_n, s_n)$ via

$$
\lambda_n = \lambda_{n-1}' + s_{n-1} + \lambda_0\lambda_{n-1}, \qquad s_n = s_{n-1}' + s_0\lambda_{n-1}.
$$

Imposing the **"termination" (quantization) condition** $s_n\lambda_{n-1} - s_{n-1}\lambda_n = 0$ at a suitably chosen point $r_0$ (often $r_0 = 0$, or the extremum of the effective potential) determines the eigenvalue $E$, either exactly (when the underlying wavefunction factor terminates as a true polynomial) or approximately, by iterating the termination condition to a chosen order $n$ and root-finding.

### 4.2 Application to the soft-core Coulomb problem

For $V_1$ ($q=1$), imposing the correct asymptotic form of the wavefunction converts the radial equation into a form amenable to AIM. When $\beta = 0$, the method is shown to reproduce exactly the known Coulomb eigenvalues, i.e., the termination condition automatically becomes $r$-independent at any iteration — a useful internal consistency check. For $\beta \neq 0$, exact analytic solutions exist only for special potential parameters (Section 3), while for arbitrary $Z,\beta$, AIM is applied numerically/symbolically to generate eigenvalues to very high precision (many studies quote **9–10 significant figures**), including for excited states up to $4f$ and beyond.

A practical numerical subtlety documented in this literature: for large $\beta$ (e.g., $\beta=200$), the eigenvalues for different $\ell$ become extremely close together (separations below $10^{-3}$), which can cause AIM's termination search to fail or converge poorly. The **scaling law** (Section 2.1) is the recommended remedy — e.g., instead of directly computing $E(n=1,\beta=200,q=2)$, one computes the numerically better-conditioned $E(n=4,\beta=50,q=2)$ and rescales by a factor of 16.

### 4.3 AIM for confined and higher-dimensional problems

AIM has likewise been the workhorse for the confined softcore Coulomb problem (Section 3.3) — used both to identify the special polynomial (exactly solvable) cases and to produce "very accurate approximate solutions for the general problem with arbitrary potential parameters." Comparative studies of AIM applied to related perturbed-Coulomb models report that its accuracy is qualitatively better than that obtained from traditional **Runge–Kutta** and **Numerov** shooting-type integrations for the same problems, which is one of the main reasons the method has been preferred in this specific body of work.

---

## 5. Envelope Theory and Analytic Spectral Bounds

**Envelope theory** exploits the established monotonicity and convexity/concavity properties of the soft-core family (Section 2.1–2.3) to construct rigorous, closed-form **upper and lower bounds** on every discrete eigenvalue $E_{\nu\ell}$, expressed in terms of the *exactly known* spectra of pure power-law potentials $V(r)=\mathrm{sgn}(q)\,r^{q}$ used as comparison ("tangential") potentials. Because $V_q(r)$ can be written as a function of $r^2$ composed with a convex/concave transformation, the envelope method yields bounds that:

- obey the same scaling and monotonicity laws as the exact eigenvalues;
- become geometrically interpretable as families of tangential curves in the $(\beta, E)$ or $(Z,E)$ plane;
- serve as fast, non-iterative **exploratory tools** for scanning parameter space before a more expensive method (AIM, direct numerical integration) is used to refine a specific eigenvalue.

A complementary, independent proof establishes the **general concavity of the scaled electron density near the nucleus** for all $q\ge1$, which underlies both the monotonicity results and the qualitative behavior of level crossings discussed in Section 2.2.

Related envelope-theory work extends this machinery to the **semi-relativistic** (spinless Salpeter / two-body) softcore Coulomb problem, constructing analytic lower bounds for the discrete Dirac-type spectrum and comparing them against accurate numerically computed eigenvalues.

---

## 6. Algebraic and Approximation Methods (Nikiforov–Uvarov, SUSY QM, Variational Approaches)

- **Nikiforov–Uvarov (NU) method.** Because the exact soft-core Coulomb problem does not reduce to a standard hypergeometric equation, most NU-based treatments require an additional **approximation of the centrifugal term** (e.g., a Pekeris-type approximation) to bring the problem into the NU framework; this is the typical route used in the relativistic (Dirac/Klein–Gordon, spin- and pseudospin-symmetric) literature, where NU is combined with Pekeris-type centrifugal approximations to obtain closed-form (approximate, $\ell$-dependent) energy formulas together with the corresponding spinor wavefunctions in terms of Jacobi polynomials.
- **Combined Coulomb + soft-core term potentials.** Studies of potentials such as $V(r) = G/r - Z/(r+\beta)$ (a superposition of a genuine Coulomb tail and a soft-core term) use a substitution ansatz $\Phi(r) = (r+\beta)r^{\ell+1}e^{-c(r+\beta)}\phi(r)$ to again arrive at the same class of quasi-exactly solvable basic equations treated by the Bethe-ansatz approach of Section 3.4.
- **Semi-relativistic two-body treatments.** The spinless Salpeter equation for a softcore Coulomb interaction between two particles (relevant to heavy-quark/heavy-particle bound states) does not admit exact analytic solutions; NU-method and Bethe-ansatz techniques with controlled approximations are used, and the quasi-exactly solvable "basic ODE" structure recurs here as well.

---

## 7. Purely Numerical Methods and Benchmarking

While AIM dominates the specialized soft-core-Coulomb literature, ordinary numerical integration techniques are used both as historical baselines (predating the Heun-equation/AIM approach) and as **independent cross-checks**:

- **Direct numerical solution of the radial Schrödinger equation** (shooting methods, Numerov's method) was used in early studies to tabulate a large number of eigenvalues for states from $1s$ to $4f$ for the $V_1$ and $V_2$ potentials at fixed $Z$; the later scaling laws extend the applicability of these tabulations to arbitrary $Z$.
- **Time-dependent Schrödinger equation (TDSE) grid simulations**, used extensively in strong-field/attosecond physics, adopt the 1-D or 3-D soft-core regularization $V(x) = -Z/\sqrt{2Z^{-2}+x^2}$ (or its 3-D analogue) purely to make finite-difference/finite-volume propagation on a numerical grid well behaved near $r=0$; the resulting discretized eigenspectrum reproduces the low-lying hydrogenic spectrum with small, quantifiable shifts (e.g., a computed ground-state energy of $E_0 \approx -13.385\ \mathrm{eV}$ versus the exact hydrogen value of $-13.606\ \mathrm{eV}$, illustrating the systematic softening-induced shift that must be controlled by the choice of the regularization parameter and grid resolution).
- **Generalized pseudospectral (GPS) methods**, developed originally for confined and screened Coulomb systems (H atom in an impenetrable spherical box, Hulthén potential), achieve eigenvalues accurate to **10–11 decimal places** across the full range of confinement radii and are used as a high-precision numerical standard against which approximate/analytic soft-core results can, in principle, be validated, since the confined-Coulomb and soft-core-Coulomb problems share much of their mathematical structure (both regularize or bound the Coulomb singularity's effect on the spectrum).
- **Comparative accuracy assessments.** Where explicit comparisons have been made, AIM-based eigenvalues for softcore-type Coulomb models have been reported as more accurate, for comparable computational effort, than results from traditional Runge–Kutta or Numerov integrations of the same radial equation.

---

## 8. Extensions: Confinement, Higher Dimensions, and Relativistic Generalizations

### 8.1 Spatial confinement

Two conceptually different but related "softening/confinement" mechanisms are studied side by side in this literature:

1. **Soft-core softening at the origin** ($\beta\neq0$ removing the singularity), the main subject of this review.
2. **Hard/soft confinement at large $r$** — an impenetrable spherical box (Dirichlet boundary condition at $r=R$), a penetrable box with a finite potential step, or additional linear/harmonic confining terms superposed on the softcore Coulomb tail (relevant to quarkonium and to pressure effects in dense plasmas/quantum dots).

Both mechanisms shift and reorder the discrete spectrum, and comparing the level-crossing patterns produced by each (Section 2.2) is used diagnostically to distinguish the physical origin of a given deviation from the free hydrogenic spectrum (e.g., distinguishing intense-laser softening from geometric/pressure confinement).

### 8.2 Arbitrary spatial dimension $d$

The generalized-confluent-Heun-equation framework (Section 3.2) was explicitly built for the softcore Coulomb potential in $d>1$ dimensions, unifying the 3-D case (where the exactly solvable spectrum reduces to Laguerre-polynomial roots) with genuinely higher-dimensional generalizations relevant to dimensional-scaling approaches in atomic and few-body physics.

### 8.3 Relativistic generalizations

- **Klein–Gordon and Dirac equations** with soft-core Coulomb potentials $V_q(r)$, $q=1,2$, have been shown to reduce to the same quasi-exactly solvable basic ODE as the non-relativistic problem, allowing a unified Bethe-ansatz solution and comparison of relativistic corrections to the eigenvalue spectrum.
- **Semi-relativistic (spinless Salpeter) two-body problem** with a softcore Coulomb interaction, relevant to heavy-particle bound-state spectroscopy, has been treated with envelope-theory lower bounds compared against accurate numerical Dirac-type spectra, and separately via Nikiforov–Uvarov techniques with Pekeris-type approximations.
- **Dirac equation with tensor (spin–orbit) softcore Coulomb terms**, including spin- and pseudospin-symmetric cases, have been solved (approximately) via the NU method and via quasi-analytical ansatz techniques, with numerical investigation of the effect of the tensor coupling on the energy spectrum.

---

## 9. Summary Comparison of Eigenvalue-Evaluation Methods

| Method | Regime of applicability | Nature of result | Typical accuracy / caveats |
|---|---|---|---|
| Heun-equation reduction + polynomial ansatz | Special ("quantized") parameter combinations of $Z,\beta$ ($q=1,2$; any $d$) | Exact closed-form eigenvalues (roots of explicit polynomials, e.g. Laguerre polynomials in the 3-D case) | Exact but only on a measure-zero subset of parameter space |
| Asymptotic Iteration Method (AIM) | General $Z,\beta,q$ (non-terminating case); also confined and higher-$d$ cases | Semi-analytic / numerical iterative approximation | High precision (routinely 9–10+ significant figures); degrades for widely separated or near-degenerate levels at large $\beta$ unless combined with the scaling law |
| Bethe ansatz (QES) | Non-relativistic and relativistic (KG, Dirac) softcore Coulomb, restricted parameter families | Exact energies for a finite subset of states, plus explicit parameter constraints | Exact where applicable; does not cover the full spectrum |
| Envelope theory / operator-inequality bounds | All $Z,\beta,q$ (monotonic, concave/convex families) | Rigorous analytic upper and lower bounds | Fast and rigorous but not exact; bound tightness depends on the comparison potential chosen |
| Nikiforov–Uvarov (with Pekeris-type approximation) | Mostly relativistic (Dirac/KG) extensions with tensor/spin terms | Approximate closed-form energy formulas | Requires an additional approximation of the centrifugal/orbital term; accuracy is approximation-dependent |
| Direct numerical integration (shooting, Numerov, finite-difference, GPS) | Any $Z,\beta,q$; especially confined and grid-based TDSE contexts | Purely numerical eigenvalues | GPS-type methods reach 10–11 decimal places for confined Coulomb-type systems; simple grid/finite-difference TDSE discretizations show controllable but non-negligible shifts from the true hydrogenic values |

---

## 10. Open Questions and Outlook

- A fully rigorous (as opposed to numerically conjectured) proof of the general level-crossing condition $\nu'\ge\nu+1,\ \ell'\ge\ell+3$ for the full family $V_q$ remains, to the reviewed literature's own admission, an open problem based on "an analysis of extensive numerical calculations" rather than a closed-form proof.
- Systematic high-precision numerical benchmarking (e.g., GPS-level accuracy) specifically for the softcore Coulomb family — as has been done for the confined hydrogen atom and the Hulthén potential — appears less developed than for the exactly/quasi-exactly solvable analytic branch of the literature, leaving room for cross-validation studies.
- Extending the exact biconfluent/generalized Heun-equation machinery to simultaneous softcore + confinement + relativistic corrections (a fully unified treatment) is only partially addressed; most relativistic treatments to date rely on additional approximations (Pekeris-type) rather than the exact Heun/QES reduction used in the non-relativistic case.

---

## 11. Bibliography

The following publications, drawn from the material reviewed above, represent the core literature on eigenvalue evaluation for the Schrödinger (and related relativistic) equation with soft-core Coulomb potentials.

1. R. L. Hall, N. Saad, and K. D. Sen, "Soft-core Coulomb potentials and Heun's differential equation," *J. Math. Phys.* **51**, 022107 (2010). [arXiv:0912.3445]
2. R. L. Hall, N. Saad, and K. D. Sen, "Energies and wave functions for a soft-core Coulomb potential," *Phys. Rev. A* **80**, 032507 (2009). [arXiv:0908.2087]
3. R. L. Hall and N. Saad, "Spectra generated by a confined soft-core Coulomb potential," (biconfluent Heun equation / confinement study). [arXiv:1407.7587]
4. R. L. Hall, N. Saad, and collaborators, "The $d$-dimensional softcore Coulomb potential and the generalized confluent Heun equation," *J. Math. Phys.* (October 2018). [arXiv:1810.06539]
5. R. L. Hall, N. Saad, and A. von Keviczky, "Eigenvalues of the Schrödinger equation with Coulomb potentials plus linear and harmonic radial terms" (related confining-potential AIM study).
6. D. Agboola and Y.-Z. Zhang, "Unified derivation of exact solutions for a class of quasi-exactly solvable models," (soft-core Coulomb, singular anharmonic oscillator, isotonic oscillator). [arXiv:1111.1050]
7. D. Agboola and Y.-Z. Zhang, "Quasi-exactly solvable relativistic soft-core Coulomb models," *Ann. Phys.* (2012). [arXiv:1311.1566]
8. "The Soft-Core Coulomb Potential in the Semi-Relativistic Two-Body Basis" (spinless Salpeter equation, envelope-theory lower bounds, Nikiforov–Uvarov treatment).
9. S. Zarrinkamar, A. A. Rajabi, B. H. Yazarloo, and H. Hassanabadi, "Dirac equation for scalar and vector soft-core Coulomb potentials and a tensor Coulomb term in spin and pseudospin symmetries via the quasi-analytical ansatz technique."
10. Application of AIM to related singular/perturbed Coulomb models: "Application of the Asymptotic Iteration Method to a Perturbed Coulomb Model" (comparison of AIM against Runge–Kutta and Numerov methods).
11. "Field ionization in short and extremely intense laser pulses" — 1-D soft-core potential $V(x)=Z/\sqrt{2Z^{-2}+x^2}$ used for strong-field ionization modeling. [arXiv:1808.06890]
12. "Model for the Atomic Dielectric Response in Time Dependent Laser Fields" — soft-core regularization in TDSE grid simulations. [arXiv:1311.5600]
13. L.-N. Li, J.-P. Wang, and F. He, "Roles of Coulomb potentials in below- and above-threshold harmonic generation for a hydrogen atom in strong laser fields," *J. Opt. Soc. Am. B* **33**, 1558 (2016).
14. Spherical-confinement and generalized-pseudospectral benchmark studies: "Spherical confinement of Coulombic systems inside an impenetrable box: H atom and the Hulthén potential." [arXiv:1802.04373]
15. N. Aquino et al., "Perturbation Theory for a Hydrogen-like Atom Confined Within an Impenetrable Spherical Cavity."
16. "Spectral characterization of the hydrogen-like atoms confined by oscillating systems" (context on soft-core vs. hard-confinement models for laser–atom interaction). [arXiv:1410.1649]
17. F. M. Fernández and collaborators, related studies on the classical dynamics of Rydberg atoms under soft-core vs. true Coulomb potentials near metal surfaces.
18. Studies applying the Nikiforov–Uvarov method with Pekeris-type approximations to Dirac/Klein–Gordon equations with exponential-type and Coulomb-tensor interactions, illustrating the algebraic-approximation route to relativistic soft-core-type spectra.

*Note: several entries above are cited via their arXiv identifiers or journal listings as located through literature search; readers should consult the original sources (arXiv/journal pages) for complete author lists, volume/page details, and any subsequent erratum.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Soft-core Coulomb potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
