# Applications of Eigenvalues and Eigenfunctions of the Soft-Core Coulomb Potential: A Review

## 1. Introduction and Definition

The **soft-core (truncated) Coulomb potential** is a regularized version of the singular Coulomb interaction, most commonly written as

$$V_q(r) = -\frac{Z}{\left(r^q + \beta^q\right)^{1/q}}, \qquad Z>0,\ \beta>0,\ q \geq 1,$$

with the two physically dominant cases $q=1$ (the *shifted* Coulomb potential $V_1(r) = -Z/(r+\beta)$) and $q=2$. In one spatial dimension, the most widely used form is

$$V(x) = -\frac{Z}{\sqrt{x^2+\beta^2}}.$$

The softening parameter $\beta$ removes the $r\to 0$ singularity of the pure Coulomb potential $-Z/r$, rendering the potential finite at the origin while preserving its long-range $-Z/r$ tail. This single modification gives the potential a dual identity: it is simultaneously (i) an excellent *numerically tractable stand-in* for the true Coulomb interaction in situations where the singularity causes computational or conceptual difficulties, and (ii) a *physically motivated model* in its own right for systems where the interacting charges are not true point charges. Because the associated radial Schrödinger equation is generally **not exactly solvable** in closed form (except in special limits), a large methodological literature has grown up around computing its eigenvalues $E_{\nu\ell}$ and eigenfunctions $\psi_{\nu\ell}(r)$ — via the Asymptotic Iteration Method (AIM), Nikiforov–Uvarov (NU) methods, Heun-function techniques, potential-envelope theory, and direct numerical (pseudospectral, finite-difference, Numerov) diagonalization. These eigenpairs then feed into a wide variety of downstream applications, reviewed below.

---

## 2. Applications Grouped by Physical Domain

### 2.1 Strong-Field and Attosecond Physics (Laser–Atom Interaction)

This is historically the single largest application area. The 1D soft-core potential $V(x) = -Z/\sqrt{x^2+\beta^2}$ was introduced specifically to make the **time-dependent Schrödinger equation (TDSE)** for an atom in an intense laser field computationally tractable in one spatial dimension, while retaining the qualitative features (infinite bound-state spectrum, correct ionization threshold behavior, long-range tail) of the real 3D Coulomb problem.

- **Eigenvalues** of the field-free soft-core Hamiltonian set the ionization potential and the ground/excited-state energies used to benchmark strong-field observables (e.g., $E_{cr}\!\sim\!0.067\,Z^3$, the critical field for over-barrier ionization).
- **Eigenfunctions** serve as the initial state for TDSE propagation and are essential for computing:
  - **Above-threshold ionization (ATI)** spectra and photoelectron momentum distributions.
  - **High-harmonic generation (HHG)** spectra, where the soft-core model (and refinements such as the "modified soft-core" potential) is tuned so its ground-state density matches the reduced 3D atomic density, improving HHG spectral accuracy.
  - **Non-sequential and sequential double/multiple ionization** dynamics in few-electron model atoms and molecules (e.g., 1D $\mathrm{H}_2$, $\mathrm{H_2^+}$ models), including **Coulomb explosion** and **charge-resonance-enhanced ionization (CREI)**.
  - **Rescattering, attoclock, and Rabi-oscillation** phenomena during strong-field excitation.
  - **Ellipticity dependence of HHG** and other polarization-sensitive strong-field effects, where the soft-core Coulomb tail is shown to reshape the harmonic ellipticity relative to short-range model potentials.
- A recognized limitation is that softening removes the true scattering singularity, degrading accuracy for **hard-recollision/backscattering** observables in multi-electron ionization; this has motivated hybrid and "optimized" 1D model potentials that retain HHG accuracy while better approximating high-momentum scattering.

### 2.2 Atomic and Molecular Structure: Model Potentials for Non-Point Charges

The $q=1$ and $q=2$ 3D soft-core potentials were originally proposed as physically motivated **finite-size corrections** to the point-Coulomb interaction:

- $V_1(r) = -Z/(r+\beta)$ approximates the potential of a **smeared (extended) nuclear charge distribution** rather than a point charge, and has been used to describe **mesonic (pionic) atoms**.
- $V_2(r)$, with its shape resembling the potential of a finite nucleus, is used to model the interaction experienced by a **muon in a muonic atom**.
- Eigenvalues/eigenfunctions from these models yield **level-crossing** patterns between different $(\nu,\ell)$ states not present in the pure Coulomb spectrum (whose degeneracy is "accidental" and lifted by the softening), providing an analytic window into **finite-nuclear-size corrections to atomic and muonic spectra**.
- Related **cusp-condition** analysis (concavity of the electron density near the origin) connects the soft-core parameter to the physically observable **electron density behavior at the nucleus**.

### 2.3 Confined Quantum Systems

Because the softening parameter interpolates smoothly between a harmonic-like well (small $r$) and a Coulombic tail (large $r$), the soft-core potential is a natural building block for **spatial confinement** problems:

- **Spherically confined hydrogen-like atoms** (hard-wall and soft-wall boundary conditions), where AIM and pseudospectral methods are used to track how eigenvalues shift and levels cross as a function of confinement radius $R$ and softening parameter $\beta$; comparisons are made against hydrogen confined in an impenetrable sphere.
- **Atoms confined in fullerene cages (endohedral confinement, e.g. H@C$_{60}$)**, modeled with square-well, Woods–Saxon, or Gaussian confining potentials layered onto the soft-core/Coulomb core.
- **Laser-driven ionization and excitation of spatially confined atoms**, combining strong-field and confinement effects simultaneously.
- These studies feed into **information-theoretic** analyses (Section 2.5) and into modeling **atoms in dense plasmas or high-pressure environments**, where confinement mimics environmental screening.

### 2.4 Quantum Dots, Excitons, and Low-Dimensional Nanostructures

In condensed-matter and nanostructure physics, the soft-core form is used to regularize the electron–electron (or electron–hole) Coulomb repulsion/attraction in **reduced-dimensionality (1D/2D) quantum-dot and nanowire models**, where the bare $1/r$ or $1/|x|$ interaction is either singular (1D) or numerically problematic:

- **1D and quasi-1D quantum dots**: the soft-core form $V_{ee} = e^2/\sqrt{r^2+a^2}$ is the standard regularized electron–electron interaction used in exact-diagonalization and quantum Monte Carlo (e.g., time-dependent quantum Monte Carlo, TDQMC) studies of **few-electron correlation and spatial/quantum entanglement**.
- **Two-electron quantum dots with harmonic confinement plus soft-core (or biconfluent-Heun-solvable) Coulomb repulsion**: closed-form eigenfunctions obtained via reduction to a **Biconfluent Heun equation** give exact partial energy spectra for the relative motion of two confined, Coulomb-interacting electrons — a benchmark system for quantum-dot spectroscopy.
- **Excitons and Wannier–Mott-like bound electron–hole pairs in atomic wires/1D nanostructures**: soft-core/truncated 1D Coulomb potentials, combined with dielectric screening (solving the 1D Poisson equation), are used to construct realistic **exciton binding-energy models** in nanowires and chains.
- **Semiconductor quantum-dot addition spectra**: soft-core-regularized Coulomb matrix elements enter multi-electron Hartree/Hartree–Fock/exact-diagonalization treatments of shell structure and Coulomb-blockade physics.

### 2.5 Quantum Information-Theoretic Measures

Because closed-form or high-precision numerical eigenfunctions of the soft-core (and its confined variants) are available, they are widely used as testbeds for **information-theoretic characterizations of quantum states**:

- **Shannon entropy**, **Fisher information**, **Rényi entropy**, **Tsallis entropy**, and **Onicescu energy**, computed in both position and momentum space, for free and confined hydrogen-like systems using soft-core/soft-wall boundary models.
- These measures are used to quantify **electron localization/delocalization**, verify **Cramér–Rao and Bialynicki-Birula–Mycielski (BBM) entropic uncertainty inequalities**, and study **correlation and complexity** (e.g., Fisher–Shannon and López-Ruiz–Mancini–Calbet complexity) as functions of confinement radius, nuclear charge, and soft-core parameter $\beta$.
- Extended to **endohedrally confined atoms (fullerene cages)** and **multi-electron ions**, connecting atomic-physics eigenproblems to concepts from quantum information theory.

### 2.6 Relativistic and Semi-Relativistic Extensions

- The **Dirac equation** with a soft-core Coulomb potential has been solved (numerically and via envelope theory) in $d$ spatial dimensions, giving relativistic corrections to the bound-state spectrum, relevant to **muonic and other exotic (non-electronic) atoms** where relativistic effects are non-negligible.
- **Semi-relativistic two-body treatments** (e.g., spinless Salpeter-type equations) with the soft-core potential have been applied to model **quark–antiquark (quarkonium)-like and other two-body bound systems**, where a Coulomb-type potential regularized at short distance is needed to avoid the collapse associated with the point-charge singularity in a relativistic kinetic-energy operator.

### 2.7 Mathematical Physics: Exact/Quasi-Exact Solvability and Special-Function Methods

Independent of specific physical applications, the soft-core potential is a standard **testbed model** in mathematical physics for methods of solving the Schrödinger/Heun equation:

- Reduction of the radial equation to a (bi)confluent **Heun equation**, connecting the soft-core problem to the broader class of **quasi-exactly solvable (QES)** potentials (along with the singular anharmonic oscillator, generalized quantum isotonic oscillator, and non-polynomially modified oscillator).
- Application and benchmarking of the **Asymptotic Iteration Method (AIM)** for high-precision eigenvalues, including for the related singular potential family $V(r) = r^2 + \lambda/r^\alpha$.
- **Potential envelope theory**, giving rigorous analytic upper/lower bounds on $E_{\nu\ell}$ in terms of exactly solvable "envelope" potentials (pure power-law potentials), and proving general **monotonicity** of eigenvalues in $Z$, $\beta$, and $q$.
- **Nikiforov–Uvarov (NU) and NU-Functional-Analysis (NUFA)** methods, typically combined with a Greene–Aldrich approximation for the centrifugal term, used to obtain approximate closed-form eigenvalues/eigenfunctions for soft-core-type and related screened/deformed Coulomb potentials.

### 2.8 Molecular and Thermodynamic Applications

Soft-core and other regularized/screened Coulomb-type potentials (Hulthén, Yukawa, exponential-cosine-screened Coulomb, Kratzer, Hellmann, etc. — all sharing the same short-distance-regularization motivation) are used to model **diatomic molecular vibrational–rotational spectra**. The resulting eigenvalue spectra feed into:

- Vibrational **partition functions**, mean energy, free energy, entropy, and specific heat via the Poisson-summation/statistical-mechanics route.
- Comparison against experimental spectroscopic constants for molecules such as H$_2$, HF, HCl, LiH, CO, and various hydride/metal-hydride species.

---

## 3. Summary Table

| Domain | Role of Eigenvalues/Eigenfunctions | Representative Methods |
|---|---|---|
| Strong-field / attosecond physics | Initial states & ionization potentials for TDSE propagation; HHG, ATI, CREI | Direct TDSE, split-operator, Numerov |
| Atomic/molecular structure (finite nucleus) | Finite-size corrections to atomic/muonic/mesonic spectra | AIM, Heun-equation methods |
| Confined quantum systems | Level shifts/crossings under spatial confinement | AIM, generalized pseudospectral method |
| Quantum dots & excitons | Regularized e–e/e–h interaction; correlation & entanglement | Exact diagonalization, Biconfluent Heun equation, QMC |
| Information theory | Shannon/Fisher/Rényi/Tsallis measures, entropic inequalities | Numerical wavefunctions, variational methods |
| Relativistic/semi-relativistic physics | Dirac & Salpeter-type spectra for exotic/quark systems | Envelope theory, numerical Dirac solvers |
| Mathematical physics | Benchmark for solvability methods; monotonicity proofs | AIM, NU/NUFA, Heun equation, envelope theory |
| Molecular thermodynamics | Vibrational spectra → thermodynamic functions | Parametric NU method |

---

## 4. Related Publications

### Foundational / Method Papers on the Soft-Core Potential
1. Hall, R. L., & Saad, N. (2009). *Energies and wave functions for a soft-core Coulomb potential*. arXiv:0908.2087 (also published in *J. Phys. A* / related proceedings).
2. Hall, R. L., Saad, N., & Sattah Bouh, A. (2007). *Soft-core Coulomb potential and Heun's differential equation*. (Preprint; ResearchGate).
3. Varshni, Y. P. (1990). *The Soft-Core Coulomb Potential in the Semi-Relativistic Two-Body Basis*. (Journal reference: pp. 3335–3337).
4. Agboola, D. (2012). *Dirac eigenvalues for a softcore Coulomb potential in d dimensions*. arXiv:1202.1814.
5. Hall, R. L., & Saad, N. *Spectra generated by a confined soft-core Coulomb potential*. ResearchGate preprint.

### Strong-Field / Laser–Atom Physics
6. Javanainen, J., Eberly, J. H., & Su, Q. (1988). *Numerical simulations of multiphoton ionization and above-threshold electron spectra*. Phys. Rev. A 38, 3430. (Origin of the 1D soft-core model.)
7. Roso-Franco, L., et al. — Roles of Coulomb potentials in below- and above-threshold harmonic generation for a hydrogen atom in strong laser fields. *J. Opt. Soc. Am. B* 33(7), 1558 (2016).
8. *One-dimensional model potentials optimized for the calculation of the HHG spectrum*, arXiv:2401.13724 (2024).
9. *Singularity in electron-core potential as a gateway to accurate multi-electron ionization spectra in strongly driven atoms*, arXiv:2302.03777 (2023).
10. *High harmonic generation from pre-ionized H₂ in ultrashort intense laser fields*, arXiv:1309.6153.
11. Yudin, G. L., & Ivanov, M. Yu. (1996). Dissociative ionization of H₂⁺: charge-resonance-enhanced ionization, Coulomb explosion, and harmonic generation. *Phys. Rev. A* 54, 3235.
12. Kim, C. M., & Lee, S. (1996). Coulomb corrections and polarization effects in high-intensity high-harmonic emission. *Phys. Rev. A* 54, 742.
13. *Role of the Coulomb potential on the ellipticity in atomic high-order harmonic generation*, arXiv:1211.4652.
14. *Field ionization in short and extremely intense laser pulses*, arXiv:1808.06890.
15. *Attosecond Rabi Oscillations in High Harmonic Generation Resonantly Driven by Extreme Ultraviolet Laser Fields*, arXiv:2404.04053.

### Confinement and Information Theory
16. Aquino, N., Flores-Riveros, A., & Rivas-Silva, J. F. (2013). *Shannon and Fisher entropies for a hydrogen atom under soft spherical confinement*. Phys. Lett. A 377, 2062.
17. Mukherjee, N., & Roy, A. K. (2018). *Information-entropic measures for non-zero ℓ states of confined hydrogen-like ions*. Eur. Phys. J. D 72, 118.
18. Mukherjee, N., & Roy, A. K. *Information-entropic measures in free and confined hydrogen atom*, arXiv:1801.05172.
19. *Shannon entropy and Fisher information for endohedral confined one- and two-electron atoms*, ScienceDirect (2020).
20. *The Rényi entropy, a comparative study for He-like atoms using the exponential-cosine-screened Coulomb potential*, ScienceDirect (2017).
21. Sen, K. D. (2005). Characteristic feature of Shannon information entropy of confined atoms. J. Chem. Phys. 123, 074110.
22. Roy, A. K. et al. — *Energies and wave functions for the exponential-cosine-screened Coulomb potential*; related work on generalized pseudospectral methods for confined/screened potentials.

### Quantum Dots, Excitons, and Nanostructures
23. *Solving a two-electron quantum dot model in terms of polynomial solutions of a Biconfluent Heun Equation* (referenced within Hall & Saad confinement literature).
24. *Spatial entanglement of fermions in one-dimensional quantum dots*, arXiv:2107.03834.
25. *Screened potential in one-dimensional systems: Application to electron-hole interaction and Wannier-Mott-like excitons in atomic wires*, Phys. Rev. B (2024/2026).
26. Bryant, G. W. (1992). Confinement of excitons in quantum dots. Phys. Rev. B 45, 3410.
27. Rontani, M., et al. *Coulomb correlation effects in semiconductor quantum dots: The role of dimensionality*, arXiv:cond-mat/9812428.
28. *Multi-particle quantum systems within the Worldline Monte Carlo formalism* (soft-Coulomb interaction section), arXiv:2512.24942.

### Relativistic / Semi-Relativistic and Mathematical-Physics Extensions
29. Agboola, D. (2012). *Dirac eigenvalues for a softcore Coulomb potential in d dimensions*, arXiv:1202.1814 (also listed above; central to the relativistic extension literature).
30. Quesne, C. — *Unified treatment of exact solutions for singular anharmonic, quantum isotonic oscillator, soft-core Coulomb, and non-polynomially modified oscillator potentials* (quasi-exact solvability), referenced via ResearchGate/related literature.

### Molecular Thermodynamics (Related Screened-Coulomb-Type Potentials)
31. Ikot, A. N., et al. (2023). *Thermal Responses and the Energy Spectral of Diatomic Molecules Using Nikiforov–Uvarov Methodology*. Mathematics 11, 3338.
32. *Eigensolution and Thermodynamic Properties of Standard Coulombic Potential*. J. Low Temp. Phys. (2024).
33. Inyang, E. P., et al. (2022). Application of Eckart-Hellmann potential to study selected diatomic molecules using NUFA method. Rev. Mex. Fís. 68, 020401.
34. *Energy spectra and thermal properties of diatomic molecules in the presence of magnetic and AB fields with improved Kratzer potential*, arXiv:2009.09294.

---

## 5. Notes on Sourcing

- Where possible, arXiv identifiers or DOIs/journal citations are given as located via web search; some entries (particularly older or preprint-only items referenced within other papers) may require verification of full bibliographic details (volume/page/year) before formal citation, as they were identified through secondary references rather than direct retrieval of the primary source.
- The review deliberately separates the **soft-core Coulomb potential proper** (Sections 2.1–2.2, 2.4 first bullet, 2.6, 2.7) from the broader family of **screened/deformed Coulomb-type potentials** (Hulthén, Yukawa, exponential-cosine-screened, Kratzer, Hellmann — Sections 2.5 partial and 2.8), which share methodology and motivation but are mathematically distinct potentials often treated alongside the soft-core case in the literature.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Soft-Core Coulomb potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
