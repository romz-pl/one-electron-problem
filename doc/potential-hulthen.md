# Evaluation of Eigenvalues of the Schrödinger Equation with the Hulthén Potential: An Exhaustive Review

## 1. Introduction

The Hulthén potential, introduced by Lars Hulthén in 1942, is one of the most extensively studied short-range exponential-type potentials in quantum mechanics. It is defined as

$$V(r) = -V_0 \frac{e^{-\delta r}}{1 - e^{-\delta r}} = -\frac{Z e^{-r/a}}{1 - e^{-r/a}},$$

where $V_0$ (or $Z/a$) sets the potential strength, $\delta = 1/a$ is the screening parameter, and $a$ is the screening (range) length. For small $r$ the potential behaves Coulombically, $V(r) \approx -Z/r$, while for large $r$ it decays exponentially, $V(r) \approx -Z\,e^{-r/a}$. This dual character makes it a screened-Coulomb-type potential, closely related to the Yukawa potential, and a special case of the more general Eckart potential.

Because of this behavior, the Hulthén potential has found application across many subfields:

- **Nuclear and particle physics** — as a model for nucleon–nucleon interactions and as an alternative to the Yukawa potential for short-range nuclear forces.
- **Atomic physics** — as a model for screened Coulomb interactions in multi-electron atoms and plasmas.
- **Solid-state physics** — in the study of screened interactions in doped semiconductors and impurity states.
- **Chemical/molecular physics** — as a model of diatomic molecular interaction, related to the Morse-type potentials.
- **Relativistic quantum mechanics** — in Dirac, Klein–Gordon, and Duffin–Kemmer–Petiau equation studies, spin/pseudospin symmetry, and PT-symmetric extensions.

The central mathematical difficulty is that the radial Schrödinger equation with the Hulthén potential is **exactly solvable in closed form only for the $s$-wave ($\ell = 0$) case**. For $\ell \neq 0$, the centrifugal term $\ell(\ell+1)/r^2$ prevents exact separability, and the equation must be treated by approximation schemes or purely numerical methods. This single fact — the non-solvability for arbitrary angular momentum — is the reason an enormous methodological literature has grown around this one potential: it has served for decades as a benchmark and testing ground for essentially every new technique developed for approximately solving the Schrödinger, Klein–Gordon, and Dirac equations.

This review surveys (i) the exact $s$-wave solution, (ii) the centrifugal-term approximation problem and the main approximation schemes proposed, (iii) the principal analytical and semi-analytical methods used to obtain eigenvalues for $\ell \neq 0$, (iv) numerical and other independent methods used for benchmarking, (v) extensions to combined/generalized Hulthén potentials and to relativistic wave equations, and (vi) a representative bibliography of the field.

---

## 2. The Exact $s$-Wave ($\ell = 0$) Solution

For $\ell = 0$, the radial Schrödinger equation

$$-\frac{\hbar^2}{2\mu}\frac{d^2 u(r)}{dr^2} + \left[-\frac{Z e^{-\delta r}}{1-e^{-\delta r}} - E\right] u(r) = 0$$

can be transformed via $x = e^{-\delta r}$ into a hypergeometric-type equation and solved exactly in terms of hypergeometric functions. The bound-state energy eigenvalues are given by the well-known closed-form expression

$$E_n = -\frac{\hbar^2 \delta^2}{8\mu}\left(\frac{n^2 \delta - 2\mu Z/\hbar^2 \delta}{n\delta}\right)^2 \quad\text{(one common parametrization)},$$

more commonly written for the standard form as

$$E_n = -\frac{\hbar^2 \delta^2}{8\mu}\left[n - \frac{\left(\frac{2\mu Z}{\hbar^2 \delta}\right)}{n}\right]^2, \qquad n = 1, 2, 3, \dots$$

A key qualitative feature already visible at $\ell=0$ is the existence of a **critical screening parameter** $\delta_c$: bound states exist only for $\delta < \delta_c(n)$, beyond which the state becomes unbound ($E \to 0$ and then disappears into the continuum). For low-lying arbitrary-$\ell$ states obtained approximately, a frequently quoted critical value takes the form $\delta_c = \dfrac{1}{n+\ell}$ or $\delta_c = \dfrac{2}{n+\ell+1)^2}$-type expressions, depending on the approximation scheme and normalization convention used; exact numerical values of $\delta_c$ have also been tabulated for several low $n,\ell$ via direct numerical integration.

## 3. The Centrifugal-Term Problem for $\ell \neq 0$

For $\ell \neq 0$ the full radial equation contains

$$\frac{\hbar^2}{2\mu}\frac{\ell(\ell+1)}{r^2},$$

which, combined with the Hulthén term, does not admit an exact solution in terms of standard special functions. Virtually the entire subsequent literature on this potential exists because of this obstruction. Two broad strategies have been used to make progress:

1. **Approximate the centrifugal term** by an exponential-type function of the same variable used to solve the $s$-wave problem, then solve the resulting equation exactly by algebraic/analytic techniques (Nikiforov–Uvarov, SUSYQM, factorization, AIM, etc.).
2. **Solve the full equation numerically** without any centrifugal approximation, to generate "exact" reference eigenvalues against which approximate analytic results are benchmarked.

### 3.1 Approximation Schemes for the Centrifugal Term

| Scheme | Approximating form (schematically) | Notes |
|---|---|---|
| **Greene–Aldrich approximation** | $\dfrac{1}{r^2} \approx \dfrac{\delta^2}{(1-e^{-\delta r})^2}$ | The most widely used scheme; valid for $\delta \ll 1$ (short-range/weak-screening regime); introduced originally for related screened-Coulomb-type potentials. |
| **Pekeris-type approximation** | Expansion of $1/r^2$ about the potential minimum / equilibrium point in terms of $e^{-\delta r}$ | Common in ro-vibrational (molecular) contexts; tends to be more accurate near equilibrium separations. |
| **Improved/combined approximations** | Linear combinations of Greene–Aldrich and Pekeris forms, with adjustable weighting parameters | Proposed to extend accuracy across the whole radial domain rather than only the short-range or equilibrium regions (e.g., Nath & Roy's improved schemes for Eckart, Hulthén, Manning–Rosen, Pöschl–Teller potentials). |
| **Improved approximation with new parametrization** (various authors) | Introduces auxiliary fitting parameters chosen so the approximation reproduces the correct behavior in specific limits | Used to systematically reduce discrepancy with numerically "exact" eigenvalues, especially for larger $\delta$ or higher $\ell$. |

The choice of scheme materially affects accuracy: Greene–Aldrich-based results agree well with numerically exact values only for small screening parameter $\delta$ and low $\ell$; deviations grow as $\delta$ or $\ell$ increase, which is why refined/combined approximations continue to be proposed.

## 4. Principal Analytical/Semi-Analytical Methods for Eigenvalue Evaluation

### 4.1 Nikiforov–Uvarov (NU) Method

The NU method reduces a generalized hypergeometric-type second-order differential equation to a form solvable via Rodrigues-type formulas, yielding energy eigenvalues via an eigenvalue quantization condition and eigenfunctions expressed in terms of **Jacobi polynomials**. Applied to the Hulthén potential (typically with the Greene–Aldrich or Pekeris approximation to the centrifugal term), the NU method has produced closed-form energy equations of the type

$$-\frac{2\mu E_{n\ell}}{\hbar^2 \delta^2} = \left[\frac{n + \ell + 1}{2} + \frac{\mu Z/(\hbar^2\delta) - \ell(\ell+1)/(n+\ell+1)}{n+\ell+1}\right]^2$$

(exact form varies by paper/convention). The NU method is by far the most commonly used analytic technique in this literature because it is systematic, algebraic, and readily generalized to $D$-dimensions and to combined/superposed potentials (Hulthén + Hellmann, Varshni + Hulthén, Hulthén + Yukawa, Hulthén + ring-shaped, etc.).

### 4.2 Supersymmetric Quantum Mechanics (SUSYQM) and Shape Invariance

SUSYQM constructs a superpotential $W(r)$ from the ground-state wave function and factorizes the Hamiltonian into "partner" Hamiltonians $H_{\pm} = A^{\dagger}A, AA^{\dagger}$. When the partner potentials are shape-invariant (differing only in parameters), the entire spectrum follows algebraically without solving a differential equation directly. Applied to the Hulthén potential with an approximated centrifugal term, SUSYQM (via the shape-invariance concept introduced by Gendenshtein) reproduces exactly the same eigenvalues and eigenfunctions as the NU method — a well-documented cross-check appearing repeatedly in the literature, confirming internal consistency between the two formalisms.

### 4.3 Asymptotic Iteration Method (AIM)

The AIM solves a second-order homogeneous linear differential equation
$$y'' = \lambda_0(x) y' + s_0(x) y$$
by an iterative differentiation procedure, terminating when a "quantization" (termination) condition is met. A particularly important feature of the AIM literature on the Hulthén potential is that several works (notably Boztosun and co-workers) applied AIM **without any approximation to the centrifugal term**, solving the equation as accurately as numerical integration for arbitrary $\ell$ and screening parameter $\delta$, and used these results as benchmark ("near-exact") values against which NU-, SUSY-, and other approximation-scheme-based results are compared. AIM has also been extended to the "deformed" Hulthén potential and to combined Hulthén–Morse systems.

### 4.4 Parametric/Generalized NU and Functional Analysis Approaches

Several works reformulate the NU method in a fully "parametric" form (writing the master equation once for a generic set of coefficients and reading off eigenvalues by substitution of the specific potential's parameters), streamlining application to the Hulthén potential and its many generalizations (e.g. "generalized," "modified," or "deformed" Hulthén forms, and Hulthén-plus-X composite potentials).

### 4.5 Factorization Method

An older algebraic technique predating and related to SUSYQM, in which raising/lowering operators are constructed to connect eigenstates of neighboring $\ell$ or $n$; applied historically to the $s$-wave and approximate $\ell$-dependent Hulthén problem.

### 4.6 Perturbative and 1/N Shifted Expansion Methods

The **shifted $1/N$ expansion** (large-dimension/large quantum-number expansion) treats the spatial dimension $N$ (or an effective analog) as a large parameter and expands the energy in powers of $1/N$ (or $1/\bar N$, an appropriately shifted version), providing an independent semiclassical route to $\ell \neq 0$ eigenvalues. This method, together with ordinary Rayleigh–Schrödinger perturbation theory (perturbing about the exactly solvable Coulomb limit or $\ell=0$ Hulthén solution), was among the earliest tools used (pre-NU/AIM era, 1980s–1990s) to obtain approximate arbitrary-$\ell$ Hulthén eigenvalues.

### 4.7 Variational Method

Trial wave functions (often hydrogenic-type or Slater-type with variational parameters) are optimized to minimize $\langle H \rangle$. This provides rigorous upper bounds on the ground-state (and, with orthogonality constraints, excited-state) energies and has historically served as one of the standard benchmarks for newer analytic methods.

### 4.8 Quantization-Rule / WKB-Type Approaches

Exact-quantization-rule methods (an extension of the Bohr–Sommerfeld/WKB idea incorporating a correction term $N_r$ related to the number of nodes) have been applied to the Hulthén potential in arbitrary dimension $D$, using new approximation schemes for the centrifugal term, to derive closed-form eigenvalue expressions valid across a range of $D$ and $\ell$.

## 5. Numerical and Other Independent Methods (Benchmarking Tools)

Because every analytic route above relies on some approximation to the centrifugal term (except select AIM/numerical treatments), independent numerically "exact" methods have played an essential benchmarking role:

- **Direct numerical integration** of the radial Schrödinger equation (e.g., Numerov-type shooting methods) — used since the 1980s as the primary reference standard for $\ell \neq 0$ Hulthén eigenvalues.
- **Generalized Pseudospectral (GPS) Method** — a highly accurate spectral technique (non-uniform, optimal grid mapping) applied to Hulthén and Yukawa potentials, giving eigenvalues accurate to many decimal digits, including near the critical screening parameter where other methods degrade.
- **Laguerre pseudospectral methods** and **Sturmian-basis expansions** — used for both bound-state and continuum-state calculations, and as a basis for relativistic corrections (first-order perturative Dirac corrections) to nonrelativistic Hulthén/Yukawa energies.
- **Basis-set diagonalization / algebraic approach** — expansion of the wave function in a finite basis (e.g., harmonic-oscillator or Coulomb-Sturmian basis) followed by matrix diagonalization.

Comparative tables across many of the papers cited above consistently show that AIM (unapproximated), GPS, and direct numerical integration mutually agree to high precision, while NU/SUSY/AIM results that rely on the Greene–Aldrich approximation show increasing deviation as $\delta$ increases or as $\ell$ grows, motivating the improved/combined approximation schemes discussed in Section 3.1.

## 6. Extensions and Generalizations

The Hulthén potential rarely appears in isolation in the recent literature; it is very often combined with other potential terms to build richer models whose Schrödinger (or relativistic wave) equation eigenvalues are then evaluated by the same toolbox of methods (mainly NU and its parametric variants, plus AIM):

- **Hulthén + Hellmann potential** — combines the Hulthén screened-Coulomb term with the Hellmann potential (Coulomb plus Yukawa); studied non-relativistically and, more recently, in fractional-derivative and curved-spacetime (topological-defect) generalizations of the Schrödinger equation.
- **Varshni + Hulthén potential** — a newly proposed superposition studied via the $N$-dimensional NU method with Greene–Aldrich approximation, with numerical eigenvalues tabulated across dimensions $N$ and states $n,\ell$.
- **Hulthén plus ring-shaped potential** — introduces an angle-dependent term to model non-central interactions; solved via NU with separation of angular/radial parts.
- **Hulthén plus (inversely quadratic) Yukawa potential** — used in nuclear-structure contexts (e.g., binding energy estimates for light nuclei).
- **PT-symmetric and non-Hermitian Hulthén potential** — studied within PT-symmetric quantum mechanics, extending eigenvalue evaluation to complex/non-Hermitian Hamiltonians while preserving real spectra.
- **Deformed / generalized Hulthén potential** — modified functional forms (e.g., extra exponential parameters) solved via AIM and NU, generalizing the critical-screening-parameter phenomenology.
- **Fractional-derivative generalizations** — the Schrödinger equation is generalized using fractional calculus (e.g., conformable or Riesz fractional derivatives), and a generalized fractional NU method is used to evaluate eigenvalues, often alongside curved-spacetime (topological defect) backgrounds.
- **Position-dependent mass** and **minimal-length** deformed quantum mechanics — Hulthén-type (and combined) potentials solved under generalized commutation relations relevant to quantum gravity phenomenology.

## 7. Relativistic Wave Equations

A large parallel literature addresses the Hulthén potential (and its generalizations) within relativistic quantum mechanics, again driven by the same centrifugal/spin-orbit approximation issue:

- **Klein–Gordon equation** — solved for the (generalized) Hulthén potential under equal scalar and vector potential conditions, via NU and AIM, for arbitrary angular momentum, including position-dependent mass extensions.
- **Dirac equation** — spin-symmetry and pseudospin-symmetry limits solved for the Hulthén potential (alone or combined with Yukawa/Coulomb-like tensor interactions), yielding relativistic energy eigenvalues and spinor wave functions; scattering-state (transmission/reflection coefficient) problems have also been addressed for the one-dimensional Dirac equation with a modified Hulthén potential.
- **Spinless Salpeter equation** — treated via SUSYQM for arbitrary quantum numbers.
- **Duffin–Kemmer–Petiau (DKP) equation** — Hulthén-type potential problems solved for spin-0 and spin-1 relativistic bosons in some studies.

## 8. Applications-Oriented Studies Beyond Pure Eigenvalue Evaluation

Once the eigenvalues and eigenfunctions are obtained, many papers proceed to compute derived physical quantities, which constitutes a further large branch of the literature:

- Thermodynamic properties (partition function, mean energy, entropy, specific heat, free energy) via the Euler–Maclaurin approach applied to the Hulthén (or Hulthén-combined) energy spectrum.
- Information-theoretic measures — Shannon entropy, Rényi entropy, Tsallis entropy, Fisher information, and complexity measures (e.g., LMC complexity), in both position and momentum space.
- Mass spectra of heavy mesons/quarkonium systems, using the Hulthén (or Hulthén + Cornell-type) potential in the non-relativistic quark model.
- Nuclear binding energies (e.g., light nuclei) using Hulthén-type nucleon–nucleon potentials.

## 9. Summary and Outlook

The literature on eigenvalue evaluation for the Hulthén potential exhibits several stable, recurring patterns over more than four decades:

1. The $\ell=0$ case is exactly solvable in closed form; all difficulty stems from the centrifugal term for $\ell \neq 0$.
2. A small number of approximation schemes for $1/r^2$ (Greene–Aldrich, Pekeris, and various combined/improved forms) underlie almost all analytic ($\ell\neq0$) results.
3. The Nikiforov–Uvarov method (and its parametric generalization) and the Asymptotic Iteration Method are today the two dominant analytic tools, cross-validated repeatedly against SUSYQM (which reproduces identical spectra under shape invariance) and against numerical benchmarks (direct integration, GPS, Sturmian/basis-set methods).
4. The Hulthén potential functions largely as a **methodological testbed**: nearly every new approximation scheme, generalized differential-equation framework (fractional derivatives, curved spacetime, minimal length, position-dependent mass), or relativistic wave equation is first, or also, tested on the Hulthén potential (frequently in combination with other potentials such as Hellmann, Yukawa, Varshni, Coulomb, or ring-shaped terms) because its near-exact numerical benchmarks are well established and its $s$-wave solution provides an analytic anchor point.
5. Current research activity (2020s) is concentrated on: (i) combined/superposed potentials, (ii) fractional and curved-spacetime generalizations, and (iii) improved centrifugal-term approximations that remain accurate over a wider range of $\delta$ and $\ell$ than the classical Greene–Aldrich scheme.

---

## 10. Representative Bibliography

*(Foundational, methodological, and representative recent papers; not exhaustive.)*

### Foundational / Original Potential

1. L. Hulthén, "Über die eigenlösungen der Schrödinger-gleichung des deuterons," *Ark. Mat. Astron. Fys.* A **28**, 5 (1942).
2. L. Hulthén, *Ark. Mat. Astron. Fys.* B **29**, 1 (1942).
3. H. Yukawa, "On the interaction of elementary particles," *Proc. Phys. Math. Soc. Jpn.* **17**, 48 (1935). (Related screened-Coulomb potential, frequently studied alongside Hulthén.)

### Nikiforov–Uvarov Method and Framework

4. A. F. Nikiforov, V. B. Uvarov, *Special Functions of Mathematical Physics* (Birkhäuser, Basel, 1988).
5. C. Berkdemir, A. Berkdemir, R. Sever, "Shape-invariance approach and Hamiltonian hierarchy method on the Woods–Saxon potential for ℓ ≠ 0 states," *J. Math. Chem.* (2007).
6. S. M. Ikhdair, R. Sever, "Approximate Eigenvalue and Eigenfunction Solutions for the Generalized Hulthén Potential with any Angular Momentum," *Mod. Phys. Lett. A*.
7. B. Ç. Lütfüoğlu et al., "Analytical Solutions of the Schrödinger Equation for the Hulthén Potential within SUSY Quantum Mechanics," arXiv:1606.08035.
8. E. P. Inyang, E. S. William, J. A. Obu, "Eigensolutions of the N-dimensional Schrödinger equation interacting with Varshni–Hulthén potential model," *Rev. Mex. Fís.* (2021); arXiv:2012.13826.
9. U. S. Okorie, A. N. Ikot, et al., "Eigensolutions of generalized fractional Schrödinger equation with Hulthén–Hellmann potential and topological defects," *Sci. Rep.* **15**, 23481 (2025).
10. Bound state solutions of Schrödinger equation with the superposition of Hulthén and Hellmann potentials via the NU method (various Okorie/Ikot co-authored works), including special-case reductions.
11. Approximate eigensolutions of the Attractive potential via parametric Nikiforov–Uvarov method, *ScienceDirect / PMC* (2018).

### Asymptotic Iteration Method

12. H. Ciftci, R. L. Hall, N. Saad, "Asymptotic iteration method for eigenvalue problems," *J. Phys. A: Math. Gen.* **36**, 11807 (2003).
13. I. Boztosun, "Bound state solutions of the Hulthén potential by using the asymptotic iteration method," *Phys. Scr.* **76**, 016 (2007).
14. O. Bayrak, I. Boztosun, "Asymptotic Iteration Method Solution of the Supersymmetric Schrödinger Equation," (conference/journal proceedings).
15. C. Berkdemir, A. Berkdemir, J. Han, "Analytical solutions to the Hulthén and the Morse potentials by using the asymptotic iteration method," *Comput. Phys. Commun.* / *Chem. Phys. Lett.* (2006).
16. E. Olğar, R. Koç, H. Tütüncüler, "The exact solution of the s-wave Klein–Gordon equation for the generalized Hulthén potential by the asymptotic iteration method," *Mod. Phys. Lett. A*.

### Supersymmetric Quantum Mechanics

17. L. E. Gendenshtein, "Derivation of exact spectra of the Schrödinger equation by means of supersymmetry," *JETP Lett.* **38**, 356 (1983).
18. L. E. Gendenshtein, I. V. Krive, "Supersymmetry in quantum mechanics," *Sov. Phys. Usp.* **28**, 645 (1985).
19. F. Cooper, A. Khare, U. Sukhatme, "Supersymmetry and quantum mechanics," *Phys. Rep.* **251**, 267 (1995); *Supersymmetry in Quantum Mechanics* (World Scientific, 2001).
20. B. Gönül, O. Özer, Y. Cancelik, M. Koçak, "Hamiltonian hierarchy and the Hulthén potential," *Phys. Lett. A* **275**, 238 (2000).
21. E. Kasap, B. Gönül, M. Şimşek, *Chem. Phys. Lett.* **172**, 499 (1990).

### Numerical / Pseudospectral / Independent Benchmark Methods

22. A. K. Roy, "The generalized pseudospectral approach to the bound states of Hulthén and Yukawa potentials," *Pramana / arXiv:1312.5900*.
23. A. K. Roy et al., "Critical parameters and spherical confinement of H atom in screened Coulomb potential," arXiv:1904.11166.
24. Relativistic effects in the screened Coulomb potentials (Sturmian-basis first-order Dirac perturbation study).
25. Simple wavefunctions for Yukawa- and Hulthén-type potentials (entropic/uncertainty-measure study), arXiv-hosted.

### Improved/Combined Centrifugal-Term Approximations

26. D. Nath, A. K. Roy, "Analytical solution of D-dimensional Schrödinger equation for Eckart potential with a new improved approximation in centrifugal term," arXiv:2205.09024.
27. D. Nath, A. K. Roy, "Ro-vibrational energy analysis of Manning–Rosen and Pöschl–Teller potentials with a new improved approximation in the centrifugal term," arXiv:2205.10313.
28. D. Nath, A. K. Roy, "Energy and information-entropic measures of Hulthén potential in D dimension by a new approximation to centrifugal term," *J. Math. Chem.* (2022).
29. Quantization rule solution to the Hulthén potential in arbitrary dimension by a new approximate scheme for the centrifugal term, arXiv:1104.0302.

### Combined / Generalized Potentials and Relativistic Extensions

30. Schrödinger equation with Hulthén potential plus ring-shaped potential, arXiv:0811.4441.
31. Analytical bound state solutions of the Dirac equation with the Hulthén plus a class of Yukawa potential including a Coulomb-like tensor interaction, *Eur. Phys. J. Plus* (2021).
32. Exact Eigenvalues and Eigenfunctions of the Hulthén Potential in the PT-Symmetry for Any Angular Momentum.
33. A Simple Efficient Method for Obtaining the Binding Energy of Lithium Nucleus under the Hulthén and Inversely Quadratic Yukawa Potentials, arXiv:1504.07359.
34. Approximate k-state solutions to the Dirac–Yukawa problem based on spin and pseudospin symmetry, arXiv:1203.2023.
35. Approximate analytical solutions of the Klein–Gordon equation with Hulthén potentials for nonzero angular momentum (various authors, *Mod. Phys. Lett. A* / *Phys. Scr.*).

### Older / Perturbative and Variational Studies

36. Structure of energy levels near critical coupling strengths for screened Coulomb and Hulthén potentials (strong-coupling expansion study).
37. Shifted 1/N expansion studies of the Hulthén potential (1980s–1990s journal literature; cited comparatively in AIM and NU papers above).
38. Variational-method studies of Hulthén potential bound states (cited comparatively across the AIM/NU/SUSY literature above).

---

*Note on sourcing: this review was compiled from a combination of open-access preprints (arXiv), peer-reviewed journal abstracts/content (Scientific Reports, European Physical Journal Plus, Journal of Mathematical Chemistry, Physica Scripta, Modern Physics Letters A, Revista Mexicana de Física, ScienceDirect/PMC), and cross-referenced citation lists found within these sources. Where exact page/volume details were not independently verifiable, entries are listed with the bibliographic information available from the sources consulted; readers requiring citation-grade precision should verify entries against the original journals.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Hulthén potential potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
