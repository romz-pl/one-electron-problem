# Applications of Eigenvalues and Eigenfunctions of the Woods–Saxon Potential: A Review

## 1. Introduction

The Woods–Saxon (WS) potential, introduced by Woods and Saxon in 1954, is defined as

$$V(r) = -\frac{V_0}{1 + \exp\left(\dfrac{r - R_0}{a}\right)}$$

where $V_0$ is the well depth, $R_0$ the effective nuclear (or system) radius, and $a$ the surface diffuseness parameter. Its smooth, rounded-square-well shape interpolates between an infinite square well (small $a$) and a soft, harmonic-oscillator-like profile (large $a$), making it a far more realistic representation of finite, diffuse-edged confining systems than either extreme.

A central mathematical difficulty is that the radial Schrödinger, Klein–Gordon, and Dirac equations with the WS potential are **not exactly solvable in closed form** for arbitrary orbital angular momentum $\ell$ (this has been explicitly demonstrated and remains a point of ongoing discussion in the literature). Exact solutions exist only for $s$-states ($\ell = 0$) in restricted cases; for $\ell \neq 0$, the centrifugal term must be treated approximately (commonly via the **Pekeris approximation**), after which the equation can be mapped onto solvable forms (hypergeometric, Jacobi, or Romanovski polynomials) using techniques such as the **Nikiforov–Uvarov (NU) method**, the **asymptotic iteration method (AIM)**, **supersymmetric quantum mechanics (SUSYQM)**, the **new improved quantization rule**, or direct **numerical (Numerov/matrix) diagonalization**. The resulting eigenvalues and eigenfunctions underpin a wide variety of applications across nuclear, atomic, molecular, and condensed-matter physics. This review surveys those applications.

---

## 2. Nuclear Structure and the Shell Model

### 2.1 Single-particle energy levels and magic numbers
The WS potential is the standard mean-field potential of the **independent-particle nuclear shell model**. Its flat interior and diffuse surface (unlike the harmonic oscillator's everywhere-curved shape or the square well's sharp edge) reproduce the correct level ordering and, once a strong surface-peaked **spin–orbit term** is added, correctly predict the empirical nuclear **magic numbers** (2, 8, 20, 28, 50, 82, 126). The finite depth of the well also produces realistic **level compression** near the continuum threshold and exponentially decaying (rather than Gaussian-decaying) asymptotic wave functions — both essential for quantitative nuclear spectroscopy.

### 2.2 Parameterization and systematic shell-model calculations
Numerous groups have derived global parameterizations of $V_0$, $R_0$, $a$, and the spin–orbit strength as functions of mass number $A$ and isospin asymmetry $(N-Z)/A$ (e.g., the "Seminole" parameterization), enabling systematic prediction of single-particle binding energies across the nuclear chart, from light nuclei ($^{18}$O, $^{42}$Ca) to doubly magic systems ($^{56}$Ni) and heavy nuclei.

### 2.3 Deformed and two-center Woods–Saxon models
Extending the spherical WS potential to **deformed** and **two-center** geometries allows treatment of strongly deformed nuclei, fission pathways, cluster/alpha decay, and the formation of superheavy elements. Codes such as the two-center shell model with spherical/deformed WS potentials compute shell and pairing corrections (Strutinsky method) used in fission-barrier and potential-energy-surface calculations.

### 2.4 Bohr Hamiltonian and the nuclear collective model
Approximate analytical solutions of the WS potential have been used as the $\beta$-potential in the **5-dimensional Bohr (Bohr–Mottelson) Hamiltonian**, describing collective quadrupole vibrational and rotational excitations, $\gamma$-unstable and $\gamma \approx 0$ rotational nuclei, critical-point symmetries (X(5), E(5), Z(5)), and — in extended treatments — **minimal-length (generalized uncertainty principle) corrections** and associated thermodynamic properties. Comparisons across many deformed nuclei have mapped out the regimes where the WS-based collective model succeeds or fails.

### 2.5 Alpha decay and cluster radioactivity
The WS potential (alone, folded, or combined with a Coulomb tail) is widely used to construct the **alpha–daughter nucleus interaction potential** for WKB or S-matrix pole calculations of alpha-decay half-lives and widths, including temperature-dependent formulations, folded WS cluster potentials for light and superheavy nuclei, and hybrid Woods–Saxon–Gaussian potentials that reproduce level schemes and electromagnetic transition rates of alpha-cluster structures (e.g., $^{212}$Po $= {}^{208}$Pb $+ \alpha$).

### 2.6 Diatomic-like nuclear/molecular expectation values
Nikiforov–Uvarov solutions of WS-type potentials are also used (via the Hellmann–Feynman theorem) to compute expectation values such as $\langle r^{-2}\rangle$, $\langle T \rangle$, and $\langle p^2\rangle$ for bound systems, connecting nuclear-type potential methods to diatomic molecular spectroscopy.

---

## 3. Relativistic Quantum Mechanics

### 3.1 Klein–Gordon equation
The radial Klein–Gordon equation with scalar and/or vector WS potentials has been solved (approximately, via NU/Pekeris methods, for arbitrary $\ell$; exactly for $s$-waves) to obtain relativistic energy spectra and eigenfunctions, including versions with **position-dependent mass**, **PT-symmetric** generalized WS potentials, and combined Woods–Saxon-plus-Mie-type potentials — relevant to relativistic treatments of mesons and other spin-0 particles in nuclear-type mean fields.

### 3.2 Dirac equation
Bound-state solutions of the Dirac equation with WS potentials (including **ring-shaped** and **$q$-deformed** generalizations) have been obtained for arbitrary $\ell$-states, often exploiting **spin symmetry** and **pseudospin symmetry**, which are important for understanding superdeformation and identical bands in nuclei.

### 3.3 PT- and non-Hermitian quantum mechanics
The WS potential is a standard testbed in **PT-symmetric quantum mechanics**: both PT-symmetric and non-PT-symmetric (complex) generalized WS potentials have been solved via the NU method, showing that the PT-symmetric version yields a real spectrum while the non-Hermitian version generally produces complex-conjugate eigenvalue pairs. This work links WS applications to broader studies of non-Hermitian Hamiltonians, complex absorbing potentials, and resonance phenomena.

---

## 4. Semiconductor Nanostructures and Condensed Matter Physics

### 4.1 Quantum dots, quantum wells, and quantum rings
Because it provides a smooth, physically realistic confinement profile (rather than an artificial infinite or abrupt finite well), the WS potential is used to model **spatial confinement in quantum dots, quantum wells, and quantum rings**, giving good agreement with the true carrier-confinement profile at semiconductor heterojunction interfaces (e.g., InAs/GaAs quantum dots with a wetting layer).

### 4.2 Linear and nonlinear optical properties
WS-confined electron/exciton/impurity systems are used to compute:
- Linear and third-order nonlinear **optical absorption coefficients** and **refractive index changes**;
- **Optical rectification, second-harmonic generation (SHG), and third-harmonic generation (THG)**;
- Effects of applied **electric fields, magnetic fields, intense/terahertz laser fields, hydrostatic pressure**, and **donor/acceptor impurities** on these properties;
- **Core/shell quantum dots** (e.g., CdSe/ZnS) where a radial WS potential captures continuous material transition and interface effects, tuning nonlinear responses for photonic and optoelectronic device applications;
- Hybrid systems combining WS quantum wells with **metal nanoparticles**, where localized surface plasmon effects modify absorption and refraction spectra.

### 4.3 Excitons and impurity states
Exact diagonalization and variational studies of excitons and shallow donor impurities confined by WS potentials in 2D quantum dots provide binding energies and optical transition spectra relevant to infrared and two-photon spectroscopy.

### 4.4 Comparative confinement-potential studies
The WS potential is frequently benchmarked against other finite-range model potentials (Pöschl–Teller, Razavy, Gaussian, etc.) to assess which best reproduces experimentally observed confinement and optical tunability in nanostructures under external perturbations such as pressure and fields.

---

## 5. Atomic Clusters and Mesoscopic Systems

The WS potential, originally a nuclear mean-field model, has been successfully repurposed to describe the electronic **shell structure of metallic clusters** (alkali-metal clusters, etc.), reproducing abundance variations in mass spectra, ionization potentials, static polarizabilities, and collective giant dipole resonances. Deformed WS and modified Nilsson-type potentials are compared in this context, including studies of the **classical chaos** underlying the corresponding quantal shell structure as a function of deformation.

---

## 6. Mathematical/Methodological Applications

Beyond direct physical applications, the WS potential serves as a major **testbed for approximate analytical methods** in quantum mechanics, driving methodological development in:
- The **Nikiforov–Uvarov method** and its parametric generalizations;
- The **asymptotic iteration method (AIM)**;
- **Supersymmetric quantum mechanics (SUSYQM)** and shape-invariance/Hamiltonian-hierarchy techniques;
- The **Pekeris approximation** for the centrifugal term and its accuracy assessment across $\ell$-states and dimensions $D$;
- The **new improved quantization rule** and studies of interdimensional degeneracies;
- Numerical approaches such as the **matrix Numerov method** (including implementations in spreadsheet/worksheet environments for pedagogical use) and the **Gamow code** for continuum/resonance states.

These methodological studies are frequently validated against the well-known nuclear shell-model benchmarks (e.g., neutron single-particle levels in $^{56}$Fe) described in Section 2.

---

## 7. Summary Table

| Application Domain | Typical Use of Eigenvalues/Eigenfunctions | Representative Method(s) |
|---|---|---|
| Nuclear shell model | Single-particle levels, magic numbers | Numerov, WS parameterizations |
| Deformed/two-center nuclei, fission | Shell & pairing corrections, potential energy surfaces | Strutinsky method |
| Bohr Hamiltonian / collective model | Collective vibrational-rotational spectra | NU, AIM, SUSYQM |
| Alpha/cluster decay | Half-lives, decay widths | WKB, S-matrix poles, folded WS |
| Relativistic wave equations | Klein–Gordon/Dirac spectra, spin/pseudospin symmetry | NU + Pekeris approximation |
| PT-symmetric QM | Real vs. complex spectra of non-Hermitian Hamiltonians | NU method |
| Semiconductor nanostructures | Confinement energies, optical coefficients (SHG/THG/OR) | Effective-mass approximation, density matrix formalism |
| Metallic/atomic clusters | Electronic shell structure, polarizabilities | Modified Nilsson/WS comparison |
| Numerical/analytical methods | Benchmark solvable/quasi-solvable models | NU, AIM, SUSYQM, matrix Numerov |

---

## 8. List of Related Publications

**Foundational**

1. R. D. Woods, D. S. Saxon, "Diffuse Surface Optical Model for Nucleon-Nuclei Scattering," *Phys. Rev.* **95**, 577 (1954).

**Nuclear shell model, parameterization, and structure**

2. "Parameterization of the Woods-Saxon Potential for Shell-Model Calculations," *arXiv:0709.3525*.
3. "Shell-model calculations with Woods-Saxon wave functions in $^{18}$O and $^{42}$Ca," *Nucl. Phys. A* (ScienceDirect, 1969).
4. "Numerical Simulation of Shell Model Single Particle Energy States using Matrix Numerov Method in Gnumeric Worksheet," *arXiv:2205.10335*.
5. "Nuclear shell structure of oxygen isotopes using a hybrid Woods-Saxon-Gaussian potential," *ScienceDirect* (2026).
6. "Structure of Heavy Nuclei Based on Nucleon Quartets," *arXiv:2306.11996*.
7. "Energy partition in low energy fission," *arXiv:1102.2733*.
8. "OWL: A code for the two-center shell model with spherical Woods-Saxon potentials," (Science.gov topic collection).

**Bohr Hamiltonian / collective model**

9. M. Çapak, D. Petrellis, B. Gönül, D. Bonatsos, "Analytical solutions for the Bohr Hamiltonian with the Woods-Saxon potential," *J. Phys. G: Nucl. Part. Phys.* **42**, 095102 (2015).
10. M. Çapak, B. Gönül, "Remarks on the Woods-Saxon Potential," *arXiv:1607.02742*.
11. "Study of Bohr Mottelson Hamiltonian with minimal length effect for Woods-Saxon potential and its thermodynamic properties," *PMC8113724* / ScienceDirect (2021).
12. "Excited collective states of nuclei within Bohr Hamiltonian with Tietz-Hua potential," *arXiv:1608.08674* (cites related WS-Bohr-Hamiltonian work).

**Alpha decay / cluster radioactivity**

13. S. S. Hosseini, H. Hassanabadi, D. T. Akrawy et al., "Alpha-decay half-lives for isotopes of even-even nuclei: A temperature-dependent approach with Woods-Saxon potential," *Eur. Phys. J. Plus* **133**, 7 (2018).
14. "Microscopic calculation of α-decay half-lives with a deformed potential," *ResearchGate*.
15. "Alpha-decay quantum-tunnelling calculations based on a folded Woods-Saxon potential," (IOPscience).
16. "A potential model for alpha decay," *Am. J. Phys.* **78**, 949 (2010).
17. "An estimate of Alpha decay half-life from the poles of S-matrix of an exactly solvable potential," *arXiv:1612.04135*.
18. "Diffuseness parameter as a bottleneck for accurate half-life calculations," *arXiv:2101.07102*.
19. Dong Bai, Zhongzhou Ren, "Woods-Saxon-Gaussian Potential and Alpha-Cluster Structures of Alpha+Closed Shell Nuclei," *arXiv:1808.10234*.

**Non-relativistic bound states / general solvability**

20. C. Berkdemir et al., "Any $\ell$-state solutions of the Woods-Saxon potential in arbitrary dimensions within the new improved quantization rule," *arXiv:1009.5083*.
21. "Analytical solutions of the D-dimensional Schrödinger equation with the Woods-Saxon potential for arbitrary $\ell$ state," *arXiv:1111.4734*.

**Relativistic (Klein–Gordon, Dirac) and PT-symmetric studies**

22. C. Berkdemir, A. Berkdemir, R. Sever, "Eigenvalues and Eigenfunctions of Woods-Saxon Potential in PT-Symmetric Quantum Mechanics," *Mod. Phys. Lett. A* **21**, 2087 (2006); *arXiv:quant-ph/0410153*.
23. A. Arda, R. Sever, "Bound States of the Klein-Gordon Equation for Woods-Saxon Potential With Position Dependent Mass," *arXiv:0712.4192*.
24. C. Berkdemir et al., "Exact Solution of the Klein-Gordon Equation for the PT-Symmetric Generalized Woods-Saxon Potential by the Nikiforov-Uvarov Method," *arXiv:quant-ph/0610183*.
25. "Any $\ell$-state analytical solutions of the Klein-Gordon equation for the Woods-Saxon potential," *arXiv:0912.3890*.
26. "Bound states for Dirac equation with Wood-Saxon potential," *ResearchGate*.
27. "Dirac bound state solutions of spherically ring-shaped q-deformed Woods-Saxon potential for any L-state," *arXiv:1308.0005*.
28. "Bound-state solutions of the Klein-Gordon equation for the generalized PT-symmetric Hulthén potential" (comparative reference to WS), *arXiv:quant-ph/0609231*.

**Semiconductor nanostructures / optical properties**

29. "The effects of intense laser on nonlinear properties of shallow donor impurities in quantum dots with the Woods-Saxon potential," *ScienceDirect* (2011).
30. "Nonlinear optical properties of a Woods-Saxon quantum dot under an electric field," *Physica E* (2013).
31. "Impurity-assisted tuning of nonlinear optical responses in core/shell quantum dots with Woods-Saxon confinement," *ScienceDirect* (2026).
32. "A study of an exciton in a quantum dot with Woods-Saxon potential," *ScienceDirect* (2009).
33. "Tunable quantum confinement under hydrostatic pressure: Exploring electronic and optical outputs in Pöschl-Teller, Razavy and Woods-Saxon potentials," *ScienceDirect* (2025).
34. "The effect of Woods-Saxon potential on envelope function, intersubband dispersion curves and group velocity of InAs/GaAs quantum dots with wetting layer," *ScienceDirect* (2014).
35. "Nonlinear optical properties in a hybrid system composed of metal nanoparticles and Woods-Saxon quantum wells," *Eur. Phys. J. Plus* (2022).

**Metallic clusters and mesoscopic shell structure**

36. "Shell Structures and Chaos in Deformed Nuclei and Large Metallic Clusters," *arXiv:nucl-th/9409025*.
37. "References" (metallic cluster shell-structure review comparing deformed WS and modified Nilsson models), *arXiv:cond-mat/9408006*.

---

*Note: Several ResearchGate/Academia.edu-hosted items above are secondary hosting of published journal articles; where available, the original journal citation is preferred for formal referencing.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Woods–Saxon potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
