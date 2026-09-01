# The Coulomb Potential: Applications in Physics and Chemistry — A Review

## 1. Introduction

The Coulomb potential,

$$V(r) = \frac{1}{4\pi\epsilon_0}\frac{q_1 q_2}{r},$$

describing the electrostatic interaction energy between two point charges $q_1$ and $q_2$ separated by a distance $r$, is one of the most consequential expressions in physics. Its simplicity — a single inverse-power law — belies the breadth of phenomena it underlies, from the binding of the hydrogen atom to the structure of stars and the folding of proteins. This review surveys the major domains in which the (bare, screened, or modified) Coulomb potential plays a central role, spanning atomic and nuclear physics, condensed matter and plasma physics, astrophysics, and chemistry, and closes with a curated list of publications relevant to each application area.

---

## 2. The Coulomb Potential in Atomic and Molecular Physics

### 2.1 The hydrogen atom and one-electron systems
The exact analytic solvability of the Schrödinger equation with a pure Coulomb potential $V(r) = -\alpha/r$ is the foundation of atomic physics. It yields the hydrogenic energy spectrum $E_n \propto -1/n^2$, the degeneracy structure exploited in the Runge–Lenz vector treatment, and the starting point for perturbative and relativistic corrections (fine structure, Lamb shift, hyperfine splitting) computed via the Dirac–Coulomb equation.

### 2.2 Many-electron atoms and quantum chemistry
In multi-electron atoms and molecules, the electron–electron and electron–nucleus Coulomb interactions constitute the dominant terms of the molecular Hamiltonian beyond kinetic energy. Hartree–Fock, post-Hartree–Fock (MP2, coupled cluster), and density functional theory (DFT) methods are all, at their core, strategies for approximating the many-body Coulomb problem. The two-electron Coulomb (and exchange) integrals are the computational bottleneck in *ab initio* quantum chemistry, motivating resolution-of-identity, Cholesky decomposition, and fast multipole techniques.

### 2.3 Coulomb explosion and strong-field physics
Intense laser fields can strip electrons from molecules faster than nuclei can respond, leaving bare ions that separate under mutual Coulomb repulsion — "Coulomb explosion." This phenomenon is used diagnostically (Coulomb explosion imaging) to reconstruct molecular geometry and dynamics.

### 2.4 Coulomb crystals and cold-ion chemistry
Laser-cooled trapped ions confined at low translational energy self-organize into ordered "Coulomb crystals" via mutual Coulomb repulsion balanced by trap confinement. These systems are now a platform for quantum information processing, precision spectroscopy, and controlled cold ion–molecule reaction studies.

---

## 3. Nuclear and Particle Physics

### 3.1 Coulomb barrier and nuclear reactions
The Coulomb repulsion between positively charged nuclei creates a potential barrier that must be overcome (classically) or tunneled through (quantum mechanically) for nuclear fusion and other charged-particle reactions to occur. This underlies stellar nucleosynthesis rates, fusion reactor physics, and radioactive alpha decay (Gamow tunneling theory).

### 3.2 Coulomb excitation
Coulomb excitation is a technique in which the time-dependent electromagnetic field of a passing charged projectile excites nuclear states in a target nucleus without requiring the short-range nuclear force to act, allowing "safe," model-independent measurements of nuclear transition strengths (B(E2) values) and collective structure.

### 3.3 Screened Coulomb (Yukawa) potentials
In nuclear and condensed-matter contexts, the bare Coulomb potential is often replaced by a screened form (the Yukawa/Debye–Hückel potential), $V(r) \propto e^{-\mu r}/r$, representing the exchange of a massive mediator or the screening effect of surrounding charge. This model is widely used in solving the Schrödinger and Klein–Gordon/Dirac equations for confined and quasi-bound states.

### 3.4 Quark confinement and hadron spectroscopy
In quark models, the interquark potential is often modeled as a Coulomb-like term (from one-gluon exchange, $\propto -\alpha_s/r$) plus a linear confining term, forming the "Cornell potential" used to describe quarkonium spectra.

---

## 4. Condensed Matter and Statistical Physics

### 4.1 Ionic crystals and lattice (Madelung) energies
The cohesive energy of ionic crystals (e.g., NaCl) is dominated by the lattice sum of pairwise Coulomb interactions — the Madelung energy. Because the $1/r$ sum converges conditionally, specialized techniques (Ewald summation, Evjen's method, direct summation with dipolar corrections) have been developed and remain an active area of methodological refinement.

### 4.2 Screening in plasmas and electrolytes: Debye–Hückel theory
In plasmas, electrolytes, and doped semiconductors, mobile charges screen the Coulomb field of a given charge, giving rise to the Debye–Hückel screened potential. This underlies plasma physics (Debye length, strongly coupled/dusty plasmas), electrochemistry (activity coefficients of electrolyte solutions), and semiconductor physics (impurity scattering, Anderson localization in doped systems).

### 4.3 Wigner crystals and strongly correlated electron systems
At low density, the Coulomb repulsion between electrons can dominate over kinetic (Fermi) energy, driving electrons into an ordered "Wigner crystal" lattice — a paradigm for strong correlation physics relevant to two-dimensional electron gases and quantum dots.

### 4.4 Coulomb blockade in mesoscopic devices
In nanoscale conductors (quantum dots, single-electron transistors), the finite charging energy $e^2/2C$ associated with adding a single electron — a direct Coulomb-interaction effect — suppresses current flow except at resonance, producing the "Coulomb blockade" phenomenon exploited in single-electron electronics and charge sensing.

### 4.5 Molecular electronics and image-charge effects
When molecules bridge metallic electrodes, Coulomb interactions (including image-charge corrections from the metal surfaces) shape the electrostatic potential profile and current–voltage characteristics, important for the design of molecular-scale electronic devices.

---

## 5. Astrophysics and Stellar Structure

### 5.1 White dwarf interiors and pulsation modeling
In dense, degenerate stellar interiors (white dwarfs), ion–ion Coulomb interactions affect the equation of state and element diffusion profiles. Comparing pure vs. screened Coulomb potential treatments in stellar evolution codes measurably changes predicted pulsation-mode frequencies, used to fit asteroseismological observations of pulsating white dwarfs.

### 5.2 Coulomb corrections to the equation of state
Non-ideal Coulomb interactions (beyond the ideal gas approximation) modify pressure and energy in dense astrophysical plasmas, relevant to modeling stellar interiors, giant-planet interiors, and the crusts of neutron stars.

---

## 6. Plasma Physics and High-Energy-Density Science

### 6.1 Molecular dynamics of Coulomb (one-component and multi-component) plasmas
Classical and semi-classical particle simulations of strongly coupled plasmas typically combine a long-range Coulomb potential with a short-range repulsive (e.g., Lennard-Jones) term to prevent unphysical recombination, used to study structure formation, transport coefficients, and non-ideal plasma thermodynamics.

### 6.2 Laser–plasma ion acceleration
In laser-driven ion acceleration (e.g., for medical, tomographic, or fusion-relevant applications), relativistic molecular dynamics simulations explicitly propagate the Coulomb (and electromagnetic) interactions among large numbers of charged particles to model nanotube- or foil-based accelerator schemes.

---

## 7. Applications in Chemistry

### 7.1 Periodic trends: ionization energy, electron affinity, atomic/ionic radii
Coulomb's law provides the qualitative and semi-quantitative basis for rationalizing periodic trends: ionization energy and electronegativity trends follow from the balance of nuclear charge, shielding, and electron–nucleus distance, all Coulombic in origin. This is a cornerstone of general and physical chemistry pedagogy.

### 7.2 Ionic and covalent bonding, lattice energies
Ionic bond strength and lattice energy calculations (Born–Landé, Born–Mayer, Kapustinskii equations) are built directly on Coulombic attraction between ions, balanced against short-range Pauli repulsion.

### 7.3 Molecular mechanics and force fields
Classical force fields used in computational chemistry and drug design (AMBER, CHARMM, OPLS, etc.) represent non-bonded electrostatic interactions between partial atomic charges via a Coulomb term, in addition to van der Waals terms. Efficient and accurate evaluation of these long-range Coulomb sums (via Ewald summation, particle-mesh Ewald, or fast multipole methods) is essential to biomolecular and materials simulations.

### 7.4 Solvation and electrolyte chemistry
The Coulomb interaction, modulated by a solvent dielectric constant and Debye–Hückel screening, underlies continuum solvation models (Born model, Poisson–Boltzmann, generalized Born) as well as classical theories of electrolyte activity coefficients and ionic conductivity.

### 7.5 Electrochemistry and redox chemistry
Coulombic (electrostatic) effects of charged residues and ions modulate redox potentials, pKa shifts, and binding constants in biomolecular and electrochemical systems, and are central to modeling electrode–electrolyte interfaces, double-layer structure, and interfacial capacitance.

### 7.6 Machine-learned interatomic potentials with explicit electrostatics
Recent work augments machine-learned (neural network) interatomic potentials — which by construction represent only short-range interactions — with an explicit long-range Coulomb term, enabling accurate simulation of systems where charge transfer and polarization matter, such as liquid–electrode interfaces.

---

## 8. Summary

| Domain | Representative Coulomb-based application |
|---|---|
| Atomic physics | Hydrogenic spectra, many-electron structure, Coulomb explosion imaging |
| Nuclear/particle physics | Coulomb barrier tunneling, Coulomb excitation, quark confinement models |
| Condensed matter | Madelung lattice energies, Coulomb blockade, Wigner crystals |
| Astrophysics | White dwarf pulsations, dense-plasma equations of state |
| Plasma physics | Strongly coupled plasma MD, laser ion acceleration |
| Chemistry | Periodic trends, ionic bonding, force fields, solvation, electrochemistry |

The unifying thread is that the bare $1/r$ Coulomb law, together with its screened (Yukawa/Debye–Hückel), regularized, or effective-field variants, remains indispensable across length scales from femtometers (nuclear/quark physics) to stellar radii (astrophysics), and continues to drive methodological innovation in numerical simulation (Ewald-type summation methods, machine-learned potentials with explicit electrostatics).

---

## 9. Publications by Application Area

### Atomic, molecular, and cold-ion physics
- Okorie, U. S. et al. "Approximate solutions of the Schrödinger equation with energy-dependent screened Coulomb potential in D–dimensions." *Eclética Química*, 45(4), 40–56 (2020).
- Band, Y. B., Avishai, Y. "Quantum Mechanics with Applications to Nanotechnology and Information Science" (2013) — treatment of 1D/2D/3D Coulomb potential scattering.
- Willitsch, S. (Chapter author). "Chemistry Using Coulomb Crystals." *ACS Symposium Series* (2021).
- Schmid, S. et al. "Localization of ions within one-, two- and three-dimensional Coulomb crystals by a standing wave optical potential." arXiv:1703.05089.

### Nuclear and particle physics
- Alder, K., Winther, A. "Theory and Applications of Coulomb Excitation" — review and associated arXiv treatment, arXiv:0908.4307.
- Lucha, W., Schöberl, F. F. "Facets of the Spinless Salpeter Equation" — Coulomb potential as illustrative interaction for relativistic bound-state bounds, arXiv:hep-ph/0408184.

### Condensed matter and mesoscopic physics
- Hammonds, K. D. "Calculating Coulomb interactions in molecular dynamics simulations: The Evjen method revisited." *J. Chem. Phys.* 164, 014505 (2026).
- Author(s). "Unification of Ewald and shifted force methods to calculate Coulomb interactions in molecular simulations." *J. Chem. Phys.* 160, 244105 (2024).
- Rottler, J., Maggs, A. C. "Local Molecular Dynamics with Coulombic Interactions." arXiv:cond-mat/0312438.
- ScienceDirect Topics. "Coulomb Potential — an overview," compiling entries from *Quantum Mechanics with Applications to Nanotechnology and Information Science* and related sources.
- Nagy, J. et al. "The electrostatic potential profile along a biased molecular wire: A model quantum mechanical calculation." arXiv:physics/0209091.

### Astrophysics
- Chen, Y. H. "Application of screened Coulomb potential in fitting DBV star PG 0112+104." arXiv:1712.00581.

### Plasma physics
- Author(s). "Structure formation by electrostatic interactions in strongly coupled medium" (LAMMPS Coulomb + Lennard-Jones MD study). arXiv:2212.14202.
- Author(s). "Relativistic and Electromagnetic Molecular Dynamics Simulations for a Carbon-Gold Nanotube Accelerator." *Computer Physics Communications*, DOI: 10.1016/j.cpc.2019.03.012; arXiv:1711.04106.

### Chemistry and biomolecular simulation
- Åqvist, J., Warshel, A. "Electrostatic screening in molecular dynamics simulations." (Studies of screened Coulombic potential in pK shifts, redox potentials, binding constants.) *PubMed* PMID 1667879.
- Hisama, K. et al. "Molecular dynamics of liquid–electrode interface by integrating Coulomb interaction into universal neural network potential." *J. Comput. Chem.* (2024), DOI: 10.1002/jcc.27487.
- Albert.io Crash Course. "Coulomb's Law Review: AP Chemistry" — periodic-trends and ionization-energy applications (educational reference).

---

*Note: Author lists and full bibliographic details for several arXiv preprints and web-indexed sources above are abbreviated to what was retrievable from search snippets; consult the linked DOIs/arXiv IDs for complete citation data before formal use.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Coulomb potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
