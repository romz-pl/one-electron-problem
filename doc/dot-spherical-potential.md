# The Spherical Potential Model for Quantum Dots: A Technical Review

## 1. Scope and Purpose

This document reviews the "spherical potential model" as applied to semiconductor quantum dots (QDs): the treatment of a nanocrystal as a particle (electron, hole, or exciton) confined by a radially symmetric potential $V(r)$, solved within the effective-mass approximation (EMA). It covers the physical basis of the model, its principal analytic and numerical variants, its extensions (impurities, external fields, multilayer structures, non-square-well potentials), its known limitations, and representative applications. A curated bibliography follows in Section 9.

---

## 2. Physical Basis: Why a Spherical Potential?

A colloidal or embedded semiconductor nanocrystal that is approximately spherical, with a lattice-matched or heterojunction-defined boundary, presents a natural three-dimensional confining geometry. When the nanocrystal radius $R$ becomes comparable to or smaller than the bulk exciton Bohr radius $a_B$, carriers experience **quantum confinement**: their kinetic energy increases and the effective bandgap blue-shifts relative to the bulk value. The spherical potential model captures this by treating the electron and hole as independent particles (or, in the weak-confinement limit, as a bound exciton) moving in an effective mass $m^\ast$ under a central potential $V(r)$ representing the band offset between the dot material and its surrounding matrix or ligand shell.

The model rests on the **effective-mass approximation (EMA)**: the rapidly varying periodic crystal potential is replaced by a smooth envelope-function equation,

$$-\frac{\hbar^2}{2m^\ast}\nabla^2\psi(\mathbf{r}) + V(r)\psi(\mathbf{r}) = E\psi(\mathbf{r})$$

with $V(r)$ representing the confinement (band-offset) potential and, where relevant, additional terms for Coulomb interaction, impurity potentials, or applied fields. Because $V(r)$ depends only on $r = |\mathbf{r}|$, the Schrödinger equation separates in spherical coordinates, and the angular part is solved exactly in terms of spherical harmonics $Y_l^m(\theta,\phi)$, leaving a one-dimensional radial equation for $u(r) = rR_{nl}(r)$:

$$-\frac{\hbar^2}{2m^\ast}\frac{d^2u}{dr^2} + \left[V(r) + \frac{\hbar^2 l(l+1)}{2m^\ast r^2}\right]u = Eu$$

This reduction to a one-dimensional radial problem is the central mathematical convenience of the spherical model and is why it remains the workhorse starting point for QD electronic-structure theory, even though real dots are rarely perfectly spherical.

---

## 3. The Foundational Models

### 3.1 The Infinite Spherical Well ("Particle-in-a-Sphere")

The simplest version sets

$$V(r) = 0,\ r \le R; \qquad V(r) = \infty,\ r > R$$

For $l=0$ (s-states), the radial equation reduces to that of a particle in a 1D infinite box of length $R$, giving the well-known spectrum

$$E_{n} = \frac{\hbar^2\pi^2 n^2}{2m^\ast R^2}$$

For general $l$, the solutions are spherical Bessel functions $j_l(kr)$, and the eigenvalues are fixed by the zeros of $j_l$. This is the model underlying the **Brus equation** (Efros & Efros 1982; Brus 1983, 1984), which estimates the size-dependent HOMO–LUMO (bandgap) shift of a nanocrystal as

$$E_g(R) \approx E_g^{\text{bulk}} + \frac{\hbar^2\pi^2}{2R^2}\left(\frac{1}{m_e^\ast}+\frac{1}{m_h^\ast}\right) - \frac{1.8\,e^2}{4\pi\varepsilon_0\varepsilon_r R}$$

combining (i) the bulk gap, (ii) the confinement energy of the electron–hole pair (particle-in-a-sphere term, $\propto 1/R^2$), and (iii) the attractive electron–hole Coulomb term ($\propto 1/R$). This equation, despite known quantitative shortcomings (see Section 6), remains the standard back-of-envelope tool for interpreting the size-tunable optical gap of colloidal QDs (CdSe, CdS, PbS, etc.) and is taught and re-derived in numerous pedagogical and review papers.

Efros and Efros's original spherical-dielectric-continuum treatment further identified three confinement regimes based on the ratio of dot radius to Bohr radius:

- **Strong confinement** ($R \ll a_B$): electron and hole confined independently; Coulomb interaction treated perturbatively.
- **Weak confinement** ($R \gg a_B$): the exciton as a whole is confined, behaving as a quasi-particle in a spherical box (the "exciton confinement" or "rigid-sphere" regime).
- **Intermediate confinement** ($a_h \ll R \ll a_e$, exploiting the differing electron/hole masses): a mixed regime important for materials with strongly disparate electron and hole effective masses.

### 3.2 The Finite Spherical Well

A more physically realistic model replaces the infinite barrier with a finite step,

$$V(r) = 0,\ r \le R; \qquad V(r) = V_0,\ r > R$$

where $V_0$ is set by the conduction- or valence-band offset between the dot and the surrounding matrix (glass host, ligand/organic shell, or wider-gap semiconductor). The radial equation must now be solved piecewise (spherical Bessel functions inside, modified spherical Bessel/Hankel functions outside) and matched via continuity of $\psi$ and of the probability current ($\psi'/m^\ast$ continuous, i.e. the standard BenDaniel–Duke boundary condition for differing effective masses across the interface). This yields transcendental eigenvalue equations that are solved numerically (shooting methods, matrix diagonalization, or finite-difference/finite-element methods). The finite well correctly predicts:

- A finite number of bound states (unlike the infinite well, which supports infinitely many).
- Non-negligible wavefunction penetration ("leakage") into the barrier region, important for tunneling-mediated processes (Auger recombination, carrier transfer between coupled dots, STM/AFM-probed dots).
- Softer confinement energies than the infinite-well limit, better matching experiment for weakly confined systems.

### 3.3 The Parabolic (Harmonic) Confinement Model

An alternative, especially popular for electrostatically defined (gate-defined) semiconductor QDs (e.g., GaAs/AlGaAs lateral or vertical dots), is the isotropic harmonic potential,

$$V(r) = \tfrac{1}{2}m^\ast\omega^2 r^2$$

This gives the analytically exact 3D isotropic harmonic-oscillator spectrum and, in 2D, is the basis of the **Fock–Darwin model**, widely used for few-electron lateral quantum dots in magnetic fields. The parabolic model is often argued to better represent smoothly varying electrostatic confinement (as opposed to abrupt heterojunction or nanocrystal-surface confinement, for which the square well is more appropriate) and reproduces observed shell structure and far-infrared (FIR) absorption selection rules (a manifestation of the generalized Kohn theorem, under which FIR couples only to the center-of-mass motion for a strictly parabolic potential). Comparative studies (e.g. for square vs. parabolic dots, and truncated/combined square-plus-parabolic potentials) show that the choice of confinement shape strongly affects addition-energy spectra, magneto-optical resonances, and Coulomb-interaction-driven correlation effects, making the confinement-shape assumption a nontrivial modeling choice rather than a mere technical convenience.

### 3.4 Model-Potential Generalizations

A large and still-active body of literature replaces the square or harmonic well with other analytically or quasi-analytically tractable central potentials chosen either for improved physical realism (smoother band-offset profiles, screening effects) or mathematical convenience (potentials admitting closed-form or Nikiforov–Uvarov / SUSYQM solutions). Widely studied variants include:

- **Gaussian confining potentials** — used for impurity and helium/multi-electron problems in QDs, and for modeling smoothly graded interfaces.
- **Woods–Saxon potential** — borrowed from nuclear physics to model a smoothed step at the dot boundary.
- **Hulthén, Manning–Rosen, Rosen–Morse, Pöschl–Teller, Kratzer(-Fues), Mathieu, Möbius-squared, and (inversely quadratic) Hellmann potentials** — a family of exactly or quasi-exactly solvable potentials adopted from molecular/atomic physics and mapped onto the QD radial equation, typically solved via the Nikiforov–Uvarov method, supersymmetric quantum mechanics (SUSYQM), or the asymptotic iteration method (AIM). These studies compute energy spectra and then feed them into expressions for linear/nonlinear optical absorption coefficients and refractive index changes — a very active sub-literature through the 2010s–2020s.
- **Combined/hybrid potentials** (e.g., harmonic-plus-Coulomb "ansatz" potentials, double-step barriers, Kratzer-like multilayer potentials) — used to interpolate between confinement regimes or better match experimental absorption-edge data.

These generalized-potential papers should be read with some caution: many are largely mathematically driven (a solvable potential is adopted primarily because it is solvable), and the physical justification for a specific functional form of $V(r)$ is sometimes secondary to the analytic tractability it affords. Nonetheless, they form a coherent and traceable methodological lineage within the broader "spherical potential model" tradition.

---

## 4. Extensions of the Basic Model

### 4.1 Multilayer / Core–Shell(–Well–Shell) Quantum Dots

Real nanocrystal engineering (core/shell QDs, quantum-dot-quantum-wells, "onion" structures) motivates piecewise-constant radial potentials with several concentric layers, e.g. core/shell (CdSe/ZnS, CdS/HgS/CdS), or core/shell/well/shell structures. The radial Schrödinger equation is solved layer-by-layer with continuity/BenDaniel–Duke matching at each interface, typically via the shooting method, transfer-matrix method, or finite-difference/finite-element discretization. Key findings across this literature:

- Placing a narrower-gap material as a thin concentric shell ("quantum dot quantum well") produces strong carrier localization in that shell, tunable independently of the overall dot size — used to engineer emission wavelength somewhat decoupled from total particle size.
- Layer thicknesses (core radius, barrier width, well width) each independently and strongly affect energy levels, wavefunction localization, and binding energies — multilayer structures give substantially more tunability than single-material dots.

### 4.2 Hydrogenic and Multi-Electron Impurities

A large sub-field studies a shallow hydrogenic donor (or acceptor) placed at the center or off-center within a spherically confined QD, adding a Coulomb term $-e^2/(4\pi\varepsilon_0\varepsilon_r|\mathbf{r}-\mathbf{r}_i|)$ to $V(r)$. Solved variationally, numerically (finite-difference/finite-element/shooting), or via matrix diagonalization in a spherical-Bessel or B-spline basis, this yields the impurity **binding energy** as a function of dot radius, barrier height, impurity position, and applied electric/magnetic fields. Robust qualitative results include:

- For an infinite well, binding energy increases monotonically as $R\to 0$.
- For a finite well, binding energy rises with decreasing $R$, reaches a maximum, then falls again as the wavefunction spills into the (now relatively deep) barrier — a signature "finite-well vs. infinite-well" qualitative difference much discussed in the literature.
- Off-center impurity position, applied hydrostatic pressure/temperature, and electric/magnetic fields (Zeeman-like or Stark-like shifts) all modify the binding energy in ways used to interpret photoluminescence and infrared absorption spectra of doped nanocrystals.
- Related work extends to negatively charged $D^-$ centers and to two-electron (helium-like) impurities/artificial-atom problems within spherical confinement, solved with Hylleraas-type, configuration-interaction, or coupled-cluster methods.

### 4.3 Excitons, Electron–Hole Correlation, and Optical Properties

Beyond single-particle spectra, the spherical model underlies calculations of:

- **Exciton binding energy and oscillator strength** as functions of dot size, in strong/weak/intermediate confinement regimes.
- **Linear and third-order nonlinear optical absorption coefficients and refractive index changes**, computed via the compact-density-matrix (iterative perturbation) formalism once the confined-state energies and dipole matrix elements are obtained from the radial Schrödinger solution — the dominant application of the "exotic model potential" literature described in Section 3.4.
- **Third/second harmonic generation (THG/SHG) and optical rectification**, particularly for multilayer and impurity-doped structures, again built on the same underlying spherical-well eigenproblem.
- Effects of **hydrostatic pressure, temperature, and external electric/magnetic (and Aharonov–Bohm flux) fields** on all of the above.

### 4.4 Beyond Single-Band EMA: k·p and Tight-Binding Comparisons

For narrower dots or materials with strong band mixing (e.g., zincblende semiconductors, or systems requiring accurate g-factors and fine-structure splitting), single-band spherical EMA is supplemented or replaced by:

- **Spherical multi-band k·p models** (e.g., 8-band k·p adapted to spherical symmetry) — used for quantum-dot-quantum-well electron/hole states and fine-structure calculations, retaining much of the spherical-symmetry machinery (envelope functions expanded in spherical harmonics/Bessel functions) while capturing valence-band mixing that a single parabolic band cannot.
- **Tight-binding models** exploiting the underlying spherical or near-spherical symmetry (e.g., symmetry-adapted tight-binding treatments of CdS/HgS/CdS quantum-dot-quantum-wells).
- Explicit studies quantifying the **accuracy limits of single-band effective-mass equations** relative to 8-band k·p, showing that non-parabolicity corrections and off-diagonal valence-band coupling terms are needed for quantitative accuracy, especially for g-factors and spin-related properties.

---

## 5. Solution Methods Used Across the Literature

| Method | Typical use case |
|---|---|
| Exact analytic solution (spherical Bessel / Hankel functions, or Hermite polynomials for the harmonic case) | Infinite well, finite well (transcendental matching), pure harmonic potential |
| Variational method (trial wavefunctions, Ritz procedure) | Impurity binding energies, exciton states, weak/intermediate confinement exciton problems |
| Shooting method | Piecewise/multilayer finite-well radial equations |
| Finite-difference method | Multilayer structures with external fields, THG/SHG calculations |
| Finite-element method | Multilayer and Kratzer-like confinement potentials, especially where smooth or exotic $V(r)$ profiles preclude simple shooting |
| Nikiforov–Uvarov method / SUSYQM / Asymptotic Iteration Method (AIM) | Quasi-exactly-solvable model potentials (Hulthén, Manning–Rosen, Möbius-squared, Hellmann, etc.) |
| Configuration interaction / Hylleraas-type expansions / coupled-cluster | Multi-electron (helium-like) confined systems, impurity correlation effects |
| B-spline basis diagonalization | Magnetic-field problems, core/shell structures with impurities |

---

## 6. Known Limitations and Criticisms

1. **Breakdown of EMA at small size.** The effective-mass/envelope-function approximation assumes the confining potential varies slowly on the scale of the lattice constant and that carrier wavefunctions do not significantly overlap at the atomic scale. For very small nanocrystals (roughly below ~1–2 nm, i.e., a few hundred atoms), this assumption becomes questionable, and atomistic methods (tight-binding, pseudopotential, DFT) are needed for quantitative accuracy.
2. **Overestimation by the simple infinite-well/Brus picture.** Multiple re-analyses (including exact solutions of the infinite spherical well with careful boundary-condition treatment) find that the naive particle-in-a-sphere confinement term systematically overestimates the observed blue-shift compared with experiment and with finite-well or more elaborate treatments; the Coulomb correction term in the Brus equation is also only approximate (empirical numerical prefactor ~1.8, derived from overlap-integral estimates rather than an exact result).
3. **Neglect of true crystal/dot shape.** Real colloidal dots are rarely perfect spheres (faceting, anisotropic growth, wurtzite vs. zincblende crystal habit); the spherical-symmetry assumption is a simplifying idealization whose validity varies by synthesis method and material system.
4. **Neglect of valence-band mixing and non-parabolicity** in the simplest single-band spherical EMA treatments, addressed only by moving to multi-band k·p or tight-binding models (Section 4.4).
5. **Dielectric mismatch / image-charge (self-polarization) effects** at the dot–matrix interface are often neglected in the bare spherical-well treatment and must be added explicitly (as in the polarization/self-energy studies of impurity binding energy) for quantitative agreement with experiments on embedded or capped dots.
6. **Choice of confining potential shape is not unique or fully first-principles-derived.** Square-well, parabolic, Gaussian, and the various "exotic" analytic potentials (Section 3.4) are largely phenomenological choices whose parameters are fit to reproduce specific experimental features (absorption edge, PL peak) rather than derived from first-principles band-structure calculations; the same experimental dataset can often be fit reasonably by several different assumed $V(r)$ shapes, which limits the model's predictive (as opposed to descriptive/interpretive) power.

---

## 7. Representative Applications

- **Colloidal semiconductor nanocrystals** (CdSe, CdS, PbS, PbSe, InP, and their core/shell variants): size-tunable absorption/emission for LEDs, displays, biological imaging labels, and photovoltaics — the original and still dominant application domain of the Brus/Efros spherical model.
- **Quantum-dot solar cells and photodetectors**: effective-mass spherical-well models feed into density-of-states and transport models used in compact device models for QD-array-based optoelectronic devices.
- **Doped/impurity-engineered nanocrystals**: interpreting infrared absorption and photoionization spectra of donor/acceptor-doped dots.
- **Core/shell and quantum-dot-quantum-well engineering**: tuning emission wavelength and carrier localization independently of overall particle size for improved photoluminescence quantum yield and photostability.
- **Nonlinear and electro-/magneto-optic device design**: predicting THG, SHG, optical rectification, and Stark/Zeeman-tunable absorption in QD-based nonlinear optical and infrared photodetector devices, especially under the "exotic potential" formalism (Section 3.4).
- **Gate-defined semiconductor quantum dots** (typically treated with the parabolic/Fock–Darwin variant rather than the hard-wall version): few-electron artificial atoms, spin qubits, and quantum information applications.

---

## 8. Summary Assessment

The spherical potential model — in its infinite-well, finite-well, and parabolic incarnations, and their many analytically-solvable generalizations — remains the single most widely used theoretical framework for a first-pass, physically transparent understanding of quantum-dot electronic and optical properties. Its enduring appeal lies in the exact separability of the 3D Schrödinger equation in spherical coordinates, which reduces a genuinely three-dimensional confinement problem to a tractable one-dimensional radial equation, permitting closed-form or near-closed-form results for energy levels, wavefunctions, binding energies, and optical response functions. This tractability has made it the natural vehicle for a very large secondary literature exploring impurities, multilayer structures, external fields, and a wide catalogue of alternative confining-potential shapes.

At the same time, the model is a deliberate idealization: real dots are not perfectly spherical, single-band EMA neglects band mixing and non-parabolicity, the specific shape of $V(r)$ is rarely derived ab initio, and quantitative accuracy — especially for the smallest nanocrystals — requires either finite-well/multi-band refinements or a move to fully atomistic (tight-binding, pseudopotential, DFT) methods. The model is therefore best understood as an excellent qualitative and semi-quantitative interpretive tool, and as a controlled starting point for perturbative or variational extensions, rather than as a first-principles predictive theory.

---

## 9. Bibliography

### 9.1 Foundational Papers

- Efros, Al. L., & Efros, A. L. (1982). Interband absorption of light in a semiconductor sphere. *Soviet Physics Semiconductors*, 16, 772.
- Brus, L. E. (1983). A simple model for the ionization potential, electron affinity, and aqueous redox potentials of small semiconductor crystallites. *Journal of Chemical Physics*, 79, 5566.
- Brus, L. E. (1984). Electron–electron and electron–hole interactions in small semiconductor crystallites: The size dependence of the lowest excited electronic state. *Journal of Chemical Physics*, 80, 4403.
- Brus, L. E. (1986). Electronic wave functions in semiconductor clusters: experiment and theory. *Journal of Physical Chemistry*, 90, 2555.
- Kayanuma, Y. (1988). Quantum-size effects of interacting electrons and holes in semiconductor microcrystals with spherical shape. *Physical Review B*, 38, 9797.

### 9.2 Reviews and Pedagogical Treatments of the Brus/Effective-Mass Model

- Chukwuocha, E. O., Onyeaju, M. C., & Harry, T. S. T. (2012). Theoretical studies on the effect of confinement on quantum dots using the Brus equation. *World Journal of Condensed Matter Physics*, 2(2), 96–100.
- Nnamdi, et al. Confinement Energy of Quantum Dots and the Brus Equation. *International Journal of Research – GRANTHAALAYAH*.
- Delerue, C., & Lannoo, M. (2004). *Nanostructures: Theory and Modeling*. Springer.

### 9.3 Infinite/Finite Spherical Well and Multilayer (Core–Shell) Structures

- Pérez-Conde, J., & Bhattacharjee, A. K. (2001). CdS/HgS/CdS quantum dot quantum wells: A tight-binding study. arXiv:cond-mat/0202412.
- Pokatilov, E. P., Fonoberov, V. A., Fomin, V. M., & Devreese, J. T. (2001). Electron and hole states in quantum-dot quantum wells within a spherical eight-band model. arXiv:cond-mat/0109277.
- (2013). The electronic properties of a core/shell/well/shell spherical quantum dot with and without a hydrogenic impurity. arXiv:1305.0908.
- Boz, F. K., et al. Geometric effects on hydrogenic-impurity energy states of a multilayered spherical quantum dot (fourth-order Runge–Kutta method).
- Akgül, S., et al. Electronic structure and binding energy of a hydrogenic impurity confined in a multilayered spherical quantum dot with parabolic confinement (shooting method).
- Mikhail, I. F. I., & El Sayed, S. B. A. On-center and off-center hydrogenic-impurity binding energy in multilayered quantum dots with differing effective masses and dielectric constants.
- Linear and nonlinear optical properties of multilayered spherical quantum dots: effects of geometrical size, hydrogenic impurity, hydrostatic pressure and temperature. *Journal of Luminescence*.
- Optical absorption coefficients of a single electron in a multilayer spherical quantum dot with a Kratzer-like confinement potential. *Results in Optics* (2023).

### 9.4 Hydrogenic Impurities, D⁻ Centers, and Multi-Electron/Helium-like Confinement

- Binding energy of an off-center shallow donor D⁻ in a spherical quantum dot. arXiv:0904.4700.
- Study of the electronic structure and electron impact excitation cross section of helium impurities in spherical quantum dots. *Journal of Physics and Chemistry of Solids* (2024).
- Electronic structure of spherical quantum dots using the coupled-cluster method (weakly confining spherical QD potentials, Hartree–Fock V(N−1) approximation).
- Sarkar, S., Sarkar, S., & Bose, C. Influence of polarization and self-polarization charges on impurity binding energy in a spherical quantum dot with parabolic confinement. arXiv:1805.01095.
- Duque, C. A., Mora-Ramos, M. E., & Duque, C. M., et al. Effects of electric and magnetic fields on binding energy and second harmonic generation for on- and off-center donor impurities in a spherical multilayer quantum dot.
- Magnetic field dependence of the binding energy of a hydrogenic impurity in a spherical quantum dot (B-spline variational method; CdSe/ZnTe core/shell system).

### 9.5 Parabolic Confinement, Fock–Darwin, and Confinement-Shape Comparisons

- Niculescu, E. C., & Niculescu, A. Effect of the parabolic confinement potential on the binding energy of a donor in a double-step barrier quantum dot.
- Ugajin, R. (1995). Far-infrared absorption for a two-electron square-well quantum dot studied by exact diagonalization.
- Electronic structure of rectangular quantum dots. arXiv:cond-mat/0302410 (square-well vs. parabolic confinement, spin-density-functional and variational Monte Carlo comparison).
- Accurate model of a vertical pillar quantum dot (parabolic lateral confinement, Fock–Darwin framework). arXiv:0804.3191.

### 9.6 Exotic/Generalized Model Potentials and Associated Optical-Property Calculations

- Linear and nonlinear optical properties in spherical quantum dots: Inversely quadratic Hellmann potential. arXiv:2012.09283.
- Linear and Nonlinear Optical Properties in Spherical Quantum Dots: Generalized Hulthén Potential. *Journal of Electronic Materials* / related.
- Linear and Nonlinear Optical Properties in Spherical Quantum Dots: Rosen–Morse Potential.
- Linear and nonlinear optical properties in spherical quantum dots: Manning–Rosen potential.
- Linear and nonlinear optical properties in spherical quantum dots: Modified Möbius-squared potential. *PMC* (2022).
- Başer, D., & Bahar, M. K. Optical properties of a quantum dot in a Mathieu potential for an InₓGa₁₋ₓAs/GaAs heterostructure with electric and magnetic fields.
- Investigation of linear and nonlinear optical properties in quantum dots: Influence of magnetic and Aharonov–Bohm flux fields (Inversely Quadratic Hellmann–Yukawa potential). *Chinese Journal of Physics* / related, 2024.
- Kria, M., et al. Related IQH/IQK-potential optical-rectification studies for GaAs/GaAlAs spherical quantum dots.

### 9.7 Ansatz/Combined Potentials and Band-Edge Shift Studies

- Quantum Confinement Induced Shift in Energy Band Edges and Band Gap of Spherical Quantum Dot (harmonic-oscillator-plus-Coulomb ansatz potential, validated against CdSe experimental data). arXiv:1705.10343.
- Size-dependent bandgap and particle-size distribution of colloidal semiconductor nanocrystals. arXiv:1710.01376.
- New theoretical approach to quantum size effects of interacting electron–hole pairs in spherical semiconductor quantum dots. arXiv:0903.4021.

### 9.8 Cylindrical/Conical Variants and Related Confined Geometries (for comparison)

- Finite confinement potentials, core and shell size effects on excitonic and electron–atom properties in cylindrical core/shell/shell quantum dots. *Scientific Reports* (2022).
- Chnafi, M., et al. (2021). Hydrostatic pressure and temperature effects on the spectrum of an off-center single dopant in a conical quantum dot with spherical edge. *Superlattices and Microstructures*, 159, 107052.
- Belamkadem, L., et al. (2021). Electronic properties and hydrogenic impurity binding energy of a new variant quantum dot. *Physica E*, 129, 114642.
- El Moussaouy, A., et al. (2014). Temperature and hydrostatic pressure effects on exciton–phonon coupled states in semiconductor quantum dots. *Superlattices and Microstructures*, 73, 22–37.

### 9.9 Multi-band k·p, Tight-Binding, and EMA Accuracy Assessment

- Limited accuracy of conduction-band effective-mass equations for semiconductor quantum dots. *Scientific Reports* / *PMC* (open review of the hierarchy of EMA approximations vs. 8-band k·p).
- Band-edge diagrams for strained III-V semiconductor quantum wells, wires, and dots. arXiv:cond-mat/0501090.

### 9.10 Device-Modeling Applications

- A compact theoretical model for opto-electronic devices based on quantum dot arrays (finite spherical potential well within EMA, used for density-of-states/transport modeling). arXiv:1305.3612.

---

*Note: Several entries above are drawn from arXiv preprints and abstract/summary text of published journal articles; full bibliographic details (volume/page numbers) should be verified against the journal of record before formal citation, particularly for the non-arXiv entries in Sections 9.3, 9.4, 9.6, and 9.7, several of which were reconstructed from secondary citation context rather than from the primary source directly.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Conduct a thorough review of the application of the spherical potential model to describe the properties of quantum dots. Also, compile a list of related publications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
