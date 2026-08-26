# Evaluation of Eigenvalues of the Schrödinger Equation with the Morse Potential: An Exhaustive Review

## 1. Introduction

The Morse potential, introduced by Philip M. Morse in 1929 as a model for the vibrational motion of diatomic molecules, remains one of the most important exactly and approximately solvable potentials in quantum mechanics. Unlike the harmonic oscillator, it correctly captures bond anharmonicity and dissociation (the existence of a finite number of bound states and a continuum above the dissociation threshold), while still admitting closed-form or highly accurate semi-analytical treatment. Because of this balance between physical realism and mathematical tractability, the eigenvalue problem for the Morse potential has served for nearly a century as a testbed for new methods in quantum theory — from early factorization techniques, through supersymmetric quantum mechanics (SUSY QM) and the Nikiforov–Uvarov (NU) formalism, to modern numerical grid, matrix, and machine-learning-assisted approaches.

This review surveys the full landscape of techniques used to compute the eigenvalues (bound-state energies) of the one-dimensional (and radial, three-dimensional) Schrödinger equation with the Morse potential, discusses the exact $\ell = 0$ solution, the fundamental difficulty introduced by the centrifugal term for $\ell \neq 0$, the main families of approximations devised to handle it, purely numerical strategies, and extensions to generalized/deformed Morse-type potentials, position-dependent mass, PT-symmetric and complex-mass variants, and D-dimensional formulations.

---

## 2. The Morse Potential and the Schrödinger Equation

### 2.1 Definition

The (one-dimensional) Morse potential is

$$V(x) = D_e\left[1 - e^{-a(x - x_e)}\right]^2 = D_e\left(e^{-2a(x-x_e)} - 2e^{-a(x-x_e)}\right) + D_e,$$

where $D_e$ is the dissociation energy, $x_e$ the equilibrium separation, and $a$ controls the potential width (related to the force constant and anharmonicity). Shifting the energy zero, the potential is often written in the exponential form

$$V(x) = V_o\left(e^{-2\alpha x} - 2 e^{-\alpha x}\right),$$

which is the form used in most eigenvalue derivations.

### 2.2 The radial/three-dimensional problem

For the diatomic-molecule application the relevant equation is the radial Schrödinger equation

$$-\frac{\hbar^2}{2\mu}\frac{d^2 u(r)}{dr^2} + \left[V(r) + \frac{\hbar^2 \ell(\ell+1)}{2\mu r^2}\right] u(r) = E\, u(r),$$

with $\mu$ the reduced mass and $\ell$ the rotational quantum number. The centrifugal term $\ell(\ell+1)/r^2$ is the central obstruction: it is *not* of the same exponential functional form as the Morse potential, so the equation is exactly solvable in closed form only for $\ell = 0$ (s-states). This single fact motivates the overwhelming majority of the approximation literature discussed below.

---

## 3. Exact Solution for $\ell = 0$ (s-wave / pure vibrational problem)

Morse's original 1929 method transforms the equation via $y = e^{-\alpha(x - x_e)}$, converting it into the differential equation for the associated Laguerre polynomials. The resulting exact bound-state energies are

$$E_n = -D_e + \hbar\omega_0\left(n + \tfrac12\right) - \hbar\omega_0 x_e\left(n + \tfrac12\right)^2, \qquad n = 0, 1, 2, \dots, n_{\max},$$

with $\hbar\omega_0 = \hbar\alpha\sqrt{2D_e/\mu}$ (harmonic frequency) and $\hbar\omega_0 x_e = \hbar^2\alpha^2/2\mu$ (anharmonicity constant). The number of bound states is finite, $n_{\max} = \lfloor 2D_e/\hbar\omega_0 - 1/2\rfloor$, reflecting the existence of a dissociation limit. The corresponding (unnormalized) eigenfunctions are expressed in terms of associated Laguerre polynomials $L_n^{(2s-2n-1)}(z)$ in the variable $z = \frac{2\sqrt{2\mu D_e}}{\hbar\alpha}e^{-\alpha(x-x_e)}$.

This closed-form quadratic-in-$(n+1/2)$ spectrum is the historically dominant expression used across spectroscopy: it reproduces experimental vibrational term values with excellent accuracy for low-lying states and underlies the standard spectroscopic constants $\omega_e$, $\omega_e x_e$ used to fit real molecular potential curves.

Equivalent derivations of this exact result have since been obtained via:

- **Operator/factorization methods** (Schrödinger-style ladder operators; Infeld–Hull factorization).
- **Supersymmetric quantum mechanics and shape invariance**: the Morse potential is a canonical example of a *shape-invariant potential*, so its entire spectrum follows algebraically from the shape-invariance condition, without solving a differential equation directly.
- **Path-integral treatments**, using a Kustaanheimo–Stiefel- or coordinate-transformation trick that maps the Morse problem onto that of the radial hydrogen atom / Coulomb problem.
- **Point canonical transformation (PCT) / Nikiforov–Uvarov (NU) methods**, which reduce the Schrödinger equation to a generalized hypergeometric equation solved by Rodrigues-type formulas.
- **Laplace-transform methods** applied directly to the s-wave radial equation.
- **Asymptotic Iteration Method (AIM)**, which reproduces the exact quantization condition through an iterative termination criterion.

All of the above are mathematically equivalent routes to the same exact spectrum, and much of the "exact solution" literature is devoted to presenting alternative, pedagogically or technically convenient derivations rather than new physics.

---

## 4. The Centrifugal ($\ell \neq 0$) Problem and Approximation Schemes

For $\ell \neq 0$, the term $\ell(\ell+1)/r^2$ prevents an exact analytic solution in the Morse variable $y = e^{-\alpha(r-r_e)}$. Two broad strategies have been developed.

### 4.1 The Pekeris approximation

Introduced by Pekeris (1934), the method expands $1/r^2$ in powers of $y = e^{-\alpha(r-r_e)}$ around the equilibrium point $r_e$, keeping terms up to the same exponential order as the Morse potential itself:

$$\frac{1}{r^2} \approx \frac{1}{r_e^2}\left[c_0 + c_1 y + c_2 y^2\right],$$

with $c_0, c_1, c_2$ fixed by matching a Taylor/Laurent expansion. This converts the centrifugal-corrected equation back into Morse-type form, restoring exact solvability of the *approximate* Hamiltonian by the same Laguerre-polynomial machinery. The Pekeris approximation is accurate near the potential minimum (i.e., for low vibrational and rotational quantum numbers, $n,\ell \ll n_{\max}$) but degrades for high $\ell$ or states far from $r_e$, since the expansion point is fixed at equilibrium.

### 4.2 Nikiforov–Uvarov (NU) method and its variants

The NU method reduces a generalized hypergeometric-type equation
$$\psi'' + \frac{\tilde\tau(s)}{\sigma(s)}\psi' + \frac{\tilde\sigma(s)}{\sigma^2(s)}\psi = 0$$
to standard form via a suitable substitution $\psi = \phi(s)y(s)$, yielding energy eigenvalues from an algebraic quantization condition and eigenfunctions in terms of Jacobi or Laguerre polynomials through the Rodrigues formula. When applied to the Morse-plus-centrifugal problem, NU is *always combined with a Pekeris-type approximation* to handle the $1/r^2$ term; the resulting method is often called **Nikiforov–Uvarov Functional Analysis (NUFA)** in its more recent parametric form. This combination (NU + Pekeris) is by far the most widely used semi-analytical technique in the modern literature for producing closed-form $E_{n\ell}$ expressions for numerous diatomic molecules (H₂, LiH, HCl, CO, VH, CrH, CuLi, TiC, NiC, ScN, and others).

### 4.3 Supersymmetric improvement of the Pekeris approximation

Because the (Pekeris-approximated) rotating Morse potential remains shape invariant, one can build a *hierarchy* of SUSY partner potentials, each shape invariant with a shifted parameter set. Successive members of the hierarchy reproduce higher-lying eigenvalues algebraically from the ground state of each partner, systematically correcting the basic Pekeris result and improving accuracy for excited rotational–vibrational states, as shown by Morales (2004) and follow-up works.

### 4.4 Asymptotic Iteration Method (AIM)

AIM converts the Schrödinger equation into a form $\lambda_1(x) \lambda_0(x)$ recursion; the termination condition $\delta_n(x) = \lambda_n \lambda_{0,n-1} - \lambda_{0,n}\lambda_{n-1} = 0$ yields the quantization condition. AIM has been applied to the (Pekeris-approximated) rotating Morse potential and generally reproduces NU/SUSY results to high precision, and is also used as an independent cross-check for numerically exact eigenvalues.

### 4.5 1/N-shifted large-N expansion and other semiclassical techniques

Large-$N$ (dimensional-scaling) expansions, in which the number of spatial dimensions $D$ is treated as a large parameter and $1/D$ (or $1/N$, $N = D + 2\ell$) becomes the perturbation parameter, provide another route to accurate rotational–vibrational energies, particularly competitive for high $\ell$ where Pekeris-type expansions weaken.

### 4.6 Supersymmetric WKB (SWKB) and related semiclassical quantization

Because the Morse potential is shape invariant, the lowest-order SWKB quantization condition
$$\int_{x_L}^{x_R}\sqrt{E_n - W^2(x)}\,dx = n\pi\hbar$$
is *exact* for the pure (non-rotating) Morse potential, providing an elegant semiclassical derivation of the same closed-form spectrum; this exactness is one of the standard illustrations in the SUSY QM/shape-invariance literature (Cooper–Khare–Sukhatme; Gendenshtein). For the centrifugally corrected (approximate) problem, SWKB and its broken-SUSY generalization (BSWKB) provide fast approximate quantization but with reduced accuracy relative to NU+Pekeris or AIM for higher $\ell$.

### 4.7 Perturbative and variational treatments

Direct Rayleigh–Schrödinger perturbation theory (treating the centrifugal term or higher anharmonic corrections perturbatively around the exact $\ell=0$ Laguerre solutions) and variational approaches (choosing trial wavefunctions informed by the exact $\ell=0$ eigenfunctions, sometimes combined with SUSY QM to optimize a variational parameter) both appear repeatedly in the literature as complementary or benchmarking techniques, especially historically before NU/AIM became dominant.

---

## 5. Purely Numerical Methods

Independent of any analytic approximation to the centrifugal term, numerically "exact" eigenvalues (to many significant digits) are obtained by discretizing the full radial or 1-D Schrödinger equation:

- **Discrete Variable Representation (DVR)** on a uniform grid with a Fourier (or sinc) basis — the standard modern workhorse for vibrational eigenproblems, used e.g. in polariton and molecular-dynamics contexts to obtain Morse eigenvalues and eigenfunctions without any centrifugal approximation.
- **Generalized pseudospectral (GPS) methods**, which use a non-uniform, optimally mapped radial grid concentrated near the potential well; Roy's generalized pseudospectral calculations for H₂, LiH, HCl, and CO are among the most accurate benchmark values available and are used to validate essentially all approximate analytic schemes.
- **Numerov / finite-difference shooting methods** on a truncated interval, historically important and still used pedagogically.
- **Confinement-in-a-box (truncated-interval) methods with lower/upper bound formulations**, as in Taşeli's work, which achieve eigenvalues accurate to ~30 significant figures for the Li₂ molecule by exploiting a critical box radius beyond which truncation error becomes negligible; this also served to rigorously validate the accuracy of Morse's original closed-form solution.
- **Rayleigh–Ritz variational diagonalization** in a finite basis (harmonic-oscillator or Fourier basis functions), applicable also to multi-well and coupled anharmonic generalizations.
- **Tridiagonal J-matrix methods**, which give accuracy comparable to the best pseudospectral results.
- **Fourier Grid Hamiltonian (FGH) method**, frequently used as a numerically exact reference against which NU/Pekeris/SUSY/AIM results are compared for HCl, CO, and LiH.

These numerical approaches carry no error from a centrifugal-term expansion and thus serve as the ultimate accuracy benchmark; virtually every semi-analytical paper on the rotating Morse potential compares its closed-form $E_{n\ell}$ against DVR, GPS, or FGH results.

---

## 6. Extensions and Generalizations

The eigenvalue problem for the Morse potential has been extended along many directions, each generating its own sub-literature:

- **Modified/shifted/generalized Morse potentials** (e.g., the modified shifted Morse potential, improved Morse potentials with extra exponential terms) tailored to reproduce experimental Rydberg–Klein–Rees (RKR) potential curves more closely than the plain three-parameter Morse form.
- **Position-dependent mass (PDM) Schrödinger equation** with Morse-type potentials, relevant to semiconductor heterostructures, quantum wells/dots, and graded materials; solved via point canonical transformations and NU-type methods (Sever & Tezcan and successors).
- **q-deformed and generalized Morse potentials**, combined with Pekeris-type centrifugal approximations and PDM, broadening applicability to a wider variety of diatomic species.
- **D-dimensional formulations**, where the Schrödinger equation is solved in arbitrary spatial dimension $D$, connecting to large-$N$/large-$D$ expansion techniques and to fractional-derivative generalizations (e.g., generalized fractional NU methods) used for improved reproduction of vibrational spectra across dozens of molecules.
- **Rosen–Morse and Deng–Fan potentials**, close relatives sharing the same exponential structure, solved with the same NU + Pekeris toolkit; frequently treated in tandem with the Morse potential in comparative studies, and relevant to QCD quark-confinement modeling (Rosen–Morse) in addition to molecular spectroscopy.
- **Two-dimensional and multi-dimensional Morse potentials**, exhibiting degeneracy structures and coherent/quasi-classical states, studied via factorization and dynamical-symmetry methods.
- **PT-symmetric, non-Hermitian, and complex-mass Morse potentials**, an actively growing direction: the Schrödinger equation is solved in an extended complex phase space for complex potential parameters and/or complex (position-dependent) mass, producing distinct classes of real or complex eigenvalue spectra depending on parameter regimes; these studies connect the Morse problem to open-quantum-system and non-Hermitian PT-symmetric quantum mechanics research, including proposed connections to "dark-matter-like" quantum states.
- **Vibrational polariton and Rabi-model applications**, where the Morse oscillator's numerically obtained eigenstates (typically via DVR) are embedded into cavity-QED / multi-level quantum Rabi Hamiltonians to study strong light–matter coupling and anharmonic vibrational polariton dynamics.
- **Confined Morse oscillators** (spherical-box boundary conditions), relevant to molecules under pressure or in restrictive environments, and used as a rigorous method for high-precision benchmarking as noted in Section 5.

---

## 7. Summary Comparison of Methods

| Method family | Handles $\ell \neq 0$ exactly? | Typical accuracy | Notes |
|---|---|---|---|
| Exact Laguerre-polynomial solution (Morse 1929) | No ($\ell=0$ only) | Exact | Basis for all others |
| SUSY QM / shape invariance (algebraic) | No ($\ell=0$ only) | Exact | Elegant, operator-based derivation of same spectrum |
| SWKB quantization | No ($\ell=0$ only) | Exact for $\ell=0$ | Special case of shape-invariance exactness |
| Pekeris approximation | Approximate | Good near equilibrium, low $n,\ell$ | Basis of most modern closed-form results |
| Nikiforov–Uvarov (+ Pekeris) / NUFA | Approximate | Good to very good | Dominant modern semi-analytical tool |
| SUSY-improved Pekeris hierarchy | Approximate | Improves on plain Pekeris | Especially for higher-lying states |
| Asymptotic Iteration Method (+ Pekeris) | Approximate | Comparable to NU | Independent algebraic cross-check |
| Large-$N$ / $1/D$ expansion | Approximate | Good for higher $\ell$ | Complementary regime to Pekeris |
| DVR / GPS / FGH / Numerov / J-matrix (numerical) | Yes (numerically) | Numerically exact | Benchmark for all analytic methods |
| Truncated-interval / confinement methods | Yes (numerically) | Extremely high (≈30 s.f. reported) | Also validates Morse's original formula |

---

## 8. Concluding Remarks

Nearly a century after Morse's original derivation, the eigenvalue problem for the Morse potential continues to generate active research, for three main reasons. First, it remains pedagogically central as one of the few exactly solvable non-trivial potentials in quantum mechanics and the archetypal example of a shape-invariant potential in SUSY QM. Second, the centrifugal term for $\ell \neq 0$ has no exact solution, so it continues to drive methodological innovation (Pekeris-type expansions, Nikiforov–Uvarov functional analysis, asymptotic iteration, large-$N$/large-$D$ expansions), each incrementally improving accuracy or extending applicability (position-dependent mass, generalized/deformed forms, D-dimensional and fractional generalizations). Third, the Morse potential's practical importance for real diatomic-molecule spectroscopy (H₂, LiH, HCl, CO, and many others) means new analytic approximations are constantly benchmarked against increasingly accurate numerical (DVR, pseudospectral, J-matrix) results and experimental RKR data, and it now also serves as a standard test bed for non-Hermitian/PT-symmetric quantum mechanics and cavity-QED (vibrational-polariton) research.

---

## 9. List of Publications

### Foundational / original papers

1. P. M. Morse, "Diatomic Molecules According to the Wave Mechanics. II. Vibrational Levels," *Phys. Rev.* **34**, 57–64 (1929).
2. P. M. Morse, "An Undulatory Theory of the Mechanics of Atoms and Molecules," *Phys. Rev.* **28**, 1049–1070 (1926).
3. C. L. Pekeris, "The Rotation-Vibration Coupling in Diatomic Molecules," *Phys. Rev.* **45**, 98 (1934).
4. A. Kratzer, "Die ultraroten Rotationsspektren der Halogenwasserstoffe," *Z. Phys.* **3**, 289–307 (1920).
5. C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Phys. Rev.* **35**, 1303–1309 (1930).

### Supersymmetric quantum mechanics / shape invariance

6. F. Cooper, A. Khare, U. Sukhatme, "Supersymmetry and Quantum Mechanics," *Phys. Rep.* **251**, 267–385 (1995).
7. A. Khare, U. P. Sukhatme, "New Shape Invariant Potentials in Supersymmetric Quantum Mechanics," *J. Phys. A* **26**, L901 (1993) [arXiv:hep-th/9212147].
8. R. Adhikari, R. Dutt, A. Khare, U. Sukhatme, "Higher-order WKB approximations in supersymmetric quantum mechanics," *Phys. Rev. A* **38**, 1679 (1988).
9. D. A. Morales, "Supersymmetric Improvement of the Pekeris Approximation for the Rotating Morse Potential," *Chem. Phys. Lett.* **394**, 68–75 (2004).
10. "Supersymmetry in Quantum Mechanics" (review), arXiv:math-ph/0409003.
11. "Recent Advances in Semiclassical Methods Inspired by Supersymmetric Quantum Mechanics," arXiv:2408.15424.
12. "Is shape invariance also necessary for lowest order supersymmetric WKB to be exact?," *Phys. Lett. A* (ScienceDirect), analytical transfer matrix method comparison.

### Nikiforov–Uvarov method and Pekeris-type approximations

13. C. Berkdemir, J. Han, "Any ℓ-state solutions of the Morse potential through the Pekeris approximation and Nikiforov–Uvarov method," *Chem. Phys. Lett.* **409**, 203–207 (2005).
14. C. Berkdemir, A. Berkdemir, J. Han, "Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential," *Chem. Phys. Lett.* **417**, 326–329 (2006).
15. "Analytical approximations to the eigenvalues of the Morse potential with centrifugal terms," *J. Mol. Spectrosc.* (ScienceDirect, 2006).
16. R. Sever, C. Tezcan, "Exact Solution of Schrödinger Equation for Modified Kratzer's Molecular Potential with Position-Dependent Mass" (arXiv:0712.0268).
17. C. Tezcan, R. Sever, "A General Approach for the Exact Solution of the Schrödinger Equation," *Int. J. Theor. Phys.* (2009).
18. "Rovibrational Spectroscopy of Diatomic Molecules in a Modified Morse Potential using Nikiforov–Uvarov Functional Analysis," arXiv:2409.06598 (2024).
19. "Bound State Solutions of the Deng–Fan Molecular Potential with the Pekeris-type Approximation using the Nikiforov–Uvarov (N–U) Method."
20. "Approximate Solution of the Schrödinger Equation with Rosen–Morse Potential Including the Centrifugal Term" (Nikiforov–Uvarov method).
21. "Improved Modelling for Vibrational Energies of Diatomic Molecules Using the Generalized Fractional Derivative," *Sci. Rep.* (2026).
22. "A Precise Estimation for Vibrational Energies of Diatomic Molecules Using the Improved Rosen–Morse Potential," PMC10354199.
23. "Non-relativistic Molecular Modified Shifted Morse Potential System," *Sci. Rep.* **12**, 15290 (2022).
24. M. Zarezadeh, M. K. Tavassoly, "Solution of the Schrödinger Equation for a Particular Form of Morse Potential Using the Laplace Transform," *Chin. Phys. C (HEP & NP)* **37**, 043106 (2009) (note: correct year per journal record).
25. A. M. Desai, N. Mesquita, V. Fernandes, "A New Modified Morse Potential Energy Function for Diatomic Molecules," *Phys. Scr.* **95**, 085401 (2020).
26. R. Khordad, A. Ghambari, "Theoretical Prediction of Thermodynamic Functions of TiC: Morse Ring-Shaped Potential," *J. Low Temp. Phys.* **199**, 1–13 (2020).

### Numerical / benchmark methods

27. A. K. Roy, "Accurate ro-vibrational spectroscopy of diatomic molecules in a Morse oscillator potential" (generalized pseudospectral method), arXiv:1307.4978.
28. H. Taşeli, "Exact Solutions for Vibrational Levels of the Morse Potential" (truncated-interval / confinement method, Li₂ benchmark), *J. Phys. A: Math. Gen.* (1998); METU repository version available.
29. H. Taşeli, "The Confinement of a Diatomic Molecule Subject to the Morse Potential," related truncated-interval studies on asymmetrical two-well oscillators and multiwell systems.
30. S. N. Yurchenko, L. Lodi, J. Tennyson, A. V. Stolyarov, "Duo: A General Program for Calculating Spectra of Diatomic Molecules," *Comput. Phys. Commun.* **202**, 262–275 (2016).
31. R. J. Hinde, "VibHam: A Classroom Tool for Predicting the Rovibrational Spectra of Diatomic Molecules beyond the Harmonic Oscillator Approximation," *J. Chem. Educ.* (2024).
32. J. N. Huffaker, P. H. Dwivedi, factorization-based raising/lowering operator treatment of the Morse oscillator (type B → type F factorization), *J. Math. Phys.*

### Asymptotic Iteration Method and semiclassical / large-N methods

33. "Asymptotic Iteration and Variational Methods for Gaussian Potential" (comparative AIM references and Morse-related bibliography), arXiv:1805.00006.
34. AIM applications to the rotating Morse potential combined with Pekeris approximation (various authors, early-to-mid 2000s literature building on H. Ciftci, R. L. Hall, N. Saad's original AIM formulation).

### Position-dependent mass, generalized/deformed potentials

35. "A New Approach to the Exact Solutions of the Effective Mass Schrödinger Equation" (Morse potential case), arXiv:0705.2940.
36. Generalized q-deformed Morse potential with position-dependent (Morse-like) mass function, parametric NU + Pekeris treatment (ResearchGate/J. Mol. Spectrosc. literature).

### Complex/PT-symmetric and non-Hermitian extensions

37. "Exact Solution of Schrödinger Equation for Complex Mass Quantum System under Complex Morse Potential to Study Emergent Matter Types and Its Phases," arXiv:2512.20318.
38. "Exact Solution of Schrödinger Equation for the Complex Morse Potential to Investigate Physical Systems with Position-Dependent Complex Mass," arXiv:2507.04658.

### Higher-dimensional, multi-mode, and molecular-physics applications

39. J. Moran, V. Hussin, I. Marquette, "Degeneracy and Coherent States of the Two-Dimensional Morse Potential," arXiv:2104.13837.
40. W. E. Smyser, D. J. Wilson, "Quantum Dynamics of Triatomic Molecules," *J. Chem. Phys.* **50**, 182 (1969).
41. J. P. Chesick, "Gaussian Basis Sets for Model Anharmonic Oscillator Systems," *J. Chem. Phys.* **49**, 3772 (1968).
42. P. F. Endres, "Energy Levels of One- and Two-Dimensional Anharmonic Oscillators," *J. Chem. Phys.* **47**, 798 (1967).
43. A. Bordoni, N. Manini, "Systematic Calculation of Molecular Vibrational Spectra through a Complete Morse Expansion," *Int. J. Quantum Chem.* **107**, 782 (2007).
44. R. N. Costa Filho et al., "Morse Potential Derived from First Principles."
45. "Approximation of the Electronic Terms of Diatomic Molecules by the Morse Function: The Role of Anharmonicity. II. Simple Terms," arXiv:2404.00388.

### Cavity QED / vibrational-polariton applications using Morse eigenstates

46. "Multi-level Quantum Rabi Model for Anharmonic Vibrational Polaritons," arXiv:1906.04374.
47. "The Shape of the Electric Dipole Function Determines the Sub-Picosecond Dynamics of Anharmonic Vibrational Polaritons," arXiv:2003.07783.

### Related applications and dynamics

48. "Vibrational Resonance in the Morse Oscillator," arXiv:1304.3988.

---

*Note: Several entries above are drawn from arXiv preprints, journal abstracts, and secondary bibliographic listings (ResearchGate, Semantic Scholar) rather than being independently verified against the original typeset journal pages; page numbers and exact publication years should be cross-checked against the primary source before citation in a formal manuscript.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Morse potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
