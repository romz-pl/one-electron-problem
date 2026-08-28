# The Hellmann Potential: Applications in Physics and Chemistry

## 1. Introduction and Definition

The Hellmann potential is a combined (superposition) potential formed from an attractive Coulomb term and a screened Yukawa-type exponential term. It is most commonly written as

$$V(r) = -\frac{A}{r} + \frac{B}{r}e^{-\delta r}$$

where $A$ and $B$ are potential-strength parameters (their relative sign and magnitude determine whether the net interaction is attractive or repulsive at short range), and $\delta$ is the screening parameter controlling the exponential decay of the second term. Equivalently, some authors write it as

$$V(r) = \frac{V_0 e^{-\alpha r}}{r} - \frac{k}{r}$$

with $k$ and $V_0$ the Coulomb and Yukawa strengths, respectively, and $\alpha \equiv \delta$ the screening parameter.

The potential was introduced by **Hans Hellmann** in the 1930s as part of his pioneering work on the **pseudopotential** concept — the idea that the complicated repulsive, Pauli-exclusion-driven effect of atomic core electrons on a valence electron can be mimicked by a simple, exponentially screened effective potential term added to the bare Coulomb interaction. This origin explains why the Hellmann potential recurs across such a wide range of physical and chemical contexts: it is simultaneously (i) a limiting/special case of more general "Coulomb + screened-exponential" model potentials, and (ii) a building block that combines naturally with other potentials (Kratzer, Morse, Eckart, Hulthén, Varshni, etc.) to produce hybrid models used across atomic, molecular, nuclear, particle, and condensed-matter physics.

Because the Schrödinger, Klein–Gordon, and Dirac equations with the Hellmann potential (and its many hybrids) generally **cannot be solved exactly in closed form** for arbitrary angular momentum $\ell \neq 0$, a large modern literature is devoted to obtaining *approximate analytical* bound-state and scattering-state solutions using techniques such as the **Nikiforov–Uvarov (NU) method**, the **Nikiforov–Uvarov Functional Analysis (NUFA) method**, the **asymptotic iteration method (AIM)**, **supersymmetric quantum mechanics (SUSYQM)**, **series expansion methods**, **variational** and **perturbative** approaches, and the **generalized pseudospectral method** — typically combined with the Greene–Aldrich (or Pekeris-type) approximation to handle the centrifugal term.

---

## 2. Applications in Atomic and Molecular Physics (Pseudopotential Theory)

This is the historical origin of the potential and remains one of its core uses.

- **Electron–core and electron–ion interactions.** The Hellmann potential was originally proposed to represent the interaction between a valence electron and the atomic core (nucleus plus inner-shell electrons), replacing the requirement of orbital orthogonality to core states with an effective repulsive pseudopotential term.
- **Alkali metal and alkali hydride systems.** The potential (and its refinements, e.g., the improved Hellmann-type pseudopotential of Pohl) has been used to model the valence-electron structure of alkali atoms and alkali hydride molecules, including cases (such as lithium) where the simplest form fails and must be extended with a second "shielded potential" term fitted to Hartree–Fock data.
- **Positron– and electron–alkali-atom scattering.** Nonlocal Hellmann model potentials, combined with polarized-orbital and JWKB methods, have been used to compute low-energy elastic scattering cross-sections of electrons and positrons from alkali atoms.
- **Inner-shell ionization.** The Hellmann-type screened Coulomb form has been proposed as suitable for modeling inner-shell ionization problems.
- **Diatomic alkaline-metal molecules.** Gell-Mann-type Hellmann pseudopotentials are used within model perturbation theory (Rayleigh–Schrödinger type) to compute dissociation energies and other spectroscopic constants of heteronuclear/homonuclear alkali dimers (e.g., KLi, KNa, KRb, KCs).

---

## 3. Applications in Condensed Matter and Plasma Physics

- **Ionic (alkali halide) crystals.** The Hellmann potential, and its extension to next-nearest neighbors, has been used to model the effective two-particle interaction between charged particles (ions) in polar/ionic crystals, capturing lattice and cohesive-energy properties.
- **High-temperature alkali and alkaline-earth plasmas.** The related **Hellmann–Gurskii–Krasko potential** accounts for ion-core structure in computing static and dynamic structure factors of dense plasmas, going beyond the simple Coulomb (point-charge) description at short range.
- **Jellium/metal surface physics** (via the closely associated Hellmann–Feynman electrostatic theorem, frequently invoked alongside Hellmann-type potentials in many-body and surface-physics calculations of total-energy variations with charge-density perturbations).

---

## 4. Applications in Molecular/Quantum Chemistry (Diatomic Molecules)

A very large body of work uses the Hellmann potential (often as a hybrid, e.g., Hellmann–Kratzer, Eckart–Hellmann, Hulthén–Hellmann) as a **molecular interaction potential** to reproduce vibrational–rotational spectra of real diatomic molecules:

- Bound-state (ro-vibrational) energy eigenvalues have been computed for molecules including **H₂, N₂, CO, NO, CH, HCl, LiH, I₂, O₂, and CrH**, typically via the NU or NUFA method with the Greene–Aldrich approximation for the centrifugal term.
- The **Hellmann–Feynman theorem** is routinely used alongside these solutions to compute **expectation values** ($\langle r^{-2} \rangle$, $\langle p^2 \rangle$, kinetic energy, etc.) and to check the **Heisenberg uncertainty product** for these molecules.
- Hybrid forms such as the **Hellmann–Kratzer**, **Hellmann–generalized Morse**, **Eckart–Hellmann**, and **Varshni–Hellmann** potentials have been fitted to spectroscopic data to improve agreement with experiment relative to either component potential alone.
- These solutions feed into computation of **thermodynamic functions** (vibrational partition function, mean energy, free energy, entropy, specific heat) for molecular systems as a function of temperature.

---

## 5. Applications in Nuclear and Particle Physics

- **Quark–antiquark interaction potentials (quarkonium spectroscopy).** The Hellmann potential — usually combined with the Hulthén potential ("Hulthén–Hellmann potential") — is widely used as a phenomenological quark-confinement/interaction potential. Solving the radial Schrödinger equation (via NU or series-expansion methods) yields energy eigenvalues used to predict the **mass spectra of heavy mesons** such as **charmonium ($c\bar{c}$)** and **bottomonium ($b\bar{b}$)**, with the screening parameter often promoted to a temperature-dependent **Debye mass** to study **quark–gluon plasma / deconfinement** effects. Special limits of the combined potential recover the pure Hellmann, Yukawa, Coulomb, and Hulthén potentials individually, which is used as an internal consistency check.
- **Thermodynamic properties of quarkonium systems.** The same energy spectra are used to derive the partition function and thence mean energy, free energy, entropy, and specific heat of the heavy-quark bound-state system.
- **Light nuclei binding energies.** A combined generalized-Yukawa-plus-Hellmann potential model has been used (via a supersymmetric-QM approach) to estimate the **binding energy of light nuclei** (e.g., the lithium nucleus), and more generally the Hellmann potential appears as a Coulomb + Yukawa superposition relevant to nucleon–nucleon-type phenomenology (e.g., in Friedberg–Lee–Zhao soliton-model applications).
- **Relativistic wave equations.** Bound-state and scattering-state solutions of the **Klein–Gordon**, **Dirac** (spin and pseudospin symmetry), and **Duffin–Kemmer–Petiau (DKPE)** equations, as well as the **spinless Salpeter equation**, have been obtained for the Hellmann potential, including scattering phase shifts, partial-wave cross sections, and S-matrix pole trajectories near the critical screening parameter.

---

## 6. Applications in Quantum Information Theory / Statistical Mechanics

A substantial and active sub-literature applies information-theoretic and statistical measures to systems bound by the Hellmann potential and its hybrids:

- **Shannon entropy** (position- and momentum-space), tested against the **Bialynicki-Birula–Mycielski (BBM)** entropic uncertainty bound.
- **Fisher information** and generalized uncertainty relations, used to quantify particle localization and detect **squeezed states**.
- **Tsallis and Rényi entropies**, computed for Hellmann-type systems as generalizations of Shannon entropy.
- **Onicescu information energy** and other global/local information measures, particularly for hybrid potentials such as the **inversely quadratic Hellmann–Kratzer** and **screened Kratzer–Hellmann** potentials.
- **Thermodynamic/statistical properties** — partition function, mean energy, specific heat, entropy, free energy — derived from the Hellmann-potential energy spectrum, including under **superstatistics** and **fractional-parameter** extensions (e.g., Eckart–Hellmann potential thermal analysis).

---

## 7. Applications in Semiconductor/Nanostructure Physics (Quantum Dots)

The **inversely quadratic Hellmann (IQH) potential** and related hybrids (e.g., **Hulthén–Hellmann**, **Hellmann + Kratzer**) have been used as **confinement potentials** for electrons in spherical and cylindrical **quantum dots** (notably GaAs/AlGaAs and GaAs/AlₓGa₁₋ₓAs heterostructures):

- Linear and third-order **nonlinear optical absorption coefficients** and **refractive index changes**, computed via the density-matrix formalism.
- **Two-photon absorption (TPA)** spectra for intraband and interband transitions.
- **Second-harmonic generation (SHG)** as a function of dot radius, confinement depth, and effective mass.

These studies are directly relevant to the design of optoelectronic and photonic nanostructure devices.

---

## 8. Applications in External-Field and Many-Body Extensions

- **Energy-dependent Hellmann potential (EDHP).** A position- *and* energy-dependent generalization has been proposed to study the **thermo-magnetic properties** of two-dimensional non-relativistic particles under an external magnetic field and **Aharonov–Bohm flux**, relevant to condensed-matter and mesoscopic-physics settings.
- **Point-like topological defects.** Hellmann-type quarkonium potentials have been studied in the presence of a point-like defect (cosmic-string-like background), linking the potential to gravitational/topological-defect physics.
- **Spectral bounds and rigorous mathematical analysis.** Beyond approximate numerical/analytical solutions, rigorous **spectral bounds** for the Hellmann potential's discrete eigenvalues have been derived using potential-envelope and comparison-theorem methods, providing benchmarks against which approximate methods (NU, AIM, SUSYQM, perturbative, variational) are validated.

---

## Summary Table

| Domain | Representative Use |
|---|---|
| Atomic/molecular pseudopotential theory | Valence electron–core interaction, alkali atoms/hydrides |
| Condensed matter physics | Ionic crystal lattice potentials, alkali halides |
| Plasma physics | Structure factors in dense alkali/alkaline-earth plasmas |
| Molecular spectroscopy | Ro-vibrational energy levels of diatomic molecules (H₂, N₂, CO, HCl, etc.) |
| Nuclear physics | Light-nucleus binding energy models |
| Particle physics | Quark–antiquark potential; charmonium/bottomonium mass spectra |
| Relativistic quantum mechanics | Klein–Gordon, Dirac, DKPE, Salpeter equation solutions |
| Quantum information theory | Shannon/Rényi/Tsallis entropy, Fisher information |
| Statistical mechanics | Partition functions, thermodynamic properties |
| Nanostructure/semiconductor physics | Quantum dot confinement, nonlinear optics |
| Mathematical physics | Rigorous spectral bounds, scattering theory |

---

## List of Publications by Application Area

### Foundational / Pseudopotential Theory
- H. Hellmann, "A New Approximation Method in the Problem of Many Electrons," *J. Chem. Phys.* **3**, 61 (1935).
- H. Hellmann, *Acta Physicochimica URSS* (1935) — original pseudopotential proposal.
- H. J. Pohl, "An improved Hellmann-type pseudopotential for atoms and molecules," *Int. J. Quantum Chem.* **8**(3), 1974.
- Wikipedia, "Pseudopotential" — historical overview of Hellmann's 1934 introduction of the pseudopotential concept.

### Condensed Matter / Plasma Physics
- "Hellmann potential extended to next-nearest neighbors for alkali halide crystals," (1991), indexed on PubMed.
- Static and Dynamic Structure Factors with Account of the Ion Structure for High-temperature Alkali and Alkaline Earth Plasmas (Hellmann–Gurskii–Krasko potential), arXiv:1003.0933.

### Bound-State Solutions / Molecular Spectroscopy
- S. M. Ikhdair and R. Sever, "A perturbative treatment for the bound states of the Hellmann potential," *J. Mol. Struct. THEOCHEM* **809**, 103 (2007).
- M. Hamzavi, K. E. Thylwe, and A. A. Rajabi, "Approximate Bound States Solution of the Hellmann Potential," *Commun. Theor. Phys.* **60**, 1 (2013). doi:10.1088/0253-6102/60/1/01
- B. I. Ita, "Solutions of the Schrödinger equation with inversely quadratic Hellmann plus Mie-type potential using Nikiforov-Uvarov method," *Int. J. Recent Adv. Phys.* **2**, 4 (2013).
- "Application of Eckart-Hellmann potential to study selected diatomic molecules using Nikiforov-Uvarov-Functional Analysis (NUFA) method," arXiv:2204.04264.
- "BOUND STATE SOLUTIONS TO THE SCHRÖDINGER EQUATION FOR SELECTED DIATOMIC MOLECULES" (Hellmann-generalized Morse potential; N₂, CO, NO, CH, HCl), ResearchGate.
- "Expectation Values of Some Diatomic Molecules With Quantum Interaction Potential In Schrodinger Equation with Hellmann-Feynman Theorem Via Conventional Nikiforov-Uvarov Method," arXiv:1702.03923.
- "Eigen solutions and entropic system for Hellmann potential in the presence of the Schrödinger equation," *Eur. Phys. J. Plus* (2017). https://doi.org/10.1140/epjp/i2017-11729-8
- C. Tezcan and R. Sever, "A general approach for the exact solution of the Schrödinger equation" (referenced in Hellmann-potential contexts for exact/special-case solutions).
- "Spectral bounds for the Hellmann potential," arXiv:math-ph/0107015.

### Particle and Nuclear Physics
- "Applicability of the Friedberg-Lee-Zhao method" (Hellmann and Cornell potentials), arXiv:hep-ph/0111374.
- "A New Model for Calculating the Binding Energy of Lithium Nucleus under the Generalized Yukawa Potential and Hellmann Potential," arXiv:1407.2200.
- E. P. Inyang, J. E. Ntibi, E. A. Ibanga, and E. S. William, "Applicability Of Hulthén-Hellmann Potential To Predict The Mass-Spectra Of Heavy Mesons Via Series Expansion Method," *Nigerian J. Phys.* **30**(2), 140 (2021); also arXiv:2207.04215.
- I. O. Akpan, E. P. Inyang, E. P. Inyang, and E. S. William, "Approximate solutions of the Schrödinger equation with Hulthen-Hellmann Potentials for a Quarkonium system," *Rev. Mex. Fis.* **67**(3), 482 (2021); arXiv:2101.01175.
- E. P. Inyang, E. P. Inyang, I. O. Akpan, J. E. Ntibi, and E. S. William, "Masses and thermodynamic properties of a Quarkonium system," *Can. J. Phys.* **99**, 990 (2021). https://doi.org/10.1139/cjp-2020-0578
- M. Allosh, Y. Mustafa, N. K. Ahmed, and A. S. Mustafa, "Ground and Excited state mass spectra and properties of heavy-light mesons," *Few-Body Syst.* **62**, 26 (2021).
- "Non-Relativistic Study of Mass Spectra, and Thermal Properties of a Quarkonium System with Eckart-Hellmann Potential," *East Eur. J. Phys.* (2022).
- J. A. Obu, E. P. Inyang, E. S. William, D. E. Bassey, and E. P. Inyang, "Comparative Study of The Mass Spectra of Heavy Quarkonium System with an Interacting Potential Mode," *East Eur. J. Phys.* **3**, 146 (2023). https://doi.org/10.26565/2312-4334-2023-3-11
- "Temperature dependence on Spectrum of Heavy Hybrid Mesons," arXiv:2603.05667.
- "Thermal Properties and Mass Spectra of Heavy Mesons in the Presence of a Point-Like Defect," *East Eur. J. Phys.* (2024).
- O. J. Oluwadare and K. J. Oyewumi, "Approximate scattering state solutions of DKPE and SSE with Hellmann Potential," arXiv:1705.03101.
- "Tensor coupling and relativistic spin and pseudospin symmetries with the Hellmann potential," arXiv:1212.1830.

### Information Theory / Statistical Mechanics
- "Statistical Analysis and Information Theory of Screened Kratzer-Hellmann Potential Model," arXiv:2001.08429.
- "Information entropies with Varshni-Hellmann potential in higher dimensions," *Results Phys. / Sci. Direct* (2024).
- "Relativistic energies and information entropy of the inversely quadratic Hellmann potential," *ScienceDirect* (2023).
- "Global and local information-theoretic measures of the inversely quadratic Hellmann–Kratzer potential," *ScienceDirect* (2023).
- "Shannon entropy for Feinberg-Horodecki equation and thermal properties of improved Wei potential model" (Eckart-Hellmann Fisher information/Shannon entropy application discussion).
- Eckart plus Hellmann potential thermodynamic/entropy study, *Mod. Phys. Lett. A* (2025). https://doi.org/10.1142/S0217732325502268

### Quantum Dots / Nanostructure Optics
- L. Máthé, C. P. Onyenegecha, A.-A. Farcaş, L.-M. Pioraş-Ţimbolmaş, M. Solaimani, and H. Hassanabadi, "Linear and nonlinear optical properties in spherical quantum dots: Inversely quadratic Hellmann potential," *Phys. Lett. A* **397**, 127262 (2021); arXiv:2012.09283.
- "Nonlinear optical properties in GaAs/Al0.3Ga0.7As quantum dots of inversely quadratic Hellmann plus Kratzer potential," *Eur. Phys. J. D* **76**, 134 (2022). https://doi.org/10.1140/epjd/s10053-022-00453-z
- "Second-order nonlinear optical response of tunable GaAs/AlηGa1−ηAs quantum dot with Hulthén-Hellmann potential," *ScienceDirect* (2022).
- "Two-photon absorption in quantum dots with Hellmann potential" (GaAs/AlGaAs), related quantum-dot TPA study.

### Energy-Dependent and Field-Modified Extensions
- "Thermo-Magnetic properties of non-relativistic particles under the effect of energy-dependent Hellmann potential," *Mol. Phys.* (2024). https://doi.org/10.1080/00268976.2024.2411327

### General Quantum-Mechanics Methodology (Hellmann potential as test case)
- "An Adaptive Log-Laguerre Spectral Method for the Radial Dirac Equation: Resolving Asymptotic Decay and Core Singularities in Atomic Calculations" (Hellmann potential as an application/benchmark case), arXiv:2604.11063.

---

*Note: Several entries above are cross-referenced in multiple source papers' bibliographies; where an explicit DOI or arXiv identifier was available in the retrieved sources, it has been included for traceability. Readers should verify exact volume/page details against the publisher's record before formal citation.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Hellmann potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
