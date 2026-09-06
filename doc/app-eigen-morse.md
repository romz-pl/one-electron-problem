# Applications of Eigenvalues and Eigenfunctions of the Morse Potential

## 1. Background

The Morse potential,

$$V(r) = D_e\left(1 - e^{-a(r-r_e)}\right)^2 - D_e ,$$

was introduced by Philip M. Morse in 1929 as a solvable anharmonic model for the vibrational motion of a diatomic molecule. Unlike the harmonic oscillator, it has a finite dissociation energy $D_e$, correctly reproduces the merging of bound states into a continuum, and yields a *closed-form* solution of the Schrödinger equation. Its discrete eigenvalues,

$$E_n = \hbar\omega_0\left(n+\tfrac{1}{2}\right) - \hbar\omega_0 x_e\left(n+\tfrac{1}{2}\right)^2 ,$$

and eigenfunctions, expressible in terms of generalized Laguerre polynomials (equivalently confluent hypergeometric functions) in the variable $z = \frac{2D_e}{a}e^{-a(r-r_e)}$, form one of the very small set of exactly solvable, physically realistic potentials in quantum mechanics — alongside the harmonic oscillator, the hydrogen atom, and the Pöschl–Teller potential. This exact solvability, combined with the model's qualitative realism, is why the Morse eigenproblem keeps reappearing across physics, chemistry, biology, mathematical finance, and quantum information science. The sections below survey the major application areas.

---

## 2. Molecular Spectroscopy and Diatomic/Polyatomic Vibrational Structure

This is the original and most direct application. The Morse eigenvalues reproduce the observed **anharmonic vibrational term structure** of diatomic molecules — the characteristic crowding of vibrational levels as $n$ increases, culminating at the dissociation limit — far better than the harmonic oscillator. Consequences and extensions include:

- **Vibration–rotation (ro-vibrational) spectra**: adding a centrifugal term $\ell(\ell+1)\hbar^2/2\mu r^2$ to the Morse potential and solving approximately (Pekeris approximation, Nikiforov–Uvarov method, supersymmetric quantum mechanics, asymptotic iteration method) gives closed-form ro-vibrational energy formulas fitted to spectroscopic constants ($D_e$, $a$, $r_e$) for real diatomics (CO, NO, HCl, LiH, I₂, N₂, etc.).
- **Morse eigenfunctions as a variational/expansion basis**: because they already encode anharmonicity, Morse eigenfunctions converge faster than harmonic-oscillator basis functions when used as a basis set for variationally computing bound vibrational–rotational states of polyatomic molecules (H₂O, NH₃, SO₂, etc.), including **local-mode** descriptions of bond-stretching overtones in hydrides.
- **Generalized/deformed Morse potentials**: q-deformed, PT-symmetric/non-Hermitian, complex, and position-dependent-mass variants extend the eigenvalue problem to open quantum systems, negative/complex effective mass carriers, and exotic molecular/solid-state contexts, while still building on the same underlying eigenfunction machinery.

## 3. Statistical Mechanics and Thermodynamic Properties

The discrete Morse spectrum feeds directly into the **vibrational partition function** $Z_{vib}=\sum_n e^{-\beta E_n}$, from which essentially all bulk thermodynamic quantities of a gas of anharmonic oscillators follow:

- Closed-form and asymptotic (Poisson summation, Euler–Maclaurin, cumulant expansion) evaluations of $Z_{vib}$ for Morse and Morse-related (Rosen–Morse, Deng–Fan, Tietz, Manning–Rosen) oscillators.
- Derived quantities: vibrational mean energy, Helmholtz free energy, entropy, and heat capacity as functions of temperature, benchmarked against real diatomics (Na₂, N₂, CO, HCl, Li₂, H₂ isotopologues).
- High-temperature/non-equilibrium extensions relevant to **plasma physics, hypersonic flow chemistry (DSMC), and combustion/chemical-kinetics models**, where anharmonic vibrational excitation governs energy partitioning.
- Isotope-fractionation and gas-phase equilibrium-constant calculations that depend sensitively on the anharmonic (Morse) vibrational partition function rather than the harmonic approximation.

## 4. Quantum Information-Theoretic Measures

The explicit Morse eigenfunctions allow analytic or high-precision numerical evaluation of information-theoretic quantities associated with each bound state, used to probe localization/delocalization and uncertainty:

- **Shannon (information) entropy** in position and momentum space, and entropic uncertainty relations (Bialynicki-Birula–Mycielski inequality) for Morse eigenstates.
- **Fisher information** and Fisher-based (Stam–Cramér–Rao) uncertainty relations, showing qualitatively different (non-monotonic) behavior with quantum number compared with the harmonic oscillator, a direct signature of anharmonicity.
- **Complexity measures** (Fisher–Shannon product, Onicescu/Rényi/Tsallis-type quantities, statistical complexity) computed from Morse (and generalized/double-Morse) eigenfunctions, used to quantify the "order" or structural complexity of molecular quantum states.
- These measures have been extended to q-deformed, complex-mass, and double-well (double-Morse) variants of the potential.

## 5. Algebraic Structure, Coherent States, and Quantum Optics

The ladder-operator/algebraic structure underlying the Morse eigenvalue problem (an su(2)-, SU(1,1)/SO(2,1)-, or q-boson-type spectrum-generating algebra, since the spectrum is finite and non-equidistant) supports:

- Construction of **coherent states** (Perelomov/Klauder-type, Gaussian, generalized su(2)-like) for the Morse oscillator, generalizing Schrödinger/Glauber coherent states beyond the harmonic case.
- **Statistical/quantum-optical properties** of these states (Q- and P-distributions, squeezing, minimum-uncertainty behavior, thermal expectation values for a canonical ensemble of Morse oscillators) — relevant to modeling vibrational wave packets and their quantum-optical analogues.
- **Path-integral solutions** of the Morse propagator (Duru's solution and extensions), including PT-symmetric and non-Hermitian generalizations, connecting the eigenvalue problem to quantization via holomorphic/parametric-time coordinates.
- Time-dependent and Feinberg–Horodecki (space-like) extensions of Morse coherent states, linked to **crystallization fronts and Gompertzian growth laws**.

## 6. Condensed Matter, Lattice Dynamics, and Materials Science

- The Morse potential is a standard **interatomic pair potential** for modeling anharmonic lattice vibrations, phonon dispersion, thermal expansion, and nonlinear lattice dynamics in crystals and metals.
- Used to parametrize **interatomic forces** in molecular-dynamics simulations of solids, surfaces, and nanostructures, and to model **Rydberg-molecule** interactions.
- Employed in comparative studies against the Lennard-Jones potential for describing metal-atom (metallic bonding) systems, including complex-eigenvalue extensions for resonance/decay phenomena.

## 7. Biophysics: DNA Denaturation and Cytoskeletal Dynamics

- **Peyrard–Bishop (and Peyrard–Bishop–Dauxois) model of DNA**: each base pair's transverse stretching coordinate is bound by a Morse potential (representing hydrogen bonding), with neighboring base pairs harmonically or anharmonically coupled along the strand. The Morse eigenvalue/transfer-integral spectrum governs the **thermal denaturation (melting) transition**, heat-capacity peaks, and the formation of localized "bubbles" of open base pairs — reproducing experimental DNA melting curves.
- **Microtubule dynamics**: nonlinear models of microtubule protofilaments use Morse potentials to represent lateral/longitudinal bonds between tubulin dimers, supporting soliton/kink excitations relevant to intracellular signal transmission and mechanical (nanoindentation) properties.
- Related nonlinear helicoidal DNA models and ionic-wave propagation models along microtubules build on the same Morse-based bonding picture.

## 8. Nuclear Physics

- The Morse potential (and Morse-type radial potentials) has been used as an effective **nucleon–nucleon or cluster–cluster interaction model**, providing a tractable, exactly solvable benchmark for bound-state and scattering calculations in simplified nuclear structure models.

## 9. Mathematical Finance

- The completeness relation for Morse eigenfunctions (discrete + continuum spectrum), established rigorously via Titchmarsh contour-integral methods, has been mapped onto the **pricing of Asian options**: the spectral decomposition of the Morse Hamiltonian provides the Green's function used to solve the relevant partial differential equation for path-dependent option prices, illustrating an unexpected bridge between exactly-solvable quantum mechanics and quantitative finance.

## 10. Mathematical Physics: Exact Solvability and Methodological Testbed

Beyond direct physical application, the Morse eigenvalue problem is one of the standard **testbeds for new approximation and solution techniques** in quantum mechanics, precisely because the exact answer is known for comparison:

- Nikiforov–Uvarov method, asymptotic iteration method, supersymmetric quantum mechanics (SUSY QM) and shape-invariance, variational methods, factorization/ladder-operator methods, and Dunkl-operator (reflection-symmetry) formalisms have all been benchmarked on the Morse potential (with and without centrifugal/rotational terms).
- Serves as a template for constructing and solving **generalized/hybrid Morse-like potentials** (Deng–Fan, Rosen–Morse, Manning–Rosen, Tietz, Kratzer-Morse hybrids, screened Morse, etc.) that better capture long-range (van der Waals/Coulombic) behavior while retaining exact or quasi-exact solvability.

---

## 11. Summary Table

| Domain | Role of Morse eigenvalues/eigenfunctions |
|---|---|
| Molecular spectroscopy | Anharmonic vibrational/ro-vibrational term values; variational basis set |
| Statistical mechanics | Vibrational partition function → thermodynamic functions |
| Quantum information theory | Shannon entropy, Fisher information, complexity measures |
| Algebra / quantum optics | Coherent states, ladder operators, path integrals |
| Condensed matter | Lattice dynamics, phonons, interatomic potentials |
| Biophysics | DNA denaturation (Peyrard–Bishop), microtubule solitons |
| Nuclear physics | Effective nucleon/cluster interaction model |
| Mathematical finance | Asian option pricing via spectral (Green's function) methods |
| Mathematical physics | Benchmark for new approximate solution methods |

---

## 12. Related Publications

**Foundational**
1. P. M. Morse, "Diatomic Molecules According to the Wave Mechanics. II. Vibrational Levels," *Physical Review* **34**, 57 (1929).

**Molecular spectroscopy / variational basis**
2. J. P. Dahl, M. Springborg, "The Morse Oscillator in Position Space, Momentum Space, and Phase Space," *J. Chem. Phys.* **88**, 4535 (1988).
3. M. L. Sage, "Morse oscillator transition probabilities for molecular bond modes," *Chem. Phys.* **35**, 375 (1978).
4. "On the use of Morse eigenfunctions for the variational calculation of bound states of diatomic molecules," *Spectrochimica Acta Part A* / related J. Mol. Spectrosc. literature.
5. Bond-stretching local-mode studies of H₂O, NH₃, SO₂ (coupled Morse oscillator models), *J. Mol. Spectrosc.*
6. C. A. Onate, "Analytical approximations to the eigenvalues of the Morse potential with centrifugal terms" (Nikiforov–Uvarov method), *Pramana*.
7. "Morse potential energy spectra through the variational method and supersymmetry," arXiv:hep-th/9910254.
8. "A Comparative Investigation of Complex Conjugate Eigenvalues of Generalized Morse and Classical Lennard-Jones Potential for Metal Atoms."

**Thermodynamics / partition functions**
9. "On the partition function of Morse oscillators," *Chemical Physics Letters* (cumulant approach), ScienceDirect.
10. "A New Approach to the Exact and Approximate Anharmonic Vibrational Partition Function of Diatomic and Polyatomic Molecules Utilizing Morse and Rosen–Morse Oscillators."
11. "Thermal properties of three-dimensional Morse potential for some diatomic molecules via Euler–Maclaurin approximation," *Rev. Mex. Fís.* (SciELO).
12. "The statistical properties of q-deformed Morse potential for some diatomic molecules," arXiv:1711.04358.
13. "High-Temperature and Nonequilibrium Partition Function and Thermodynamic Data of Diatomic Molecules."
14. "Partition functions I. Improved partition functions and thermodynamic quantities for normal, equilibrium, and ortho/para molecular hydrogen," *Astronomy & Astrophysics*.

**Quantum information measures**
15. "Fisher Information for the Morse Oscillator," *Results in Physics* (ScienceDirect).
16. "Quantum information entropies of the eigenstates of the Morse potential," arXiv:quant-ph/0602203.
17. "Fisher Information and Complexity Measure of Generalized Morse Potential Model," C. A. Onate, J. O. A. Idiodi.
18. "Position- and Momentum-Space Quantum Information Measures of the Double-Morse Oscillator," arXiv:2608.25953.
19. "Quantum information measurements of the exact solution of the Schrödinger equation for a q-deformed Morse potential," *J. Comput. Electron.* (Springer).
20. "Quantum Information Measures in Quartic and Symmetric Potentials," arXiv:2308.07353.

**Coherent states / algebraic methods / quantum optics**
21. M. M. Nieto, L. M. Simmons, "Eigenstates, coherent states, and uncertainty products for the Morse oscillator," *Phys. Rev. A* **19**, 438 (1979).
22. C. C. Gerry, "Coherent states and a path integral for the Morse oscillator," *Phys. Rev. A* **33**, 2207 (1986).
23. M. Daoud, D. Popov, "Statistical properties of Klauder-Perelomov coherent states for the Morse potential," arXiv:math-ph/0409054.
24. "Construction of coherent states for Morse potential: A su(2)-like approach," arXiv:2005.04302.
25. "Generalised and Gaussian coherent states for the Morse potential."
26. "Coherent states of the two-dimensional non-separable supersymmetric Morse potential," arXiv:2108.13543.
27. "Coherent States for PT-/Non-PT-Symmetric and Non-Hermitian Morse Potential via Path Integral Method," arXiv:1003.2264.
28. I. L. Cooper, R. K. Gupta, "q-deformed Morse oscillator," *Phys. Rev. A* **52**, 941 (1995).

**Condensed matter / nuclear physics / methodology**
29. "Spectral and Thermal Analysis of the Morse Potential within the Dunkl Formalism: Analytical Approximations and Applications," arXiv:2506.00877.
30. J. M. Maruhn et al., *Nuclear Models* (Springer, 1995) — effective interaction context.
31. "Application of exact solution of complex morse potential to investigate physical systems with complex and negative masses," *J. Phys. Commun.* (IOPscience).
32. "Exact solution of Schrödinger equation for the complex Morse potential [position-dependent mass]," arXiv:2507.04658.

**Biophysics**
33. M. Peyrard, A. R. Bishop, "Statistical Mechanics of a Nonlinear Model for DNA Denaturation," *Phys. Rev. Lett.* **62**, 2755 (1989).
34. T. Dauxois, M. Peyrard, A. R. Bishop, "Entropy-driven DNA denaturation," *Phys. Rev. E* **47**, R44 (1993).
35. M. Peyrard, "Nonlinear dynamics and statistical physics of DNA," *Nonlinearity* **17**, R1 (2004).
36. "The thermal denaturation of the Peyrard–Bishop model with an external potential," *Phys. Scr.* **86**, 015802 (2012).
37. "The direct investigation of DNA denaturation in Peyrard-Bishop-Dauxois model by molecular dynamics method," ScienceDirect.
38. "Modelling Disorder: the Cases of Wetting and DNA Denaturation," arXiv:cond-mat/0511532.
39. "Phase transitions in homogeneous biopolymers: basic concepts and methods," arXiv:cond-mat/0210188.
40. "Models of DNA denaturation dynamics: universal properties," arXiv:1402.6492.
41. S. Zdravković, A. N. Bugay, A. Y. Parkhomenko, "Application of Morse potential in nonlinear dynamics of microtubules," *Nonlinear Dynamics* **90**, 2841 (2017).
42. O. Kononova et al., "Tubulin Bond Energies and Microtubule Biomechanics Determined from Nanoindentation in Silico," *J. Am. Chem. Soc.* **136**, 17036 (2014).
43. M. V. Satarić, D. I. Ilić, N. Ralević et al., "A nonlinear model of ionic wave propagation along microtubules," *Eur. Biophys. J.* **38**, 637 (2009).

**Mathematical finance**
44. P. Zhang, "Morse Potential, Contour Integrals, and Asian Options," arXiv:1010.3820.

**Related/hybrid potential extensions (methodological benchmarking)**
45. "Theoretic quantum information entropies for the generalized hyperbolic potential."
46. A. Mkolesia, S. Surulere, A. A. Adeniji, "The Integral-differential and Integral Approach for the Exact Solution of the Hybrid Functional Forms for Morse Potential," *International Journal of Applied Mathematics – IAENG* (2020).
47. "Thermodynamic properties of diatomic molecule systems under SO(2,1)-anharmonic Eckart potential."

---

*Note: Several entries above are drawn from review articles, arXiv preprints, and secondary citations; where a full bibliographic record (volume/page) was not confirmed in the available sources, the article title and venue are given as located. Readers should verify exact citation details before formal use.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Morse potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
