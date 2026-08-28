# The Ring-Shaped Potential: Applications in Physics and Chemistry

## 1. Introduction

The term "ring-shaped potential" refers to a family of non-central (angle-dependent) potentials in which a conventional radial interaction — Coulombic, harmonic-oscillator-like, Kratzer, Hulthén, Pöschl–Teller, Manning–Rosen, Schiöberg, exponential-type, etc. — is supplemented by an additional angular term of the generic form

$$V_{\text{ring}}(\theta) = \frac{\beta}{r^2 \sin^2\theta}$$

superimposed on a central term $V(r)$, giving a total potential $V(r,\theta) = V(r) + V_{\text{ring}}(\theta)/r^2$. This term is singular on the polar axis ($\theta = 0, \pi$) and vanishes in the equatorial plane, producing a torus- or ring-like region of enhanced probability density around $\theta = \pi/2$ — hence the name.

The best-known member of this family is the **Hartmann potential**, introduced by H. Hartmann in 1972,

$$V_H(r,\theta) = \eta\sigma^2\varepsilon_0\left(\frac{2a_0}{r} - \frac{\eta a_0^2}{r^2\sin^2\theta}\right),$$

which combines a Coulomb radial part with the ring-shaped angular term. A second classic member is the **ring-shaped (non-spherical) harmonic oscillator**, studied systematically by Quesne, which combines $\alpha r^2$ with the same $\beta/(r^2\sin^2\theta)$ term.

What makes this class of potentials mathematically distinctive is that, despite being non-central, the Schrödinger (and relativistic Dirac/Klein–Gordon) equation remains **separable** in spherical coordinates. This separability is tied to a **hidden SU(2) dynamical symmetry** that produces "accidental" degeneracies in the bound-state spectrum beyond what rotational symmetry alone would predict — the ring-shaped analogue of the well-known dynamical symmetries of the hydrogen atom (SO(4)) and isotropic oscillator (SU(3)). This combination of physical relevance and mathematical tractability is what has driven decades of sustained interest across nuclear physics, atomic/molecular physics, and quantum chemistry.

---

## 2. Applications in Quantum Chemistry

### 2.1 Ring-shaped and cyclic molecules (benzene and cyclic polyenes)

The original and most frequently cited motivation for the ring-shaped potential is as a **model Hamiltonian for planar ring molecules**, most notably **benzene** and other **cyclic polyenes**. The angular ring term $1/\sin^2\theta$ naturally confines probability density to a torus, mimicking the delocalized π-electron ring current and the toroidal charge distribution characteristic of aromatic ring systems. Hartmann's original 1972 work, and subsequent extensions, were explicitly framed as providing an exactly solvable quantum-mechanical caricature of this bonding geometry, letting chemists obtain closed-form or quasi-closed-form energy spectra and wavefunctions instead of relying purely on numerical electronic-structure calculations.

### 2.2 Diatomic molecule vibration–rotation spectroscopy

Combining the ring-shaped angular term with radial potentials designed for **diatomic molecules** — the Kratzer potential, Hulthén potential, Manning–Rosen potential, Deng–Fan potential, Tietz–Hua potential, Pöschl–Teller potential, Schiöberg potential, and others — yields models used to fit and predict **ro-vibrational energy levels** of real diatomic and polyatomic species. Because the Coulomb and harmonic-oscillator radial forms are both known to give good first approximations to the spectroscopy and structure of diatomic molecules in their ground electronic state, pairing either with the ring-shaped angular term extends this approximation to include non-central (bending/angular) effects, broadening the potential's use as a **spectroscopic modelling tool**.

### 2.3 Persistent currents, induced magnetization, and confined atoms

More recent chemistry/physics-adjacent applications use Hulthén-plus-ring-shaped and related potentials to study a **hydrogen atom confined under spherical confinement** in the presence of external magnetic fields and laser pulses, computing **persistent currents**, **induced magnetization**, and **transition probabilities**. This connects the ring-shaped potential framework to modern topics in confined quantum systems, spherically bounded atoms (relevant to atoms trapped in cavities, fullerene cages, or zeolites), and their optical/magnetic response.

### 2.4 Supersymmetric quantum mechanics (SUSYQM) in theoretical chemistry

The Hartmann potential has served as a testbed for introducing **supersymmetric quantum mechanics** methods into theoretical chemistry, with the eigenvalues and radial eigenfunctions rederived via SUSYQM superpotential techniques on both the half-line and full-line formulations. This work extended SUSYQM — previously used mainly in particle and atomic physics — into a purely chemistry-motivated context, offering an alternative, more elegant route to the same spectroscopic results.

---

## 3. Applications in Nuclear Physics

### 3.1 Deformed nuclei and nucleus–nucleus interactions

A second major motivation for the ring-shaped potential, alongside the benzene analogy, is describing the **interaction between a pair of deformed nuclei**. The non-spherical, axially-symmetric angular dependence of the ring term provides a schematic way to capture how deformation away from a spherical shape modifies the interaction potential between colliding or bound nuclear systems.

### 3.2 Spin–orbit coupling in nuclear mean-field models

Hartmann and Schuch (1980) extended the ring-shaped potential framework explicitly to include **spin–orbit coupling** for a particle moving in a ring-shaped potential — directly relevant to the nuclear shell model, where spin–orbit interaction is essential to reproducing the magic numbers and single-particle level ordering. This line of work sits alongside the broader nuclear-structure literature on spin–orbit and $l^2$ (orbital angular momentum squared) terms in deformed mean-field potentials (e.g., the Nilsson model), which are central to explaining phenomena such as the **prolate-shape dominance** of deformed nuclear ground states.

### 3.3 Superdeformed nuclei and non-spherical oscillator potentials

The **ring-shaped (non-spherical) harmonic oscillator** and its relativistic pseudospin-symmetric extensions have been used to model **super-deformed nuclei**, where the nuclear mean-field potential departs substantially from the spherical harmonic-oscillator shape assumed in the standard shell model. Relativistic treatments (Dirac equation with scalar and vector ring-shaped non-spherical oscillator potentials) have been applied to study **pseudospin symmetry** — an approximate symmetry observed in the nuclear single-particle spectrum — providing benchmark spectra for realistic deformed nuclei such as $^{208}$Pb.

### 3.4 Nuclear collective (Bohr Hamiltonian) models

A distinct and very active application combines ring-shaped-type angular potentials with the **Bohr collective Hamiltonian** used to describe low-lying collective quadrupole excitations (vibrational, rotational, and transitional states) of atomic nuclei. In these "Z(5)"-type models, the $\beta$ (shape-elongation) degree of freedom is governed by a radial potential (Hulthén, Davidson, Manning–Rosen, Tietz–Hua, etc.) while the $\gamma$ (triaxiality) degree of freedom is governed by a **ring-shaped-derived potential**, allowing analytic or quasi-analytic solutions for **triaxial nuclei**. These models are fitted against measured excitation energies and $B(E2)$ electromagnetic transition rates for real nuclei (e.g., isotopes of Xe, Pt, Ru), and have been further generalized to include **deformation-dependent mass** formalisms and interplay between $\gamma$-stable and $\gamma$-rigid collective motion.

### 3.5 Relativistic wave equations for nuclear/particle interactions

Because relativistic corrections matter both in nuclear physics and particle physics, the ring-shaped potential (and generalizations such as double-ring-shaped, Schiöberg-type, or pseudo-Coulomb ring-shaped potentials) has been embedded in the **Klein–Gordon**, **Dirac**, and **finite-difference relativistic** wave equations, yielding closed-form bound-state spectra used as benchmarks for relativistic corrections to nuclear and molecular systems.

---

## 4. Applications in Atomic Physics and Quantum Information / Nanostructures

### 4.1 Hidden symmetry, dynamical algebras, and accidental degeneracy

Beyond concrete physical systems, the ring-shaped potential is a paradigm case for studying **hidden dynamical symmetries**. The SU(2) invariance underlying the Hartmann and ring-shaped oscillator potentials produces "accidental" degeneracies in the energy spectrum, and this has been analyzed via **dynamical invariance algebras** (Kibler and Winternitz), classical/quantum correspondence for generalized Kepler–Coulomb systems, and other group-theoretical approaches. This makes the potential a standard pedagogical and research example for exploring symmetry beyond the obvious geometric symmetry of a Hamiltonian.

### 4.2 Quantum dot–ring nanostructures

In condensed-matter/nanostructure physics, potentials with an effective ring-shaped geometry (dot-ring or "DRN" structures) are used to model **coupled quantum-dot–quantum-ring nanostructures**, where confined electrons occupy a combined dot-like and ring-like potential landscape. While these are typically treated with numerical many-body methods rather than the closed-form Hartmann-type potential, they are part of the same broader family of "ring-shaped confinement" problems and are directly motivated by the same singular-angular-term or toroidal-confinement idea.

### 4.3 Mathematical/methodological role

Beyond its physical applications, the ring-shaped potential (and its many deformed variants: Hulthén-ring, Kratzer-ring, Pöschl–Teller-ring, Coulomb-ring, exponential-ring, Schiöberg double-ring, etc.) has become a **standard benchmark problem** for testing new solution techniques in quantum mechanics: the Nikiforov–Uvarov method, the asymptotic iteration method, the tridiagonal representation approach, supersymmetric quantum mechanics, quantum Hamilton–Jacobi (WKB-exact) formalism, and the exact/approximate treatment of the centrifugal term in relativistic wave equations. Each new radial potential paired with the ring-shaped angular term typically appears in the literature as a fresh test case for one of these methods, which explains the very large number of closely related publications on this topic.

---

## 5. Summary Table

| Domain | Representative Use | Typical Potential Combination |
|---|---|---|
| Quantum chemistry | Benzene / cyclic polyene ring structure | Hartmann (Coulomb + ring) |
| Quantum chemistry | Diatomic molecule vibration–rotation spectra | Kratzer-, Hulthén-, Manning-Rosen-, Deng-Fan-ring |
| Quantum chemistry / atomic physics | Confined atoms, persistent currents, magnetization | Hulthén-ring under spherical confinement |
| Theoretical chemistry | SUSYQM methodology | Hartmann potential |
| Nuclear physics | Deformed nucleus–nucleus interaction | Generic ring-shaped potentials |
| Nuclear physics | Spin–orbit coupling / shell structure | Hartmann–Schuch spin–orbit ring potential |
| Nuclear physics | Superdeformed nuclei, pseudospin symmetry | Ring-shaped non-spherical harmonic oscillator |
| Nuclear physics | Collective quadrupole excitations (Bohr Hamiltonian, Z(5) models) | Hulthén (β) + ring-shaped-derived (γ) |
| Nuclear/particle physics | Relativistic bound states | Klein–Gordon / Dirac + ring-shaped or double-ring potentials |
| Mathematical physics | Hidden SU(2) symmetry, dynamical algebras | Hartmann, ring-shaped oscillator |
| Nanostructure physics | Quantum dot–ring confinement | Dot-ring (DRN) numerical potentials |
| Computational/methods | Benchmarking solution techniques (NU, AIM, TRA, SUSYQM, WKB) | Any radial potential + ring-shaped term |

---

## 6. List of Related Publications

1. Hartmann, H. "Die Bewegung eines Körpers in einem ringförmigen Potentialfeld." *Theoretica Chimica Acta* 24, 201–206 (1972).
2. Hartmann, H., Schuch, D. "Spin-orbit coupling for the motion of a particle in a ring-shaped potential." *International Journal of Quantum Chemistry* 18, 125–141 (1980).
3. Kibler, M., Winternitz, P. "Dynamical invariance algebra of the Hartmann potential." *Journal of Physics A: Mathematical and General* 20, 4097–4108 (1987).
4. Kibler, M., Campigotto, C. "Classical and quantum study of a generalized Kepler–Coulomb system." *International Journal of Quantum Chemistry* 45, 209–224 (1993).
5. Chen, C. Y., Liu, C. L., Dong, S. S. "The normalized wavefunctions of the Hartmann potential and explicit expressions for their radial average values." *Physics Letters A* 305, 341–348 (2002).
6. Berkdemir, C., Berkdemir, A., Han, J. "Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential." *Chemical Physics Letters* 417, 326–329 (2006).
7. Blado, G. G. "A Supersymmetric Treatment of a Particle Subjected to a Ring-Shaped Potential." arXiv:quant-ph/9511040 (1995).
8. Blado, G. G. "Supersymmetry and the Hartmann Potential of Theoretical Chemistry." arXiv:quant-ph/9602005.
9. "Exact solutions of the Schrödinger equation with non-central potential by Nikiforov–Uvarov method." arXiv:quant-ph/0410144.
10. "Polynomial Solution of Non-Central Potentials." arXiv:quant-ph/0702186.
11. "Energy spectra of Hartmann and ring-shaped oscillator potentials using the quantum Hamilton–Jacobi formalism." arXiv:1312.0087.
12. "The visualization of the space probability distribution for a moving particle I: in a single ring-shaped Coulomb potential." arXiv:1708.05315.
13. "Solutions of the D-dimensional Schrödinger equation with the hyperbolic Pöschl–Teller potential plus modified ring-shaped term." arXiv:1711.05774.
14. "Solutions of Dirac equation for a new improved pseudo-Coulomb ring-shaped potential." *Journal of King Saud University – Science* (ScienceDirect), 2016.
15. "Pseudospin symmetry and the relativistic ring-shaped non-spherical harmonic oscillator." *Physics Letters B*, ScienceDirect, 2006.
16. "Persistent currents and induced magnetization in presence of external magnetic field and transition probabilities in presence of combined laser pulse and external magnetic field for a confined hydrogen atom." *Chemical Physics* / ScienceDirect, 2019.
17. "Analytical solutions for the Klein–Gordon equation with combined exponential type and ring-shaped potentials." *Scientific Reports* 14, article s41598-024-53650-8 (2024).
18. "Relativistic bound-state solutions for a non-central Schiöberg-type hyperbolic potential with double ring-shaped angular terms." arXiv:2607.16265.
19. Chabab, M., Lahbas, A., Oulne, M. "Bohr Hamiltonian with Hulthén plus Ring-shaped potential for triaxial nuclei." *European Physical Journal A* 51, 131 (2015). arXiv:1510.04525.
20. Adahchour, A., Ait El Korchi, S., El Batoul, A., Lahbas, A., Oulne, M. "Bohr Hamiltonian with Hulthén plus ring-shaped potential for triaxial nuclei with Deformation-Dependent Mass term." *European Physical Journal Plus* 135, 586 (2020). arXiv:2008.01651 / arXiv:2001.10095.
21. "Bohr Hamiltonian and interplay between γ-stable and γ-rigid collective motions with both Harmonic oscillation and Ring-shaped potentials for the γ-part." (Conference/journal proceedings, cites Chabab et al. and related Z(5) literature.)
22. Tajima, N., Suzuki, N. "Prolate dominance of nuclear shape caused by a strong interference between the effects of spin–orbit and $l^2$ terms of the Nilsson potential." arXiv:nucl-th/0103061.
23. "The role of spin–orbit potential in nuclear prolate-shape dominance." *Physics Letters B*, ScienceDirect, 2012.
24. "From spin to pseudospin symmetry: The origin of magic numbers in nuclear structure." arXiv:2504.09148.
25. "Dot-ring nanostructure: Rigorous analysis of many-electron effects." *Scientific Reports* 6, 29887 (2016).

---

*Note: Citation details for some review-cited works (e.g., items drawn from secondary reference lists) are reproduced as given in the citing articles and should be cross-checked against the original source for full bibliographic accuracy (volume, page, DOI) before formal use.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Ring-shaped potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
