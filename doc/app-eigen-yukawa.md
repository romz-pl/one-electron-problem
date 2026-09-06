# Applications of Eigenvalues and Eigenfunctions of the Yukawa Potential: A Review

## 1. Introduction

The Yukawa potential,

$$V(r) = -\frac{g^2 \, e^{-\alpha r}}{r},$$

was introduced by Hideki Yukawa in 1935 as a model for the short-range nuclear force mediated by a massive exchange boson (the pion), with $\alpha$ (the screening or mass parameter) setting the interaction range and $g$ its strength. Structurally it is a Coulomb potential modulated by an exponential screening factor, and in the limit $\alpha \to 0$ it reduces exactly to the Coulomb potential.

Despite this superficial resemblance to the Coulomb problem, the radial Schrödinger equation with a Yukawa potential is **not exactly solvable** in closed form for general angular momentum $\ell$; only numerical, perturbative, variational, or approximate analytical (e.g., Nikiforov–Uvarov, supersymmetric quantum mechanics, asymptotic iteration, series-expansion) treatments are available. This mathematical intractability, combined with the potential's ubiquity across physics, has made the computation of its eigenvalues (bound-state energies) and eigenfunctions (wavefunctions) a long-standing benchmark problem. The same functional form appears under different names depending on the physical context:

- **Nuclear physics** — Yukawa potential (nucleon–nucleon interaction)
- **Plasma physics** — Debye–Hückel potential (screened Coulomb interaction in a plasma)
- **Solid-state / condensed matter physics** — Thomas–Fermi potential (screened impurity or electron-gas interaction)
- **Atomic/molecular and chemical physics** — screened Coulomb potential (shielding effects, ionic/molecular bonding)
- **High-energy/particle physics** — inter-quark confinement potential component, Yukawa-type meson-exchange forces

This review surveys the principal applications of the eigenvalues and eigenfunctions obtained from the Yukawa potential (and its many generalized/hybrid forms), organized by physical domain, followed by a curated list of representative publications for each area.

---

## 2. Mathematical Character of the Eigenvalue Problem

Before surveying applications, it is useful to note *why* the eigenvalue/eigenfunction problem itself has generated such a large literature:

- **No exact closed-form solution** exists for the eigenvalues, eigenfunctions, or the critical screening parameter of the 3D radial Schrödinger equation with a Yukawa potential for $\ell \neq 0$ (and even for $\ell = 0$ beyond leading order), making it a standard **testbed for new approximation methods** in quantum mechanics.
- Common solution techniques include:
  - **Nikiforov–Uvarov (NU) method** and its parametric/functional-analysis variants
  - **Supersymmetric quantum mechanics (SUSYQM)** / hidden supersymmetry with Taylor-series (Padé-resummed) expansions in the screening parameter
  - **Variational principle**, often using Hulthén-potential trial wavefunctions
  - **Perturbation theory** built on the exactly solvable Coulomb Hamiltonian
  - **Asymptotic Iteration Method (AIM)**
  - **Series expansion / power-series methods** and matrix Numerov methods
  - **Pseudospectral (generalized pseudospectral) methods**
  - **Renormalization-group inspired approaches**
- A key derived quantity is the **critical screening parameter** $\alpha_c$, above which no bound state exists — of central importance in plasma and solid-state applications, and estimated to high precision ($\alpha_c \approx 1.19061227$ in atomic units for the ground state).
- Because the Coulomb $\ell$-degeneracy is broken, eigenvalues display **level crossing/cross-over** phenomena near critical screening, and the resulting eigenfunctions generalize hydrogenic (Laguerre-polynomial) wavefunctions to Jacobi-type or other special-function forms depending on the method used.

---

## 3. Applications by Domain

### 3.1 Nuclear and Particle Physics — Meson-Exchange and Quark Confinement

The eigenvalues and eigenfunctions of Yukawa-type potentials underpin models of the strong interaction at two very different scales:

- **Nucleon–nucleon interaction**: Yukawa's original motivation — the potential models the force between nucleons mediated by pion exchange, with the screening parameter tied to the pion mass, and the eigenvalue spectrum used to interpret nuclear binding.
- **Quarkonium spectroscopy**: Yukawa-type terms (often combined with a linear confining term, as in the Cornell potential, or with Hellmann/Hulthén/Kratzer terms) are used as the quark–antiquark interaction potential. Solving the Schrödinger or Klein–Gordon equation for these combined potentials yields energy eigenvalues that are mapped onto the **mass spectra of heavy mesons** — charmonium ($c\bar c$), bottomonium ($b\bar b$), and $b\bar c$ states — across various radial and orbital quantum numbers, compared directly against experimental meson masses.
- **Finite-temperature QCD**: A Debye-mass-dependent ("class of Yukawa") potential models the temperature dependence of quarkonium binding in a quark–gluon plasma, connecting the eigenvalue spectrum to dissociation temperatures and lattice-QCD-inspired potentials.
- **Relativistic treatments**: The Klein–Gordon–Yukawa problem is solved for bound and scattering states, giving relativistic corrections to meson mass spectra and scattering phase shifts.

### 3.2 Plasma Physics — Debye–Hückel Screening

In a weakly coupled plasma, the effective potential seen by a charged particle is exponentially screened by the surrounding ions/electrons — this is precisely the Yukawa/Debye–Hückel potential, with the screening length identified as the **Debye length** $\lambda_D = 1/\mu = \sqrt{k_BT/n_e e^2(1+Z^2)}$.

- **Bound-state spectra in plasma**: Eigenvalues give the modified (lowered, non-degenerate) energy levels of ions/atoms embedded in a plasma relative to free-space values, with a **finite number of bound states** existing below a critical screening length.
- **Spectral line shifts and broadening**: The screened-Coulomb eigenvalue spectrum is used to compute plasma-induced shifts and broadening of emission/absorption lines — a key **diagnostic tool for plasma density, temperature, and composition**.
- **Inertial confinement fusion (ICF) and tokamak diagnostics**: X-ray spectroscopy of highly charged ions in ICF experiments, and impurity line radiation in magnetic-confinement devices (tokamaks), rely on accurate screened-Coulomb (Yukawa-type) atomic structure calculations to interpret plasma conditions and transport.
- **Critical screening parameter**: Determines the threshold plasma density/temperature at which bound states cease to exist — relevant to pressure ionization and equation-of-state calculations in dense plasmas.

### 3.3 Solid-State and Condensed Matter Physics — Thomas–Fermi Screening

The same mathematical potential describes screening of a charged impurity by a degenerate electron gas (conduction electrons in a metal or doped semiconductor):

- **Impurity states in doped semiconductors**: The Thomas–Fermi screening length (set by the injected carrier density) plays the role of $1/\mu$; eigenvalues give **donor/acceptor impurity binding energies**.
- **Metal–insulator transition models**: The critical screening parameter of the Yukawa potential has been used as a model ingredient in describing metal–insulator transitions.
- **Biplaron and polaron problems**: For heavy impurities in polar/ionic solids, ground-state energies of the resulting Schrödinger equation with a Yukawa-type interaction are used to estimate **biplaron binding energies**.

### 3.4 Atomic, Molecular, and Chemical Physics

- **Screened Coulomb / shielding effects in atoms**: The Yukawa form models the shielding of nuclear charge by inner electrons, relevant for computing bound states and normalizations of **neutral atoms**.
- **Diatomic molecule spectroscopy**: Generalized/hybrid Yukawa potentials (e.g., inversely quadratic Yukawa, "class of Yukawa," Yukawa plus Hulthén, Yukawa plus Kratzer, cosine-Yukawa) are fit to spectroscopic constants of real diatomic molecules — H$_2$, LiH, ScH, HCl, HBr, HF, CO, NO, N$_2$, I$_2$, HgH, ZnH, CdH — to obtain:
  - **Ro-vibrational energy eigenvalues** as functions of vibrational ($n$) and rotational ($\ell$) quantum numbers, benchmarked against experimental spectroscopic data.
  - **Thermodynamic/statistical-mechanical properties** derived from the vibrational partition function built from the eigenvalue spectrum: vibrational mean energy, free energy, entropy, and specific heat capacity.
- **External-field effects**: Eigenvalue spectra of Yukawa-type potentials in the presence of magnetic fields and Aharonov–Bohm flux are used to study **Zeeman-like splitting**, magnetization, and magnetic susceptibility of diatomic systems, with degeneracy lifted by the external field.
- **Momentum-space structure**: Momentum-space eigenfunctions of the Yukawa potential have been analyzed as an operator mixing hydrogen-atom momentum-space states, relevant to scattering and structure calculations in atomic physics.

### 3.5 Astrophysics

- The Yukawa potential has also been applied in astrophysical contexts, e.g., in modeling screened gravitational or dark-matter-mediator interactions, and in stellar/plasma environments where Debye-type screening is relevant to nuclear reaction rates and opacity calculations.

### 3.6 Mathematical Physics / Methodological Testbed

Independent of any single physical application, the Yukawa potential is one of the most widely used **benchmark potentials for testing new quantum-mechanical approximation techniques**, because:
- it is simple enough to be tractable to many independent methods,
- it lacks an exact solution, so different methods can be meaningfully compared against high-precision numerical eigenvalues,
- and it smoothly interpolates to the exactly solvable Coulomb problem as $\alpha \to 0$, providing a built-in consistency check.

This has driven a large methodological literature (NU method, SUSYQM, AIM, pseudospectral methods, renormalization-group techniques, Bethe ansatz methods) that uses the Yukawa potential as its primary or first test case before application to more complex physical potentials.

---

## 4. Summary Table

| Domain | Name Used for Potential | What Eigenvalues/Eigenfunctions Are Used For |
|---|---|---|
| Nuclear physics | Yukawa potential | Nucleon–nucleon binding, pion-exchange force range |
| Particle physics | Yukawa / Cornell-type | Quarkonium mass spectra ($c\bar c$, $b\bar b$, $b\bar c$), meson scattering phase shifts |
| Plasma physics | Debye–Hückel potential | Ion/atom bound states in plasma, spectral line shifts, ICF/tokamak diagnostics |
| Solid-state physics | Thomas–Fermi potential | Impurity binding energies, metal–insulator transition models, polaron/biplaron energies |
| Atomic physics | Screened Coulomb potential | Neutral-atom bound states, shielding effects |
| Molecular/chemical physics | Yukawa-class hybrid potentials | Diatomic ro-vibrational spectra, thermodynamic functions |
| Astrophysics | Yukawa / screened potential | Screened interactions in stellar/dark-matter contexts |
| Mathematical physics | Yukawa potential | Benchmark for approximation methods (NU, SUSYQM, AIM, pseudospectral, RG) |

---

## 5. List of Related Publications

### Foundational / Mathematical Treatments
1. Rogers, F. J., Graboske, H. C., & Harwood, D. J. (1970). *Bound Eigenstates of the Static Screened Coulomb Potential.* Phys. Rev. A, 1, 1577.
2. Harris, G. M. (1962). *Bound States in a Debye–Hückel Potential.* Phys. Rev., 134, A1235.
3. Lai, C. S. (1986). *The Yukawa potential in momentum space: Analytic behavior of the eigenfunctions.* (ADS: 1986JChPh..85..949L)
4. Ferrante, R. F., et al. *Renormalization-Group Solutions for Yukawa Potential.* arXiv:cond-mat/9806250.
5. Garavelli, S. L., & Oliveira, F. A. *Analytical solution for a screened Thomas–Fermi (Yukawa) potential.*
6. Compean, C. B., & Kirchbach, M. (2021). *Bound states of the Yukawa potential from hidden supersymmetry.* Prog. Theor. Exp. Phys., 2021, 073B03; arXiv:2102.07160.
7. (2017). *The Yukawa potential: ground state energy and critical screening.* Prog. Theor. Exp. Phys., 2017, 083A01; arXiv:1706.09979.
8. *The resonance levels of the Yukawa potential.* Chem. Phys. (ScienceDirect), 2006.
9. Mukherjee, N., & Roy, A. K. (2013). *The generalized pseudospectral approach to the bound states of Hulthén and Yukawa potentials.* arXiv:1312.5900.
10. (2020). *Bound state solutions of the Schrödinger equation for the atomic systems interacting with the radial screened Coulomb potential: analytical approximation methods.* arXiv:2607.19197.

### Approximate Analytical Methods (NU, SUSYQM, AIM, Variational, Series)
11. Yazarloo, B. H., et al. (2020). *Calculation of the Energy Eigenvalues of the Yukawa Potential via Variation Principle.* Int. J. Mod. Phys. E, 29, 2050067.
12. Hamzavi, M., Movahedi, M., Thylwe, K.-E., & Rajabi, A. A. (2012). *Approximate Analytical Solution of the Yukawa Potential with Arbitrary Angular Momenta.* Chin. Phys. Lett., 29, 080302.
13. (Solution of Radial Schrödinger Equation with Yukawa Potential via Bethe Ansatz Method.) Acta Phys. Pol. A, 140, 15.
14. Ikhdair, S. M., & Sever, R. *Effective-Mass Klein–Gordon–Yukawa Problem for Bound and Scattering States.* arXiv:1108.4252.

### Quarkonium / Particle Physics Applications
15. Purohit, K. R., et al. (2022). *Quarkonium spectroscopy of the linear plus modified Yukawa potential.* Phys. Scr., 97; arXiv:2307.11481.
16. Inyang, E. P., Faithpraise, F. O., Akpan, I. O., Ntibi, J. E., & William, E. S. *Analytical Solutions of the Schrödinger Equation with Class of Yukawa Potential for a Quarkonium System Via Series Expansion Method.*
17. *The spectrum of charmed quarkonium in non-relativistic quark model using matrix Numerov's method.*
18. Abu-Shady, M., & Inyang, E. P. *Approximate solutions of the Schrödinger equation with Hulthén–Hellmann Potentials for a Quarkonium system* (thermodynamic properties and mass spectra).
19. *Screened Coulomb potential applications to the Quarkonium systems.* arXiv:2101.01174.
20. Obu, J. A., Inyang, E. P., William, E. S., & Bassey, D. E. (2023). *Comparative Study of the Mass Spectra of Heavy Quarkonium System with an Interacting Potential Model.* East Eur. J. Phys.
21. *First Principle QCD/QED Potentials, Quark Confinement and Electron–Positron Pair Annihilation.* arXiv:2103.13576.

### Plasma and Condensed-Matter Physics
22. Compean & Kirchbach (2021), as above (§ Foundational), for plasma/solid-state context discussion.
23. Various works on Debye–Hückel screened-ion spectroscopy for ICF and tokamak diagnostics (see arXiv:2607.19197 references).

### Diatomic Molecules and Thermodynamic Properties
24. Inyang, E. P., et al. *Thermodynamic Properties of the Modified (Coshine) Yukawa Potential.*
25. *Thermodynamic evaluation of Coshine Yukawa potential (CYP) for some diatomic molecule systems.* Res. Square / ResearchGate, 2022–2023.
26. Faithpraise, F. O., & Inyang, E. P. (2023). *Bound State and Ro-Vibrational Energies Eigenvalues of Selected Diatomic Molecules with a Class of Inversely Quadratic Yukawa Plus Hulthén Potential Model.* East Eur. J. Phys.
27. *Energy spectra and magnetic properties of diatomic molecules in the presence of magnetic and AB fields with the inversely quadratic Yukawa potential.* Eur. Phys. J. D (2021).
28. *Analytical solutions of the N-dimensional Schrödinger equation with modified screened Kratzer plus inversely quadratic Yukawa potential and thermodynamic properties of selected diatomic molecules.* ScienceDirect (2022).
29. *Bound state solutions and thermodynamic properties of modified exponential screened plus Yukawa potential.* J. Egyptian Math. Soc. (2022).
30. *Eigenfunctions, uncertainties and thermal properties of diatomic molecules under screened modified Kratzer potential.*

---

## 6. Notes on This Bibliography

- Several entries are drawn from preprint servers (arXiv) and secondary aggregators (ResearchGate, Academia.edu abstracts); where possible, the arXiv identifier or journal DOI/venue is given for independent verification.
- The "class of Yukawa potential" and "inversely quadratic Yukawa potential" families represent an active, ongoing line of research (predominantly 2018–2023) generalizing the base Yukawa form by adding Hulthén, Kratzer, Hellmann, or cosine-modification terms; entries under §5.4 are representative rather than exhaustive, as this sub-literature is large and rapidly growing.
- For primary verification of any specific numerical result (e.g., the critical screening parameter, specific meson mass predictions), consult the original journal article rather than the secondary source listed here.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Yukawa potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
