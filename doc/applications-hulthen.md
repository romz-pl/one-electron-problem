# The Hulthén Potential: A Review of Its Applications in Physics and Chemistry

## 1. Introduction and Mathematical Form

The Hulthén potential, introduced by Lars Hulthén in 1942, is one of the most extensively studied short-range exponential-type potentials in quantum mechanics. It is defined as

$$V_H(r) = -V_0 \, \frac{e^{-r/a}}{1 - e^{-r/a}} = -\frac{V_0}{e^{r/a} - 1}$$

where $V_0$ is the potential depth (often written $V_0 = Ze^2\delta$ for atomic systems, with $Z$ the atomic/nuclear charge), $a$ is a range parameter, and $\delta = 1/a$ is the screening parameter.

Two features explain its enduring popularity:

- **Coulomb-like short range behavior**: as $r \to 0$, $V_H(r) \to -V_0 a/r$, reproducing an attractive Coulomb singularity.
- **Exponential screening at large $r$**: as $r \to \infty$, the potential decays exponentially, so — unlike the pure Coulomb potential — it supports only a *finite* number of bound states.

It belongs to the broader family of "screened Coulomb potentials," alongside the Yukawa (Debye–Hückel) and exponential-cosine-screened-Coulomb (ECSC) potentials, and is recognized as a special case of the more general Eckart potential. The radial Schrödinger equation is exactly solvable in closed form only for $s$-waves ($\ell = 0$); for $\ell \neq 0$ states, the centrifugal term requires an approximation (e.g., the Greene–Aldrich approximation) before approximate analytic or semi-analytic solutions can be obtained via methods such as the Nikiforov–Uvarov (NU) method, supersymmetric quantum mechanics (SUSY QM), the asymptotic iteration method (AIM), the exact quantization rule (EQR), or the Pekeris approximation.

Because of this exact solvability at short range combined with realistic long-range screening, the Hulthén potential has been applied across an unusually broad span of physics and chemistry subfields. This review surveys those applications.

---

## 2. Applications in Atomic and Molecular Physics

### 2.1 Screened Coulomb interactions and atomic structure
The Hulthén potential is used as a tractable model for the **screened Coulomb interaction** experienced by an electron in a many-electron atom or ion, where the nuclear charge is partially screened by other electrons. It is used to compute bound-state energies, wavefunctions, critical screening parameters (beyond which no bound state exists), and oscillator strengths, and has been applied to relativistic (Dirac-equation) treatments of atomic structure, transition probabilities, and electron-impact excitation cross sections for ions embedded in **plasma environments**.

### 2.2 Spherical confinement problems
The potential is a standard testbed for studying **confined quantum systems** — atoms or ions placed inside an impenetrable spherical cavity ("quantum dot in a box," pressure/confinement effects). Because the free-space Hulthén potential already has finite range, adding spherical confinement produces rich energy-level crossing behavior, critical cage radii, and pressure-induced ionization phenomena that are compared against the hydrogen atom case.

### 2.3 Molecular/vibrational spectroscopy and diatomic molecules
In molecular physics, the Hulthén potential (often combined with other potentials such as Kratzer, Hellmann, Yukawa, or Woods–Saxon terms) is used as a **model for the internuclear interaction potential** of diatomic molecules, replacing or complementing the Morse potential. It has been applied to compute rovibrational energy spectra, dissociation energies, and thermodynamic functions for molecules including **H₂, HCl, LiH, CO, NO, CrH, NiC, CuLi, and ScH**. Combined Hulthén-type potentials (e.g., Hulthén + Yukawa, Hulthén + screened Kratzer, Hulthén + Hellmann) are fitted to spectroscopic constants (equilibrium bond length, dissociation energy) of real molecules and benchmarked against experimental spectroscopic data.

### 2.4 Thermodynamic and statistical properties
A major recent thread computes **thermodynamic functions** (partition function, vibrational mean energy, entropy, Helmholtz/Gibbs free energy, specific heat) of molecular/atomic systems bound by the Hulthén potential (or Hulthén-based combined potentials), typically via the Poisson summation formula applied to the analytic energy spectrum. These studies extend to **superstatistics** (Tsallis statistics, generalized distribution functions — uniform, 2-level, gamma, log-normal, F-distribution) to study non-equilibrium/non-extensive thermal behavior of Hulthén-bound systems.

### 2.5 Information-theoretic measures
The Hulthén potential (alone and combined with the Yukawa potential) has been used as a model system for studying **Shannon entropy, Fisher information, and related information-theoretic quantities** in position and momentum space, testing information-entropic uncertainty relations (Bialynicki-Birula–Mycielski inequality, Cramér–Rao inequality) for realistic screened-Coulomb-type systems.

### 2.6 Algebraic and group-theoretic methods
Ladder/shift operators satisfying $SU(2)$ commutation relations have been constructed for the Hulthén potential using algebraic (Lie-algebraic) approaches, connecting it to the broader algebraic theory of molecular spectroscopy pioneered for vibron models of diatomic and polyatomic molecules.

---

## 3. Applications in Nuclear and Particle Physics

### 3.1 Nucleon–nucleus and nucleon–nucleon interactions
The Hulthén potential was historically developed and used to model **short-range nuclear forces**, particularly nucleon–heavy-nucleus interactions, given its Coulomb-like core and finite range mimicking the finite range of the strong force.

### 3.2 Alpha–alpha and light-ion scattering
A **"double Hulthén" potential** has been used to model the nuclear part of the $\alpha$–$\alpha$ interaction (with an atomic-type Hulthén ansatz used to represent the screened Coulomb part), fitted to elastic scattering phase shifts up to ~100 MeV, and compared against Morse-type and Gaussian potential models within phenomenological potential-fitting frameworks.

### 3.3 Astrophysical and plasma screening
Screened Coulomb potentials of Hulthén type are used to model **electron screening effects in astrophysical thermonuclear fusion reactions** (relevant to stellar nucleosynthesis) and to describe interactions in **non-ideal dense plasmas**, where the Hulthén screening parameter is related to the Debye length/shielding parameter via dielectric response function methods.

### 3.4 Hadron spectroscopy and quark–antiquark interactions
In particle physics, the Hulthén potential — often combined with the Hellmann potential ("Hulthén–Hellmann potential") or used as a Coulomb-like short-distance term alongside confinement terms — models the **quark–antiquark interaction potential** in non-relativistic quark models. It is used to compute the **mass spectra of heavy quarkonia** (charmonium $c\bar{c}$, bottomonium $b\bar{b}$, and hybrid mesons) across S, P, D, and F states via the Nikiforov–Uvarov method, series expansion methods, and the exact quantization rule, with results fitted against experimental meson mass data. Temperature-dependent versions (replacing the screening parameter with a Debye mass) are used to study **quarkonium dissociation in a quark–gluon plasma**, connecting the model to heavy-ion collision and QCD thermodynamics phenomenology.

### 3.5 Relativistic wave equations
Approximate bound-state solutions of the **Dirac equation** and the **Klein–Gordon equation** with the Hulthén potential (including Coulomb-like tensor potential terms, spin and pseudospin symmetry limits, and position-dependent mass generalizations) have been extensively studied, extending the potential's applicability to relativistic quantum mechanics and relativistic energy spectra of diatomic molecules.

---

## 4. Applications in Solid-State and Condensed Matter Physics

### 4.1 Quantum dot confinement potentials
The Hulthén potential (and its "Hulthén–Hellmann" generalization) is used as a **confinement potential for charge carriers in spherical semiconductor quantum dots** (e.g., GaAs, AlGaAs, GaAs/AlₓGa₁₋ₓAs heterostructures), replacing the more common parabolic or Gaussian confinement models. It has been used to compute:
- linear and nonlinear (third-order, second-harmonic) optical absorption coefficients and refractive index changes;
- the effects of applied electric and magnetic fields and Aharonov–Bohm flux on the electronic structure;
- two-electron "Hulthén quantum dots" embedded in Debye and quantum plasmas.

### 4.2 Screened impurity and lattice defect states
As a screened Coulomb-type potential, the Hulthén form is used to approximate the potential of a **screened charged impurity in a solid**, relevant to donor/acceptor states and defect levels in semiconductors, in a manner analogous to its use for screened nuclear charges in atomic physics.

---

## 5. Mathematical/Methodological Applications (Cross-Cutting)

Independent of the specific physical system, the Hulthén potential is a standard **benchmark potential** for testing new methods in quantum mechanics, because it is exactly solvable for $\ell=0$ but requires approximation for $\ell \neq 0$, making it a good stress-test case. Methods developed or validated on it include:
- the Nikiforov–Uvarov (NU) and NU-functional-analysis (NUFA) methods;
- supersymmetric quantum mechanics (SUSY QM) and the Hamiltonian hierarchy/shape-invariance approach;
- the asymptotic iteration method (AIM);
- the exact/WKB quantization rule;
- the generalized pseudospectral method;
- Jost-function/off-shell scattering formalisms;
- the Feynman path-integral propagator approach (used to derive partition functions and thermodynamic quantities directly).

---

## 6. Summary Table

| Domain | Representative use |
|---|---|
| Atomic physics | Screened Coulomb interactions, plasma-embedded ions, confined atoms |
| Molecular/chemical physics | Diatomic vibrational spectra (H₂, HCl, LiH, CO, NO, CrH, NiC, CuLi, ScH), thermodynamic functions |
| Nuclear physics | Nucleon–nucleus interactions, α–α scattering |
| Particle/hadron physics | Quark–antiquark potential, quarkonium mass spectra, quark–gluon plasma screening |
| Astrophysics/plasma physics | Electron screening in fusion reactions, non-ideal dense plasmas |
| Solid-state physics | Quantum dot confinement, optical properties, screened impurities |
| Relativistic quantum mechanics | Dirac and Klein–Gordon equation solutions |
| Information theory / statistical mechanics | Shannon entropy, Fisher information, superstatistics |
| Mathematical physics | Benchmark for NU, SUSY QM, AIM, and other solution methods |

---

## 7. Bibliography

### Foundational
1. Hulthén, L. (1942). *Über die eigenlösungen der Schrödinger-Gleichung des deuterons*. Arkiv för Matematik, Astronomi och Fysik, **28A**, 5.
2. Hulthén, L. (1942). Arkiv för Matematik, Astronomi och Fysik, **29B**, 1.

### Reviews and encyclopedic treatments
3. *Hulthen potential*, Encyclopedia of Mathematics, EMS Press. https://encyclopediaofmath.org/wiki/Hulthen_potential

### Atomic physics, screened Coulomb, and confinement
4. Roy, A. K. (2005). *Critical parameters and spherical confinement of H atom in screened Coulomb potential*. Pramana, **65**(1), 1–15. https://www.ias.ac.in/article/fulltext/pram/065/01/0001-0015
5. Roy, A. K. et al. *Spherical confinement of Coulombic systems inside an impenetrable box: H atom and the Hulthén potential*. arXiv:1802.04373. https://arxiv.org/pdf/1802.04373
6. Chen, Z.-B. (2023). *Electron-impact excitation of atoms or ions with the screened Coulomb potential*. Physics of Plasmas, **30**(3), 032103. https://doi.org/10.1063/5.0140534
7. *The generalized pseudospectral approach to the bound states of Hulthén and Yukawa potentials*. arXiv:1312.5900. https://arxiv.org/pdf/1312.5900
8. Bahar, M. K., & Soylu, A. *Confinement control mechanism for two-electron Hulthén quantum dots in plasmas* (screened-Coulomb/quantum-plasma treatment).

### Molecular physics, diatomic molecules, and thermodynamics
9. Ramantswana, M. et al. (2023). *Determination of thermodynamic properties of CrH, NiC and CuLi diatomic molecules with the linear combination of Hulthen-type potential plus Yukawa potential*. ScienceDirect. https://www.sciencedirect.com/science/article/pii/S2666032622000369
10. *Thermal Functions of Diatomic Molecules Using Hulthén Plus Screened Kratzer Potential*. Journal of Low Temperature Physics (2023). https://link.springer.com/article/10.1007/s10909-023-02952-8
11. *Solutions of the Schrödinger equation with Hulthén-screened Kratzer potential: Application to Diatomic Molecules*. East European Journal of Physics (2022). https://periodicals.karazin.ua/eejp/article/view/18409
12. *Eigensolutions and thermodynamic properties of generalized hyperbolic Hulthen and Woods–Saxon potential*. arXiv:2412.18637. https://arxiv.org/html/2412.18637
13. *Thermodynamic properties of diatomic molecule systems under SO(2,1)-anharmonic Eckart potential* (includes Eckart + Hulthén analysis of HCl and ScH). ResearchGate. https://www.researchgate.net/publication/318899454
14. *Information theory and thermodynamic properties for a combined potential model* (Yukawa + Hulthén). Scientific Reports (2025). https://www.nature.com/articles/s41598-025-86335-x
15. Khorrammanesh, A. H., Sadeghi, J., & Noori Gashti, S. (2024). *Investigation of thermal properties of Hulthén potential from statistical and superstatistical perspectives with various distributions*. arXiv:2408.03962. https://arxiv.org/abs/2408.03962
16. *A new approximation scheme for the centrifugal term and the Hulthén potential* (q-deformed Hulthén–quadratic exponential potential applied to H₂, HCl, CO, LiH). ResearchGate. https://www.researchgate.net/publication/229343703

### Algebraic/group-theoretic and supersymmetric methods
17. *Algebraic Approach to the Hulthen Potential*. International Journal of Theoretical Physics (2007). https://link.springer.com/article/10.1007/s10773-006-9276-z
18. *Analytical Solutions of the Schrödinger Equation for the Hulthén Potential Within SUSY Quantum Mechanics*. arXiv:1606.08035. https://arxiv.org/pdf/1606.08035
19. *Hamiltonian hierarchy and the Hulthen potential*. ResearchGate. https://www.researchgate.net/publication/2153352
20. *Energies of the Hulthén potential for l ≠ 0*. Physics Letters A (SUSY QM perturbative treatment). https://www.sciencedirect.com/science/article/abs/pii/0375960180903886
21. Iachello, F., & Ibrahim, M. (1998). *Analytic and Algebraic Studies of Anharmonicity in Diatomic Molecules*. Journal of Physical Chemistry A, **102**, 9427–9432.
22. Iachello, F., & Levine, R. D. (1995). *Algebraic Theory of Molecules*. Oxford University Press.
23. van Roosmalen, O. S., Iachello, F., Levine, R. D., & Dieperink, A. E. (1983). Journal of Chemical Physics, **79**, 2515.

### Nuclear and astrophysical applications
24. *Comparative Study of alpha-alpha interaction potentials constructed using various phenomenological models* (double Hulthén nuclear potential). arXiv:2307.13207. https://arxiv.org/pdf/2307.13207
25. Liolios, T. E. *Screened Coulomb potentials for astrophysical nuclear fusion reactions*. arXiv:nucl-th/0005011. https://arxiv.org/pdf/nucl-th/0005011
26. *Calculation of effective potential of Hulthen interaction for a nonideal dense plasma using dielectric response method*. ScienceDirect (2021). https://www.sciencedirect.com/science/article/abs/pii/S0577907321003166

### Particle physics / hadron spectroscopy / quarkonium
27. *Models and Potentials in Hadron Spectroscopy* (§3.17, The Hulthen potential). arXiv:2307.13278. https://arxiv.org/pdf/2307.13278
28. *Approximate solutions of the Schrödinger equation with Hulthén-Hellmann potentials for a quarkonium system*. arXiv:2101.01175. https://arxiv.org/pdf/2101.01175
29. Inyang, E. P., Ntibi, J. E., Ayedun, F., Ibanga, E. A., & William, E. S. (2021). *Applicability of Hulthen-Hellmann Potential to Predict the Mass-Spectra of Heavy Mesons Via Series Expansion Method*. Nigerian Journal of Physics, **30**(2), 140–145.
30. *Masses and thermodynamic properties of a quarkonium system* (Hulthén–Hellmann, temperature-dependent via Debye mass). ResearchGate. https://www.researchgate.net/publication/352810945
31. *MASS Spectrum of Heavy Quarkonium for Combined Potentials (Modified Kratzer Plus Screened Coulomb Potential)*. Iranian Journal of Science (2022). https://link.springer.com/article/10.1007/s40995-022-01377-4
32. *Temperature dependence on Spectrum of Heavy Hybrid Mesons*. arXiv:2603.05667. https://arxiv.org/pdf/2603.05667

### Relativistic wave equations
33. *Approximate bound state solutions of Dirac equation with Hulthén potential including Coulomb-like tensor potential*. arXiv:1001.4327. https://arxiv.org/pdf/1001.4327

### Solid-state physics / quantum dots
34. *Linear and Nonlinear Optical Properties in Spherical Quantum Dots: Generalized Hulthén Potential*. Few-Body Systems (2016). https://link.springer.com/article/10.1007/s00601-016-1110-4
35. *Second-order nonlinear optical response of tunable GaAs/AlηGa1−ηAs quantum dot with Hulthén-Hellmann potential*. ScienceDirect (2022). https://www.sciencedirect.com/science/article/abs/pii/S0921452622005403
36. Onyeaju, M. C. et al. *Optical properties of spherical AlGaAs quantum dots using Hulthén and Manning-Rosen potentials* (as cited in ScienceDirect review of QD confinement potentials). https://www.sciencedirect.com/science/article/abs/pii/S0921452623010219

---

## 8. Notes on Scope

This review focuses on the **non-relativistic and relativistic quantum-mechanical applications** of the Hulthén potential as documented in the physics and chemistry literature (atomic, molecular, nuclear, particle, plasma, astrophysical, and condensed-matter physics), together with associated mathematical-physics methodology papers. Many primary sources above are review-adjacent or research articles that themselves cite dozens of earlier foundational works (particularly Flügge, Lai, Varshni, Gönül, Vanden Berghe & De Meyer, and Iachello & Oss for the older literature); consulting their reference lists is recommended for a deeper historical genealogy of any single subfield.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Hulthén potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
