# The Triangular Potential: Applications in Physics and Chemistry

## 1. Introduction and Definition

The **triangular potential** is one of the small set of exactly (or quasi-exactly) solvable model potentials in quantum mechanics, alongside the infinite square well, the harmonic oscillator, and the Coulomb potential. In its two principal forms it appears as:

- **Triangular potential *well*** (semi-infinite / linear ramp): an infinite hard wall at $x = 0$ combined with a potential rising linearly with distance,
$$V(x) = \begin{cases} eFx, & x \ge 0 \\ \infty, & x < 0 \end{cases}$$
This is the generic model for a charged particle confined against a hard interface by a uniform electric (or gravitational) field.

- **Symmetric (double-sided) triangular / "V-shaped" potential**:
$$V(y) = \kappa |y|$$
used as a confining potential without a hard wall, and as a short-range pairwise interaction model in statistical mechanics of fluids.

Both forms reduce the stationary Schrödinger equation to the **Airy equation**, so eigenfunctions are Airy functions $\mathrm{Ai}(z)$, and (for the semi-infinite well) the energy eigenvalues are fixed by the zeros of $\mathrm{Ai}$. This single mathematical fact — exact solvability in terms of a well-tabulated special function — is what makes the triangular potential recur across so many, otherwise unrelated, physical and chemical contexts: whenever a system is dominated by a locally uniform force field acting against a hard confining boundary (or a short-range attractive/repulsive interaction is approximated by a linear ramp), the triangular potential is the natural minimal model.

---

## 2. Applications in Physics

### 2.1 Semiconductor heterostructures, MOSFETs, and 2D electron gases
This is the dominant *engineering* application. At a semiconductor interface under a strong perpendicular electric field — the Si/SiO₂ interface in a MOSFET inversion layer, or a modulation-doped AlGaAs/GaAs or AlGaN/GaN heterojunction in a High Electron Mobility Transistor (HEMT) — the conduction-band bending is well approximated by a triangular well. Electrons confined there occupy quantized **Airy subbands**, giving rise to the two-dimensional electron gas (2DEG) that carries current in HEMTs and defines the accumulation/inversion-layer physics of MOS devices.
- Threshold-voltage, capacitance, and quantum-corrected surface-potential compact models for MOSFETs are built directly on the triangular-well approximation, and its accuracy versus full self-consistent Schrödinger–Poisson solutions has been explicitly benchmarked.
- Analytic 2DEG sheet-density models for HEMTs (including piezoelectric AlGaN/GaN devices) use the triangular-well approximation to relate gate voltage to carrier density.
- Tunnelling and resonant-tunnelling spectroscopy of double-barrier heterostructures interprets subband structure and precursor resonances in terms of electrons injected from a triangular accumulation-layer well.

### 2.2 Field ionization, field emission, and atom-probe tomography
An external electric field applied to an atom or a metal surface converts the long-range Coulomb (or work-function) barrier into a field-lowered, finite-width triangular barrier. The Fowler–Nordheim treatment of field electron emission, and the Landau–Lifshitz-type treatment of field ionization used in **field-ion microscopy** and **atom-probe tomography**, both model tunnelling through this triangular barrier, with the barrier width and slope set by the local field strength.

### 2.3 Quantum tunnelling and Stark-effect theory
The triangular potential is the standard minimal model for tunnelling and level-shift problems in a uniform field:
- Bound-state and tunnelling-time analyses of a particle in short-range linear/triangular wells, correcting earlier flawed quantization treatments and connecting the problem explicitly to "exciting applications in solid state physics."
- Closed-circuit and barrier-tunnelling toy models using Airy-function matching across triangular barriers.
- The linear Stark potential of hydrogenic/Rydberg atoms in a strong DC field reduces, along the field axis, to a triangular-type barrier problem whose solutions underlie field-ionization rates of Rydberg states.

### 2.4 Gravitationally bound quantum states of neutrons
A landmark and widely cited application: ultracold neutrons bouncing above a horizontal mirror experience a potential that is a hard wall (the mirror) combined with the linear gravitational potential $V(z) = mgz$ — an essentially exact physical realization of the triangular well. This system was used in a celebrated Nature experiment to observe **quantized gravitational states of a particle** for the first time, with eigenfunctions given by (rescaled, shifted) Airy functions and eigenenergies in the peV range ($E_1 \approx 1.4$ peV, corresponding to $z_1 \approx 14\,\mu\mathrm{m}$). It remains an active platform for testing short-range modifications of gravity and equivalence-principle physics, and the interpretation/validity of the original measurements has itself been the subject of continued theoretical debate.

### 2.5 Relativistic and topological condensed-matter physics
Recent work extends the triangular-well problem to the **relativistic (Dirac) regime**: massless Dirac fermions confined to a graphene nanoribbon strip in an in-plane electric field map onto a Dirac equation with a triangular potential well across the ribbon width, yielding new special functions related to (but not reducible to) Airy functions, and connecting to chiral-anomaly physics in topological materials.

### 2.6 Driven/periodic and semiclassical dynamics
The triangular well is also used as a testbed for nonlinear and semiclassical dynamics beyond the static case:
- Classical and quantum dynamics of a **periodically driven** particle in a triangular well, studied for Floquet resonances, quantum tunnelling between resonance zones, and the classical–quantum correspondence of chaotic-like dynamics.
- Elementary semiclassical (WKB/Bohr–Sommerfeld) quantization of the triangular well is a standard pedagogical route to deriving the $E_n \sim (F^2\hbar^2 n^2/m)^{1/3}$ energy-level scaling common to all of the device and atomic applications above.

### 2.7 Cold-atom and optical-lattice physics
Ultracold atoms loaded into triangular (or hexagonal) optical lattices — a periodic array of triangular-type confining potentials — realize rich condensed-matter phenomena including proposed supersolid phases, quantum stripe-ordered states, exotic superconducting analogues, and graphene-like physics, extending the concept from a single potential well to a lattice of them.

### 2.8 Mechanical and elastic analogues
Because the Schrödinger equation and the Euler–Bernoulli beam-buckling equation share mathematical structure, the quantum triangular-well problem has an exact classical mechanical analogue: a particle in a triangular well maps onto **self-buckling of a vertical elastic rod (worm-like chain)** under its own weight with combined end forces, providing a macroscopic mechanical realization of the same eigenvalue problem.

---

## 3. Applications in Chemistry and Physical Chemistry

### 3.1 The triangle-well fluid: a statistical-mechanical model potential
In liquid-state theory, the symmetric triangular (ramp-shaped) potential is used, alongside the square-well and Lennard-Jones potentials, as a simplified **intermolecular pair potential** — a hard core plus a linearly decreasing (rather than stepwise or continuously curved) attractive well:
$$u(r) = \begin{cases} \infty, & r < \sigma \\ -\epsilon\left(1 - \dfrac{r-\sigma}{\lambda\sigma - \sigma}\right), & \sigma \le r \le \lambda\sigma \\ 0, & r > \lambda\sigma \end{cases}$$
This "triangle-well" (or "triangular-well") fluid model has been used extensively for:
- Deriving analytical **equations of state** via thermodynamic perturbation theory, including exact one-dimensional solutions (equation of state, radial distribution function, structure factor, direct correlation function) and comparison with the Percus–Yevick/hypernetted-chain closures.
- Computing **vapour–liquid phase equilibria and interfacial (surface) tension** by Monte Carlo and molecular dynamics simulation, in both two and three dimensions, and testing the principle of corresponding states.
- Comparative studies against the square-well and Lennard-Jones potentials to isolate the effect of attractive-well *shape* (rather than depth or range alone) on thermodynamic and structural properties — relevant to coarse-grained modelling of simple liquids, colloids, and associating fluids (e.g., in Statistical Associating Fluid Theory-type frameworks).

### 3.2 Adsorption on heterogeneous surfaces
A modified triangular-well potential has been used explicitly as a coarse-grained interaction model in **Monte Carlo simulations of protein and colloidal-particle adsorption on energetically heterogeneous surfaces**, allowing spatially varying surface free energy to be incorporated in a simulation of adsorption and surface diffusion — a direct chemistry/biophysics application of the triangular-well concept as a tunable short-range attractive potential.

### 3.3 Quantum-confinement treatment of gas physisorption in nanopores
In modelling **physisorption of small gas molecules (CH₄, CO₂) in nanoporous materials**, the confining potential of the pore wall is treated as giving rise to quantized adsorption "orbitals" analogous to a particle confined near a wall in a field — conceptually the same triangular/linear-ramp confinement picture used in the semiconductor case, applied here to explain quantized adsorption capacity and orbital-resolved Boltzmann population of adsorption sites.

### 3.4 Semiconductor surface chemistry (MOS/oxide interface)
The triangular-potential-well approximation used for MOS inversion/accumulation layers (Section 2.1) is simultaneously a **surface-chemistry problem**: the electronic structure of the semiconductor–oxide interface, oxide charge trapping, and gate-oxide tunnelling barriers (also triangular under bias) are treated with the same Airy-function machinery, linking solid-state device physics directly to interfacial/surface chemistry of the Si–SiO₂ (or III–V oxide) system.

### 3.5 Chemisorption/physisorption potential-energy landscapes (conceptual link)
More broadly in surface chemistry, gas–surface interaction potentials (combined physisorption and chemisorption wells, as in CO/Au(111) or grain-surface astrochemistry) are often locally approximated by simple analytic well shapes — square, Morse, or triangular — for tractable rate-theory and diffusion/desorption modelling; the triangular-well shape offers the simplest model retaining a finite well depth, a finite range, and linear (constant-force) walls, useful where curvature details of the true potential are not needed.

---

## 4. Summary Table

| Domain | Role of the triangular potential | Key physical quantity obtained |
|---|---|---|
| MOSFET / HEMT devices | Band bending at interface under gate/junction field | 2DEG subband energies, sheet density, threshold voltage |
| Field ionization / atom-probe / field emission | Field-lowered tunnelling barrier | Ionization/emission rate (Fowler–Nordheim, Landau–Lifshitz) |
| Rydberg atoms / Stark effect | Linear-field barrier along field axis | Field-ionization rates, Stark level shifts |
| Ultracold neutrons in gravity | Mirror + linear gravitational potential | Quantized gravitational energy levels ($E_n$, $z_n$) |
| Graphene nanoribbons (Dirac fermions) | Gauge-field triangular well across ribbon | Chiral anomaly structure, zero-energy modes |
| Driven quantum/classical systems | Periodically modulated triangular well | Floquet resonances, tunnelling rates |
| Cold atoms in optical lattices | Periodic triangular confining lattice | Supersolid/exotic quantum phases |
| Elastic rod buckling | Mechanical analogue of Schrödinger eigenproblem | Buckling mode shapes and thresholds |
| Triangle-well fluids (statistical mechanics) | Pairwise intermolecular attraction model | Equation of state, phase diagram, interfacial tension |
| Heterogeneous-surface adsorption | Coarse-grained adsorption potential | Adsorption/desorption kinetics, surface coverage |
| Gas physisorption in nanopores | Confinement potential near pore wall | Quantized adsorption levels, capacity |

---

## 5. Publication List (by application area)

### Quantum mechanics / mathematical treatment
1. Castro, L.B. & de Castro, A.S., *"On the bound-state spectrum of a nonrelativistic particle in the background of a short-ranged linear potential,"* arXiv:1003.2993.
2. Rao, N.A. & Kagali, B.A., original (revised) triangular potential well quantization paper referenced in Castro & de Castro (2010) above.
3. Suzuki, T. (Binghamton Univ. lecture notes), *"A particle confined within a triangular potential well"* (Airy function pedagogical treatment), based on J. Schwinger, *Quantum Mechanics: Symbolism of Atomic Measurements* (Springer, 2001), pp. 248–254.
4. *"Airy Function in Triangular Wells"* — pedagogical treatment of parity, eigenvalues from Airy zeros (Scribd document, 2020).
5. Determination of the modes in two types of closed circuits with quantum tunneling, arXiv:2304.14910 (triangular barrier closed-circuit model).
6. *"Multiresolution analysis of quantum theories using Daubechies wavelet basis"* (Section 3.5, "The triangular potential"), arXiv:2512.18372.
7. *"Physics in the information age: qualitative methods (with examples from quantum mechanics),"* Section 6, "Quantization in a triangular well," arXiv:1907.08154.

### Relativistic / condensed matter (Dirac fermions, graphene)
8. Payod, R.B. & Saroka, V.A., *"On a Solution to the Dirac Equation with a Triangular Potential Well,"* arXiv:2409.04595 (2024).

### Semiconductor devices (MOSFET, HEMT, 2DEG)
9. *"Validity and applicability of triangular potential well approximation in modeling of MOS structure inversion and accumulation layer,"* IEEE Trans. Electron Devices (IEEE Xplore, DOI accessible via ieeexplore.ieee.org/document/861589).
10. nextnano Documentation, *"3.20.15. Triangular well"* — tutorial on Airy-function solution for GaAs conduction-band triangular well (nextnano.com).
11. Gehring, A., *"Simulation of Tunneling in Semiconductor Devices,"* PhD thesis, TU Wien — Section 3.6.1, "Eigenvalues of a Triangular Energy Well" (iue.tuwien.ac.at).
12. *"Simple yet comprehensive unified physical model of the 2-D electron gas in delta-doped and uniformly doped high electron mobility transistors,"* (ResearchGate/journal article on HEMT 2DEG surface-density modelling using the triangular-well approximation).
13. *"Subband spectroscopy in two-dimensional electron gas systems"* — resonant tunnelling and triangular accumulation-layer subband structure (Academia.edu-hosted article).
14. Various HEMT/GaN semiconductor device patents describing the triangular-well-induced 2DEG at channel/barrier heterojunctions (e.g., US Patents 11,862,721; 12,094,875; 12,490,490; 12,154,864; 12,550,357).

### Field ionization / field emission / atom probe
15. *"Compositional Metrology of Atom Probe Applied to non-Metallic Materials,"* arXiv:2602.14565 (field ionization via triangular tunnelling barrier).
16. *"Post-field ionization of Si clusters in atom probe tomography: A joint theoretical and experimental study,"* arXiv:2207.05230.
17. *"Tunnel ionization,"* overview article (Wikipedia, background reference).
18. *"Tunneling ionization of deep centers in high frequency electric fields,"* arXiv:cond-mat/0301410.

### Gravitationally bound neutron quantum states
19. Nesvizhevsky, V.V. et al., *"Quantum states of neutrons in the Earth's gravitational field,"* Nature **415**, 297–299 (2002).
20. Nesvizhevsky, V.V. et al., *"Investigation of the Neutron Quantum States in the Earth's Gravitational Field,"* (PMC4849602).
21. *"Study of the neutron quantum states in the gravity field,"* arXiv:hep-ph/0502081.
22. *"On observation of neutron quantum states in Earth gravitational field at Laue-Langevin Institute, Grenoble,"* arXiv:0808.1362.
23. Voronin, A.Y. et al. (critical re-analysis), *"On observation of neutron quantum states in the Earth's gravitational field,"* Phys. Rev. D **81**, 052008 (2010).
24. Abele, H. & Leeb, H., *"Gravitation and quantum interference experiments with neutrons,"* New J. Phys. **14**, 055010 (2012).
25. *"The neutron and its role in cosmology and particle physics,"* arXiv:1105.3694 (Section on gravitational quantum levels).
26. Physics Today news article, *"Ultracold Neutrons Exhibit Quantum States in the Earth's Gravitational Field."*

### Driven / periodic quantum dynamics
27. Flatté, M.E. & Holthaus, M., *"Classical and Quantum Dynamics of a Periodically Driven Particle in a Triangular Well,"* arXiv:cond-mat/9506001.

### Mechanical analogue (buckling)
28. *"The quantum character of buckling instabilities in thin rods,"* arXiv:2002.05772 (Section C, "Particle in a triangular well").

### Statistical mechanics / triangle-well fluids (chemistry — equations of state & phase behaviour)
29. Feinberg, M.J. & De Rocco, A.G., *"Intermolecular Forces: The Triangle Well and Some Comparisons with the Square Well and Lennard-Jones,"* J. Chem. Phys. **41**, 3439–3450 (1964).
30. Fowler, R.H., Graben, H.W., De Rocco, A.G., & Feinberg, M.J., *"Some Additional Results for the Triangle-Well Potential Model,"* J. Chem. Phys. **43**, 1083–1084 (1965).
31. Farrar, W.C. & De Rocco, A.G., *"Perturbation Theory for a High-Temperature Triangle-Well Fluid,"* J. Chem. Phys. **54**, 2024–2025 (1971).
32. Adhikari, J. & Kofke, D.A., *"Monte Carlo and cell model calculations for the solid–fluid phase behaviour of the triangle-well model,"* Mol. Phys. **100**, 2727–2739 (2002).
33. Rivera, L.D., Robles, M., & López de Haro, M., *"Equation of state and liquid–vapour equilibrium in a triangle-well fluid,"* Mol. Phys. **110**, 1317–1323 (2012).
34. Bárcenas, M., Odriozola, G., & Orea, P., *"Coexistence and interfacial properties of triangle-well fluids,"* Mol. Phys. **112**, 2114–2121 (2014).
35. Trejos, V.M., Martínez, A., & Valadez-Pérez, N.E., *"Statistical fluid theory for systems of variable range interacting via triangular-well pair potential,"* J. Mol. Liq. **265**, 337–346 (2018).
36. Benavides, A.L., Cervantes, L.A., & Torres-Arenas, J., *"Analytical equations of state for triangle-well and triangle-shoulder potentials,"* J. Mol. Liq. **271**, 670–676 (2018).
37. *"Thermodynamic properties of triangle-well fluids in two dimensions: MC and MD simulations,"* PubMed ID 27825218 (phase diagrams and interfacial tension in 2D).
38. López de Haro, M. & Rodríguez-Rivas, Á., *"Thermodynamic Properties of the Parabolic-Well Fluid,"* Front. Phys. **8**, 627017 (2020) (comparative discussion referencing triangular-well fluids).
39. *"Correlation functions and thermophysical properties of one-dimensional liquids,"* arXiv:1710.01118 (exact 1D triangle-well and ramp-potential fluid theory).
40. *"Triangle-Well and Ramp Interactions in One-Dimensional Fluids: A Fully Analytic Exact Solution,"* CORE repository record (core.ac.uk/works/54177759).
41. SklogWiki, *"Triangular well model"* page — consolidated bibliography of the triangle-well fluid literature.

### Adsorption / surface chemistry
42. Danwanichakul, P., *"Monte Carlo Simulation of Protein Adsorption on Energetically Heterogeneous Surfaces,"* J. Chem. (Hindawi/PMC), DOI: 10.1155/2014/278098 (PMC4124203).
43. *"Quantum Physisorption of Methane and Carbon Dioxide within Nanoporous Materials,"* arXiv:2203.07076.
44. LibreTexts, *"31.6: Atoms and Molecules can Physisorb or Chemisorb to a Surface"* — background reference for adsorption potential-energy curves.

---

## 6. Notes on Scope
This review focuses on documented, literature-grounded applications where the triangular (linear-ramp or V-shaped) potential is used explicitly as a model potential. Some entries (device patents, textbook/tutorial sources) are included for their concrete engineering or pedagogical value even though they are not primary research articles; these are marked as such above. Chemistry applications cluster into two largely independent literatures — (a) the "triangle-well fluid" as an intermolecular pair-potential model in liquid-state statistical mechanics, and (b) triangular/linear confinement potentials used in surface and adsorption chemistry — both of which are distinct from, but mathematically related to, the quantum triangular potential *well* used throughout physics.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Triangular Potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
