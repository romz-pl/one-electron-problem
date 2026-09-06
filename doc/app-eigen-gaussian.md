# Applications of Eigenvalues and Eigenfunctions of the Gaussian Potential

## 1. Introduction

The Gaussian potential,

$$V(r) = -V_0 \, e^{-\alpha r^2} \qquad \text{(attractive well)}, \qquad \text{or} \qquad V(r) = +V_0\, e^{-\alpha r^2} \qquad \text{(repulsive barrier)},$$

is one of the most widely used short-range model potentials in quantum theory. Unlike the Coulomb or harmonic-oscillator potentials, the Schrödinger equation

$$-\frac{\hbar^2}{2m}\nabla^2\psi(\mathbf r) + V(\mathbf r)\,\psi(\mathbf r) = E\,\psi(\mathbf r)$$

with a Gaussian $V(\mathbf r)$ does **not** admit closed-form analytical solutions in general (a small number of quasi-exactly-solvable special cases exist). This apparent inconvenience is precisely what has made the Gaussian potential a fertile testing ground: it is smooth, finite everywhere, decays faster than any power law, has only two free parameters (depth $V_0$ and range/width $\alpha$ or $\lambda$), and is simple enough to fit to experimental data yet complicated enough to demand genuine approximation methods. Consequently, the eigenvalue problem for the Gaussian potential has served for nearly a century as a benchmark for numerical and semi-analytical techniques, and the potential itself (or superpositions of it, i.e. Gaussian *basis sets*) has become a practical modelling tool across several branches of physics and chemistry.

This review surveys the major application domains in which the eigenvalues (bound-state energies, resonance positions, propagation constants) and eigenfunctions (bound-state wavefunctions, basis functions, normal modes) of Gaussian-type potentials play a central role.

---

## 2. Mathematical Character of the Problem

- **Non-analytic solvability.** For the pure radial Gaussian well $V(r) = -V_0 e^{-r^2/r_0^2}$, the Schrödinger equation cannot be reduced to any of the classical special-function equations (Hermite, Laguerre, hypergeometric) for general angular momentum $\ell$, in contrast to the harmonic oscillator or Coulomb potentials. This motivated a long sequence of approximate and numerical treatments.
- **Quasi-exact solvability.** Certain generalizations — the *pseudo-Gaussian* or *pseudoharmonic* oscillators — belong to the class of quasi-exactly solvable (QES) models, for which a finite subset of eigenvalues and eigenfunctions (often expressed through Jacobi or other orthogonal polynomials) can be obtained in closed form, while the rest of the spectrum must still be computed numerically.
- **Standard solution techniques applied to it** include:
  - Direct numerical integration (shooting/Numerov methods) — historically the first approach (Buck, 1977, unpublished).
  - The Liouville–Green (WKB-type) uniform asymptotic method (Stephenson).
  - Perturbative and variational treatments on a Jacobi-function basis (Bessis, Drukarev, and co-workers).
  - Hypervirial–Padé resummation schemes (Lai).
  - Scaled harmonic-oscillator perturbation theory (Cohen).
  - The Asymptotic Iteration Method (AIM) and its variational hybrids (Mutuk and others).
  - The Asymptotic Taylor Expansion Method (ATEM), Nikiforov–Uvarov method, and related algebraic techniques.
  - Few-parameter analytic *Ansätze* constructed from the exact small- and large-$r$ asymptotics of the true wavefunction, used to build rapidly convergent basis sets (Rodriguez-Espejo et al.).

These general-purpose methods, developed and validated specifically against the Gaussian-potential eigenvalue problem, have subsequently been reused for many other non-solvable potentials (Morse, Kratzer, Manning–Rosen, bistable/double-well potentials, etc.), making the Gaussian well a recurring "standard candle" in mathematical physics.

---

## 3. Application Domains

### 3.1 Nuclear Physics — Nucleon–Nucleon Interactions and Light Nuclei

The Gaussian well is a long-standing model for the short-range strong (nuclear) force between nucleons.

- **Deuteron binding energy.** Because the nuclear force is attractive and effectively vanishes beyond ~1–2 fm, a Gaussian well $V(r) = -V_0 e^{-\lambda r^2}$ reproduces the essential short-range, smooth-cutoff character of the interaction better than the discontinuous square well. The lowest eigenvalue of this potential is fit to the experimental deuteron binding energy (~2.2 MeV), and the corresponding eigenfunction models the deuteron's relative-motion wavefunction. Recent work derives analytic threshold expansions for this binding energy as the potential parameters approach the critical (just-barely-bound) regime.
- **Nucleon mean-field / single-particle motion in nuclei.** A "half-Gaussian" well is used as an effective mean-field potential for a nucleon moving in the field of the rest of the nucleus, exploiting the potential's smooth (as opposed to discontinuous) falloff at the nuclear surface.
- **Three-nucleon and light-nuclei Hamiltonians.** Sums of Gaussian two- and three-body terms (with spin-dependent coefficients fit to the deuteron and triton) are used to build effective nuclear Hamiltonians for few-body calculations.
- **Effective-range / scattering-phase-shift studies.** Non-local Gaussian potentials derived from quark-model baryon–baryon interactions are used to compute neutron–deuteron scattering observables (effective range parameters, scattering length) via the Faddeev formalism, again requiring the eigenvalue/eigenphase structure of Gaussian-type interaction kernels.

### 3.2 Semiconductor Nanostructures — Quantum Dot Confinement

The Gaussian potential (and its generalizations) is a standard, experimentally motivated model for the electrostatic confinement of electrons in semiconductor quantum dots (QDs).

- **Realistic confinement modelling.** Parabolic (harmonic) confinement, while analytically convenient, fails to reproduce transport-spectroscopy data for real QDs at higher excitation, particularly the finite number of bound states. A Gaussian confining potential has a *finite* depth and correctly predicts that only a limited number of electrons can be bound, unlike the harmonic oscillator which binds infinitely many states.
- **Few- and many-electron QDs.** Hartree–Fock and configuration-interaction calculations of $N \le 10$ electrons confined by a Gaussian well identify shell-like stability at $N = 2, 5, 8$ (in agreement with Hund's rule) and show that the single scaling parameter $V_0 R^2$ controls the number of bound electrons.
- **Impurities, complexes and optical properties.** Eigenvalue/eigenfunction calculations for donor impurities and ionized donor complexes (e.g. $D_2^+$) in 2D Gaussian QDs are used to predict binding energies, dissociation energies, and intersubband optical absorption spectra, which are directly tunable via the dot size and confinement depth — relevant to optoelectronic device design.
- **Double and coupled quantum dots.** Combined harmonic–Gaussian double-well confinement potentials model asymmetric double QDs, with the resulting eigenstates used to compute tunnelling splittings, coherent population oscillations between the wells (relevant to qubit implementations), and information-theoretic (Shannon entropy) measures of electron localization.
- **Comparative potential-shape studies.** Because real confinement profiles are neither purely harmonic nor a hard square well, "power-exponential" families of confinement potentials (with the Gaussian as the $p=2$ member) have been introduced to interpolate between soft (Gaussian) and hard-wall confinement and to study how the confinement *shape* itself affects electronic, thermodynamic, magnetic, and transport properties of GaAs quantum dots.
- **Density-functional treatments.** Few-electron systems under spherically symmetric Gaussian confinement have also been analyzed via density-functional and information-theoretic approaches (Shannon/Fisher information measures of the resulting eigenstates).

### 3.3 Quantum Chemistry — Gaussian-Type Orbitals and Basis Sets

Beyond the Gaussian potential as a model *interaction*, Gaussian *functions* themselves (Gaussian-type orbitals, GTOs) are the dominant basis-function choice for solving molecular electronic-structure eigenvalue problems.

- **Why Gaussians:** all multi-center molecular integrals (overlap, kinetic, nuclear-attraction, and especially the notoriously difficult two-electron repulsion integrals) can be evaluated **analytically** when the basis functions are Gaussians, in contrast to Slater-type or other exponential-type orbitals. This computational tractability is the historical reason GTOs revolutionized computational quantum chemistry (Hartree–Fock, DFT, post-HF correlated methods).
- **The underlying eigenvalue problem.** Expanding molecular orbitals in a GTO basis converts the electronic Schrödinger equation into a generalized matrix eigenvalue problem $\mathbf{H}\mathbf{C} = \mathbf{S}\mathbf{C}\boldsymbol\varepsilon$ (Roothaan–Hall equations), where $\mathbf S$ is the (generally non-orthogonal) Gaussian-basis overlap matrix; standard practice symmetrically orthogonalizes via $\mathbf S^{-1/2}$ to obtain a conventional eigenvalue problem for the orbital energies $\varepsilon_n$ and coefficients.
- **Basis-set engineering.** Contracted Gaussian basis sets (e.g., 6-31G*, and modern all-electron sets for excited-state/TDDFT calculations) combine multiple primitive Gaussians per atomic orbital to balance accuracy against computational cost; even-tempered and Hermite Gaussian bases are compared for their ability to capture the nuclear cusp of the true (non-Gaussian) atomic wavefunction.
- **Numerical analysis perspective.** Rigorous numerical-analysis studies establish convergence rates (often semi-exponential) of Gaussian-basis approximations to Schrödinger eigenproblems (hydrogen atom, and larger molecules such as H₂O via packages like Molpro).
- **Adaptive and reduced-order methods.** More recent work reduces the "basis-set error" inherent to fixed Gaussian bases via on-the-fly adaptive Gaussian-mixture reduction, discontinuous-Galerkin-embedded Gaussians, and Wasserstein-barycenter-based nonlinear reduced-basis methods for parametric electronic-structure eigenvalue problems.

### 3.4 Vibrational/Rovibrational Spectroscopy of Diatomic Molecules

Attractive Gaussian-type wells (and related pseudo-Gaussian/pseudoharmonic generalizations) are used, alongside the Morse and Kratzer potentials, as model interatomic potentials for diatomic molecules.

- The radial Schrödinger equation with such potentials is solved (via Nikiforov–Uvarov, AIM, ATEM, or hypervirial-Padé methods) to obtain rovibrational energy eigenvalues for arbitrary angular-momentum quantum number $\ell$ and vibrational quantum number $n$, with eigenfunctions expressed via Jacobi or other orthogonal polynomials.
- These eigenvalues are compared against spectroscopic data for real diatomic molecules to test the suitability of the Gaussian-type potential as an interatomic interaction model, complementing the more traditional Morse-oscillator description.

### 3.5 Numerical/Computational Methods and Multiscale Modelling

Gaussian potentials and Gaussian basis functions play a broader methodological role in computational physics beyond any single application area.

- **Method benchmarking.** Because the Gaussian well has no closed-form solution but is simple and smooth, it is a standard test case for validating new eigensolvers and semi-analytic techniques (AIM, ATEM, hypervirial-Padé, asymptotic Ansätze) before they are applied to more complex, physically realistic potentials.
- **Gaussian bases for the Schrödinger equation (chemical dynamics).** Position/momentum-adapted Gaussian basis sets — wider and sparser in classically forbidden/high-potential regions, narrower and denser in classically allowed/low-potential regions — are used to efficiently discretize multidimensional Schrödinger eigenproblems in quantum dynamics and chemical-reaction studies.
- **Mixed-basis and enriched finite-element methods.** Combining localized Gaussian enrichment functions with finite-element methods yields well-conditioned generalized eigenvalue problems for both harmonic and Gaussian-well test potentials, improving convergence rates for large-scale electronic-structure calculations (an alternative to plane-wave pseudopotential codes such as VASP/ABINIT).

### 3.6 Non-Hermitian and PT-Symmetric Systems (Optics and Photonics)

Complex-valued Gaussian potentials — real Gaussian wells combined with an odd imaginary (gain/loss) part — are widely used to construct exactly parity-time (PT) symmetric model Hamiltonians whose eigenvalues can remain entirely real despite the non-Hermiticity, a phenomenon with direct physical realizations in optics.

- **PT-symmetric optical potentials.** In the paraxial approximation, the propagation of light in a medium with a transversely varying refractive index (real part) and gain/loss profile (imaginary part) obeys a Schrödinger-like equation; Gaussian-shaped PT-symmetric potentials support families of guided modes (fundamental, dipole, tripole, quadrupole solitons) whose propagation-constant "eigenvalues" merge and disappear at symmetry-breaking (exceptional) points as the gain/loss strength is increased.
- **Solitons in PT-symmetric Gaussian potentials.** Both linear (waveguide) and nonlinear (cubic, cubic–quintic, power-law nonlinearity) Schrödinger equations with Gaussian PT potentials have been analyzed for the existence, stability, and dynamics of self-trapped optical beams; the linear eigenvalue spectrum of the underlying Gaussian potential provides the starting point (linear guided modes) for the subsequent nonlinear soliton analysis.
- **Experimental photonic implementations.** PT-symmetric potential landscapes (including Gaussian-profile wells) have been implemented using coupled optical waveguides and microring resonators with balanced gain and loss, enabling experimental observation of exceptional points, non-reciprocal light propagation, and PT-symmetric lasing — with direct applications to photonic sensors exploiting the heightened sensitivity of eigenvalues near exceptional points.

### 3.7 Cold Atoms, Optical Lattices, and q-Gaussian Ground States

- Gaussian-shaped potentials are the standard model for laser-generated optical dipole traps confining ultracold atoms and Bose–Einstein condensates; the eigenvalue problem determines trap-level spacings relevant to loading, evaporative cooling, and quantum-simulation experiments (closely related to the quantum-dot confinement problem in Section 3.2 but realized with neutral atoms rather than electrons).
- Generalized "q-Gaussian" ground-state wavefunctions have been used to construct classes of quantum potentials (via inversion of the Schrödinger equation) whose ground-state eigenfunction is prescribed to be a q-Gaussian, connecting this potential family to non-extensive statistical mechanics and information-theoretic measures of the resulting quantum states.

---

## 4. Summary Table

| Domain | Role of Gaussian eigenvalues/eigenfunctions | Representative outputs |
|---|---|---|
| Nuclear physics | Model of short-range nucleon–nucleon force | Deuteron binding energy, scattering phase shifts |
| Quantum dots / nanostructures | Confinement potential for electrons | Shell structure, binding/dissociation energies, optical spectra |
| Quantum chemistry | Basis functions (GTOs) for molecular orbitals | Molecular orbital energies, HF/DFT/post-HF wavefunctions |
| Molecular spectroscopy | Interatomic interaction model | Rovibrational energy levels for diatomics |
| Numerical/computational methods | Benchmark for non-solvable potentials | Validated eigensolvers (AIM, ATEM, hypervirial-Padé) |
| Photonics / PT-symmetric optics | Real+imaginary refractive-index profile | Guided-mode propagation constants, exceptional points, solitons |
| Cold atoms / optical traps | Confinement of ultracold atomic gases | Trap eigenstates, level spacings |

---

## 5. Related Publications

### Foundational and Methodological Studies
1. Buck, B. — unpublished (1977). First numerical (direct integration) determination of Gaussian-potential eigenvalues.
2. Stephenson, G. — eigenvalues of the 3D radial Gaussian potential via the Liouville–Green uniform asymptotic method.
3. Bessis, N., Bessis, G., Drukarev, G., et al. — perturbational/variational treatment of the radial Gaussian potential on a Jacobi-function basis.
4. Lai, C. S. — "The Hypervirial–Padé scheme applied to the Gaussian potential," energy eigenvalues for various eigenstates.
5. Cohen, M. — first-order perturbation treatment of the Gaussian potential based on a scaled harmonic-oscillator model.
6. Mutuk, H. — *Asymptotic Iteration and Variational Methods for Gaussian Potential*, Pramana – J. Phys. (also arXiv:1805.00006). Comparative AIM/variational treatment across $n,\ell$ quantum numbers.
7. Özer, O., Koklu, H., Resitoglu, S. — *Application of the Asymptotic Taylor Expansion Method to Bistable Potentials*, arXiv:1309.1381.
8. (Exact-solution study) — *Exact Solution to the Schrödinger Equation with Pseudo-Gaussian Potential*, Nikiforov–Uvarov / quasi-exactly-solvable treatment of pseudo-Gaussian oscillators.

### Nuclear Physics
9. Rodriguez-Espejo, G., Segura-Landa, J. A., Ortiz-Monfil, J., Nader, D. J. — *The Weakly Bound States in Gaussian Wells: From the Binding Energy of Deuteron to the Electronic Structure of Quantum Dots*, Int. J. Quantum Chem. (2024); also arXiv:2311.03404.
10. Fukukawa, K., Fujiwara, Y. — *Effective-Range Expansion of the Neutron–Deuteron Scattering Studied by a Quark-Model Nonlocal Gaussian Potential*, Prog. Theor. Phys. (also arXiv:1010.2024).
11. (Review/derivation) — *The Quantum Gaussian Well*, arXiv:1011.3637 — includes the "half-Gaussian" mean-field application to single-nucleon motion in nuclei.

### Quantum Dots and Nanostructures
12. Adamowski, J., Sobkowicz, M., Szafran, B., Bednarek, S. — *Modelling of Confinement Potentials in Quantum Dots*, Physica E / Phys. Rev. B-related study of Gaussian vs. parabolic confinement.
13. Gomez, S. S., Romero, R. H. — *Few-Electron Semiconductor Quantum Dots with Gaussian Confinement*, Physica E / J. Phys.: Condens. Matter.
14. Sari, H., Al, E. B., Kasapoglu, E., et al. — *Electronic and Optical Properties of a $D_2^+$ Complex in Two-Dimensional Quantum Dots with Gaussian Confinement Potential*, Eur. Phys. J. Plus 137, 464 (2022).
15. Boda, A. — *Effect of Magnetic Field on the Energy Spectrum, Binding Energy and Magnetic Susceptibility of an Impurity in a 2D Gaussian Quantum Dot*.
16. Kwaśniowski, A., Adamowski, J. — study of exchange interaction for electrons in coupled quantum dots via configuration-interaction with various confinement profiles.
17. Ciurla, M., et al. — power-exponential (PE) confinement potentials generalizing Gaussian/parabolic/rectangular limits.
18. (GaAs finite-temperature study) — *Effect of Confinement Potential Shape on the Electronic, Thermodynamic, Magnetic and Transport Properties of a GaAs Quantum Dot at Finite Temperature*, Scientific Reports (2019).
19. (Density-functional study) — *Structure and Information Measures of Few-Electron Systems Under a Spherically Symmetric Gaussian Potential within a Density Functional Approach*, arXiv (2606.23538).
20. (Double-QD informational study) — *Informational Analysis of the Confinement of an Electron in an Asymmetric Double Quantum Dot*, arXiv:2410.22538.

### Quantum Chemistry / Gaussian Basis Sets
21. Fournier, R., et al. — *Atomic Basis Functions for Molecular Electronic Structure Calculations*, arXiv:1808.05454.
22. (JCTC study) — *Gaussian Basis Sets for All-Electron Excited-State Calculations of Large Molecules*, J. Chem. Theory Comput.
23. Yang, C., et al. — *Numerical Analysis of Gaussian Approximations in Quantum Chemistry* (TU Berlin preprint / DFG-SPP1324 preprint 128).
24. Beylkin, G., Fann, G., Harrison, R. J., et al. — *Adaptive Algorithm for Electronic Structure Calculations Using Reduction of Gaussian Mixtures*, arXiv:1812.09284.
25. Dalery, M., Dusson, G., Ehrlacher, V., Lozinski, A. — *Nonlinear Reduced Basis Using Mixture Wasserstein Barycenters: Application to an Eigenvalue Problem Inspired from Quantum Chemistry*, arXiv:2307.15423.
26. (DG basis study) — *Fast Adaptive Discontinuous Basis Sets for Electronic Structure*, arXiv:2510.21213.
27. Yserentant, H., et al. — *Electronic State Calculation of Hydrogen in Metal Clusters Based on Gaussian–FEM Mixed Basis Function*, ScienceDirect / computational physics.
28. Degani, I. — *Observations on Gaussian Bases for Schrödinger's Equation*, arXiv:0707.4587.

### PT-Symmetric / Non-Hermitian Optics
29. Hu, S., Ma, X., Lu, D., Yang, Z., Zheng, Y., Hu, W. — *Solitons Supported by Complex PT-Symmetric Gaussian Potentials*, arXiv:1107.0809.
30. (Cubic–quintic soliton study) — *Optical Solitons in PT-Symmetric Potentials with Competing Cubic–Quintic Nonlinearity: Existence, Stability, and Dynamics*, arXiv:1804.02629.
31. (Gaussian PT soliton study) — *Analytical Stable Gaussian Soliton Supported by a Parity-Time-Symmetric Potential with Power-Law Nonlinearity*, arXiv:1404.7322.
32. Ruter, C. E., Makris, K. G., El-Ganainy, R., Christodoulides, D. N., Segev, M., Kip, D. — *Observation of Parity-Time Symmetry in Optics*, Nat. Phys. 6, 192 (2010).
33. Guo, A., et al. — *Observation of PT-Symmetry Breaking in Complex Optical Potentials*, Phys. Rev. Lett. 103, 093902 (2009).
34. El-Ganainy, R., Makris, K. G., Khajavikhan, M., Musslimani, Z. H., Rotter, S., Christodoulides, D. N. — *Parity-Time Symmetry Meets Photonics: A New Twist in Non-Hermitian Optics*, review (arXiv:1802.05025).
35. (2D PT crystal study) — *Demonstration of a Two-Dimensional PT-Symmetric Crystal: Bulk Dynamics, Topology, and Edge States*, arXiv:1809.00041.
36. (2D PT soliton study) — *2D Solitons in PT-Symmetric Photonic Lattices*, arXiv:1905.02909.
37. (Sensor application) — *Deep Learning in PT-Symmetric Multimode Waveguide Sensors*, APL Photonics.

### Cold Atoms / q-Gaussian and Information-Theoretic Studies
38. (q-Gaussian ground-state study) — *Quantum Potentials with q-Gaussian Ground States*, arXiv:1011.3459.

---

## 6. Concluding Remarks

The Gaussian potential occupies a distinctive niche in mathematical and applied quantum physics: it is realistic enough to model genuine short-range interactions (nuclear forces, nanostructure confinement, optical refractive-index profiles) yet mathematically resistant enough to have driven the development and validation of numerous semi-analytical and numerical eigenvalue techniques (AIM, ATEM, hypervirial-Padé, Nikiforov–Uvarov, adaptive Gaussian-basis methods). Its eigenfunctions, whether interpreted as bound-state wavefunctions, molecular-orbital basis functions, or optical guided modes, underpin quantitative predictions across nuclear physics, condensed-matter/nanostructure physics, quantum chemistry, molecular spectroscopy, and non-Hermitian photonics — a breadth of application matched by relatively few other model potentials in quantum theory.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Gaussian potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
