# Evaluation of Eigenvalues of the Schrödinger Equation with the Pöschl–Teller Potential: A Review

## 1. Introduction

The Pöschl–Teller (PT) potential, introduced by Gustav (Herta) Pöschl and Edward Teller in 1933, is one of the oldest and most important members of the small family of *exactly solvable* potentials in one-dimensional quantum mechanics. Its enduring relevance stems from three facts: (i) it admits closed-form bound-state and scattering solutions for arbitrary integer or non-integer strength parameters in the $s$-wave (zero angular momentum) case; (ii) it serves as an accurate and computationally convenient model potential for molecular vibrations, solitons, optical waveguides, and reflectionless scattering; and (iii) once orbital angular momentum ($\ell \neq 0$) or additional structure (position-dependent mass, deformation parameters, relativistic corrections) is introduced, the equation ceases to be exactly solvable, making it a standard testbed for essentially every modern approximate eigenvalue technique developed in mathematical physics and quantum chemistry.

This review surveys the mathematical structure of the PT potential, the exact solution of the associated Schrödinger equation, and the wide range of methods that have been used to evaluate its energy eigenvalues — both in the exactly solvable sector and in generalized/deformed variants that require approximation.

---

## 2. Forms of the Pöschl–Teller Potential

Several inequivalent potentials share the "Pöschl–Teller" name in the literature; care must be taken to distinguish them.

### 2.1 Hyperbolic (non-periodic) form

$$V(x) = -\frac{\lambda(\lambda+1)\hbar^2\alpha^2}{2m}\,\mathrm{sech}^2(\alpha x)$$

This is the potential most often called simply "the Pöschl–Teller potential" in the soliton and reflectionless-potential literature. For $\lambda = 1, 2, 3, \dots$ it is reflectionless and coincides with the $N$-soliton potentials of the Korteweg–de Vries (KdV) equation.

### 2.2 Trigonometric (periodic) form

$$V(x) = \frac{\hbar^2\alpha^2}{2m}\left[\frac{\kappa(\kappa-1)}{\sin^2(\alpha x)} + \frac{\mu(\mu-1)}{\cos^2(\alpha x)}\right]$$

confined to $0 < \alpha x < \pi/2$, historically used for molecular vibrational spectra and often labelled "Scarf" or "trigonometric PT" depending on parameterization.

### 2.3 Generalized/modified hyperbolic form (most used in molecular physics)

$$V(x) = D_e\left[\frac{\mathrm{sech}^2(\alpha x)}{\ldots}\right] \quad \text{or equivalently} \quad V(r) = V_1\,\mathrm{sech}^2(\alpha r) - V_2\,\mathrm{sech}(\alpha r)\tanh(\alpha r)$$

or the frequently used two-parameter "generalized Pöschl–Teller" (also called Rosen–Morse-type when combined with a $\tanh$ term):

$$V(r) = \frac{\hbar^2\alpha^2}{2\mu}\left[\frac{A(A-1)}{\sinh^2(\alpha r)} - \frac{B}{\cosh^2(\alpha r)}\right]$$

This form, and its "second" and "modified" variants (often written $-V_0\,\mathrm{sech}^2(\alpha r)$ with a repulsive core), is the one most commonly fitted to diatomic-molecule vibrational data and is the workhorse of the ro-vibrational eigenvalue literature.

### 2.4 $q$-deformed / superstatistics variants

Recent literature has introduced deformation parameters $q$ (via deformed hyperbolic functions $\sinh_q$, $\cosh_q$) to interpolate between PT-type and other exactly solvable potentials, motivated by non-extensive statistical mechanics (Tsallis-type superstatistics) and used to model anharmonic corrections in diatomic spectra.

---

## 3. Exact Solution for $\ell = 0$ (S-wave / One-Dimensional Case)

For the one-dimensional (or $s$-wave radial) Schrödinger equation

$$-\frac{\hbar^2}{2m}\psi''(x) - \frac{\hbar^2\alpha^2}{2m}\lambda(\lambda+1)\,\mathrm{sech}^2(\alpha x)\,\psi(x) = E\,\psi(x),$$

the substitution $s = \tanh(\alpha x)$ converts the equation into the associated Legendre differential equation. The normalizable bound-state solutions exist only for integer $\lambda = 1, 2, 3, \dots$, with

$$\psi_{\lambda,\mu}(x) = P_\lambda^{\mu}(\tanh \alpha x), \qquad E_{\lambda,\mu} = -\frac{\hbar^2\alpha^2}{2m}\mu^2, \qquad \mu = \lambda, \lambda-1, \dots, 1,$$

where $P_\lambda^\mu$ are associated Legendre functions. Equivalently, in terms of the more commonly used quantum number $n = 0, 1, \dots, \lambda - 1$ (with $\mu = \lambda - n$),

$$E_n = -\frac{\hbar^2\alpha^2}{2m}(\lambda - n)^2.$$

For non-integer $\lambda$, the equation is solved in terms of hypergeometric or Gegenbauer/Jacobi functions, and the discrete spectrum is obtained from the condition that the hypergeometric series terminates (polynomial solution), giving the general closed-form result

$$E_n = -\frac{\hbar^2\alpha^2}{2m}\left(\lambda - n\right)^2, \qquad n = 0, 1, \dots, \lfloor \lambda \rfloor .$$

Continuum (positive-energy) states exist for all $E > 0$ and are characterized by reflectionless transmission when $\lambda$ is an integer — the origin of the potential's role as the KdV $N$-soliton potential and its use as a model of a perfectly transparent quantum barrier/well.

This exact solvability places the PT potential, together with the Coulomb, harmonic oscillator, Morse, Eckart, Hulthén, and Scarf potentials, in the standard list of *shape-invariant* potentials of supersymmetric quantum mechanics (SUSY QM).

---

## 4. Why Exact Solvability Breaks Down: The Centrifugal/Rotational Term

In three-dimensional or ro-vibrational applications, the radial Schrödinger equation for $\ell \neq 0$ acquires a centrifugal barrier $\ell(\ell+1)/r^2$ (or, for the trigonometric form, an additional $1/\sin^2$ or $1/\cos^2$ term already present). Once this term is combined with the hyperbolic PT terms, the resulting equation is **no longer exactly solvable** — the effective potential does not map onto a hypergeometric equation with the same structure. This is the central technical obstacle that motivates essentially the entire approximate-methods literature discussed below. The two dominant strategies are:

1. **Approximate the centrifugal/rotational term** by an exponential or hyperbolic form that preserves exact solvability of the *approximated* problem (Pekeris-type approximation, Greene–Aldrich approximation, and hybrid/improved combinations thereof), then solve exactly.
2. **Solve the original equation approximately** using perturbative, semiclassical, variational, or purely numerical machinery, without modifying the centrifugal term.

---

## 5. Methods Used to Evaluate the Eigenvalues

### 5.1 Direct exact solution (hypergeometric / Legendre / Jacobi function approach)
Applicable only to $\ell = 0$ or one-dimensional PT problems; solved via the substitution $s=\tanh(\alpha x)$ or $s = \mathrm{sech}(\alpha x)$, reducing the equation to the (associated) Legendre or hypergeometric differential equation.

### 5.2 Nikiforov–Uvarov (NU) Method
The single most widely used technique in the modern literature. The NU method reduces a generalized hypergeometric-type equation
$$\psi''(s) + \frac{\tilde\tau(s)}{\sigma(s)}\psi'(s) + \frac{\tilde\sigma(s)}{\sigma^2(s)}\psi(s) = 0$$
to a form solvable via Rodrigues-type formulas, yielding energy eigenvalues algebraically once the centrifugal term has been approximated (see §5.7–5.8). The "parametric NU method" (a streamlined tabulated version) is now standard for PT-type, Morse, Eckart, Hulthén, Deng–Fan, Manning–Rosen, and Hua potentials alike.

### 5.3 Supersymmetric Quantum Mechanics (SUSY QM) and Shape Invariance
Because the hyperbolic PT potential is shape-invariant under parameter translation, the SUSY QM hierarchy of Hamiltonians method yields the *exact* bound-state spectrum algebraically, without ever solving a differential equation explicitly — via the superpotential $W(x) = A\tanh(\alpha x)$ and the shape-invariance condition relating successive partner potentials. This method has been extended to non-central and multi-parameter generalizations of PT (e.g., PT plus Rosen–Morse, PT plus trigonometric Scarf) and to $q$-deformed superpotentials.

### 5.4 Factorization Method
Historically the precursor of SUSY QM (Infeld–Hull, 1951); ladder/raising-lowering operators are constructed directly for the PT Hamiltonian, generating the spectrum via the algebra of the operators.

### 5.5 Asymptotic Iteration Method (AIM)
An iterative technique for solving second-order linear ODEs of the form $y'' = \lambda_0(x) y' + s_0(x) y$; a termination condition $\delta_n \equiv \lambda_n s_{n-1} - \lambda_{n-1}s_n = 0$ yields the eigenvalues. AIM has been applied extensively to PT-type potentials (bound states, and even quasinormal modes of black holes modeled by inverted/PT-like barriers), typically reproducing NU-method results and offering an alternative computational route amenable to symbolic algebra software.

### 5.6 WKB and Semiclassical Quantization Rules
- **Standard WKB (Bohr–Sommerfeld) quantization**: known to give relatively poor accuracy for PT-type (and other trigonometric-well) potentials, especially at low quantum numbers.
- **Matrix Bohr–Sommerfeld (mBS)**: an improved matrix formulation, better but still not highly accurate for PT wells.
- **Supersymmetric WKB (SWKB)**: remarkably, SWKB reproduces the *exact* PT eigenvalues, because PT is shape-invariant — a celebrated illustration of the connection between shape invariance and exactness of the lowest-order SWKB quantization condition.
- **Exact Quantization Rule (EQR) / Proper Quantization Rule (PQR)**: modern refinements of WKB-type quantization (built from the logarithmic derivative of the wavefunction and Maslov-type correction terms) that reproduce exact or near-exact PT eigenvalues and generalize well to deformed/asymmetric PT variants.

### 5.7 Pekeris-Type Approximation for the Centrifugal Term
Introduced originally for the Morse potential (Pekeris, 1934) and subsequently transplanted to essentially every exponential-type potential, this approximates $1/r^2$ by an expansion in $e^{-\alpha r}$ (or $\mathrm{csch}^2$/$\mathrm{sech}^2$ terms) around the potential minimum $r_e$, preserving the exact solvability of the *effective* equation and permitting a closed algebraic formula for $E_{n\ell}$.

### 5.8 Greene–Aldrich Approximation and Hybrid/Improved Schemes
An alternative approximation, $1/r^2 \approx \alpha^2/\sin^2(\alpha r)$ (or $\mathrm{csch}^2$ analogues), commonly combined with the NU method. Recent work (Nath & Roy, 2022) proposes a tunable hybrid scheme interpolating between the Greene–Aldrich and Pekeris-type approximations via adjustable parameters, systematically recovering both limits and improving accuracy for ro-vibrational spectra of diatomic molecules.

### 5.9 Quasilinearization Method (QLM)
An iterative linearization of the Riccati equation associated with the logarithmic derivative of the wavefunction; the lowest QLM iterate reproduces the *exact* PT eigenvalues (along with Coulomb, harmonic oscillator, Morse, Hulthén, Hylleraas, and Eckart potentials), while higher iterates converge extremely rapidly (many significant figures) for potentials that are not exactly solvable.

### 5.10 Variational, Perturbative, and Numerical (Shooting/Matrix Diagonalization) Methods
Used both as independent eigenvalue solvers and, more commonly, as **benchmarks** against which the analytic/semi-analytic approximations above are validated. Finite-difference and generalized pseudospectral methods are frequently cited for this purpose in the ro-vibrational spectroscopy literature.

### 5.11 Point Canonical Transformation (PCT) and Position-Dependent Mass (PDM) Extensions
The PT potential (and its generalized/deformed forms) arises naturally as the target potential under specific point canonical transformations applied to solvable reference equations; this framework has been used to systematically generate PDM-Schrödinger-equation analogues of the PT problem, including magnetic/Aharonov–Bohm-flux-dressed versions relevant to low-dimensional condensed-matter systems.

---

## 6. Summary Comparison of Methods

| Method | Exactness | Handles $\ell \neq 0$? | Typical Output Form |
|---|---|---|---|
| Direct hypergeometric/Legendre solution | Exact | No (ℓ=0 only) | Closed algebraic formula |
| SUSY QM / shape invariance | Exact | Limited (non-central extensions) | Closed algebraic formula |
| Factorization method | Exact | No | Closed algebraic formula |
| Nikiforov–Uvarov + Pekeris/Greene–Aldrich | Approximate (from centrifugal term) | Yes | Closed algebraic formula |
| Asymptotic Iteration Method | Approximate or exact (case-dependent) | Yes | Iterative/semi-analytic |
| SWKB | Exact (for shape-invariant PT) | Limited | Quantization condition |
| Standard WKB / Bohr–Sommerfeld | Approximate, often poor at low $n$ | Yes | Quantization condition |
| Exact/Proper Quantization Rule | Near-exact to exact | Yes | Quantization condition |
| Quasilinearization Method | Exact (1st iterate for PT) | Yes (general potentials) | Iterative closed form |
| Numerical (shooting, diagonalization) | Numerically exact (benchmark) | Yes | Numerical eigenvalues |

---

## 7. Applications Driving Eigenvalue Studies

- **Diatomic molecular spectroscopy**: ro-vibrational energy levels of H₂, HCl, LiH, CO, ScH, TiH, VH, CrH, CuLi, TiC, NiC, ScN, ScF, and related molecules, with thermodynamic functions (partition function, mean energy, specific heat, free energy, entropy) derived from the resulting spectra.
- **Relativistic extensions**: Klein–Gordon and Dirac equations with (spin- and pseudospin-symmetric) PT-type potentials, including position-dependent mass and $q$-deformed generalizations.
- **Solitons and integrable systems**: reflectionless PT potentials as the exact potentials associated with $N$-soliton solutions of the KdV equation.
- **Condensed matter / nanostructures**: PT-like confinement potentials in quantum wells and wires, magnetic/Aharonov–Bohm flux-threaded systems.
- **Black-hole physics**: PT and inverted-PT ("Scarf II"-like) potentials as approximations to the effective potential barriers governing quasinormal-mode spectra.
- **Mathematical finance**: recently, the PT eigenvalue problem has been repurposed in stochastic volatility modeling (quadratic local-volatility models mapped onto hyperbolic-geometry Schrödinger problems).

---

## 8. Concluding Remarks

The Pöschl–Teller potential occupies a unique place in the catalogue of exactly solvable quantum-mechanical problems: it is simple enough to yield closed-form eigenvalues via elementary function substitutions, yet rich enough that its generalizations (arbitrary $\ell$, deformed/asymmetric forms, position-dependent mass, relativistic wave equations) have motivated — and continue to motivate — the development and cross-validation of essentially every major analytic and semi-analytic eigenvalue technique in molecular and mathematical physics: the Nikiforov–Uvarov method, supersymmetric shape-invariance techniques, the asymptotic iteration method, WKB and its supersymmetric/exact refinements, the quasilinearization method, and Pekeris/Greene–Aldrich-type centrifugal approximations. The continuing stream of publications on "modified," "generalized," "q-deformed," and multi-dimensional PT potentials indicates that this ninety-year-old potential remains an active proving ground for new eigenvalue methods.

---

## 9. List of Related Publications

**Foundational**
1. G. Pöschl, E. Teller, "Bemerkungen zur Quantenmechanik des anharmonischen Oszillators," *Z. Phys.* **83**, 143 (1933).
2. L. Infeld, T. E. Hull, "The Factorization Method," *Rev. Mod. Phys.* **23**, 21 (1951).
3. C. L. Pekeris, "The Rotation-Vibration Coupling in Diatomic Molecules," *Phys. Rev.* **45**, 98 (1934).

**Supersymmetric QM / Shape Invariance**
4. L. É. Gendenshteĭn, "Derivation of exact spectra of the Schrödinger equation by means of supersymmetry," *JETP Lett.* **38**, 356 (1983).
5. R. Dutt, A. Khare, U. P. Sukhatme, "Supersymmetry, shape invariance, and exactly solvable potentials," *Am. J. Phys.* **56**, 163 (1988).
6. F. Cooper, A. Khare, U. Sukhatme, "Supersymmetry and quantum mechanics," *Phys. Rep.* **251**, 267 (1995).
7. C.-L. Ho, "Shape invariance in prepotential approach to exactly solvable models," arXiv:0811.1511 (2009).
8. C. Rasinariu, J. V. Mallow, A. Gangopadhyaya, "Exactly solvable problems of quantum mechanics and their spectrum generating algebras: A review," *De Gruyter* (open review article).
9. F. Correa, V. Jakubský, "Shape invariant potentials with PT symmetry," arXiv:quant-ph/9911116.
10. H. Li et al., "Shape Invariance of Solvable Schrödinger Equations with the Generalized Hyperbolic Pöschl–Teller Potential," *Adv. Math. Phys.* **2022**, 4345342 (2022).
11. B. Bagchi, "Nonlinear Supersymmetric Quantum Mechanics: concepts and realizations," arXiv:1207.6799.

**Nikiforov–Uvarov Method and Centrifugal-Term Approximations**
12. A. F. Nikiforov, V. B. Uvarov, *Special Functions of Mathematical Physics* (Birkhäuser, Basel, 1988).
13. S. M. Ikhdair, R. Sever, "Exact Supersymmetric Solution of Schrödinger Equation for central confining Potentials by using the Nikiforov–Uvarov Method," arXiv:hep-th/0409139.
14. C. Berkdemir, A. Berkdemir, J. Han, "Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential," related NU-method literature on exponential-type potentials.
15. C. S. Jia, T. Chen, L. G. Cui, "Approximate analytical solutions of the Dirac equation with the generalized Pöschl–Teller potential including the pseudo-centrifugal term," *Phys. Lett. A* (representative NU/Pekeris study).
16. "Approximate Analytical Solutions to the Generalized Pöschl–Teller Potential in D Dimensions," *Chin. Phys. Lett.* **29**, 020303 (2012).
17. "Solutions of the Second Pöschl–Teller Potential Solved by an Improved Scheme to the Centrifugal Term," (ResearchGate/journal article, NU + Pekeris-type approximation).
18. K. J. Oyewumi, O. J. Oluwadare, K. D. Sen, O. A. Babalola, "Bound state solutions of the Deng–Fan molecular potential with the Pekeris-type approximation using the Nikiforov–Uvarov (N–U) method," *J. Math. Chem.* **51**, 976 (2013).
19. D. Nath, A. K. Roy, "Ro-vibrational energy analysis of Manning-Rosen and Pöschl-Teller potentials with a new improved approximation in the centrifugal term," arXiv:2205.10313 (2022).
20. D. Nath, A. K. Roy, "Ro-vibrational energy and thermodynamic properties of molecules subjected to Deng-Fan potential through an improved approximation," arXiv:2205.09590 (2022).
21. "Rovibrational Spectroscopy of Diatomic Molecules in a Modified Morse Potential using Nikiforov-Uvarov Functional Analysis," arXiv:2409.06598 (2024).
22. "Energy spectrum and zero-temperature magnetic functions of a position-dependent mass system in a Pöschl-Teller-type potential constrained by a vector magnetic potential field," (PDM + AB flux, parametric NU + Pekeris-like scheme).
23. "Solutions to the Modified Pöschl–Teller Potential in D-Dimensions," (Wiley, representative D-dimensional NU study).

**Asymptotic Iteration Method**
24. H. Ciftci, R. L. Hall, N. Saad, "Asymptotic iteration method for eigenvalue problems," *J. Phys. A: Math. Gen.* **36**, 11807 (2003).
25. H. T. Cho, A. S. Cornell, J. Doukas, W. Naylor, "A New Approach to Black Hole Quasinormal Modes: A Review of the Asymptotic Iteration Method," *Adv. Math. Phys.* **2012**, 281705 (2012).
26. B. J. Falaye, S. M. Ikhdair, M. Hamzavi, "Relativistic and non-relativistic solutions for the Pöschl-Teller potential via AIM," representative AIM/PT studies (2013–2015).
27. "Approximate Analytical Solutions to Relativistic and Nonrelativistic Pöschl-Teller Potential with its Thermodynamic Properties," arXiv:1308.0155.
28. "Pöschl–Teller potential" (An-Najah University staff profile summary of AIM applied to Schrödinger and Dirac PT problems with spin/pseudospin symmetry).

**WKB, SWKB, and Quantization-Rule Methods**
29. A. Sinha, R. Roychoudhury, "SWKB Quantization Rules for Bound States in Quantum Wells," arXiv:quant-ph/9911012.
30. M. A. F. Gomes, S. K. Adhikari, "Matrix formulation of the Bohr–Sommerfeld quantization rule for bound states," *J. Phys. B* **30**, 5987 (1997).
31. R. Krivec, V. B. Mandelzweig, "Quasilinearization Method and WKB," arXiv:math-ph/0410016.
32. V. B. Mandelzweig, "Quasilinearization method and summation of the WKB series," (2005).
33. "Application of WKB Method in Evaluation of Energy Eigenvalue of a Symmetric Parabolic AlAs Quantum Well Structure," (application study referencing PT quantization-rule comparisons).
34. E. Z. Liverts, V. B. Mandelzweig, "Approximate non-relativistic s-wave energy spectra with non-polynomial potentials within the framework of the WKB approximation," *Quantum Stud. Math. Found.* (2021).

**Trigonometric / Non-Central / Deformed Pöschl–Teller**
35. S. Antomi, Suparmi, Cari, Y. Hatma, "Analysis of Energy Spectra and Wave Function of Trigonometric Pöschl-Teller plus Rosen-Morse Non-Central Potential Using Supersymmetric Quantum Mechanics Approach," *Int. J. Eng. Res.* (2013).
36. "Solution of the Schrödinger Equation for Trigonometric Scarf Plus Pöschl-Teller Non-Central Potential Using Supersymmetry Quantum Mechanics," (2016/2019 versions).
37. "Thermodynamic properties of the Superstatistics and Normal Statistics of the Schrödinger Equation with generalized trigonometric Pöschl-Teller potential," arXiv:1912.00148.
38. A. Arda, R. Sever, C. Tezcan, "Analytical Solutions of Klein-Gordon Equation with Position-Dependent Mass for q-Parameter Pöschl-Teller potential," arXiv:0911.4558.

**Position-Dependent Mass and Point Canonical Transformation**
39. "A systematic study on the exact solution of the position dependent mass Schrödinger equation," arXiv:quant-ph/0410127.
40. B. Bagchi, P. Gorain, C. Quesne, R. Roychoudhury, "A general scheme for the effective-mass Schrödinger equation and the generation of the associated potentials," related PDM/PCT literature on PT-family potentials.

**Mathematical Reference / Encyclopedic**
41. Wikipedia contributors, "Pöschl–Teller potential," *Wikipedia, The Free Encyclopedia* (overview of symmetric/asymmetric forms, Legendre-function solutions, reflectionless/KdV connection).
42. Wolfram Demonstrations Project, "Eigenstates for Pöschl-Teller Potentials" (interactive exact bound-state/continuum-state summary).

**Recent / Interdisciplinary Applications**
43. "Quadratic Volatility from the Pöschl-Teller Potential and Hyperbolic Geometry," arXiv:2507.12501 (2025) — application of the PT eigenvalue problem to stochastic volatility modeling in mathematical finance.

---

*Note: Several entries above are drawn from arXiv preprints, conference proceedings, and secondary (ResearchGate/abstract-service) listings rather than final journal versions; readers requiring precise volume/page/DOI data for citation purposes should verify against the publisher's or arXiv's canonical record for each entry.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Pöschl–Teller potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
