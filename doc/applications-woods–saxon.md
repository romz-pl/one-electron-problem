# The Woods–Saxon Potential: Applications in Physics and Chemistry

## 1. Introduction and Historical Background

The Woods–Saxon (WS) potential was introduced in 1954 by Roger D. Woods and David S. Saxon to describe elastic scattering of 20 MeV protons from heavy nuclei. It has the form

$$V(r) = -\frac{V_0}{1 + \exp\left(\dfrac{r - R}{a}\right)}$$

where $V_0$ is the potential depth, $R$ is the nuclear (or system) radius, and $a$ is the surface diffuseness parameter controlling how sharply the potential falls off at the boundary. Unlike the infinite square well or the harmonic oscillator, the WS form has a smooth, finite-depth surface and a flat interior, which mimics the nearly constant density of a self-bound many-body system with a diffuse edge — a feature shared by atomic nuclei, quantum dots, and other confined quantum systems.

Because the WS potential is *not* exactly solvable in closed analytical form for arbitrary angular momentum (only approximately so, via methods such as the Pekeris/Greene–Aldrich approximation of the centrifugal term), a large body of literature is devoted both to practical parameterizations for real physical systems and to approximate/semi-analytical solution techniques (Nikiforov–Uvarov method, supersymmetric quantum mechanics, asymptotic iteration method, etc.). This dual character — phenomenological workhorse and mathematically interesting model potential — is what has made it one of the most widely used potentials in quantum physics and quantum chemistry.

---

## 2. Applications in Nuclear and Particle Physics

### 2.1 Nuclear Shell Model and Single-Particle Structure
The WS potential is the standard mean-field potential of the nuclear shell model, replacing the harmonic oscillator for realistic calculations. Combined with a spin–orbit term of Thomas form,

$$V_{SO}(r) = V_{SO,0}\,\frac{1}{r}\frac{d}{dr}\left[\frac{1}{1+\exp\left(\frac{r-R_{SO}}{a_{SO}}\right)}\right]\,\mathbf{L}\cdot\mathbf{S},$$

it reproduces experimental single-particle spectra, magic numbers, nuclear radii, and drip-line predictions across the nuclear chart from light nuclei up to superheavy elements.

### 2.2 Optical Model Potentials for Nucleon–Nucleus and Ion–Ion Scattering
Both the real and imaginary parts of the nuclear optical model potential — used to describe elastic and inelastic nucleon scattering, reaction cross sections, and transmission coefficients — are almost universally parameterized in WS or derivative (WS-squared, surface-derivative WS) form. Global and local optical potential parameterizations (e.g., Koning–Delaroche, Bespalova et al.) span wide ranges of mass number and energy and are essential inputs for reaction theory, nuclear astrophysics reaction-rate calculations, and nuclear data evaluation for reactor and stockpile-stewardship applications.

### 2.3 Alpha Decay and Cluster Radioactivity
The WS potential (often combined with a Coulomb barrier term) is used to model the nucleus–cluster (α-core) interaction in quantum-tunneling calculations of α-decay and heavier cluster-decay half-lives, including folded/generalized WS forms and WS-Gaussian potentials that also reproduce level schemes and electromagnetic transition rates of α-cluster states. These models are actively used to predict decay properties of superheavy nuclei not yet fully characterized experimentally.

### 2.4 Heavy-Ion Fusion, Fission, and Sub-Barrier Reactions
Nucleus–nucleus (ion–ion) potentials built from WS forms (including energy-dependent WS, or "EDWSP," models) are used to compute fusion barriers, fusion and quasi-fission cross sections, and sub-barrier fusion enhancement in coupled-channels calculations (e.g., with the CCFULL code). The diffuseness parameter anomaly — WS diffuseness values needed to fit fusion data are often larger than those from elastic scattering — remains an active research topic.

### 2.5 Deformed and Collective Nuclear Models
Deformed WS potentials, in which $R$ depends on the nuclear orientation angle, underlie calculations of deformed superheavy nuclei, fission barriers, and proton/α emission from deformed parents. WS-based solutions of the five-dimensional Bohr Hamiltonian have also been used within the geometric collective model to study nuclear shape transitions and critical-point symmetries (X(5), E(5)-type models).

### 2.6 Atomic and Hyperfine Structure Calculations
In atomic and molecular physics, WS-type nuclear charge/magnetization distributions are used (in place of simpler uniform-ball models) to compute finite-nuclear-size corrections to atomic energy levels and hyperfine splittings in high-precision atomic structure calculations, including relativistic coupled-cluster calculations of heavy, few-electron, and neutral atomic systems.

### 2.7 Quark Models and Hadron/Meson Spectroscopy
WS-related exponential-type potentials are used within non-relativistic and relativistic (Klein–Gordon, Dirac) quark-model frameworks to obtain mass spectra of mesons, baryons, and tetraquarks, and to study thermodynamic properties of quark–gluon plasma via partition functions derived from WS-type confinement potentials.

---

## 3. Applications in Chemistry and Molecular/Condensed-Matter Physics

### 3.1 Diatomic Molecule Vibrational–Rotational Spectroscopy
The WS potential (and its generalized/hyperbolic variants, e.g., the Generalized Symmetric Woods–Saxon, GSWS, potential) is used as a model interatomic potential energy function for diatomic molecules. Solving the radial Schrödinger equation (typically via the Nikiforov–Uvarov or asymptotic iteration method with the Greene–Aldrich approximation for the centrifugal term) yields ro-vibrational energy levels for molecules such as HCl, CO, N₂, LiH, I₂, KBr, NiC, CuLi, and CrH, which are compared against experimental spectroscopic constants.

### 3.2 Thermodynamic Functions of Molecular and Quantum Systems
From the WS (or GSWS/hyperbolic WS) energy spectrum, the vibrational partition function is derived (often via the Poisson summation formula), enabling calculation of mean energy, entropy, specific heat capacity, and Helmholtz/Gibbs free energy as functions of temperature — used both for real diatomic molecules and, in nuclear-physics-adjacent studies, for nucleons confined in WS mean fields (e.g., in ¹⁷F).

### 3.3 Semiconductor Quantum Dots and Nanostructures
In condensed matter/materials chemistry, the WS potential is widely used as a smooth, physically realistic confinement potential for electrons (and holes/excitons) in spherical and core/shell semiconductor quantum dots (e.g., CdSe, CdSe/ZnS, InAs/GaAs), replacing the unphysical infinite or abrupt finite square well. Applications include:
- Calculating electronic energy levels, envelope wavefunctions, and probability densities.
- Predicting linear and nonlinear optical properties: optical absorption coefficients, refractive index changes, second- and third-harmonic generation (SHG/THG), and optical rectification.
- Studying the effects of donor/hydrogenic impurities, external electric and magnetic fields, and intense laser fields on quantum-dot optical response — relevant to optoelectronic device design.

### 3.4 Exactly/Quasi-Exactly Solvable Model Potentials in Chemical Physics
Because the pure WS potential lacks a closed-form analytical solution for $\ell>0$, much theoretical-chemistry-adjacent work focuses on approximate analytic techniques (Nikiforov–Uvarov, supersymmetric WKB, asymptotic iteration method, Pekeris approximation) and related exactly solvable exponential-type potentials (Deng–Fan, Tietz, Schiöberg, Rosen–Morse, Hulthén, Manning–Rosen), several of which reduce to or are compared against the WS form. These studies contribute methodology broadly used in molecular quantum mechanics and spectroscopy modeling.

### 3.5 Contact-Interaction and Delta-Function-Decorated Models
WS potentials decorated with Dirac delta-function terms at the surface have been used to model short-range (localized) interactions relevant to both atomic and nuclear bound-state problems, providing simplified analytically tractable frameworks for surface-localized chemical/physical interactions.

---

## 4. Summary Table

| Domain | Typical Use of Woods–Saxon Potential |
|---|---|
| Nuclear shell model | Mean-field single-particle potential; magic numbers, radii, drip lines |
| Nuclear reactions | Optical model potential (elastic/inelastic scattering, cross sections) |
| Radioactive decay | α-decay and cluster-decay tunneling half-life calculations |
| Heavy-ion collisions | Ion–ion (nucleus–nucleus) potential for fusion/fission barriers |
| Nuclear structure | Deformed WS potentials for collective/Bohr Hamiltonian models |
| Atomic physics | Nuclear charge/magnetization distributions for hyperfine structure |
| Particle/hadron physics | Quark confinement potentials; meson/baryon mass spectra |
| Molecular spectroscopy | Diatomic vibrational–rotational energy levels |
| Statistical thermodynamics | Partition functions and thermodynamic properties of bound systems |
| Nanotechnology/chemistry | Confinement potential in semiconductor quantum dots; optical properties |

---

## 5. Selected Publications

### Foundational
- R. D. Woods and D. S. Saxon, "Diffuse Surface Optical Model for Nucleon–Nuclei Scattering," *Physical Review* **95**, 577 (1954).

### Nuclear Shell Model / Parameterizations
- N. Schwierz, I. Wiedenhöver, A. Volya, "Parameterization of the Woods-Saxon Potential for Shell-Model Calculations," arXiv:0709.3525 (2007).
- O. V. Bespalova, E. A. Romanovsky, T. I. Spasskaya, "Nucleon–nucleus real potential of Woods–Saxon shape between −60 and +60 MeV for the 40 ≤ A ≤ 208 nuclei," *Journal of Physics G* **29**, 1193 (2003).
- Sukhendu Saha, Dipali Basak, Chinmay Basu, "The Wood-Saxon proton optical potential for p-nuclei," arXiv:2408.03697 (2024).
- "A phenomenological Woods-Saxon potential for p-shell nuclei," *Nuclear Physics A* (1973).

### Optical Model / Scattering Theory
- L. Hlophe, Ch. Elster (TORUS Collaboration), "Separable Representation of Phenomenological Optical Potentials of Woods-Saxon Type," arXiv:1310.8334.
- "Ultraviolet suppression and nonlocality in optical model potentials for nucleon-nucleus scattering," arXiv:2011.11080.
- "Nonlocal nucleon-nucleus optical potentials from chiral effective field theory," arXiv:2509.04665.
- "Optical model potentials involving loosely bound p-shell nuclei around 10 MeV/A," arXiv:nucl-ex/9908022.

### Alpha and Cluster Decay
- "Calculations of α-decay half-lives for heavy and superheavy nuclei" (deformed cluster model with WS potential), *Physical Review C*, OSTI 21499568 (2011).
- "Alpha-decay quantum-tunnelling calculations based on a folded Woods-Saxon potential," *Journal of Physics: Conference Series* **436**, 012064 (2013).
- Dong Bai, Zhongzhou Ren, "Woods-Saxon-Gaussian Potential and Alpha-Cluster Structures of Alpha+Closed Shell Nuclei," arXiv:1808.10234.
- "A potential model for alpha decay," *American Journal of Physics* **78**, 949 (2010).
- "Study on alpha decay chains of Z = 122 superheavy nuclei with deformation effects and Langer modification," arXiv:1810.04421.
- "α-decay half-lives of some nuclei from ground state to ground state using different nuclear potential," *EPJ Nuclear Sciences & Technologies* (2018).
- "Theoretical calculations on half-lives of spontaneous one-proton radioactivity," arXiv:2606.17785.
- "An estimate of Alpha decay half-life from the poles of S-matrix of an exactly solvable potential," arXiv:1612.04135.

### Heavy-Ion Fusion / Fission
- "Diffuseness of Woods Saxon Potential and Sub-Barrier Fusion" (CCFULL coupled-channels study).
- "Modified Woods-Saxon potential for heavy-ion fusion reaction," INIS record mbw91-5r398.
- "Analysis of nuclear structure effects in sub-barrier fusion dynamics using energy dependent Woods-Saxon potential," *Revista Mexicana de Física* (2016).
- "Systematic study of the Woods-Saxon potential parameters between heavy-ions," ResearchGate (2021).
- "Constraining the Woods-Saxon Potential in Fusion Reactions Based on the Neural Network," arXiv:2306.11236 (2023).

### Mathematical / Solvability Studies
- M. Çapak, B. Gönül, "Remarks on the Woods-Saxon Potential," arXiv:1607.02742.
- M. Çapak, D. Petrellis, B. Gönül, D. Bonatsos, "Bohr Hamiltonian with Woods-Saxon Potential," *Journal of Physics G* **42**, 095102 (2015).
- "An approximation to the Woods-Saxon potential based on a contact interaction," arXiv:1911.10050.
- "The Woods–Saxon potential with point interactions," *Physics Letters B* (ScienceDirect).
- "Explicit asymptotics of coupling matrix elements for central potentials in the hyperspherical harmonics expansion method," arXiv:2603.02020.

### Nuclear Collective Model / Thermodynamics
- A. Suparmi, L. K. Permatahati, S. Faniandari, Y. Iriani, A. Marzuki, "Study of Bohr Mottelson Hamiltonian with minimal length effect for Woods-Saxon potential and its thermodynamic properties," *Heliyon* **7**, e06861 (2021).
- "Thermodynamic Properties of a Nucleon under the Generalized Symmetric Woods-Saxon Potential in Fluorine 17 Isotope," arXiv:1604.07964.

### Molecular Spectroscopy and Chemistry
- Y. M. Assimiou, S. T. Daniel, G. Issoufou, D. F. Anselme, G. Y. H. Avossevou, "Eigensolutions and thermodynamic properties of generalized hyperbolic Hulthén and Woods-Saxon potential," *Condensed Matter Physics* **27**, 43301 (2024).
- "Bound-state energy spectrum and thermochemical functions of the deformed Schiöberg oscillator," *Scientific Reports* **13** (2023).
- "A precise estimation for vibrational energies of diatomic molecules using the improved Rosen–Morse potential," *Scientific Reports* **13** (2023).
- M. Abu-Shady, E. P. Inyang, "The fractional Schrödinger equation with the generalized Woods-Saxon potential," *East European Journal of Physics* **41**, 63 (2023).
- "Thermodynamic Properties of Improved Deformed Exponential-type Potential (IDEP) for some Diatomic Molecules," arXiv:2001.04799.

### Quantum Dots and Nanostructures
- "The effect of Woods–Saxon potential on envelope function, intersubband dispersion curves and group velocity of InAs/GaAs quantum dots with wetting layer," *Journal of Physics and Chemistry of Solids* **114**, 187 (2018).
- "Impurity-assisted tuning of nonlinear optical responses in core/shell quantum dots with Woods–Saxon confinement," *ScienceDirect* (2026).
- "The effects of intense laser on nonlinear properties of shallow donor impurities in quantum dots with the Woods–Saxon potential," *Physica E* (2011).

### Atomic/Hyperfine Structure
- "Effect of nuclear magnetization distribution within the Woods-Saxon model: Hyperfine splitting in neutral Tl," arXiv:2101.01145.

---

*Note: Several entries above are drawn from preprint servers (arXiv), conference proceedings, and secondary aggregators; readers should verify final journal publication details (volume/page/DOI) before citing formally.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Woods–Saxon potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
