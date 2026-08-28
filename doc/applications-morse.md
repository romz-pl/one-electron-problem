# The Morse Potential: A Review of Applications in Physics and Chemistry

## 1. Introduction and Mathematical Form

The Morse potential was introduced by Philip M. Morse in 1929 to describe the potential energy of a diatomic molecule as a function of internuclear separation $r$ [1]. It is written as

$$V(r) = D_e\left(1 - e^{-\alpha(r - r_e)}\right)^2,$$

or, in the equivalent shifted exponential form often used in nuclear and condensed-matter contexts,

$$V(x) = D\left(e^{-2\alpha x} - 2e^{-\alpha x}\right), \qquad x = r - r_e,$$

where $D_e$ (or $D$) is the dissociation/well-depth energy, $r_e$ is the equilibrium separation, and $\alpha$ sets the width of the well. Unlike the harmonic oscillator, the Morse potential is anharmonic, has a finite dissociation limit as $r \to \infty$, and possesses a steep repulsive wall at short range — all features shared with real interatomic interactions. Critically, the corresponding time-independent Schrödinger equation is one of the few exactly solvable problems in quantum mechanics, giving closed-form bound-state energies and wavefunctions. This combination of physical realism and mathematical tractability is the reason the potential has been applied across an unusually broad span of physics and chemistry for nearly a century.

This review surveys the major application domains, organized thematically, with representative and foundational publications cited for each.

---

## 2. Molecular Spectroscopy and Diatomic Molecule Vibrations

### 2.1 Anharmonic vibrational structure

The original and still dominant application is modeling the vibrational (and rovibrational) energy levels of diatomic molecules. Because the Schrödinger equation for the Morse potential is exactly solvable, it yields the well-known anharmonic term-value expansion

$$G(v) = \omega_e\left(v + \tfrac{1}{2}\right) - \omega_e x_e\left(v + \tfrac{1}{2}\right)^2 + \cdots,$$

which reproduces the empirical Birge–Sponer behavior of real molecules far better than the harmonic oscillator, particularly near dissociation where the Morse oscillator is an anharmonic potential that effectively describes vibrational systems deviating from ideal harmonic behavior, particularly useful for modeling the vibrations of diatomic molecules. The vibrational wavefunctions for a Morse oscillator can be expressed analytically in terms of Whittaker functions or polygamma functions, and unlike harmonic-oscillator eigenfunctions, the exact Morse eigenfunctions are not symmetric about the equilibrium distance and become increasingly skewed toward the outer turning point at high vibrational quantum number.

Because its three parameters ($D_e$, $r_e$, $\alpha$) map directly onto measurable spectroscopic constants, the Morse potential remains the standard first correction beyond the harmonic approximation taught in physical chemistry curricula, and continues to be used as a benchmark and starting point in modern rovibrational-spectroscopy software such as VibHam, a classroom and research tool that uses numerical solutions to the rovibrational Schrödinger equation to reproduce spectroscopic constants beyond the harmonic-oscillator approximation, for which the Morse potential is the potential frequently employed to capture inherent anharmonicity.

Detailed studies comparing the idealized Morse model against real spectroscopic data show its strengths and limits: Birge–Sponer extrapolation analysis of the Morse approximation to real diatomic potentials, using literature transition-frequency data for H₂, O₂, Be₂, Li₂, ArXe, Xe₂, Kr₂, and excited-state Li₂, shows that the anharmonicity parameter of real molecules deviates from the constant value assumed by the ideal Morse model, and that the ideal Morse molecule does not exist exactly in nature.

### 2.2 Comparative accuracy against other analytic model potentials

A recurring theme is benchmarking the Morse potential against alternative solvable potentials (Manning–Rosen, Kratzer, Deng–Fan, etc.) for predicting spectroscopic constants: a comparative study across many diatomics — including LiH, HI, Li₂, HBr, LiD, HCl, HF, F₂, O₂, CS, N₂, CO, SiS, Na₂, K₂, Rb₂ and excited electronic states of Li₂ — found the Morse oscillator generally superior to the Manning-Rosen oscillator for predicting vibrational levels, and that anharmonicity and rotation-vibration coupling constants derived from the Morse oscillator agreed better with experiment.

### 2.3 Bond dissociation and electronic-structure connections

A recent line of work connects the empirical Morse parameters directly to atomic/electronic-structure quantities. The Morse potential can be derived from a screened-charge model that accounts for shielding of the nuclear charge by electron density, in which the potential-width parameter relates to average shielding strength and atomic-orbital exponents used in electronic structure calculations, while the dissociation-energy parameter is derived by combining quantum-mechanical covalent and classical electrostatic contributions. This derivation links the Morse parameters to Pauling's bond order and electronegativity, and is expected to inform new Slater-type-orbital basis sets and transferable reactive force fields for molecular dynamics.

### 2.4 Related canonical/algebraic treatments

Canonical-transformation methods built on the Morse potential as a reference allow accurate generation of Born–Oppenheimer potential curves for systems such as H₂⁺, covalently bound H₂, van der Waals-bound Ar₂, and the hydrogen-bonded dissociative coordinate of a water dimer, with inverse transformations giving vibrational eigenvalues in significantly improved agreement with values from the original accurate potentials.

---

## 3. Quantum Mechanics: Exact Solvability, Supersymmetry, and Formal Structure

### 3.1 Exactly solvable model and pedagogical benchmark

The Morse potential accounts for bond anharmonicity, providing a more realistic description of molecular vibrations and dissociation processes than the harmonic oscillator, and beyond molecular modeling it plays a foundational role in quantum mechanics, where it serves as an exactly solvable model providing a benchmark for testing approximation methods. Because closed-form solutions exist, the Morse potential is routinely used to test numerical methods (WKB, Nikiforov–Uvarov, supersymmetric quantum mechanics, path-integral techniques) against an exact reference.

### 3.2 Supersymmetric quantum mechanics (SUSY QM) and shape invariance

The Morse potential is a textbook example of a **shape-invariant potential** in SUSY QM, meaning its supersymmetric partner potential has the same functional form with shifted parameters, which allows the entire spectrum to be obtained algebraically. Gendenshtein first showed that supersymmetric partner potentials satisfying shape invariance and unbroken supersymmetry are exactly solvable, with the shape-invariance condition allowing full algebraic determination of energy eigenvalues, eigenfunctions, and scattering matrices. Building on this property, the entire hierarchy of Morse potentials generated by shape invariance is exactly solvable, forming a chain of intertwined Hamiltonians connected by ladder-type operators.

This framework has been extended to generate new solvable potentials and rational extensions: a novel enlarged shape-invariance property, first identified for the Morse potential, has been used to derive rational extensions of the Rosen–Morse II and Eckart potentials solvable within first-order supersymmetric quantum mechanics. Related work has generated q-deformed reflectionless potential families from the Morse/Rosen–Morse framework by using a scaling ansatz for the change of parameters within shape-invariant SUSY QM, producing a large class of new reflectionless shape-invariant potentials, including a shape-invariant double-well potential whose supersymmetric partner reduces to a single well.

### 3.3 Non-Hermitian and PT-symmetric extensions

A supersymmetric one-dimensional matrix procedure analogous to Dirac–Schrödinger relationships in particle physics has been applied to introduce a non-Hermitian Morse Hamiltonian, with the imaginary part proportional to the solution of a Riccati equation of Witten type, suggested as a possible model for molecular diffraction in evanescent waves over nanostructured surfaces.

### 3.4 Nonclassicality and quantum-optics applications

The exact solvability of the Morse potential has also made it a useful test system in modern quantum-information contexts. The Morse potential provides a better description of the vibrational structure of diatomic molecules than the quantum harmonic oscillator, and its associated Schrödinger equation can be solved analytically, with energy eigenstates labeled by two quantum numbers; expanding the potential in the limit of vanishing width parameter at fixed well depth recovers the harmonic oscillator with a frequency set by the well depth and width — this exact solvability has enabled its use as a model anharmonic system for studying nonclassical states and nonlinearity as a quantum resource.

### 3.5 Dunkl formalism and modern spectral extensions

More recent work generalizes the spectral and thermal analysis of the Morse potential within the Dunkl formalism, motivated by the fact that the Morse potential's exponential form makes its applicability to more complex structures limited without suitable mathematical extensions.

---

## 4. Nuclear and Particle Physics

### 4.1 Alpha decay and cluster radioactivity

The Morse potential has been adopted as an effective nucleus–nucleus (or cluster–daughter-nucleus) interaction potential for modeling quantum tunneling in radioactive decay. A systematic study of experimental alpha-decay half-lives for 263 parent nuclei with proton number between 52 and 107 used the Morse potential together with the WKB approximation and Bohr–Sommerfeld quantization to find optimum potential parameters, achieving better agreement with experiment than the unified model for alpha decay/capture (UMADAC) and the Universal Decay Law (UDL), while using fewer free parameters.

More recent work has extended this to modified forms of the potential: a 2025 study calculated alpha-decay half-lives for even–even nuclei using a modified Morse potential within Gamow tunneling theory.

### 4.2 Nucleon–nucleon and alpha–alpha scattering

The Morse potential's short-range repulsive core, attractive intermediate-range well, and exponentially decaying tail make it a natural phenomenological model for the nuclear force at low energies. The short-range nuclear interaction between two alpha particles can be modeled using the Morse potential, which naturally incorporates strong short-range repulsion, an attractive pocket at intermediate distances, and an exponentially decaying tail, all characteristic of realistic nuclear forces; the corresponding time-independent Schrödinger equation is exactly solvable, giving closed-form bound-state energies and wavefunctions, and for scattering problems the Morse potential admits analytical solutions for specific partial waves such as the ¹S₀ state — a property not shared by many other phenomenological potentials such as Manning–Rosen, Hulthén, or Malfliet–Tjon. Comparative studies have benchmarked it against other phenomenological forms: a comprehensive comparative analysis of Morse, Double Gaussian, Double Hulthén, Malfliet–Tjon, and Double Exponential potentials was performed to model alpha–alpha elastic scattering in the S, D, and G channels up to 25.5 MeV using the atomic Hulthén potential to screen the Coulomb interaction. The same group applied the Morse potential to another two-body nuclear system in a study of low-energy S-wave proton–deuteron scattering phase shifts using the Morse potential.

---

## 5. Condensed Matter and Solid-State Physics

### 5.1 Lattice dynamics, elastic constants, and thermal properties

The Morse potential is widely used as a pairwise interatomic interaction for crystalline solids, since its anharmonicity naturally captures thermal expansion and nonlinear lattice-vibration effects that a harmonic potential cannot. The Morse potential has applications throughout chemical physics, including the discussion of thermal properties of systems such as diamond-class materials, determination of vibrational force constants and elastic properties, discussion of correlations in alloy phases, spectral analysis, quantum effects, vibrational energy states, alpha decay, and the structure of dimers. Related work derives closed-form thermodynamic/structural quantities directly from the potential: a formula for the Morse-potential specific bond volume was derived using integral-equation theory of simple fluids based on the Ornstein–Zernike equation, applicable to dimers and to soft–hard slab-slider systems.

In condensed matter and solid-state physics, the Morse potential is used to study nonlinear lattice vibrations and phonon dynamics, and it has also found use in atomic physics to model Rydberg-molecule interactions and interatomic forces in crystal-structure analysis.

### 5.2 Mechanical/elastic properties via atomistic simulation

The Morse potential is a standard choice for computing elastic moduli and mechanical response of crystals and nanostructures at the atomistic level. A finite-element-analysis-based atomistic-continuum method combined with the Morse potential for metals was used to determine the elastic modulus of atomic-level single-crystal copper, where the interactive energy of two copper atoms in a face-centered lattice was described by a mechanical spring-stiffness response derived from Morse-potential parameters, giving effective elastic moduli of 86.8, 152.6, and 205.2 GPa along the Cu(100), Cu(110), and Cu(111) orientations.

Graphene and carbon-nanotube mechanics is another prominent example: a computationally efficient pairwise Morse-based potential for molecular dynamics simulations of large graphene or carbon-nanotube systems under mechanical deformation, and of mixed systems including biomolecules, is only slightly more complex and expensive than a harmonic bond potential, allowing large-scale simulations to reach experimentally relevant time scales; fitting to quantum-mechanical data representing bond breaking in graphene patches gave a dissociation energy of 805 kJ/mol reflecting the steepness of the QM potential up to the inflection point.

### 5.3 Friction, wear, and adhesion at interfaces

A modified pairwise interatomic Morse potential has been used to describe interatomic interaction and adhesive properties between contacting bodies in atomistic simulations of friction and wear, where only the tail of the potential was modified to isolate the effect of interfacial adhesion from bulk material properties, modeling adhesion between a rigid probe and a metal crystal (itself modeled with a standard embedded-atom-method potential) while varying the shape of the attractive tail.

### 5.4 Thin-film growth and deposition

Molecular dynamics modeling of electrolytic deposition of silicon carbide films on copper, nickel, and graphite substrates in a fluoride melt compared Tersoff and Morse potentials for the film–substrate interaction, finding that the Morse potential gave 1.5 times higher adhesion energy of the SiC film to graphite and higher film crystallinity than the Tersoff potential.

---

## 6. Molecular Dynamics Force Fields and Reactive Simulations

### 6.1 Reactive bond potentials replacing harmonic terms

A major modern application is the use of Morse bond terms to enable bond breaking/forming in otherwise non-reactive classical force fields. The Reactive Interface Force Field (IFF-R) uses a Morse potential instead of the harmonic potential typically employed in molecular dynamics force fields to describe bond energy, allowing any desired bond to be rendered reactive by specifying the curve shape and dissociation energy, extending force fields such as IFF, PCFF, AMBER, CVFF, CHARMM, and OPLS-AA — which normally use harmonic bond terms incapable of bond breaking/forming — without loss of functionality, accuracy, or speed. Applied to real materials, cellulose parameters modified to use the Morse potential following the IFF-R protocol predicted an elastic modulus about 20% lower than experiment with a 20% overestimate of strength, in better and less ambiguous agreement than corresponding ReaxFF predictions.

The same Morse-substitution strategy has been extended to metal–organic framework simulation: a partially reactive force field for the UiO-66 metal–organic framework replaces the hard bonded potential between metal node and ligand with a non-bonded Morse potential combined with charge-dependent atomic (CDA) parametrization, enabling simulation of dynamic bond breaking and formation while preserving correct bond topology.

### 6.2 Metal clusters and isotropic systems

In molecular dynamics simulations of matter exposed to ultrafast X-ray lasers, non-bonded Morse and angular potentials suffice to describe the dynamics of metal clusters because of their rather isotropic structure, which permits the use of spherically symmetric two-body potentials, in contrast to biological macromolecules which require additional bonded terms for bonds, angles, dihedrals, and CMAPs.

---

## 7. Surface Science: Adsorption, Chemisorption, and Gas–Surface Scattering

### 7.1 Physisorption potentials and atom–surface scattering dynamics

The Morse potential is a standard model for the physisorption well an incident atom experiences near a solid surface, since it naturally reproduces a long-range attractive tail and a repulsive short-range wall. Morse potentials have been used to model the interaction of argon atoms with a platinum surface in surface-scattering and desorption simulations, with the well depth and vibrational frequency independently tunable to study trapped versus escaping trajectories and the resulting energy dissipated from adsorbate to lattice. Analytically, the Morse potential provides a well-modeled physisorption well for atom–surface scattering, with the associated classical trajectory known analytically, allowing derivation of closed-form expressions for the rainbow-angle shift parameter that characterizes asymmetry in the scattered angular distribution.

A one-dimensional Morse potential has been used to model a desorption potential for adsorbates on metal surfaces in quantum-corrected Langevin dynamics simulations, quantizing the potential to obtain a discrete set of bound states plus a continuum of free states in order to study electron-mediated desorption dynamics under a thermal electron pulse.

### 7.2 Chemisorption, dissociation barriers, and bond-order conservation models

The bond-order-conservation (BOC) model, which employs Morse-type potentials, rigorously interrelates diverse chemisorption phenomena including preferred adsorbate sites, activation barriers for surface migration and dissociation, relations between atomic and molecular heats of chemisorption, coverage and coadsorption effects, overlayer phase transitions, and the nature of catalytic promotion and poisoning.

---

## 8. Summary Table of Application Domains

| Domain | Representative Use | Key References |
|---|---|---|
| Molecular spectroscopy | Anharmonic vibrational/rovibrational energy levels of diatomics | [1–6, 9–15] |
| Quantum mechanics (formal) | Exactly solvable benchmark; SUSY QM shape invariance; non-Hermitian extensions | [2, 8, 37–45] |
| Nuclear physics | Alpha-decay half-lives (WKB/Gamow tunneling); nucleon–nucleon and α–α scattering | [18–26] |
| Condensed matter/solid state | Lattice dynamics, elastic moduli, phonons, thermal expansion | [1, 2, 27] |
| Nanomechanics | Graphene/CNT mechanics, friction/wear/adhesion, thin-film growth | [7, 28, 36] |
| Molecular dynamics force fields | Reactive bond potentials (IFF-R), MOF and cluster simulations | [30–35] |
| Surface science | Physisorption, gas–surface scattering, chemisorption barriers | [46–52] |

---

## 9. List of Publications by Application Area

### Foundational / General
1. Morse, P. M. (1929). *Diatomic Molecules According to the Wave Mechanics. II. Vibrational Levels.* Phys. Rev. 34, 57.
2. Rahali, M. et al. (2025). *Spectral and Thermal Analysis of the Morse Potential within the Dunkl Formalism: Analytical Approximations and Applications.* arXiv:2506.00877.
3. Bulava-Fischer, M. / Bučinský, L. et al. *Derivation of Morse potential.* Molecular Physics, 123(3) (2024). DOI: 10.1080/00268976.2024.2360542.
4. Li, J., Zgid, D., Freericks, J. (2025). *The Morse potential and its applications in describing vibrations and bond breaking in molecules.* Eur. J. Phys. 46, 055801.
5. Al-Raeei, M. (2022). *Morse potential specific bond volume: a simple formula with applications to dimers and soft–hard slab slider.* J. Phys.: Condens. Matter 34, 284001.
6. Rahali, M. et al. (2021). *Accuracy of Morse and Morse-like oscillators for diatomic molecular interaction: A comparative study.* (ScienceDirect / Karbala Int. J. Modern Sci.)

### Molecular Spectroscopy
7. Roy, A. K. (2013). *Accurate ro-vibrational spectroscopy of diatomic molecules in a Morse oscillator potential.* arXiv:1307.4978.
8. Denisov, G. S., Tokhadze, K. G. (2022). *Implementation of Morse potential for approximation of vibrational terms of diatomic molecules.* Optics and Spectroscopy, 130(14).
9. Nikitin, A. et al. *More about properties of Morse oscillator.* (ScienceDirect, 2021).
10. VibHam developers (2024). *VibHam: A Classroom Tool for Predicting the Rovibrational Spectra of Diatomic Molecules beyond the Harmonic Oscillator Approximation.* J. Chem. Educ.
11. Barletta, P., Zicovich-Wilson, C. et al. *Morse, Lennard-Jones, and Kratzer Potentials: A Canonical Perspective with Applications.* J. Phys. Chem. A, 2016.

### Quantum Mechanics / Supersymmetric Quantum Mechanics
12. Khare, A., Sukhatme, U. P. (1993). *New Shape Invariant Potentials in Supersymmetric Quantum Mechanics.* arXiv:hep-th/9212147; J. Phys. A 26, 18 (1993).
13. Khare, A., Sukhatme, U. P. (1993). *New Exactly Solvable Hamiltonians: Shape Invariance and Self-Similarity.* Phys. Rev. A 48, 2786.
14. Quesne, C. (2012). *Novel Enlarged Shape Invariance Property and Exactly Solvable Rational Extensions of the Rosen–Morse II and Eckart Potentials.* SIGMA 8, 080. arXiv:1208.6165.
15. Andrianov, A. et al. (2012). *Nonlinear Supersymmetric Quantum Mechanics: concepts and realizations.* arXiv:1207.6799.
16. Compean, C. B., Kirchbach, M. (2005). *The Trigonometric Rosen–Morse Potential in Supersymmetric Quantum Mechanics and its Exact Solutions.*
17. Cornejo-Pérez, O., López-Sandoval, R., Rosu, H. C. (2005). *Riccati Nonhermiticity with Application to the Morse Potential.* Rev. Mex. Fís. 51(3), 316–319. arXiv:quant-ph/0502074.
18. Author(s) (2015). *Nonlinearity as a resource for nonclassicality in anharmonic systems.* arXiv:1507.07840.

### Nuclear and Particle Physics
19. (2021). *A new potential model for alpha decay calculations.* Nuclear Physics A, DOI: 10.1016/j.nuclphysa.2021.122211.
20. Tchuidjan, M., Ema'a Ema'a, J. M., Ahmadou, K., Ndzono, V. P., Ben-Bolie, G. H. (2025). *Calculation of alpha decay half-lives for even–even nuclei with modified Morse potential using Gamow theory.* Int. J. Mod. Phys. E, 34(5).
21. Awasthi, S., Sastri, O. S. K. S., Khachi, A. (2022). *Low Energy S-Wave Proton–Deuteron Scattering Phase-Shifts using Morse Potential.* J. Nucl. Phys. Mater. Sci. Radiat. Appl. 9(2), 223–228.
22. Khachi, A., Sastri, O. S. K. S., Kumar, L. (2021). *Alpha–Alpha Scattering Potentials for Various ℓ-Channels Using Phase Function Method.* Phys. At. Nucl. 85, 382–391.
23. (2026). *A Computational Phase Function Method for α–α Scattering: Wavefunction Construction from Single and Two-Term Morse Potentials.* arXiv:2601.11749.
24. (2023). *Comparative Study of alpha-alpha interaction potentials constructed using various phenomenological models.* arXiv:2307.13207.
25. (2024). *Algorithm to Obtain Inverse Potentials for α–α Scattering using Variable Phase Approach.* arXiv:2403.19173.

### Condensed Matter, Solid State, and Nanomechanics
26. Lee, C.-C., He, J.-Y. (2020). *Interactive Field Effect of Atomic Bonding Forces on the Equivalent Elastic Modulus Estimation of Micro-Level Single-Crystal Copper by Utilizing Atomistic-Continuum Finite Element Simulation.* Molecules 25(21), 5107.
27. Aghababaei, R. et al.; and (2024) *On the Adhesive Interaction Between Metals in Atomistic Simulations of Friction and Wear.*
28. Ghasemi, A., Pastewka, L. et al. *Graphene mechanics: I. Efficient first principles based Morse potential.* Phys. Chem. Chem. Phys., 2014.
29. (2023). *Molecular Dynamics Simulation of Thin Silicon Carbide Films Formation by the Electrolytic Method.* (PMC10144933).
30. Mardiyah, R. U. et al. (2020). *Energy Cohesive Calculation for Some Pure Metals Using the Lennard-Jones Potential in Lammps Molecular Dynamics.* J. Phys.: Conf. Ser. 1491, 012020. (Comparative context for Morse vs. Lennard-Jones parametrization.)

### Molecular Dynamics Force Fields
31. Heinz, H. et al. (2024). *Implementing reactivity in molecular dynamics simulations with harmonic force fields.* Nature Communications; arXiv:2107.14418; NSF PAR: 10297187.
32. (2025). *Partially reactive force field for the UiO-66 metal-organic framework.* arXiv:2605.19808.
33. (2024). *MolDStruct: modelling the dynamics and structure of matter exposed to ultrafast X-ray lasers with hybrid collisional-radiative/molecular dynamics.* arXiv:2401.03180.

### Surface Science: Adsorption and Scattering
34. (2023). *Modeling surface vibrations and their role in molecular adsorption: a generalized Langevin approach.* arXiv:2301.04873.
35. (2013). *Second order classical perturbation theory for atom surface scattering: analysis of asymmetry in the angular distribution.* arXiv:1304.3294.
36. Hayes, W. W., Manson, J. R. et al. (2018). *Microscopic modeling of gas-surface scattering. II. Application to argon atom adsorption on a platinum (111) surface.* arXiv:1802.01985.
37. (2010). *Quantum corrected Langevin dynamics for adsorbates on metal surfaces interacting with hot electrons.* arXiv:1003.2318.
38. Shustorovich, E. (1985). *Dissociation activation barrier and heat of chemisorption: A Morse-type analytical approach* (Bond-Order-Conservation model). Surface Science.
39. (2023). *The ignition of fine iron particles in the Knudsen transition regime.* arXiv:2302.06704.

---

## 10. Notes on Coverage and Caveats

- This review prioritizes recent (post-2000, with an emphasis on 2020s) sources retrievable via web search, alongside a small number of foundational papers identified through citation trails; it is representative rather than exhaustive of a century-long literature.
- Several entries above are cross-referenced from bibliography lists in papers found in the searches (e.g., items 8, 21–22) rather than directly verified against original abstracts; full bibliographic details (page numbers, exact author lists) should be independently confirmed before formal citation.
- Additional established application areas not covered in depth here but worth noting for completeness: Morse-potential-based equations of state for simple fluids and virial coefficients; Morse-type potentials in quantum cosmology (via shape-invariant potential families); and Rydberg-molecule interaction modeling in atomic physics.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Morse potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
