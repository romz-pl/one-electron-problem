# The One-Electron Problem in Quantum Chemistry

## 1. Overview and Motivation

The **one-electron problem** refers to the class of quantum-mechanical problems describing the behavior of a single electron moving in the electrostatic field of one or more fixed (or slowly moving) nuclei. It is the simplest nontrivial problem in molecular quantum mechanics and serves as the conceptual and computational backbone of quantum chemistry for several reasons:

- It is the only class of *electronic* structure problem that can be solved essentially exactly (analytically for atoms, semi-analytically or numerically for diatomics).
- The molecular orbitals used in essentially all mean-field and post-mean-field methods (Hartree–Fock, Kohn–Sham DFT, configuration interaction, coupled cluster) are themselves eigenfunctions of an *effective* one-electron Hamiltonian.
- Many-electron molecular properties (energies, dipole moments, polarizabilities, spectroscopic constants) are built up from sums and products of one-electron integrals evaluated over such one-electron functions.
- It provides the exactly solvable reference systems (hydrogen atom, hydrogen molecular ion) against which approximate many-electron methods are calibrated.

## 2. Mathematical Formulation

### 2.1 The One-Electron Hamiltonian

Within the Born–Oppenheimer approximation, the nuclei are treated as fixed point charges. The Hamiltonian for a single electron of mass $m_e$ and charge $-e$ moving in the field of $M$ fixed nuclei with charges $Z_A e$ located at positions $\mathbf{R}_A$ is:

$$
\hat{h}(\mathbf{r}) = -\frac{\hbar^2}{2m_e}\nabla^2 - \sum_{A=1}^{M} \frac{Z_A e^2}{4\pi\epsilon_0 |\mathbf{r}-\mathbf{R}_A|}
$$

In atomic units ($\hbar = m_e = e = 4\pi\epsilon_0 = 1$):

$$
\hat{h}(\mathbf{r}) = -\frac{1}{2}\nabla^2 - \sum_{A=1}^{M} \frac{Z_A}{|\mathbf{r}-\mathbf{R}_A|}
$$

The time-independent Schrödinger equation for this system is:

$$
\hat{h}(\mathbf{r})\,\psi(\mathbf{r}) = \varepsilon\,\psi(\mathbf{r})
$$

This is the defining equation of the one-electron problem. Its solutions $\psi(\mathbf{r})$ are **one-electron wavefunctions**, commonly called **orbitals** in the chemistry context, and $\varepsilon$ are the corresponding **orbital energies**.

### 2.2 Special Cases by Number of Centers

| System | $M$ (nuclei) | Solvability | Canonical example |
|---|---|---|---|
| Hydrogenic atom | 1 | Exact, closed form | H, He$^+$, Li$^{2+}$ |
| One-electron diatomic | 2 | Exact via prolate spheroidal coordinates (special functions) | H$_2^+$, HeH$^{2+}$ |
| One-electron polyatomic | $\geq 3$ | No closed form; numerical/basis-set methods required | H$_3^{2+}$ |

## 3. The Hydrogenic Atom ($M=1$)

### 3.1 Separation of Variables

With a single nucleus of charge $Z$ at the origin, spherical symmetry allows separation in spherical polar coordinates $(r,\theta,\phi)$:

$$
\psi_{n\ell m}(r,\theta,\phi) = R_{n\ell}(r)\, Y_\ell^m(\theta,\phi)
$$

where $Y_\ell^m$ are spherical harmonics (angular momentum eigenfunctions) and $R_{n\ell}(r)$ are radial functions expressed in terms of **associated Laguerre polynomials**:

$$
R_{n\ell}(r) = -\sqrt{\left(\frac{2Z}{n}\right)^3 \frac{(n-\ell-1)!}{2n[(n+\ell)!]}} \; e^{-Zr/n}\left(\frac{2Zr}{n}\right)^{\ell} L_{n-\ell-1}^{2\ell+1}\!\left(\frac{2Zr}{n}\right)
$$

### 3.2 Quantum Numbers and Energies

- Principal quantum number: $n = 1,2,3,\dots$
- Angular momentum (azimuthal) quantum number: $\ell = 0,1,\dots,n-1$ (labeled s, p, d, f, …)
- Magnetic quantum number: $m = -\ell,\dots,+\ell$
- Spin quantum number: $m_s = \pm\tfrac12$ (added post hoc; the non-relativistic spatial Hamiltonian is spin-independent)

The energy depends only on $n$ (accidental/Coulombic degeneracy):

$$
\varepsilon_n = -\frac{Z^2}{2n^2}\quad\text{(hartree)}
$$

giving the characteristic degeneracy $n^2$ (or $2n^2$ including spin) per shell — the origin of the aufbau shell structure exploited throughout chemistry.

### 3.3 Physical/Chemical Significance

- Defines **atomic orbitals** (1s, 2s, 2p, 3d, …) used as the qualitative and often quantitative building blocks of bonding theory (LCAO).
- Basis for **Slater-type orbitals (STOs)** and, through fitting, **Gaussian-type orbitals (GTOs)** used in virtually all quantum chemistry software.
- Underpins periodic trends: orbital energies, radii, ionization energies, electronegativity concepts.

## 4. The One-Electron Diatomic Problem: H$_2^+$ ($M=2$)

### 4.1 The Born–Oppenheimer Electronic Hamiltonian

For two fixed nuclei A and B separated by distance $R$:

$$
\hat{h} = -\frac{1}{2}\nabla^2 - \frac{Z_A}{r_A} - \frac{Z_B}{r_B}
$$

### 4.2 Exact Separability in Prolate Spheroidal Coordinates

Unlike general polyelectronic or polyatomic problems, H$_2^+$ is **exactly separable** using confocal elliptic (prolate spheroidal) coordinates:

$$
\mu = \frac{r_A + r_B}{R}, \qquad \nu = \frac{r_A - r_B}{R}, \qquad \phi \ (\text{azimuthal angle about the internuclear axis})
$$

with $1\le\mu<\infty$, $-1\le\nu\le1$, $0\le\phi<2\pi$. The Schrödinger equation separates into three ordinary differential equations, one each in $\mu$, $\nu$, $\phi$, connected through separation constants. The resulting solutions are expressed via **spheroidal wave functions** and cannot generally be written in elementary closed form, but they are obtainable to arbitrary numerical precision — this is what is meant by "exact" for H$_2^+$: exact in the sense of being an exactly solvable model (like the 3-body Kepler problem in classical mechanics), not necessarily expressible in elementary functions.

### 4.3 Molecular Orbitals from H$_2^+$

The eigenfunctions are classified by:
- $\lambda$ = $|m|$, the projection of angular momentum along the internuclear axis, labeled $\sigma$ ($\lambda=0$), $\pi$ ($\lambda=1$), $\delta$ ($\lambda=2$), …
- Parity under inversion through the bond midpoint: gerade ($g$) / ungerade ($u$)

This yields the familiar molecular-orbital diagram labels: $1\sigma_g, 1\sigma_u, 2\sigma_g, 2\sigma_u, 1\pi_u, 1\pi_g,\dots$ — the direct ancestor of qualitative MO diagrams taught for all diatomics.

### 4.4 LCAO Approximation

Because exact spheroidal solutions are cumbersome, chemistry universally approximates H$_2^+$-type orbitals as **linear combinations of atomic orbitals (LCAO)**:

$$
\psi_\pm = \frac{1}{\sqrt{2(1\pm S)}}\left(\chi_A \pm \chi_B\right)
$$

where $\chi_A,\chi_B$ are (typically 1s) atomic orbitals on centers A and B, and

$$
S = \langle \chi_A|\chi_B\rangle
$$

is the **overlap integral**. This introduces the bonding ($\psi_+$, lower energy) and antibonding ($\psi_-$, higher energy) orbital concept — the single most important qualitative construct in molecular orbital theory — directly from the one-electron problem.

### 4.5 The Three Fundamental One-Electron Integral Types

Solving H$_2^+$ (exactly or via LCAO) requires evaluating three canonical integral classes that recur throughout all of quantum chemistry:

1. **Overlap integral**: $S_{AB} = \int \chi_A^\ast \chi_B \, d\mathbf{r}$
2. **One-electron (core/kinetic+nuclear-attraction) integral**: $h_{AB} = \int \chi_A^\ast \hat{h}\, \chi_B \, d\mathbf{r}$, decomposable into kinetic energy and nuclear attraction pieces
3. **Two-center nuclear attraction integral**: $\int \chi_A^\ast \frac{1}{r_C}\chi_B\, d\mathbf{r}$

These are the prototypes of the one- and two-electron integrals ($S_{\mu\nu}$, $h_{\mu\nu}$/core-Hamiltonian, and eventually two-electron repulsion integrals $(\mu\nu|\lambda\sigma)$ in the many-electron case) that dominate the computational cost of ab initio methods.

## 5. Role of the One-Electron Problem in Many-Electron Theory

Although "the one-electron problem" strictly denotes systems with exactly one electron, its mathematical machinery is the scaffold for **all** mean-field treatments of many-electron molecules:

### 5.1 Hartree–Fock Theory
The Hartree–Fock equations reduce the many-body problem to a set of coupled **effective one-electron eigenvalue problems** (the Fock equations):

$$
\hat{f}(\mathbf{r}_1)\,\psi_i(\mathbf{r}_1) = \varepsilon_i\, \psi_i(\mathbf{r}_1)
$$

where the Fock operator $\hat{f} = \hat{h} + \sum_j\left(2\hat{J}_j - \hat{K}_j\right)$ contains the bare one-electron Hamiltonian $\hat h$ (identical in form to Section 2.1) plus mean-field Coulomb ($\hat J$) and exchange ($\hat K$) operators representing the averaged effect of all other electrons. The problem is formally one-electron in structure but self-consistent (the effective potential depends on the solutions themselves), requiring the **Self-Consistent Field (SCF)** iterative procedure.

### 5.2 Kohn–Sham Density Functional Theory
Analogously, Kohn–Sham DFT maps the interacting many-electron problem onto a fictitious system of non-interacting electrons obeying one-electron-like equations:

$$
\left[-\frac{1}{2}\nabla^2 + v_{\text{eff}}(\mathbf{r})\right]\phi_i(\mathbf{r}) = \varepsilon_i\,\phi_i(\mathbf{r})
$$

with $v_{\text{eff}}$ including the nuclear attraction, Hartree (classical Coulomb), and exchange-correlation potentials.

### 5.3 The Core Hamiltonian in ab initio Methods
In practical LCAO-based calculations (HF, post-HF, DFT), the true one-electron Hamiltonian $\hat h$ from Section 2.1 appears directly as the **core Hamiltonian matrix**:

$$
h_{\mu\nu} = \int \chi_\mu^\ast(\mathbf{r})\left[-\frac{1}{2}\nabla^2 - \sum_A \frac{Z_A}{|\mathbf{r}-\mathbf{R}_A|}\right]\chi_\nu(\mathbf{r})\, d\mathbf{r}
$$

evaluated over the chosen basis set $\{\chi_\mu\}$ (Gaussian- or Slater-type functions). This matrix is the first quantity built in every SCF calculation and represents the exact one-electron physics before any electron-electron mean-field correction is added.

### 5.4 Basis Sets as Approximate Solutions to One-Electron Problems
Contracted Gaussian basis sets (STO-3G, Pople-style 6-31G*, Dunning correlation-consistent cc-pVXZ, etc.) are constructed by fitting to solutions of one-electron atomic problems (numerically exact Hartree–Fock atomic orbitals) so that they reproduce the correct nodal structure and asymptotic decay of true one-electron wavefunctions as closely as possible with a small number of primitive functions.

## 6. Molecular Properties Derived from One-Electron Quantities

Many measurable and computed molecular properties are, at leading order, **one-electron properties** — expectation values of one-electron operators over the (many-electron) wavefunction, which reduce to sums over occupied orbitals in a mean-field picture:

| Property | Operator $\hat{O}$ | Expression |
|---|---|---|
| Electron density | $\hat{\rho}(\mathbf{r}) = \sum_i \delta(\mathbf{r}-\mathbf{r}_i)$ | $\rho(\mathbf{r}) = \sum_i n_i |\psi_i(\mathbf{r})|^2$ |
| Dipole moment | $\hat{\boldsymbol{\mu}} = -\sum_i \mathbf{r}_i + \sum_A Z_A \mathbf{R}_A$ | $\boldsymbol{\mu} = -\int \mathbf{r}\,\rho(\mathbf{r})\,d\mathbf{r} + \sum_A Z_A \mathbf{R}_A$ |
| Kinetic energy | $\hat{T} = -\tfrac12\sum_i \nabla_i^2$ | $T = \sum_i n_i \langle\psi_i|-\tfrac12\nabla^2|\psi_i\rangle$ |
| Electric field gradient / NMR shielding | one-electron spatial derivative operators | orbital-summed |
| Orbital (Koopmans) ionization energies | $\hat h$ / Fock eigenvalues | $\varepsilon_i \approx -\text{IE}_i$ |
| Spin densities (UHF/UKS) | $\hat\rho^\alpha - \hat\rho^\beta$ | orbital-summed, spin-resolved |
| Molecular electrostatic potential (MEP) | one-electron Coulomb operator | $V(\mathbf{r}) = \sum_A \frac{Z_A}{|\mathbf{r}-\mathbf{R}_A|} - \int \frac{\rho(\mathbf{r}')}{|\mathbf{r}-\mathbf{r}'|}d\mathbf{r}'$ |

These stand in contrast to genuinely **two-electron properties** (electron correlation energy, exchange-correlation energy contributions beyond mean field, second-order response properties involving electron–electron coupling), which require explicit treatment of electron pairs and cannot be reduced to single-orbital sums without approximation.

## 7. Relativistic and Extended One-Electron Problems

For heavier elements or high-precision spectroscopy, the non-relativistic one-electron Hamiltonian is extended:

- **Dirac one-electron Hamiltonian**: replaces the Schrödinger kinetic energy operator with the Dirac operator, giving four-component spinor solutions and naturally incorporating spin–orbit coupling; exactly solvable for hydrogenic atoms (Dirac equation for the Coulomb potential).
- **Douglas–Kroll–Hess (DKH) and Zeroth-Order Regular Approximation (ZORA)**: two-component approximate reductions of the Dirac one-electron problem used for relativistic corrections in heavy-element quantum chemistry while retaining a one-electron-operator structure compatible with standard quantum chemistry codes.
- **Finite nuclear size / QED corrections (Lamb shift)**: refinements to the point-nucleus Coulomb potential in the one-electron Hamiltonian for the most precise atomic/molecular calculations.

## 8. Numerical and Computational Methods for the One-Electron Problem

| Method | Applicability | Notes |
|---|---|---|
| Analytic separation (spherical/spheroidal coordinates) | Atoms, diatomics | Exact but limited to 1–2 centers |
| Basis-set expansion (LCAO) | Any molecule | Reduces differential equation to a generalized matrix eigenvalue problem $\mathbf{h}\mathbf{c} = \varepsilon\,\mathbf{S}\mathbf{c}$ |
| Direct numerical grid/finite-difference/finite-element solution | Atoms, small diatomics, benchmarking | High accuracy, poor scalability to polyatomics |
| Perturbation theory (e.g., for weak external fields) | Property calculations (polarizability, shielding) | Builds on unperturbed one-electron solutions |
| Variational method | General | Standard route to approximate one-electron (and Fock/Kohn–Sham) eigenstates via basis-set diagonalization |

The matrix formulation

$$
\mathbf{h}\,\mathbf{c}_i = \varepsilon_i\, \mathbf{S}\,\mathbf{c}_i
$$

(a **generalized eigenvalue problem** built from the core Hamiltonian matrix $\mathbf h$ and overlap matrix $\mathbf S$) is the universal computational endpoint of the one-electron problem in quantum chemistry software, and is solved directly for true one-electron systems, or iteratively (self-consistently) with $\mathbf h$ replaced by the Fock or Kohn–Sham matrix for many-electron systems.

## 9. Summary

The one-electron problem — an electron in the field of fixed nuclear charges — is exactly solvable for one center (hydrogenic atoms, closed-form Laguerre/spherical-harmonic solutions) and exactly separable for two centers (H$_2^+$, spheroidal coordinates), but requires basis-set/numerical approximation for three or more centers. Its significance in quantum chemistry extends far beyond these literal one-electron species:

1. It defines the **atomic and molecular orbital concept** (bonding/antibonding, $\sigma/\pi$ classification, nodal structure).
2. It supplies the **core Hamiltonian** and basis-function machinery used in every mean-field (HF/DFT) and correlated method for many-electron molecules.
3. Many key **molecular properties** (density, dipole moment, orbital energies, electrostatic potential) are one-electron properties, computable as orbital sums.
4. It is the natural point of entry for **relativistic corrections** (Dirac equation, DKH, ZORA) in modern quantum chemistry.
5. It generates the **generalized matrix eigenvalue problem** that is the computational core of essentially all electronic structure software.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive description of the one-electron problem in quantum chemistry for describing molecular properties. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
