# Evaluation of Eigenvalues of the Schrödinger Equation with the Rosen–Morse Potential: An Exhaustive Review

## 1. Introduction and Historical Origin

The Rosen–Morse (RM) potential was introduced by Nathan Rosen and Philip M. Morse in 1932 as a model for the vibrational and rotational motion of polyatomic molecules (originally applied to NH₃), extending the earlier Morse potential (1929) which itself was designed for diatomic vibrational spectra. Since then, the RM potential has become one of the standard exactly (or quasi-exactly) solvable potentials of non-relativistic quantum mechanics, occupying a place alongside the Morse, Eckart, Hulthén, Pöschl–Teller, Scarf, Manning–Rosen, and Woods–Saxon potentials as members of the family of "shape-invariant," hypergeometric-type potentials.

The importance of the RM potential stems from several factors:

- It admits **closed-form (exact) solutions for the s-wave (ℓ = 0) radial equation** and **semi-analytical or approximate solutions for ℓ ≠ 0** once the centrifugal term is handled via approximation schemes.
- It is one of the six translationally shape-invariant potentials in one-dimensional supersymmetric quantum mechanics (SUSY QM), which guarantees an algebraic (ladder-operator) route to its full bound-state spectrum.
- It interpolates between other well-known solvable systems (Eckart potential, Pöschl–Teller potential, PT-symmetric potentials) as special/limiting cases of its parameters.
- It has direct physical relevance in molecular spectroscopy (diatomic/polyatomic vibrational-rotational spectra), particle/nuclear physics (quark–antiquark confinement via the trigonometric Rosen–Morse potential), soliton and kink stability analysis in field theory, and PT-symmetric/non-Hermitian quantum mechanics.

## 2. Functional Forms of the Rosen–Morse Potential

There is no single "Rosen–Morse potential" in the literature; rather, the name is applied to a family of related functional forms distinguished by whether the natural variable is hyperbolic or trigonometric, and whether the potential is symmetric or contains a linear (odd) term. The commonly used forms are:

### 2.1 Rosen–Morse I (hyperbolic, symmetric) — often called Rosen–Morse potential proper

$$V(x) = -V_1 \,\mathrm{sech}^2(\alpha x)$$

This form reduces to the symmetric hyperbolic Pöschl–Teller potential and is exactly solvable for all bound states.

### 2.2 Rosen–Morse II (hyperbolic, with linear/asymmetric term)

$$V(x) = -V_1\,\mathrm{sech}^2(\alpha x) + V_2\,\tanh(\alpha x)$$

This is the most frequently studied version in the SUSY-QM and Nikiforov–Uvarov literature. It is a shape-invariant potential with a finite number of bound states for $V_2 \neq 0$, and it reduces to Rosen–Morse I when $V_2 = 0$.

### 2.3 Trigonometric Rosen–Morse (TRM) potential

$$V(z) = a(a+1)\csc^2 z - 2b\cot z, \qquad 0 < z < \pi$$

This form supports an **infinite** discrete spectrum (owing to the confining $\csc^2 z$ singularity structure) and has been used extensively to model quark–antiquark confinement, giving rise to quasi-linear Regge trajectories for light mesons.

### 2.4 Radial/generalized (deformed) Rosen–Morse potential

In the radial Schrödinger equation for a diatomic molecule, a "deformed" or "generalized" Rosen–Morse potential of the form

$$V(r) = D\left[\left(\frac{1-e^{-\alpha(r-r_e)}}{1-q\,e^{-\alpha(r-r_e)}}\right)^2 - 1\right] + \dots$$

or, in another common parametrization,

$$V(r) = V_1\,\mathrm{sech}^2(\alpha r) + V_2\tanh(\alpha r) + \frac{\hbar^2\ell(\ell+1)}{2\mu r^2}$$

is used, where the centrifugal term forces recourse to approximation schemes (see Section 4).

### 2.5 Improved Rosen–Morse potential (IRMP)

A modified form introduced to better reproduce Rydberg–Klein–Rees (RKR) potential energy curves of diatomic molecules,

$$V(r) = D_e\left(\frac{1-e^{-\alpha(r-r_e)}}{1-e^{-\alpha r_e}}\right)^2 + \text{correction terms},$$

used widely by Jia and collaborators for high-precision spectroscopic fitting.

## 3. General Strategy for Eigenvalue Evaluation

Regardless of which precise form is used, the radial (or one-dimensional) time-independent Schrödinger equation

$$-\frac{\hbar^2}{2\mu}\frac{d^2\psi}{dx^2} + \left[V(x) + \frac{\hbar^2\,\ell(\ell+1)}{2\mu x^2}\right]\psi(x) = E\,\psi(x)$$

is converted, through a change of variable (typically $y = \tanh(\alpha x)$ for the hyperbolic form or $y=\cot z$ / $y = \cos z$ for the trigonometric form), into a **hypergeometric-type (Sturm–Liouville) second-order ODE**:

$$\psi''(y) + \frac{\tilde\tau(y)}{\sigma(y)}\psi'(y) + \frac{\tilde\sigma(y)}{\sigma^2(y)}\psi(y) = 0,$$

where $\sigma(y)$ is at most quadratic and $\tilde\tau(y)$ is at most linear. Once in this canonical form, the eigenvalues are extracted essentially algebraically. The families of methods used to carry out this program are described below.

## 4. Methods Used to Evaluate the Eigenvalues

### 4.1 Direct substitution / Jacobi- or Romanovski-polynomial method
For $\ell = 0$ (s-wave), an exact change of variable reduces the equation to a hypergeometric or Jacobi/Romanovski differential equation whose polynomial solutions immediately fix the quantization condition. This was the method used in essentially all of the early (1930s–1970s) treatments and gives the classic **closed-form energy formula**

$$E_n = -\frac{\hbar^2\alpha^2}{2\mu}\left[\frac{V_2^2/(\hbar^2\alpha^2/2\mu)^2 - (n+\delta)^2}{2(n+\delta)}\right]^2 \quad (\text{schematic form; exact coefficients depend on convention}),$$

typically written as

$$E_n = -\frac{\hbar^2\alpha^2}{8\mu}\left(2n+1+\delta\right)^2 - \frac{V_2^2/\left(\tfrac{\hbar^2\alpha^2}{2\mu}\right)}{2(2n+1+\delta)^2}$$

with $\delta$ fixed by $V_1$, $\alpha$, and $\mu$ (see the Flügge/Landau-and-Lifshitz style textbook treatments, and the Nikiforov–Uvarov derivations cited below).

### 4.2 Nikiforov–Uvarov (NU) Method
The most widely used technique in the post-2000 literature. The NU method provides a systematic algorithm (via a polynomial $\pi(s)$ and a parameter $\lambda$) for reducing the transformed equation to the hypergeometric type and extracting both the eigenvalues $E_n$ and the eigenfunctions (expressed as Jacobi polynomials, generalized Laguerre polynomials, or Gauss hypergeometric functions) in one unified procedure. It has been applied to essentially every variant of the RM potential: hyperbolic, trigonometric, PT-symmetric, deformed/q-deformed, position-dependent-mass, and D-dimensional generalizations.

### 4.3 Supersymmetric Quantum Mechanics (SUSY QM) and Shape Invariance
The RM II and trigonometric RM potentials are shape-invariant under parameter translation, i.e., their SUSY partner potentials $V_{\pm}(x;a_i)$ differ only by a shift of parameters $a_1 \to a_2 = f(a_1)$. This yields the entire bound-state spectrum algebraically:

$$E_n = E_0 + \sum_{k=1}^{n} R(a_k),$$

without ever solving a differential equation explicitly, plus the ladder (raising/lowering) operators that generate the eigenfunctions. This is historically important since the RM potential (specifically RM II) is one of the six original shape-invariant potentials with translation of parameters identified by Cooper, Khare, and Sukhatme, and by Gendenshtein.

### 4.4 Asymptotic Iteration Method (AIM)
AIM converts the Schrödinger equation into the form $\psi'' = \lambda_0(x)\psi' + s_0(x)\psi$ and iterates a termination condition $\delta_n(x) = \lambda_n s_{n-1} - \lambda_{n-1}s_n = 0$ to extract $E_n$. This has been applied to the RM potential including the centrifugal term, typically producing results in excellent agreement with NU and SUSY-QM results.

### 4.5 Factorization Method / Operator (Ladder) Approach
Historically, Infeld and Hull's factorization method (1951) classified the RM potential among the solvable potentials obtainable from factorizable Hamiltonians, giving an early algebraic derivation of its spectrum equivalent to the modern SUSY treatment.

### 4.6 Point Canonical Transformation (PCT)
Used especially for position-dependent effective-mass (PDM) Schrödinger equations. A PCT maps the constant-mass exactly solvable Schrödinger equation onto the PDM equation, generating exact RM-type eigenvalues as functions of a free deformation/mass parameter (Tezcan–Sever and related works).

### 4.7 Wentzel–Kramers–Brillouin (WKB) and Improved Quantization Rules
Semiclassical WKB quantization, and its refinements ("exact quantization rule," "improved quantization rule" of Ma and Xu), have been applied to obtain both exact and approximate eigenvalues, useful cross-checks against the algebraic methods, and are particularly convenient for potentials lacking closed-form NU solutions (e.g., certain deformed/q-deformed RM variants).

### 4.8 Numerical / Variational and Perturbative Techniques
For strongly deformed potentials, q-deformed forms, or when higher-order centrifugal/relativistic corrections are included, numerical diagonalization, variational trial wavefunctions, or perturbation theory around the exactly solvable ℓ = 0 case are used to benchmark the analytic approximations.

## 5. The Centrifugal Term Problem (ℓ ≠ 0)

For orbital angular momentum $\ell \neq 0$, the term $\ell(\ell+1)/r^2$ (or $\ell(\ell+1)\csc^2$/$\mathrm{sech}^2$ analogues) destroys the exact solvability of the radial equation because it does not have the same functional form as $\mathrm{sech}^2(\alpha r)$ or $\tanh(\alpha r)$. The standard remedy is an **approximation scheme for the centrifugal term**, of which the major variants are:

| Scheme | Approximate form used | Notes |
|---|---|---|
| Greene–Aldrich approximation | $\dfrac{1}{r^2}\approx \dfrac{\alpha^2}{(1-e^{-\alpha r})^2}$ | Classic, valid for $\alpha r \ll 1$; widely used pre-2000 |
| Pekeris-type approximation | Expansion of $1/r^2$ around the equilibrium point $r_e$ | Standard in molecular-spectroscopy applications |
| "Improved" approximation schemes (post-2004) | Various rational/exponential fits designed to extend validity to larger $\alpha r$ | Introduced by Jia, Qiang and coworkers; significantly improves agreement with numerical results, especially for higher $\ell$ |
| Exact treatment for special cases | s-wave (ℓ=0) is treated exactly; sometimes ℓ=0,1 handled exactly via special potential parameter choices | Used to check accuracy of approximation schemes |

Because of this necessity, the vast majority of "Schrödinger equation with Rosen–Morse potential including the centrifugal term" papers are, strictly speaking, **approximate** analytic solutions, whose accuracy is benchmarked against direct numerical integration (e.g., via Numerov's method) or against the exactly solvable s-wave case.

## 6. Representative Closed-Form Results

For the hyperbolic Rosen–Morse (RM-II) potential

$$V(x) = -V_1\,\mathrm{sech}^2(\alpha x) + V_2\tanh(\alpha x),$$

the bound-state energies obtained via NU/SUSY-QM methods take the schematic closed form

$$E_n = -\frac{\hbar^2\alpha^2}{8\mu}\left(2n+1+\varepsilon\right)^2 \;-\; \frac{2\mu V_2^2/\hbar^2}{\alpha^2\left(2n+1+\varepsilon\right)^2}, \qquad n = 0,1,2,\dots,n_{\max},$$

where $\varepsilon = \sqrt{1 + 8\mu V_1/(\hbar^2\alpha^2)}$, and the sum is capped at the maximum $n$ for which $E_n < 0$ (finite number of bound states, characteristic of the RM-II potential due to its asymptotic tilt).

For the trigonometric Rosen–Morse potential

$$V(z) = a(a+1)\csc^2 z - 2b\cot z,$$

the exact (all-$\ell$, ℓ here entering through $a$) spectrum is

$$E_n = (a+n+1)^2 + \frac{b^2}{(a+n+1)^2}, \qquad n = 0,1,2,\dots$$

(infinite tower of bound states — a key structural difference from RM-II), with eigenfunctions expressible through real orthogonal (Romanovski-type) polynomials rather than the originally-used complex Jacobi polynomials — an important correction to the literature identified by Compean and Kirchbach (2005).

## 7. Special/Limiting Cases and Related Potentials

The RM potential family connects to, and is sometimes used interchangeably or as a generalization of:

- **Eckart potential** — obtained as a limit/special case of RM-II.
- **(Symmetric) Pöschl–Teller potential** — RM-I is identical to the symmetric hyperbolic Pöschl–Teller potential.
- **PT-symmetric Rosen–Morse potential** — obtained by analytic continuation of parameters to complex values; studied extensively in non-Hermitian/PT-symmetric quantum mechanics (Bender–Boettcher-type analyses), including cases with asymptotically non-vanishing imaginary components.
- **Manning–Rosen potential** — a related but functionally distinct exponential potential, often treated by the same toolkit (NU, SUSY QM, AIM) and frequently confused with, or discussed alongside, the RM potential in the literature.
- **q-deformed / Rosen–Morse-based reflectionless potentials** — Khare and Sukhatme's construction of new shape-invariant potentials as q-deformations of the single-soliton (RM) solution.
- **Exactly solvable rational extensions** — using Darboux–Crum transformations and exceptional orthogonal polynomials (Xᵢ-Jacobi type) to construct new shape-invariant rational extensions of the RM-II and Eckart potentials with additional bound states.

## 8. Extensions Beyond the Basic Non-Relativistic Problem

The eigenvalue problem for the RM potential has been generalized along many directions, each producing its own dedicated eigenvalue literature:

1. **Relativistic extensions**: Klein–Gordon and Dirac equations with RM-type scalar/vector potentials (spin symmetry and pseudospin symmetry limits).
2. **D-dimensional generalizations**: Radial Schrödinger/Klein–Gordon equations in arbitrary spatial dimension $D$, relevant to formal studies of dimensional scaling.
3. **Position-dependent mass (PDM) Schrödinger equation**: Via point canonical transformations, exact/approximate RM eigenvalues as functionals of a spatially varying effective mass — relevant to semiconductor heterostructures and quantum dots.
4. **Complex/non-Hermitian mass and potential**: Complex Morse/Rosen–Morse-type potentials for open quantum systems and dark-matter-inspired toy models.
5. **q-deformed / fractional-derivative generalizations**: Generalized fractional NU method applied to the improved RM potential, producing energy formulas depending on the fractional order.
6. **Thermodynamic properties**: Once the closed-form (or approximate) energy spectrum $E_n$ is available, the partition function $Z(\beta) = \sum_n e^{-\beta E_n}$ (or its integral approximation) is used to derive vibrational specific heat, entropy, free energy, and mean energy of diatomic molecules — a very active application area (Jia and coworkers, Abu-Shady and coworkers, Ikot and coworkers).
7. **Applications to particle/hadron physics**: The trigonometric RM potential as a confining quark–antiquark potential, generating meson mass spectra and Regge trajectories used in QCD phenomenology.
8. **Kink/soliton stability analysis**: The RM-type potential arises as the fluctuation (stability) operator for kink solutions in classical field theory (e.g., $\phi^4$ and sine-Gordon-adjacent models); a complete NU treatment including the continuum (scattering) states was given by Alonso-Izquierdo, Fuertes, and coworkers.

## 9. Accuracy and Cross-Validation

Because the ℓ ≠ 0 case is intrinsically approximate, cross-validation between methods is a recurring theme:

- NU-method and SUSY-QM results are shown to coincide (as they must, given the shape invariance property).
- AIM results are typically checked against NU/SUSY results and found to agree closely for low-lying states, with deviations growing for higher $n$ or larger $\ell$ depending on the centrifugal approximation used.
- WKB and improved-quantization-rule results serve as an independent semiclassical check, generally accurate for large quantum numbers but sometimes surprisingly accurate even at low $n$ for exactly/quasi-exactly solvable potentials.
- Direct numerical (shooting/Numerov) solutions of the full radial equation (with the exact, unapproximated centrifugal term) are used in a number of papers as the final arbiter of accuracy, especially in the "improved Rosen–Morse potential" molecular-spectroscopy literature, where fits are benchmarked against experimental/RKR turning-point data for numerous diatomic molecules (e.g., H₂, HCl, CO, N₂, O₂, I₂, NO, ICl, and others).

## 10. Summary Table of Methods

| Method | Applicable regime | Output form | Key references (see list below) |
|---|---|---|---|
| Exact substitution / Jacobi–Romanovski polynomials | ℓ = 0, or trigonometric RM (all states) | Closed-form $E_n$ | Rosen & Morse 1932; Compean & Kirchbach 2005 |
| Nikiforov–Uvarov (NU) | ℓ = 0 exact; ℓ≠0 with centrifugal approximation | Closed-form $E_n$, Jacobi/hypergeometric wavefunctions | Nikiforov & Uvarov 1988; numerous 2005–2024 papers |
| SUSY QM / shape invariance | Exact, algebraic | Full spectrum + ladder operators | Cooper, Khare & Sukhatme 1995; Gendenshtein 1983 |
| Asymptotic Iteration Method (AIM) | ℓ = 0 exact; ℓ≠0 approximate | Iterative/closed-form $E_n$ | Ciftci, Hall & Saad 2003 (method); RM applications 2009+ |
| Point Canonical Transformation | PDM Schrödinger equation | Parametrized $E_n$ | Tezcan & Sever 2009 |
| WKB / improved quantization rule | Semiclassical, all $n$ | Approximate/exact $E_n$ | Ma & Xu 2005 (method) |
| Factorization method | Exact, algebraic | Closed-form $E_n$ | Infeld & Hull 1951 |
| Numerical (Numerov, variational) | Benchmark / arbitrary regime | Numerical $E_n$ | Various molecular spectroscopy papers |

## 11. Concluding Remarks

The evaluation of the eigenvalue spectrum of the Schrödinger equation with the Rosen–Morse potential is a mature but still active research area, sitting at the intersection of special-function theory (hypergeometric/Jacobi/Romanovski polynomials), algebraic methods (SUSY QM, shape invariance, factorization), and applied molecular/particle physics. The exact solution is available in closed form for the ℓ = 0 radial problem and for the full trigonometric RM potential; for ℓ ≠ 0 in the hyperbolic radial problem, a well-developed hierarchy of centrifugal-term approximations (Greene–Aldrich, Pekeris, and "improved" schemes) allows accurate semi-analytic energy formulas, cross-validated across NU, SUSY-QM, AIM, and WKB approaches. Current research activity focuses on: (i) higher-precision "improved" and fractional-order RM potentials for diatomic-molecule spectroscopy; (ii) rational/exceptional-polynomial extensions with enlarged shape invariance; (iii) relativistic (Klein–Gordon/Dirac), D-dimensional, and PDM generalizations; and (iv) applications to hadron spectroscopy via the trigonometric RM potential and to kink-stability analysis in classical field theory.

---

## List of Publications Related to the Rosen–Morse Potential Eigenvalue Problem

### Foundational / Historical

1. Rosen, N. & Morse, P. M. (1932). "On the Vibrations of Polyatomic Molecules." *Physical Review*, 42, 210.
2. Morse, P. M. (1929). "Diatomic Molecules According to the Wave Mechanics. II. Vibrational Levels." *Physical Review*, 34, 57.
3. Infeld, L. & Hull, T. E. (1951). "The Factorization Method." *Reviews of Modern Physics*, 23, 21.
4. Pekeris, C. L. (1934). "The Rotation-Vibration Coupling in Diatomic Molecules." *Physical Review*, 45, 98.
5. Eckart, C. (1930). "The Penetration of a Potential Barrier by Electrons." *Physical Review*, 35, 1303.

### Nikiforov–Uvarov Method Applications

6. Nikiforov, A. F. & Uvarov, V. B. (1988). *Special Functions of Mathematical Physics*. Birkhäuser, Basel.
7. "Approximate Solutions of the Schrödinger Equation for the Rosen-Morse Potential Including Centrifugal Term." *International Journal of Theoretical Physics* (2009). DOI: 10.1007/s10773-009-0059-1.
8. "Approximate Solution of the Schrödinger Equation with Rosen-Morse Potential Including the Centrifugal Term" (via Nikiforov-Uvarov method), thermodynamic properties of diatomic molecules.
9. Ikhdair, S. M. (2010). "Rotational and vibrational diatomic molecule energies using hypergeometric method." (Related applications to RM-type potentials.)
10. "The complete solution of the Schrödinger equation with the Rosen–Morse type potential via the Nikiforov–Uvarov method." *Nuclear Physics B* / ScienceDirect (2023).
11. "Exact solution of Schrödinger equation with q-deformed quantum potentials using Nikiforov-Uvarov method." *arXiv:1109.3894*.
12. "The Nikiforov-Uvarov method" (pedagogical review including Rosen–Morse II as a worked example). *arXiv:2411.00804*.

### Supersymmetric Quantum Mechanics / Shape Invariance

13. Gendenshtein, L. E. (1983). "Derivation of exact spectra of the Schrödinger equation by means of supersymmetry." *JETP Letters*, 38, 356.
14. Cooper, F., Khare, A. & Sukhatme, U. (1995). "Supersymmetry and Quantum Mechanics." *Physics Reports*, 251, 267.
15. Khare, A. & Sukhatme, U. P. (1993). "New Shape Invariant Potentials in Supersymmetric Quantum Mechanics." *Journal of Physics A: Mathematical and General*, 26, L901. (*arXiv:hep-th/9212147*).
16. Compean, C. B. & Kirchbach, M. (2006). "The Trigonometric Rosen–Morse Potential in the Supersymmetric Quantum Mechanics and its Exact Solutions." *Journal of Physics A: Mathematical and General*, 39, 547. (*arXiv:quant-ph/0509055*).
17. Bermudez, D. & Fernández C., D. J. "Non-Hermitian Hamiltonians and supersymmetric quantum mechanics" (Rosen-Morse related susy chains).
18. Quesne, C. (2013). "Novel Enlarged Shape Invariance Property and Exactly Solvable Rational Extensions of the Rosen-Morse II and Eckart Potentials." *SIGMA* / *arXiv:1208.6165*.
19. "A Method of Constructing Superpotentials by Combining Two Functions Based on Shape Invariance" (application to Rosen–Morse family).
20. "Analysis of Energy Spectra and Wave Function of Trigonometric Poschl-Teller plus Rosen-Morse Non-Central Potential Using Supersymmetric Quantum Mechanics Approach."

### Asymptotic Iteration Method

21. Ciftci, H., Hall, R. L. & Saad, N. (2003). "Asymptotic iteration method for eigenvalue problems." *Journal of Physics A: Mathematical and General*, 36, 11807.
22. "Approximate Solution of the Schrödinger Equation with Rosen-Morse Potential Including the Centrifugal Term" (AIM-based treatment).
23. "Exact Solution to the Schrödinger Equation with Manning-Rosen Potential Via WKB Approximation Method" (comparative AIM/WKB study referencing RM-type potentials).
24. "Solutions to the Modified Pöschl–Teller Potential in D-Dimensions" (AIM, with cross-reference to Rosen-Morse-family results).

### Position-Dependent Mass / Point Canonical Transformation

25. Tezcan, C. & Sever, R. (2009). "Exact Solutions of the Schrödinger Equation with Position-Dependent Effective Mass via General Point Canonical Transformation." *Journal of Mathematical Chemistry* (*arXiv:quant-ph/0604041*).

### PT-Symmetric / Non-Hermitian Extensions

26. "The PT-symmetric Rosen-Morse II potential: effects of the asymptotically non-vanishing imaginary potential component." *European Physical Journal Plus* (2017).
27. "Exact solution of Schrödinger equation for the complex Morse potential to investigate physical systems with position-dependent complex mass." *arXiv:2507.04658*.

### Molecular Spectroscopy / Improved Rosen–Morse Potential

28. Jia, C.-S., Liu, S.-R. & Chen, T. (2013). "Solutions of the Klein-Gordon equation with the improved Rosen–Morse potential energy model." *European Physical Journal Plus*, 128, 69.
29. "Rotation-vibrational energies for some diatomic molecules with improved Rosen–Morse potential in D-dimensions." *Journal of Molecular Modeling* (2019).
30. Abu-Shady, M. & Khokha, E. M. (2023). "A precise estimation for vibrational energies of diatomic molecules using the improved Rosen–Morse potential." *Scientific Reports*, 13, 11578.
31. Khokha, E. M., Abu-Shady, M. & Abdel-Karim, T. A. "Fractional-order improved Rosen-Morse potential applications" (thermodynamic and RKR data fitting).
32. Wang, P.-Q. et al. (2012). "Improved expressions for the Schiöberg potential energy models for diatomic molecules." *Journal of Molecular Spectroscopy*, 278, 23.
33. Araújo, R. et al. (2021). "A comparative review of 50 analytical representation of potential energy interaction for diatomic systems: 100 years of history." *International Journal of Quantum Chemistry* (survey including Rosen–Morse).

### Relativistic (Klein–Gordon / Dirac) Extensions

34. "Solution of Klein Gordon Equation for Some Diatomic Molecules with New Generalized Morse-like Potential Using SUSYQM."
35. "Arbitrary ℓ-state solutions of the Klein-Gordon equation with the Manning-Rosen plus a Class of Yukawa potentials." *arXiv:2003.02854*.
36. Ikot, A. N., Obong, H. P. & Hassanabadi, H. (2015). "Relativistic symmetries of D-dimensional Dirac equation with multiparameter exponentials using supersymmetric quantum mechanics."
37. "Relativistic treatment of the Hellmann-generalized Morse potential." *Revista Mexicana de Física* (SciELO, 2020).

### Particle Physics / Hadron Spectroscopy Applications

38. "Trigonometric Rosen-Morse Potential as the Quark-Antiquark Interaction Potential for Meson Properties in the Non-Relativistic Quark Model Using EAIM." *arXiv:1905.05689*.
39. Kirchbach, M. & Compean, C. B. "Baryon spectroscopy via conformal / trigonometric Rosen-Morse potentials" (related quark-model applications).

### Kink Stability / Field-Theoretic Applications

40. Alonso-Izquierdo, A. and coworkers, "The complete solution of the Schrödinger equation with the Rosen–Morse type potential via the Nikiforov–Uvarov method" (kink fluctuation operator; bound and scattering states). *ScienceDirect* (2023).

### General Reviews / Compilations

41. Flügge, S. *Practical Quantum Mechanics*. Springer (standard textbook derivation of Rosen–Morse/Pöschl–Teller-type bound states).
42. "rosen-morse potential including" — topic aggregation, Science.gov / OSTI compilation of related U.S. DOE-sponsored physics papers on Rosen–Morse and related exponential-type potentials.

*Note: Several entries above are drawn from conference proceedings, preprint servers (arXiv), and aggregator/secondary sources; where a full bibliographic record (volume/page) was not confirmed during this review, the entry is included with the most complete citation information available and should be verified against the original journal before formal citation.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Rosen–Morse potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
