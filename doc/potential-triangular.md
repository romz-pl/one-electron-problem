# Evaluation of Eigenvalues of the Schrödinger Equation with a Triangular Potential: An Exhaustive Review

## Abstract

The triangular (linear) potential is one of the few exactly solvable confining potentials in one-dimensional quantum mechanics, and it is simultaneously one of the most important potentials in applied semiconductor physics, atomic physics in external fields, and semiclassical theory. This review surveys the mathematical formulation of the triangular-potential eigenvalue problem, its exact solution in terms of Airy functions, semiclassical (WKB/Bohr–Sommerfeld) approximations, purely numerical approaches (shooting, finite-difference, finite-element, matrix diagonalization, variational methods), and self-consistent extensions relevant to inversion-layer and heterostructure physics. Analytical formulas, asymptotic expansions for Airy zeros, comparative accuracy of approximate schemes, and physical applications are discussed. A curated bibliography of primary and secondary sources is provided.

---

## 1. Statement of the Problem

### 1.1 The pure (semi-infinite) triangular well

The canonical triangular-potential eigenvalue problem is the one-dimensional, time-independent Schrödinger equation

$$-\frac{\hbar^2}{2m}\frac{d^2\psi(x)}{dx^2} + V(x)\,\psi(x) = E\,\psi(x)$$

with the linear ("triangular") potential

$$V(x) = \begin{cases} \infty, & x<0 \\ Fx, & x \ge 0 \end{cases}$$

where $F$ is a constant force (e.g. $F=eE_{\text{field}}$ for a charge $e$ in a uniform electric field, or $F=mg$ for a particle in a uniform gravitational field). The hard wall at $x=0$ enforces $\psi(0)=0$, and boundedness requires $\psi(x)\to 0$ as $x\to\infty$. This is the model realized physically by:

- an electron trapped against a semiconductor–oxide interface by a uniform electric field (MOSFET/heterojunction inversion layer),
- ultracold neutrons bouncing under gravity above a mirror (the "quantum bouncer," relevant to the qBounce experiment),
- a particle confined by one infinite wall and a uniform force field in general.

### 1.2 The symmetric/double-sided triangular well

A second common variant is the **symmetric triangular well**,

$$V(x) = F|x|,$$

with no infinite wall — the particle is confined solely by the V-shaped potential on both sides. This variant yields two families of eigenstates (even and odd parity) and is frequently used as a pedagogical WKB example and as a testbed for numerical eigenvalue solvers.

### 1.3 The finite/truncated triangular well

In semiconductor device physics, the physically relevant potential is a **truncated** or **self-consistent** triangular well: linear over a finite region, capped by a finite (or, in the idealized limit, infinite) barrier at the interface, and eventually flattening out or interfacing with the conduction band offset. This is the model used for MOS inversion layers and modulation-doped heterojunctions (Section 5).

---

## 2. Exact Solution via Airy Functions

### 2.1 Reduction to the Airy equation

Introducing the characteristic length and energy scales

$$x_0 = \left(\frac{\hbar^2}{2mF}\right)^{1/3}, \qquad E_0 = \left(\frac{\hbar^2 F^2}{2m}\right)^{1/3},$$

and the dimensionless variable

$$\xi = \frac{x - E/F}{x_0},$$

the Schrödinger equation reduces exactly to the **Airy equation**

$$\frac{d^2\psi}{d\xi^2} - \xi\,\psi = 0,$$

whose two linearly independent solutions are the Airy functions $\mathrm{Ai}(\xi)$ and $\mathrm{Bi}(\xi)$. Since $\mathrm{Bi}(\xi)$ diverges as $\xi\to+\infty$, physical (normalizable) solutions in the classically forbidden region require discarding $\mathrm{Bi}$, leaving

$$\psi(x) \propto \mathrm{Ai}\!\left(\frac{x - E/F}{x_0}\right).$$

### 2.2 Quantization condition

**Semi-infinite well (hard wall at $x=0$):** the boundary condition $\psi(0)=0$ gives the exact quantization condition

$$\mathrm{Ai}\!\left(-\frac{E_n}{E_0}\right) = 0 \quad\Longrightarrow\quad E_n = -a_n\, E_0,$$

where $-a_n$ ($n=1,2,3,\dots$) are the zeros of the Airy function $\mathrm{Ai}$ on the negative real axis ($a_n>0$). Equivalently,

$$E_n = \left[\frac{\hbar^2 F^2}{2m}\right]^{1/3} c_n, \qquad c_n \equiv a_n.$$

The first five zeros are commonly tabulated as

$$a_1 = 2.33811,\quad a_2 = 4.08795,\quad a_3 = 5.52056,\quad a_4 = 6.78671,\quad a_5 = 7.94413.$$

**Symmetric well $V(x)=F|x|$:** parity separates the problem into even states, quantized by zeros of $\mathrm{Ai}'$ (derivative), and odd states, quantized by zeros of $\mathrm{Ai}$ itself, each evaluated at $\xi=0$ — i.e., even states require $\mathrm{Ai}'(-E/E_0)=0$ and odd states require $\mathrm{Ai}(-E/E_0)=0$, interlacing the two spectra.

### 2.3 Normalization

The normalized eigenfunctions for the semi-infinite well are

$$\psi_n(x) = N_n\, \mathrm{Ai}\!\left(\frac{x}{x_0} - a_n\right), \qquad N_n = \left[x_0 \int_{-a_n}^{\infty} \mathrm{Ai}^2(\zeta)\,d\zeta\right]^{-1/2} = \frac{1}{\sqrt{x_0}\,\left|\mathrm{Ai}'(-a_n)\right|},$$

the last equality following from a standard Airy-function identity relating the normalization integral to the derivative at the zero.

### 2.4 Asymptotic (large-$n$) behavior of the eigenvalues

For large quantum number, the Airy zeros admit the asymptotic expansion

$$a_n \sim \left[\frac{3\pi}{2}\left(n - \frac{1}{4}\right)\right]^{2/3}\left[1 + O(n^{-2})\right],$$

with higher-order corrections available in the literature (e.g. terms in $5/(48 t^2)$, etc., where $t\propto n$). This is precisely the **Bohr–Sommerfeld / WKB result** for the linear potential (Section 3), which for this potential turns out to reproduce the exact quantization essentially exactly once appropriately matched — a notable and often-cited coincidence.

---

## 3. Semiclassical (WKB) Treatment

### 3.1 Bohr–Sommerfeld quantization

For the symmetric well $V(x)=F|x|$, WKB quantization,

$$\oint p\,dx = 2\pi\hbar\left(n+\tfrac12\right),$$

with classical turning points at $x=\pm E/F$, gives upon evaluating the action integral

$$E_n^{\text{WKB}} \propto \left[\frac{3\pi\hbar F}{4\sqrt{2m}}\left(n+\tfrac12\right)\right]^{2/3}.$$

For the semi-infinite (hard-wall) case, the appropriate connection formula at the hard wall contributes an extra phase of $\pi/2$ rather than the usual $\pi/4$, giving the analogous formula with $(n-1/4)$ in place of $(n+1/2)$, matching the exact asymptotic Airy-zero formula quoted above.

### 3.2 Connection formulas and Airy matching

Because the potential is exactly linear near the turning point (indeed, everywhere), the **local Airy-function matching** used generically in WKB theory to connect oscillatory and evanescent regions is *exact* for the triangular potential rather than approximate. This makes the triangular well the paradigmatic textbook example for deriving and validating the WKB connection formulas across a turning point, and it appears in essentially every quantum mechanics textbook treatment of the WKB method (Section 6 gives representative choices).

### 3.3 Accuracy assessment

Because the semiclassical phase-integral method is asymptotically exact for a strictly linear potential, the leading WKB eigenvalues already agree with the exact Airy-zero eigenvalues to a few percent even for the ground state and converge rapidly with $n$; this makes the triangular potential a preferred benchmark for testing more general WKB-type or phase-integral methods for other potentials (e.g., in studies of $\mathcal{PT}$-symmetric potentials, where the imaginary linear potential $V(ix)=igx$ is used as a solvable calibration case for higher-order WKB formulas).

---

## 4. Numerical Methods for the Triangular-Potential Eigenproblem

While the pure triangular potential is exactly solvable, numerical methods are indispensable (a) for validating general-purpose eigensolvers against a known analytic benchmark, and (b) for the physically realistic *finite* or *self-consistent* triangular wells that arise in devices, where exact closed forms are unavailable. Numerical strategies reported in the literature include:

1. **Shooting method** — integrate the ODE from the classically forbidden region inward/outward and adjust $E$ until boundary conditions (decay at infinity, node at the wall) are satisfied; a standard approach recommended in applied treatments (e.g., MATLAB/Python-based solvers for triangular quantum wells with a triangular barrier).

2. **Finite-difference discretization** — replace $d^2/dx^2$ by a tridiagonal difference operator on a spatial grid, converting the eigenproblem into a matrix diagonalization; widely used in self-consistent Schrödinger–Poisson solvers for inversion layers (e.g., nextnano and similar device simulators).

3. **Finite-element method (FEM)** — used especially for multi-dimensional generalizations, e.g., triangular *cross-section* quantum wires, where the 2D Schrödinger–Poisson system is solved self-consistently on a finite-element mesh.

4. **Basis-set expansion / matrix diagonalization** — expand the wavefunction in a convenient complete basis (harmonic-oscillator functions, "Olsson" basis functions, power-law bases, an infinite-square-well basis, etc.) and diagonalize the resulting Hamiltonian matrix; convergence to the exact Airy-zero eigenvalues with increasing basis truncation order $N$ is a standard convergence test (see worked comparison tables in the literature, where the $N=10$ truncated matrix reproduces the first Airy zero to 4–5 significant digits and higher excited states more slowly).

5. **Variational methods** — trial wavefunctions (e.g., Fang–Howard-type trial functions $\psi(z)\propto z\,e^{-bz/2}$, or sinusoidal basis functions on a symmetric infinite well) are commonly used in semiconductor physics to obtain approximate ground- and low-lying subband energies self-consistently with the electrostatic potential, particularly where full numerical diagonalization at every self-consistency iteration is computationally expensive.

6. **Algebraic / hypervirial and Hill-series methods** — used to obtain highly accurate eigenvalues for the linear potential and its generalizations (e.g., power-law confinement, or linear-plus-Coulomb potentials in heavy-quarkonium spectroscopy) by expanding around known solvable limits.

### 4.1 Representative convergence data

A representative table (matrix truncation approach applied to the potential $V(r)=r$, equivalent to the triangular well) shows how numerically diagonalized eigenvalues converge onto the exact Airy zeros as the basis size $N$ grows:

| Truncation $N$ | $E_0$ | $E_1$ | $E_2$ |
|---|---|---|---|
| 0 | 2.17747 | — | — |
| 3 | 2.33298 | 4.06720 | 5.87930 |
| 6 | 2.33623 | 4.08466 | 5.51523 |
| 10 | 2.33730 | 4.08652 | 5.51905 |
| **Exact (Airy zero)** | **2.33811** | **4.08795** | **5.52056** |

This illustrates the generic numerical-methods lesson that ground-state convergence is fastest and higher excited states require proportionally larger basis/grid resolution — a benchmark pattern repeatedly used to validate new numerical eigenvalue solvers against the triangular potential's exact solution.

---

## 5. Physical Applications Requiring Eigenvalue Evaluation

### 5.1 MOSFET inversion layers and semiconductor heterostructures

The dominant application of the triangular-potential eigenvalue problem is the **quantization of the two-dimensional electron (or hole) gas** at a semiconductor–oxide or semiconductor–semiconductor interface (Si MOSFETs, GaAs/AlGaAs heterojunctions, SiC MOSFETs). To first order, the confining conduction-band bending near the interface is approximated as linear (triangular), and the eigenvalues

$$E_n = \left[\frac{e^2\hbar^2 F^2}{2m^*}\right]^{1/3} a_n$$

give the quantized subband energies that determine the sheet carrier density, gate capacitance–voltage characteristics, and channel mobility. Because the true self-consistent potential (from the coupled Schrödinger–Poisson system) deviates from a pure triangle at large $x$ and near the interface (due to wavefunction penetration into the oxide/barrier, image-charge effects, and non-parabolicity), most modern treatments:

- solve the **triangular-well problem analytically** as a zeroth-order/benchmark estimate, and
- solve the **full self-consistent Schrödinger–Poisson problem numerically** (finite difference/finite element, with iterative or Newton-based self-consistency) for quantitative device modeling, often incorporating boundary conditions that allow finite wavefunction penetration into the gate dielectric rather than an idealized infinite wall.

### 5.2 Quantum-confined nanostructures with triangular geometry

Beyond the 1D linear-potential problem, "triangular potential" also refers to 2D/3D structures with **triangular confinement geometry** (equilateral or right-triangular cross-section quantum wires, triangular quantum dots, e.g. in hexagonal boron nitride). These are geometrically distinct problems (2D Helmholtz/Schrödinger eigenproblems on a triangular domain, solved exactly via Lamé's 1852 method for the equilateral triangle, or numerically via finite elements for self-consistent 2D wires) but are frequently discussed alongside the 1D linear-triangular-well problem in the broader "triangular potential" literature and are included here for completeness.

### 5.3 Neutron quantum states in gravity ("quantum bouncer") and cold-atom systems

The vertical bouncing motion of ultracold neutrons above a horizontal mirror under gravity is exactly the semi-infinite triangular-well problem with $F=mg$. This system (studied experimentally in the GRANIT and qBounce experiments) provides one of the cleanest physical realizations of the Airy-function eigenvalue spectrum and has motivated detailed theoretical work on self-adjoint extensions and boundary conditions at the mirror, sum rules for Airy zeros, and precision tests of gravity at short distances.

### 5.4 Semiclassical/mathematical physics benchmarking

Because the connection-formula matching via Airy functions is exact for a linear potential, the triangular well (including its imaginary/$\mathcal{PT}$-symmetric generalization $V(ix)=igx$) is routinely used as an analytically tractable calibration case for testing higher-order WKB approximations, uniform asymptotic methods, and semiclassical quantization schemes intended for more complicated (non-solvable) potentials.

### 5.5 Quarkonium and other power-law potential spectroscopy

The linear potential $V(r)=\sigma r$ (radial version, with $\ell=0$) appears as the confining term in the **Cornell potential** for heavy-quark bound states (charmonium, bottomonium) in particle physics, where its exactly known Airy-zero spectrum serves as a benchmark for basis-expansion, hypervirial, and shooting-method solutions of the more general linear + Coulomb radial Schrödinger equation.

---

## 6. Summary of Methods and Their Trade-offs

| Method | Exactness | Typical use | Key limitation |
|---|---|---|---|
| Airy-function analytic solution | Exact | Pure semi-infinite/symmetric triangular well | Not applicable once potential deviates from strictly linear |
| WKB / Bohr–Sommerfeld | Asymptotically exact for linear $V$ | Benchmarking semiclassical methods; quick estimates | Requires care with connection-formula phase at hard walls |
| Shooting method | Numerically exact (up to tolerance) | Finite/truncated wells, general 1D potentials | Sensitive to shooting-parameter tuning near high $n$ |
| Finite-difference / finite-element | Numerically exact (up to grid resolution) | Self-consistent Schrödinger–Poisson device simulation | Computational cost; grid convergence needed for higher states |
| Basis-expansion / diagonalization | Convergent with basis size | General potentials, quarkonium spectroscopy | Slower convergence for higher excited states |
| Variational (trial wavefunction) | Approximate (upper bound) | Fast self-consistent iteration in device simulators | Systematic error depends on trial-function flexibility |

---

## 7. Bibliography

### 7.1 Foundational / analytic treatments

1. Vallée, O. & Soares, M. *Airy Functions and Applications to Physics*, Imperial College Press / World Scientific (2010 revised ed.). — Standard reference on Airy-function theory and its use in the triangular-potential eigenvalue problem.
2. Flügge, S. *Practical Quantum Mechanics*, Springer (1971/1999). — Classic worked solution of the linear-potential (triangular-well) bound-state problem.
3. Vallée, O., "Comment on the infinite square well with a linear perturbation," *Am. J. Phys.* (various editions discuss the triangular well and Airy connection).
4. Gordon, J. P., "Exact Solution for the Linear Potential", and related pedagogical papers on the Airy-function solution to $V(x)=F|x|$.
5. Landau, L. D. & Lifshitz, E. M., *Quantum Mechanics: Non-Relativistic Theory*, Pergamon Press — treats WKB connection formulas via the linear-potential (Airy) turning-point problem, the canonical derivation reproduced in nearly all subsequent textbook treatments.

### 7.2 Textbook/lecture-note treatments (WKB and Airy matching)

6. University of Washington (Seattle), *Physics 541 Lecture Notes: The WKB Method* and *WKB Method: Solved Problems* — derives the WKB bound-state quantization for $V(x)=mgx$ (triangular well) via Airy-function connection formulas. https://faculty.washington.edu/seattle/physics541/14text.pdf ; https://faculty.washington.edu/seattle/physics541/14solved.pdf
7. University of Texas at Austin, *WKB Approximation Lecture Notes* (Vadim, PHYS course), discussion of Airy-function turning-point matching. https://web2.ph.utexas.edu/~vadim/Classes/2023f/WKB.pdf
8. Cvitanović, P. et al., *Chapter 32: WKB Quantization*, ChaosBook lecture notes, Georgia Tech. https://cns.gatech.edu/~predrag/courses/PHYS-6124-10/WKB.pdf
9. University of Tennessee, *WKB Approximation* course notes (bound states, Airy asymptotics). http://electron6.phys.utk.edu/qm1/modules/m3/wkb.htm

### 7.3 Semiconductor / MOSFET inversion-layer applications

10. Gehring, A., *PhD Thesis, Section 3.6.1: "Eigenvalues of a Triangular Energy Well"*, Institute for Microelectronics, TU Wien. https://www.iue.tuwien.ac.at/phd/gehring/node54.html — Direct treatment of MOSFET inversion-layer triangular-well eigenvalues via Airy zeros, with normalization constant derivation.
11. nextnano GmbH, *"3.20.15. Triangular well" — nextnano³ Tutorial Documentation*. https://www.nextnano.com/docu/nextnano3/tutorials/nnp/1D_triangular_well.html — Numerical (finite-difference) solution of the triangular well compared against the analytic Airy-zero formula, including the WKB large-$n$ approximation for $c_n$.
12. Stern, F. & Howard, W. E., "Properties of Semiconductor Surface Inversion Layers in the Electric Quantum Limit," *Phys. Rev.* **163**, 816 (1967). — Foundational paper on quantization of MOSFET inversion layers, self-consistent Schrödinger–Poisson solution and the triangular-well approximation.
13. Stern, F., "Self-Consistent Results for n-Type Si Inversion Layers," *Phys. Rev. B* **5**, 4891 (1972). — Numerical self-consistent solution benchmarked against the triangular-well approximation.
14. Ando, T., Fowler, A. B., & Stern, F., "Electronic properties of two-dimensional systems," *Rev. Mod. Phys.* **54**, 437 (1982). — Comprehensive review including triangular-well subband quantization, variational and self-consistent methods.
15. Various authors (cited collectively as [161–164] in Gehring's thesis) on linear approximations to the MOSFET conduction-band edge; representative of the broader device-physics literature using the triangular approximation.
16. "On the use of appropriate boundary conditions to calculate the normalized wave functions in the inversion layers of MOSFETs with ultra-thin gate oxides," *Solid-State Electronics* (2001). https://www.sciencedirect.com/science/article/abs/pii/S0038110100001155 — Discusses wavefunction-penetration corrections to the idealized infinite-wall triangular model.
17. "Anomalous conduction band fluctuation in silicon carbide metal-oxide-semiconductor structures... combined with self-consistent numerical calculations," arXiv:1904.08574. — Self-consistent Schrödinger–Poisson subband calculation in SiC MOSFETs.
18. "Electrical operation of hole spin qubits in planar MOS silicon quantum dots," arXiv:2309.12243 — Uses infinite-square-well basis expansion for the triangular confinement direction in a self-consistent variational scheme.
19. "Spin-orbit interactions in inversion-asymmetric 2D hole systems: a variational analysis," arXiv:1604.08759 — Variational solution of the self-consistent triangular-like confining potential at a heterojunction.
20. "Patterned backgating using single-sided mask aligners...," arXiv:0807.0117 — Self-consistent Poisson–Schrödinger solution for layered heterostructures with near-triangular confinement.
21. "Phase separation from electron confinement at oxide interfaces," arXiv:1506.04777 — Numerical self-consistent electronic well calculation (Appendix), triangular-like confinement at oxide interfaces.
22. Springer, *Journal of Computational Electronics* article on self-consistent quantum-corrected Monte Carlo MOSFET simulation using 1D Schrödinger solutions along the channel. https://link.springer.com/article/10.1023/B:JCEL.0000011406.20864.06

### 7.4 Numerical/finite-element/finite-difference generalizations

23. Gil-Corrales, J. A., Vinasco, J. A., Radu, A., Restrepo, R. L., Morales, A. L., Mora-Ramos, M. E., & Duque, C. A., "Self-Consistent Schrödinger–Poisson Study of Electronic Properties of GaAs Quantum Well Wires with Various Cross-Sectional Shapes," *Nanomaterials* **11**, 1219 (2021). DOI: 10.3390/nano11051219. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8147977/ — Finite-element self-consistent solution for triangular (and other) cross-section quantum wires.
24. Duo, S. & Zhang, Y., "Computing the ground and first excited states of the fractional Schrödinger equation in an infinite potential well," arXiv:1405.0409 — Numerical eigenvalue methods benchmarked against solvable well potentials, methodologically relevant to triangular-well numerics.

### 7.5 Pedagogical worked solutions

25. Suzuki, T., "A particle confined within a triangular potential well: Airy function" (Physics 421/422 course notes), Binghamton University. https://bingweb.binghamton.edu/~suzuki/QuantumMechanicsFiles/13-6%20Airy%20function%20for%20triangular%20potential.pdf — Full derivation with Mathematica-based numerical evaluation of Airy zeros and wavefunctions, referencing Townsend's *A Modern Quantum Mechanics*.
26. Townsend, J. S., *A Modern Approach to Quantum Mechanics*, 2nd ed., University Science Books (2012), Problems 6.9–6.10. — Standard textbook problem set on the triangular potential well.
27. "A Particle Confined Within A Triangular Potential Well: Airy Function," lecture document. https://www.scribd.com/document/530843498/Airyfunctionfortriangularpotential12-29-20
28. Physics Forums thread, "Electron in a triangular quantum well with triangular barrier" — practical discussion of numerical (MATLAB/Python) solution strategies. https://www.physicsforums.com/threads/electron-in-a-triangular-quantum-well-with-triangular-barrier.979406/

### 7.6 Airy-zero asymptotics and precision numerics

29. Olver, F. W. J., *Asymptotics and Special Functions*, Academic Press / A K Peters (1997 reprint). — Definitive reference for asymptotic expansions of Airy function zeros used in the large-$n$ eigenvalue formula.
30. DLMF (NIST Digital Library of Mathematical Functions), Chapter 9: "Airy and Related Functions" — standard tabulated values and asymptotic series for Airy zeros, https://dlmf.nist.gov/9
31. "Uniform asymptotic expansions for the zeros of Bessel functions," arXiv:2310.16016 — Includes detailed treatment of Airy zero asymptotics used as an ingredient.
32. "Uniform asymptotic expansions for the zeros of parabolic cylinder functions," arXiv:2407.13936 — Appendix on Airy-function zero asymptotics with high-order correction terms.
33. "Breakdown of Quantum Chaos in the Staggered-Field XXZ Chain: Confinement and Meson Formation," arXiv:2511.14847 — Uses and tabulates Airy zeros with asymptotic formula in a many-body-physics context.
34. "Lévy flights in inhomogeneous environments," arXiv:0907.0102 — Appendix derivation of approximate analytic expressions for Airy function zeros.
35. "Constraints on Airy function zeros from quantum-mechanical sum rules," https://www.researchgate.net/publication/45928441 — Sum rules and generalized boundary-condition analysis (relevant to the qBounce/neutron-in-gravity realization of the triangular well).

### 7.7 WKB/semiclassical benchmarking using the (possibly complex) linear potential

36. Bender, C. M. & collaborators, "WKB Analysis of PT-Symmetric Sturm–Liouville Problems," arXiv:1201.1234 — Uses the Airy potential $V(ix)=ix$ as an exactly solvable benchmark for higher-order WKB/phase-integral formulas.
37. "Airy function" (fixed-point quantization / fractal Weyl-type analysis of Airy zeros as a solvable spectral problem), arXiv:math-ph/9811001.
38. "Inverse problem in energy-dependent potentials using semiclassical methods," arXiv:2404.11478 — General WKB quantization-condition framework applicable to (and illustrated with) linear/triangular-type potentials.
39. "The Modified Airy Function Approximation Applied to the Double-Well Potential," arXiv:2502.15063 — Uses Airy-function matching (as in the triangular well) to construct improved semiclassical wavefunctions near turning points.

### 7.8 Related power-law / linear-potential spectroscopy (algebraic and basis-expansion methods)

40. "Algebraic approach to the spectral problem for the Schrödinger equation with power potentials," arXiv:hep-ph/9705421 — Explicit numerical comparison of matrix-diagonalization eigenvalues against exact Airy-zero eigenvalues for the linear potential $V(r)=r$ (radial triangular well), with detailed convergence tables.
41. "Techniques for solving bound state problems" (MKN-type basis expansion for linear/Cornell-type potentials), arXiv:hep-ph/0010243 — Comparison of basis-expansion (Olsson basis) eigenvalues with exact Airy zeros for the nonrelativistic linear potential.
42. "MKN Theory of Bound States," arXiv:hep-ph/0103035 — Exact and numerical treatment of the nonrelativistic radial Schrödinger equation with a linear potential via reduction to the Airy equation.

### 7.9 Triangular-domain (2D) confinement (related but geometrically distinct problem)

43. Lamé, G., *Leçons sur la théorie mathématique de l'élasticité des corps solides*, Paris (1852) — original exact solution of the Helmholtz/Schrödinger eigenproblem on an equilateral triangular domain.
44. "Wannier Excitons Confined in Hexagonal Boron Nitride Triangular Quantum Dots," arXiv:2209.03331 — Reviews and compares analytic solutions for the equilateral triangular hard-wall well.
45. "Wave functions for high-symmetry, thin microstrip antennas and two-dimensional quantum boxes," arXiv:2108.07916 — Even/odd eigenfunction construction for the equilateral triangular infinite well.
46. "Polymer representation of the Bianchi IX Cosmology in the Misner variables," arXiv:1907.12083 — Discusses the equilateral triangular-well eigenvalue problem in a cosmological quantization context (Misner's approach), comparing to the square-well approximation.

---

## 8. Concluding Remarks

The triangular potential occupies a unique position in quantum mechanics: it is simultaneously exactly solvable (via Airy functions), semiclassically exact (the WKB connection formulas are not approximations but identities for this potential), and of direct, ongoing importance in condensed-matter device physics (MOSFET and heterostructure inversion layers), precision tests of gravity (neutron quantum bouncing), and semiclassical/mathematical-physics methodology (calibration of higher-order WKB and uniform asymptotic techniques). Numerical methods — shooting, finite-difference, finite-element, and basis-expansion diagonalization — are indispensable once the idealized linear form is replaced by a realistic, self-consistently determined confining potential, and the exactly known Airy-zero spectrum of the idealized triangular well continues to serve as the standard benchmark against which such numerical eigensolvers are validated.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Triangular potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
