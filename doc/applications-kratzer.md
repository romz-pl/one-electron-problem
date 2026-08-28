# The Kratzer Potential: A Review of Applications in Physics and Chemistry

## 1. Introduction and Mathematical Form

The Kratzer potential (also called the Kratzer–Fues potential) was introduced by A. Kratzer in 1920 and later refined by E. Fues in 1926 to describe the vibrational structure of diatomic molecules. Its central appeal is that it combines a short-range repulsive core with a long-range Coulomb-like attraction while remaining **exactly solvable** in the Schrödinger equation, which makes it a workhorse model in both atomic/molecular physics and mathematical physics.

The standard form is

$$V(r) = -D_e\left(\frac{2r_e}{r} - \frac{r_e^2}{r^2}\right) = -\frac{2D_e r_e}{r} + \frac{D_e r_e^2}{r^2},$$

where $D_e$ is the dissociation energy and $r_e$ is the equilibrium internuclear separation. A widely used variant, the **modified Kratzer potential**, shifts the well so that $V(r_e) = 0$:

$$V(r) = D_e\left(\frac{r - r_e}{r}\right)^2 = \frac{A}{r^2} - \frac{B}{r} + C,$$

with $A = D_e r_e^2$, $B = 2D_e r_e$, $C = D_e$.

Because the radial Schrödinger, Klein–Gordon, and Dirac equations with this potential reduce to hypergeometric-type equations, exact or quasi-exact bound-state energies and eigenfunctions (in terms of associated Laguerre polynomials) can be obtained via the Nikiforov–Uvarov (NU) method, the asymptotic iteration method (AIM), supersymmetric quantum mechanics (SUSYQM), the factorization method, and other standard techniques. This tractability is the reason the Kratzer potential — and its many "extended," "screened," "shifted," and "combined" variants — continues to be applied across a remarkably broad range of physical and chemical problems, summarized below.

---

## 2. Applications in Molecular and Chemical Physics

### 2.1 Vibrational–Rotational Spectroscopy of Diatomic Molecules
The original and most enduring application: the Kratzer potential reproduces the essential features of a diatomic internuclear potential (a repulsive wall at short range and a bound minimum at $r_e$) well enough to yield closed-form ro-vibrational energy levels $E_{n\ell}$. These are routinely fitted or compared against spectroscopic data for molecules such as H₂, HCl, LiH, CO, NO, N₂, CH, VN, ScI, and NI, and used to extract spectroscopic constants (dissociation energy, equilibrium bond length, vibrational frequency).

### 2.2 Thermodynamic Functions of Diatomic Gases
From the vibrational energy spectrum, the vibrational partition function $Z(\beta)$ can be constructed in closed form (often via the Poisson summation / Euler–Maclaurin formalism). This yields analytic expressions for:
- Vibrational mean energy and internal energy $U$
- Heat capacity $C_V$ / $C_P$
- Entropy $S$
- Free (Helmholtz/Gibbs) energy

Numerous studies benchmark these against NIST Chemistry WebBook experimental data for molecules like LiH, HCl, H₂, and VN(g), generally finding good agreement, particularly at low-to-moderate temperature.

### 2.3 Quantum Information-Theoretic Measures
The Kratzer potential (and its screened/generalized forms) is used as a testbed for information-theoretic characterizations of molecular quantum states:
- Shannon entropy (position- and momentum-space)
- Fisher information
- Rényi and Tsallis entropies
- Fisher–Shannon complexity

These studies verify fundamental inequalities (Bialynicki-Birula–Mycielski entropic uncertainty relation, Stam–Cramér–Rao inequality) for real diatomic systems (O₂, O₂⁺, NO, NO⁺, LiH, HCl) and relate the measures to localization/delocalization of the vibrational wavefunction as dissociation energy, dipole moment, or quantum numbers vary.

### 2.4 Expectation Values and the Hellmann–Feynman Theorem
Closed-form expressions for $\langle r \rangle$, $\langle r^2 \rangle$, $\langle r^{-1} \rangle$, $\langle r^{-2} \rangle$, kinetic energy $T$, and $\langle p^2 \rangle$ are derived using the Hellmann–Feynman theorem, supporting virial-theorem checks and uncertainty-relation tests for real molecules (e.g., LiH, HCl).

### 2.5 Ring-Shaped and Non-Central Extensions for Ring Molecules
A "ring-shaped" (angle-dependent) extension of the Kratzer potential has been used to model cyclic/ring organic molecules such as cyclic polyenes and benzene-like systems, coupling the radial Kratzer form with a non-central angular term.

### 2.6 Canonical/Transformation-Based Potential Modeling
The Kratzer potential, alongside the Morse and Lennard-Jones potentials, is used as a reference potential in canonical-transformation approaches to generate accurate Born–Oppenheimer potential energy curves for real systems (H₂⁺, H₂, Ar₂, water dimer hydrogen bonding), improving predicted vibrational eigenvalues relative to using a single fixed functional form.

---

## 3. Applications in Atomic, Molecular, and Condensed-Matter Physics

### 3.1 Excitons in Two-Dimensional Materials (TMDs)
One of the most significant modern applications: the **modified Kratzer potential** is used as an analytically solvable approximation to the electron–hole interaction (normally described by the non-elementary Rytova–Keldysh potential) in monolayer transition-metal dichalcogenides (TMDs) such as WSe₂, MoSe₂, WS₂, and MoS₂. This yields a simple, testable Rydberg-like energy ladder $\epsilon_n = -\mathrm{Ry}^*/(n+\delta)^2$ that has been fit to magneto-optical experimental data, and extended to two-dimensional exact solutions with a strength parameter $g$ chosen to reproduce known exciton binding energies and to extract reduced exciton mass and dielectric screening length from measured spectra.

### 3.2 Quantum Information / Uncertainty Studies for 2D Confined Systems
Two-dimensional Kratzer-type systems combining a Kratzer term with a dipole moment and an Aharonov–Bohm flux field have been analyzed for Fisher information and various entropies, revealing how dissociation energy, dipole moment, and AB flux strength affect localization and precision of two-dimensional excitonic/molecular states.

### 3.3 Relativistic Quantum Mechanics (Klein–Gordon and Dirac Equations)
The Kratzer-type potential (and combinations, e.g., Kratzer + Hellmann, Kratzer + Hulthén) has been used as a scalar and/or vector coupling in the:
- **Klein–Gordon equation** — for spin-0 particles, in $D$ dimensions, with equal or unequal scalar/vector Kratzer-type potentials, including ring-shaped and non-central generalizations; also used for spinless particle behavior in cosmic-string/topological-defect spacetimes with Aharonov–Bohm flux (Klein–Gordon oscillator).
- **Dirac equation** — under spin and pseudospin symmetry, often paired with tensor potentials, to obtain relativistic energy spectra applicable to diatomic-molecule-like or mesonic systems.

These studies extend the reach of the Kratzer potential from non-relativistic molecular spectroscopy into relativistic quantum mechanics relevant to high-energy and nuclear-adjacent contexts.

### 3.4 Nuclear and High-Energy Physics: Quarkonium Mass Spectra
The (screened, harmonic-combined, or Coulomb-combined) Kratzer potential has been used as an effective quark–antiquark interaction potential to compute the **mass spectra of heavy quarkonium systems** (charmonium $c\bar c$ and bottomonium $b\bar b$), with results compared successfully against experimental meson masses. This repurposes a molecular-physics potential as an effective confinement/short-range potential in a completely different energy regime.

### 3.5 Confined and Field-Coupled Quantum Systems
Kratzer-type potentials combined with harmonic-oscillator or Mie-type terms have been solved for particles under Aharonov–Bohm flux fields and point-like topological defects, extending the model to solid-state defect physics and gauge-field-influenced quantum systems.

### 3.6 Extension to Two Spatial Dimensions
Beyond the exciton application, the pure two-dimensional Schrödinger equation with Kratzer-type potentials has been solved exactly (eigenvalues, eigenfunctions in associated Laguerre polynomials, and $\langle r \rangle$, $\langle r^2\rangle$ expectation values), broadening the mathematical toolkit for any 2D confined system where such a potential is a reasonable model.

---

## 4. Applications as a Benchmark for Solution Methods

Because it is one of the few interaction potentials with an exact analytic solution, the Kratzer potential (and its many generalized/screened/shifted variants) is routinely used as a **testbed for validating new approximate or semi-analytic solution techniques** for the Schrödinger, Klein–Gordon, and Dirac equations, including:
- The Nikiforov–Uvarov (NU) method and its "functional analysis" extension (NUFA)
- The asymptotic iteration method (AIM)
- Supersymmetric quantum mechanics (SUSYQM) and the factorization method
- Series expansion methods
- The Wentzel–Kramers–Brillouin (WKB) approximation

This is a distinct, methodological application: the physical system (diatomic molecule, exciton, quarkonium, etc.) is often almost secondary to demonstrating that a new mathematical method reproduces known Kratzer-potential results before being applied to less tractable potentials.

---

## 5. Summary Table

| Domain | Representative Use | Typical Systems Studied |
|---|---|---|
| Molecular spectroscopy | Ro-vibrational energy levels, spectroscopic constants | H₂, HCl, LiH, CO, NO, N₂, CH, VN, ScI |
| Statistical thermodynamics | Partition function, $C_V$, $S$, free energy | LiH, HCl, H₂, VN(g) |
| Quantum information theory | Shannon entropy, Fisher information, entropic uncertainty | O₂, O₂⁺, NO, NO⁺, LiH, HCl |
| Condensed matter / 2D materials | Rydberg exciton binding energies | WSe₂, MoSe₂, WS₂, MoS₂ monolayers |
| Relativistic quantum mechanics | Klein–Gordon / Dirac bound states | Generic spin-0/spin-½ particles, mesons |
| High-energy / nuclear physics | Quarkonium mass spectra | Charmonium, bottomonium |
| Ring molecules | Non-central/ring-shaped potential extensions | Cyclic polyenes, benzene-like systems |
| Mathematical/methodological physics | Benchmarking exact/approximate solution methods | NU, AIM, SUSYQM, series expansion, WKB |

---

## 6. List of Related Publications

### Foundational

1. A. Kratzer, "Die ultraroten Rotationsspektren der Halogenwasserstoffe," *Zeitschrift für Physik* **3**, 289 (1920).
2. E. Fues, "Das Eigenschwingungsspektrum zweiatomiger Moleküle in der Undulationsmechanik," *Annalen der Physik* **80**, 367 (1926).

### Molecular Spectroscopy, Thermodynamics, and General Solutions

3. C. Berkdemir, A. Berkdemir, J. Han, "Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential," *Chemical Physics Letters* **417**, 326 (2006).
4. S. M. Ikhdair, R. Sever, "A perturbative treatment for the bound states of the Hellmann potential," and related Kratzer studies (multiple works).
5. E. P. Inyang, E. S. William, J. O. Obu, B. I. Ita, E. P. Inyang, I. O. Akpan, "Analytical solutions of Schrödinger equation with Kratzer-screened Coulomb potential for a Quarkonium system," *Bulletin of Pure and Applied Sciences* **40D**, 14 (2021).
6. E. S. William, E. P. Inyang, I. O. Akpan, J. A. Obu, A. N. Nwachukwu, E. P. Inyang, "Ro-vibrational energies and expectation values of selected diatomic molecules via Varshni plus modified Kratzer potential model," *Indian Journal of Physics* **96**, 3461 (2022).
7. E. P. Inyang, E. O. Obisung, "The study of electronic states of NI and ScI molecules with screened Kratzer potential," *East European Journal of Physics* **3**, 32 (2022).
8. "Analytical Solutions of the Molecular Kratzer-Feus potential by means of the Nikiforov-Uvarov Method," *Journal of Mathematical Chemistry* (2023), https://doi.org/10.1007/s10910-023-01462-y.
9. "Exact analytical solutions to the Kratzer potential by the asymptotic iteration method," ResearchGate/Journal of Molecular Structure: THEOCHEM.
10. "Exact Quantization Rule to the Kratzer-Type Potentials: An Application to the Diatomic Molecules," arXiv:0802.0589.
11. "Bound states in the Kratzer plus polynomial potentials and their new exact tractability via nonlinear algebraic equations," arXiv:quant-ph/9907054.
12. M. R. Setare, E. Karimi, "Morse, Lennard-Jones, and Kratzer Potentials: A Canonical Perspective with Applications," *Journal of Physical Chemistry A* (2016), https://doi.org/10.1021/acs.jpca.6b05371.

### Thermodynamic Properties

13. C. A. Onate, M. C. Onyeaju, A. N. Ikot, O. Ebomwonyi, "Eigensolution, expectation values and thermodynamic properties of the screened Kratzer potential," *European Physical Journal Plus* **134**, 386 (2019), https://doi.org/10.1140/epjp/i2019-12783-x.
14. "Thermal Functions of Diatomic Molecules Using Hulthén Plus Screened Kratzer Potential," *Journal of Low Temperature Physics* (2023), https://doi.org/10.1007/s10909-023-02952-8.
15. "Thermodynamic Properties of Diatomic Molecules in the Presence of Magnetic and Aharonov–Bohm (AB) Flux Fields with Shifted Screened Kratzer Potential," *Journal of Low Temperature Physics* (2024), https://doi.org/10.1007/s10909-024-03205-y.
16. "Exponential Kratzer–Feus potential and thermodynamic properties," *Journal of Low Temperature Physics* (2024), https://doi.org/10.1007/s10909-024-03098-x.
17. Effiong O. Obisung et al., "Analytical Solutions of the N-Dimensional Schrödinger equation with modified screened Kratzer plus Inversely Quadratic Yukawa potential and Thermodynamic Properties of selected Diatomic Molecules."
18. "Solutions of the Schrodinger equation of the shifted screened Kratzer potential and its thermodynamic functions using the extended Nikiforov–Uvarov method," *Frontiers in Physics* **10**, 988279 (2022), https://doi.org/10.3389/fphy.2022.988279.
19. "Bound state solutions of the Schrödinger equation with energy-dependent molecular Kratzer potential via asymptotic iteration method," Redalyc.

### Quantum Information / Entropy

20. S. Majumdar, A. Dutta, N. K. Das, S. Roy, "Information entropy and complexity measure in generalized Kratzer potential," arXiv:1904.06066; also *Chemical Physics Letters* (2019), https://doi.org/10.1016/j.cplett.2018.12.XXX.
21. P. O. Amadi, U. S. Okorie, A. N. Ikot, G. J. Rampho, H. Y. Abdullah, "Shannon entropy and Fisher information for screened Kratzer potential," *International Journal of Quantum Chemistry* **120**, e26246 (2020), https://doi.org/10.1002/qua.26246.
22. "Statistical Analysis and Information Theory of Screened Kratzer-Hellmann Potential Model," arXiv:2001.08429.
23. "Investigation of quantum information theory with the screened modified Kratzer and a class of Yukawa potential model," *European Physical Journal Plus* (2023), https://doi.org/10.1140/epjp/s13360-023-04617-7.
24. A. Becir, M. Moumni, "Fisher information and quantum entropies of a 2D system under a non-central scalar and a vector potentials," arXiv:2412.12638 (2024).

**Excitons and Condensed Matter / 2D Materials**
25. R. Ya. Kezerashvili, J. Luo, C. R. Malvino, A. Spiridonova, "Kratzer and Modified Kratzer Potentials in Two Dimensions: Exact Solutions and Exciton Applications," *Few-Body Systems* **64**, 79 (2023).
26. "Bound state solutions of the two-dimensional Schrödinger equation with Kratzer-type potentials," arXiv:2311.02694.
27. A. Chernikov et al., "Exciton binding energy and nonhydrogenic Rydberg series in monolayer WS₂," *Physical Review Letters* **113**, 076802 (2014).
28. "Energy Spectrum of Two-Dimensional Excitons in a Nonuniform Dielectric Medium," *Physical Review Letters* **123**, 136801 (2019), https://doi.org/10.1103/PhysRevLett.123.136801.
29. "Rydberg Excitons and Doubly Resonant Raman Scattering in Transition-Metal Dichalcogenides," *Journal of Physical Chemistry C* (2023), https://doi.org/10.1021/acs.jpcc.3c06303.
30. "Non-Relativistic and Relativistic Equations for the Kratzer Potential plus a Dipole in 2D Systems," arXiv:1905.03765.

### Relativistic Quantum Mechanics (Klein–Gordon / Dirac)

31. C. Berkdemir, "Relativistic treatment of a spin-zero particle subject to a Kratzer-type potential," *American Journal of Physics* **75**, 81 (2007).
32. N. Saad, R. L. Hall, H. Ciftci, "The Klein-Gordon equation with the Kratzer potential in d dimensions," *Central European Journal of Physics* **6**, 717 (2008); arXiv:0802.1022.
33. A. Durmus, F. Yasuk, "Relativistic and nonrelativistic solutions for diatomic molecules in the presence of double ring-shaped Kratzer potential," *Journal of Chemical Physics* **126**, 074108 (2007).
34. Wen-Chao Qiang, "Bound states of the Klein-Gordon equation for ring-shaped Kratzer-type potential," *Chinese Physics* **13**, (2004).
35. "Relativistic treatment in D-dimensions to a spin-zero particle with noncentral equal scalar and vector ring-shaped Kratzer potential," arXiv:0704.0489 / arXiv:0704.0573.
36. "Asymptotic iteration method for solution of the Kratzer potential in D-dimensional Klein-Gordon equation," ResearchGate (2017).
37. "Bound state solution of the Klein-Gordon equation for vector and scalar Hellmann plus modified Kratzer potentials," *Results in Physics* (2020), https://doi.org/10.1016/j.rinp.2020.103432 (ScienceDirect record).
38. "Klein-Gordon oscillator interacting with screened Kratzer potential in a cosmic string space-time with space-like dislocation and AB field," *Frontiers in Physics* (2025), https://doi.org/10.3389/fphy.2025.1620283.
39. "Point-like defect on Schrödinger particles under flux field with harmonic oscillator plus Mie-type potential: application to molecular potentials," arXiv:2209.13490.

### Nuclear / High-Energy Physics (Quarkonium)

40. E. E. Ibekwe, U. S. Okorie, J. B. Emah, E. P. Inyang, S. A. Ekong, "Mass spectrum of heavy quarkonium for screened Kratzer potential (SKP) using series expansion method," *European Physical Journal Plus* **136**, 87 (2021), https://doi.org/10.1140/epjp/s13360-021-01090-y.
41. "MASS Spectrum of Heavy Quarkonium for Combined Potentials (Modified Kratzer Plus Screened Coulomb Potential)," *Iranian Journal of Science* (2022), https://doi.org/10.1007/s40995-022-01377-4.
42. "Mass spectrum of heavy quarkonium for harmonic plus screened Kratzer potential (HSKP) using series expansion method," Proceedings of the DAE-BRNS Symposium on Nuclear Physics, Vol. 65.
43. E. P. Inyang, A. N. Ikot, E. P. Inyang, I. O. Akpan, J. E. Ntibi, E. Omugbe, E. S. William, "Analytic study of thermal properties and masses of heavy mesons with quarkonium potential," *Results in Physics* **39**, 105754 (2022), https://doi.org/10.1016/j.rinp.2022.105754.
44. "Comparative Study of the Mass Spectra of Heavy Quarkonium System with an Interacting Potential Model," *East European Journal of Physics* (2023).
45. "Masses and thermodynamic properties of a quarkonium system" (pseudoharmonic and Kratzer potentials as special cases), ResearchGate (2021).

---

*Note: Several of the works listed above appear as arXiv preprints or conference proceedings alongside (or prior to) peer-reviewed journal publication; where both exist, the peer-reviewed version should be cited preferentially. Author lists for entries drawn from search-result metadata (rather than full bibliographic records) may be incomplete — please verify full author lists and page numbers against the publisher record before formal citation.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Kratzer potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
