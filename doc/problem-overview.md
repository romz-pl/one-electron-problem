# The One-Electron Problem in Quantum Mechanics

## 1. Introduction and Scope

The "one-electron problem" refers to the quantum-mechanical treatment of a single electron bound to a fixed (or nearly fixed) positively charged nucleus, most fundamentally the hydrogen atom, but generalized to hydrogenic (hydrogen-like) ions such as $\text{He}^+$, $\text{Li}^{2+}$, and more generally any ion with a single remaining electron and nuclear charge $Ze$. This is one of the few problems in quantum mechanics that is exactly solvable in closed analytic form, and it plays a foundational role because:

- It is the simplest realistic atomic system, and its solution underlies the qualitative structure of the entire periodic table via the orbital approximation.
- It provides the quantum numbers ($n$, $\ell$, $m$, spin) and the notion of atomic orbitals used throughout chemistry and physics.
- It is the testing ground for relativistic corrections, QED effects (Lamb shift), and hyperfine structure.
- Its degeneracies and symmetries (the "accidental" $SO(4)$ degeneracy) reveal deep connections between geometry and dynamics (Runge–Lenz vector, dynamical symmetry).

This document proceeds from the non-relativistic Schrödinger treatment through relativistic corrections, fine and hyperfine structure, external field effects, and modern refinements.

---

## 2. Physical Setup

Consider a nucleus of charge $+Ze$ (mass $M$) and an electron of charge $-e$ (mass $m_e$) interacting via the Coulomb potential. In SI (or Gaussian) units the potential energy is

$$
V(r) = -\frac{Ze^2}{4\pi\epsilon_0 r}
$$

(Gaussian units: $V(r) = -Ze^2/r$.)

### 2.1 Reduction to a One-Body Problem

The full two-body Hamiltonian,

$$
H = -\frac{\hbar^2}{2m_e}\nabla_e^2 - \frac{\hbar^2}{2M}\nabla_N^2 + V(|\mathbf{r}_e - \mathbf{r}_N|),
$$

separates into center-of-mass motion (a free particle of total mass $M + m_e$) and relative motion of a fictitious particle with the **reduced mass**

$$
\mu = \frac{m_e M}{m_e + M}.
$$

For hydrogen, $\mu \approx m_e (1 - m_e/M) \approx 0.99945\, m_e$, a small but measurable correction (isotope shift between H and deuterium is a direct consequence). The relative-motion Hamiltonian is then

$$
H = -\frac{\hbar^2}{2\mu}\nabla^2 - \frac{Ze^2}{4\pi\epsilon_0 r}.
$$

---

## 3. Non-Relativistic Solution (Schrödinger Equation)

### 3.1 Separation of Variables

Because $V(r)$ is spherically symmetric, the Laplacian is written in spherical coordinates $(r,\theta,\phi)$ and the wavefunction is separated as

$$
\psi(r,\theta,\phi) = R(r)\, Y_\ell^m(\theta,\phi).
$$

The angular part $Y_\ell^m$ are the **spherical harmonics**, eigenfunctions of $L^2$ and $L_z$:

$$
L^2 Y_\ell^m = \hbar^2 \ell(\ell+1) Y_\ell^m, \qquad L_z Y_\ell^m = \hbar m\, Y_\ell^m,
$$

with $\ell = 0,1,2,\dots$ and $m = -\ell,\dots,\ell$.

### 3.2 Radial Equation

Substituting $u(r) = rR(r)$ yields the effective 1D Schrödinger equation

$$
-\frac{\hbar^2}{2\mu}\frac{d^2u}{dr^2} + \left[-\frac{Ze^2}{4\pi\epsilon_0 r} + \frac{\hbar^2 \ell(\ell+1)}{2\mu r^2}\right] u(r) = E\, u(r),
$$

where the second bracketed term is the **centrifugal barrier**.

### 3.3 Bound-State Energies

Requiring normalizability ($u \to 0$ as $r \to \infty$ and $u(0)=0$) quantizes the energy:

$$
E_n = -\frac{\mu Z^2 e^4}{2(4\pi\epsilon_0)^2 \hbar^2 n^2} = -\frac{Z^2}{n^2}\,\mathrm{Ry},
$$

where $n = 1, 2, 3,\dots$ is the **principal quantum number**, and the Rydberg energy is

$$
\mathrm{Ry} = \frac{\mu e^4}{2(4\pi\epsilon_0)^2\hbar^2} \approx 13.6057\ \text{eV (for } \mu \approx m_e\text{)}.
$$

Equivalently, defining the fine-structure constant $\alpha = e^2/(4\pi\epsilon_0 \hbar c)$,

$$
E_n = -\frac{1}{2}\mu c^2 \alpha^2 \frac{Z^2}{n^2}.
$$

For each $n$, the allowed orbital quantum numbers are $\ell = 0, 1, \dots, n-1$, and for each $\ell$, $m = -\ell,\dots,\ell$. The degeneracy of level $n$ (ignoring spin) is

$$
g_n = \sum_{\ell=0}^{n-1} (2\ell+1) = n^2,
$$

and including the two spin states of the electron, $2n^2$.

### 3.4 Radial Wavefunctions

The normalized bound-state radial functions involve **associated Laguerre polynomials** $L_{n-\ell-1}^{2\ell+1}$:

$$
R_{n\ell}(r) = -\sqrt{\left(\frac{2Z}{na_0}\right)^3 \frac{(n-\ell-1)!}{2n[(n+\ell)!]^3}}\; e^{-Zr/(na_0)} \left(\frac{2Zr}{na_0}\right)^{\ell} L_{n-\ell-1}^{2\ell+1}\!\left(\frac{2Zr}{na_0}\right),
$$

where the **Bohr radius** is

$$
a_0 = \frac{4\pi\epsilon_0 \hbar^2}{\mu e^2} \approx 0.529\ \text{\AA (for }\mu\approx m_e\text{)}.
$$

The full wavefunction is $\psi_{n\ell m}(r,\theta,\phi) = R_{n\ell}(r) Y_\ell^m(\theta,\phi)$, orthonormal:

$$
\int \psi_{n\ell m}^{\ast} \psi_{n'\ell'm'}\, d^3r = \delta_{nn'}\delta_{\ell\ell'}\delta_{mm'}.
$$

### 3.5 Ground State and Low-Lying Examples

- **Ground state** ($n=1,\ell=0,m=0$):
$$
\psi_{100}(r) = \frac{1}{\sqrt{\pi}}\left(\frac{Z}{a_0}\right)^{3/2} e^{-Zr/a_0}.
$$
- **First excited shell** ($n=2$): $2s$ (spherically symmetric, one radial node) and $2p$ ($\ell=1$, three orientations $m=-1,0,1$, angular nodal planes).

### 3.6 Nodal Structure

The radial function $R_{n\ell}$ has $n-\ell-1$ radial nodes; the angular part $Y_\ell^m$ has $\ell$ total angular nodes (a mix of conical and planar nodal surfaces depending on $m$). Total nodes = $n - 1$.

---

## 4. Algebraic / Symmetry Approach

### 4.1 The Runge–Lenz Vector

Classically, the Kepler problem possesses a conserved vector (the Laplace–Runge–Lenz vector) beyond angular momentum, responsible for the non-precessing elliptical orbits. Quantum mechanically, the symmetrized operator

$$
\mathbf{A} = \frac{1}{2\mu}\left(\mathbf{p}\times\mathbf{L} - \mathbf{L}\times\mathbf{p}\right) - Ze^2\,\frac{\mathbf{r}}{r}
$$

(units depending on convention) commutes with $H$, $[\mathbf{A}, H] = 0$, revealing a **hidden $SO(4)$ dynamical symmetry** for bound states (or $SO(3,1)$ for scattering states, $E(3)$ at threshold). This symmetry is precisely what explains the "accidental" $\ell$-degeneracy at fixed $n$ — degeneracy not required by the obvious rotational $SO(3)$ symmetry alone.

### 4.2 Algebraic Derivation of the Spectrum

Defining rescaled operators $\mathbf{M} = \mathbf{A}/\sqrt{-2\mu E}$ for bound states, one can form

$$
\mathbf{J}_1 = \frac{1}{2}(\mathbf{L}+\mathbf{M}), \qquad \mathbf{J}_2 = \frac{1}{2}(\mathbf{L}-\mathbf{M}),
$$

each satisfying independent $SU(2)$ angular momentum algebras. This reproduces the energy spectrum $E_n \propto -1/n^2$ purely algebraically (a method historically important, pioneered by Pauli before Schrödinger's wave-mechanical solution).

---

## 5. Alternative Solution Methods

- **Factorization / ladder operator method**: raising and lowering operators for $n$ and $\ell$, analogous to the harmonic oscillator treatment.
- **Path integral solution** (Duru–Kleinert transformation): the Coulomb path integral is solved by mapping to a 4D harmonic oscillator via the Kustaanheimo–Stiefel transformation, exploiting the same underlying group-theoretic connection between $SO(4,2)$ (Coulomb) and $Sp(8)$ (oscillator) dynamical groups.
- **Momentum-space solution** (Fock, 1935): Fourier transforming the Schrödinger equation, the bound states map onto spherical harmonics on a 4-sphere $S^3$, exposing the $SO(4)$ symmetry geometrically.
- **Supersymmetric quantum mechanics**: the radial Coulomb problem is a shape-invariant potential, solvable via SUSY QM ladder methods.

---

## 6. Continuum (Scattering) States

For $E > 0$, the spectrum is continuous, corresponding to unbound (ionized) electron trajectories (Coulomb scattering). The radial equation admits solutions expressible via **confluent hypergeometric functions** $_1F_1$, giving rise to **Coulomb wavefunctions** $F_\ell(\eta,\rho)$ and $G_\ell(\eta,\rho)$ (regular and irregular), where $\eta = -Ze^2\mu/(\hbar^2 k)$ is the Sommerfeld parameter. These underlie:

- The Rutherford scattering cross-section (correctly reproduced in the Born approximation and, remarkably, exactly by full quantum treatment).
- Photoionization cross-sections and radiative recombination.
- The unified treatment of bound and continuum states via the analytic continuation $n \to 1/i\eta$.

---

## 7. Relativistic Treatment

### 7.1 Fine Structure (Perturbative, from Dirac Reduction)

The non-relativistic Hamiltonian omits three same-order-in-$\alpha^2$ corrections, collectively producing **fine structure**:

1. **Relativistic kinetic energy correction**:
$$
H_{\rm rel} = -\frac{p^4}{8m_e^3c^2}.
$$

2. **Spin–orbit coupling**:
$$
H_{\rm SO} = \frac{1}{2m_e^2c^2}\frac{1}{r}\frac{dV}{dr}\, \mathbf{L}\cdot\mathbf{S}.
$$

3. **Darwin term** (relevant only for $\ell=0$, arising from *Zitterbewegung*):
$$
H_{\rm D} = \frac{\hbar^2}{8m_e^2c^2}\nabla^2 V = \frac{\pi\hbar^2 Ze^2}{2m_e^2c^2\epsilon_0}\,\delta^3(\mathbf{r}).
$$

Together, using the total angular momentum $\mathbf{J} = \mathbf{L}+\mathbf{S}$ with quantum number $j$, the fine-structure energy shift is

$$
\Delta E_{n j} = \frac{(\mu c^2)\, (Z\alpha)^4}{2 n^4}\left(\frac{n}{j+\tfrac12} - \frac{3}{4}\right).
$$

Levels are labeled spectroscopically $n\, {}^{2S+1}L_J$ (e.g., $2p_{1/2}$, $2p_{3/2}$), and fine structure lifts the $\ell$-degeneracy while states of the same $j$ (but different $\ell$) remain degenerate at this order — a residual degeneracy later broken by the Lamb shift.

### 7.2 Exact Dirac Equation Solution

The one-electron Coulomb problem is exactly solvable for the **Dirac equation** as well. The exact relativistic bound-state energies are

$$
E_{n,j} = m_e c^2 \left[1 + \left(\frac{Z\alpha}{n - (j+\tfrac12) + \sqrt{(j+\tfrac12)^2 - (Z\alpha)^2}}\right)^{2}\right]^{-1/2}.
$$

Expanding in powers of $Z\alpha$ reproduces the Bohr formula plus the fine-structure correction above. Dirac wavefunctions are 4-component bispinors involving both large and small components, with radial parts again expressed via confluent hypergeometric (or Whittaker) functions.

---

## 8. Beyond Dirac: QED and Nuclear Effects

### 8.1 Lamb Shift

Quantum electrodynamic effects — vacuum polarization and, dominantly, the electron's interaction with vacuum fluctuations of the electromagnetic field (self-energy) — split states with the same $n,j$ but different $\ell$ (e.g., $2s_{1/2}$ vs $2p_{1/2}$), which the pure Dirac equation leaves degenerate. This **Lamb shift** was historically pivotal in motivating the development of renormalized QED.

### 8.2 Hyperfine Structure

The interaction of the electron's magnetic moment with the nuclear magnetic moment (for nuclei with nonzero spin $I$, e.g., the proton) produces **hyperfine splitting**, characterized by the total angular momentum $\mathbf{F} = \mathbf{J} + \mathbf{I}$. The famous **21 cm hydrogen line** (ground-state hyperfine transition, $F=1 \to F=0$) is a landmark example, central to radio astronomy.

### 8.3 Nuclear Size and Recoil Effects

- **Finite nuclear size**: departure from a point-charge Coulomb potential slightly raises the energy of $s$-states (nonzero probability density at the origin); this is the leading effect probed in muonic hydrogen spectroscopy and the "proton radius puzzle."
- **Recoil corrections**: beyond the simple reduced-mass substitution, relativistic recoil terms (Salpeter correction) enter at higher order.

---

## 9. External Fields

### 9.1 Stark Effect (Electric Field)

An external uniform field $\mathbf{E} = E\hat z$ adds $H' = eEz$. Because the Coulomb problem separates in **parabolic coordinates** $(\xi,\eta,\phi)$ as well as spherical ones, the Stark effect for hydrogen is solvable to all orders in perturbation theory using parabolic quantum numbers $(n_1, n_2, m)$. The linear Stark effect (present because of the $n^2$-degeneracy) shifts energies as

$$
\Delta E = \frac{3}{2} n (n_1 - n_2)\, e E a_0 / Z,
$$

in contrast to hydrogenic-like systems without degeneracy, which show only a quadratic (polarizability-driven) Stark shift.

### 9.2 Zeeman Effect (Magnetic Field)

A uniform magnetic field couples to orbital and spin magnetic moments,

$$
H' = \frac{e}{2m_e}(\mathbf{L}+2\mathbf{S})\cdot\mathbf{B} + \frac{e^2 B^2}{8m_e}(x^2+y^2),
$$

producing the normal/anomalous Zeeman effect at weak field (good quantum numbers $j, m_j$) crossing over to the Paschen–Back regime at strong field (good quantum numbers $m_\ell, m_s$), and the diamagnetic (quadratic) term dominating at extreme field strengths relevant to, e.g., white dwarf and neutron star atmospheres.

---

## 10. Special / Extreme Cases and Generalizations

- **Hydrogenic ions**: same solution with $Z > 1$; energies scale as $Z^2$, radii as $1/Z$, useful in X-ray spectroscopy (Moseley's law) and highly charged ion physics.
- **Exotic atoms**: muonic hydrogen (muon replacing the electron, much larger reduced mass, much smaller orbit, enhanced sensitivity to nuclear size), positronium (electron–positron bound state, requiring full two-body treatment since masses are equal), antiprotonic and pionic atoms.
- **Rydberg atoms**: states of very large $n$, where the electron is far from the nucleus and behaves quasi-classically; sensitive to external fields and useful in quantum information and precision spectroscopy.
- **2D and confined hydrogen**: hydrogen constrained to a plane or inside an impenetrable sphere — used as toy models for excitons in semiconductor heterostructures and for studying the effect of confinement on spectra.
- **Screened Coulomb / Debye–Hückel-type potentials**: modify the pure Coulomb problem in plasmas; no longer exactly solvable in general, treated perturbatively or numerically.

---

## 11. Physical Significance and Applications

- **Atomic and molecular physics**: hydrogenic orbitals form the qualitative basis (via the orbital/aufbau approximation and Slater-type/Gaussian-type basis functions) for multi-electron atoms and molecules, even though those require numerical (Hartree–Fock, DFT, configuration interaction) methods due to electron–electron correlation.
- **Spectroscopy**: the Lyman, Balmer, Paschen, etc., series of hydrogen spectral lines arise directly from $E_n \propto -1/n^2$ transitions; precision spectroscopy of hydrogen (1S–2S transition) is among the most accurately measured quantities in physics and a stringent test of QED and possible new physics.
- **Astrophysics**: the 21 cm line, Balmer-series emission from ionized nebulae, and quasar absorption spectra all rely on one-electron hydrogen physics.
- **Foundational physics**: precision comparisons between theory (bound-state QED) and experiment (Lamb shift, hydrogen 1S–2S frequency, muonic hydrogen) test fundamental constants (Rydberg constant, proton charge radius) and search for physics beyond the Standard Model.
- **Pedagogically**: it is the canonical worked example for separation of variables, special functions (Laguerre and Legendre polynomials, spherical harmonics), degeneracy and symmetry, and perturbation theory in every quantum mechanics curriculum.

---

## 12. Summary Table of Key Results

| Quantity | Expression |
|---|---|
| Energy levels | $E_n = -\dfrac{1}{2}\mu c^2 \alpha^2 \dfrac{Z^2}{n^2}$ |
| Bohr radius | $a_0 = \dfrac{4\pi\epsilon_0\hbar^2}{\mu e^2}$ |
| Degeneracy (no spin) | $n^2$ |
| Degeneracy (with spin) | $2n^2$ |
| Radial nodes | $n - \ell - 1$ |
| Fine structure | $\Delta E_{nj} \propto (Z\alpha)^4/n^3$ |
| Lamb shift | breaks $\ell$-degeneracy at fixed $n,j$ (QED effect) |
| Hyperfine splitting | from $\mathbf{I}\cdot\mathbf{J}$ coupling; e.g. 21 cm line |

---

## 13. Key References for Further Study

- Bethe, H. A. & Salpeter, E. E., *Quantum Mechanics of One- and Two-Electron Atoms* (classic comprehensive reference).
- Griffiths, D. J., *Introduction to Quantum Mechanics* — standard pedagogical treatment.
- Sakurai, J. J. & Napolitano, J., *Modern Quantum Mechanics* — algebraic (Runge–Lenz) treatment.
- Bjorken, J. D. & Drell, S. D., *Relativistic Quantum Mechanics* — Dirac equation solution.
- Eides, M. I., Grotch, H., Shelyuto, V. A., *Theory of Light Hydrogenic Bound States* — modern QED corrections review.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive description of he one-electron problem in quantum mechanics. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
