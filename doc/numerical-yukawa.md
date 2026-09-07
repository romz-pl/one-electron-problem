# Numerical Eigenvalues of the Schrödinger Equation with a Yukawa Potential — A Review

## 1. The Problem

The (static screened Coulomb / Yukawa) potential is

$$V(r) = -\alpha\,\frac{e^{-\mu r}}{r},$$

where $\alpha$ sets the interaction strength and $1/\mu$ the screening length. The radial Schrödinger equation, in units $\hbar = m = 1$, reads

$$\left(-\frac{1}{2}\frac{d^2}{dr^2} - \alpha\frac{e^{-\mu r}}{r} + \frac{l(l+1)}{2r^2}\right)\psi(r) = E\,\psi(r).$$

Unlike the pure Coulomb potential ($\mu = 0$), this equation is **not exactly solvable** for $\mu \neq 0$: no closed-form expression exists for $E_{nl}(\mu)$, the eigenfunctions, or the critical screening parameter $\mu_c$ above which no bound state survives. This intractability, combined with the potential's ubiquity (nuclear physics, where it originates as the meson-exchange potential; plasma physics, where it is the Debye–Hückel potential; solid-state physics, where it is the Thomas–Fermi screened potential; and quarkonium spectroscopy), has made it one of the most-studied test potentials in quantum mechanics for over 80 years.

Because no analytic solution exists, the literature is built from four broad approaches whose numerical outputs can be directly compared:

1. **Direct numerical integration** of the radial Schrödinger equation (finite-difference / shooting methods) — treated as the benchmark "exact" values.
2. **Variational methods** (Hulthén-type, Coulomb-type, or SUSY-QM-induced trial wavefunctions).
3. **Perturbation theory** (standard Rayleigh–Schrödinger, logarithmic perturbation theory, semiclassical $\hbar$-expansions).
4. **Quasi-analytical approximation schemes** (Nikiforov–Uvarov method, asymptotic iteration method (AIM), supersymmetric QM, $1/N$-shifted expansion, Bethe ansatz) — these replace the centrifugal $1/r^2$ term with an approximating exponential (the Greene–Aldrich substitution) to render the equation solvable in closed form, at the cost of approximation error for $l \neq 0$.

---

## 2. Benchmark Numerical Eigenvalues

### 2.1 The foundational numerical dataset: Rogers, Graboske & Harwood (1970)

The reference numerical solution remains **Rogers, Graboske, and Harwood, *Phys. Rev. A* **1**, 1577 (1970)**, who solved the radial equation by one-dimensional finite-difference integration for 45 eigenstates (1s through n = 9, l = 8) over a wide range of the screening length $D = 1/\mu$. Key results:

- All energy levels shift upward (toward the continuum) as the screening length $D$ decreases (screening increases).
- For each $(n,l)$ state there exists a critical screening length $D_0(n,l)$ at which $E_{nl} \to 0$.
- For the **1s ground state**, the critical screening length is

$$D_0(1s) = 0.83991\ a_0/Z,$$

in agreement with earlier variational estimates — equivalent to a critical screening parameter $\mu_c \approx 1.19\,\alpha m$ (in atomic units with $\alpha = Z$).

This dataset (and the closely related tables of Roussel & O'Connell, *Phys. Rev. A* **4**, 52 (1971)) is the numerical standard against which essentially all subsequent approximate/analytic methods are benchmarked.

### 2.2 Representative eigenvalue table (1s state), in Rydberg units ($\alpha=1$)

The table below (from Drigo Filho & Ricotta, *hep-th/0002015*, comparing their SUSY-variational method to the Rogers–Graboske–Harwood exact numerical values) illustrates how the ground-state energy $E_{1s}(\delta)$ evolves with the screening parameter $\delta \equiv \mu$:

| Screening $\delta$ | Exact numerical $E_{1s}$ | SUSY-variational $E_{1s}$ |
|---:|---:|---:|
| 0.002 | −0.4980 | −0.49802 |
| 0.005 | −0.4950 | −0.49504 |
| 0.010 | −0.4901 | −0.49009 |
| 0.020 | −0.4803 | −0.48031 |
| 0.025 | −0.4755 | −0.47548 |
| 0.05  | −0.4518 | −0.45180 |
| 0.10  | −0.4071 | −0.40705 |
| 0.20  | −0.3268 | −0.32681 |
| 0.25  | −0.2909 | −0.29092 |
| 0.50  | −0.1481 | −0.14806 |
| 1.00  | −0.01029 | −0.01026 |

Agreement is typically better than $10^{-3}$–$10^{-4}$ Ry across the whole screening range, degrading somewhat as the critical screening is approached (bound state becoming very shallow and the wavefunction very extended).

### 2.3 Excited / higher-angular-momentum states

For $l \neq 0$ states the effective potential departs from the exactly-solvable Hulthén form, and eigenvalues become more sensitive to the choice of centrifugal approximation. Comparison of variational and exact-numerical values (same source) for 2p, 3d, and 4f states:

| $\delta$ | $E_{2p}$ (exact) | $E_{2p}$ (variational) | $E_{3d}$ (exact) | $E_{3d}$ (variational) | $E_{4f}$ (exact) | $E_{4f}$ (variational) |
|---:|---:|---:|---:|---:|---:|---:|
| 0.001 | −0.2480 | −0.2480 | −0.10910 | −0.10910 | −0.06052 | −0.06051 |
| 0.010 | −0.2305 | −0.2305 | −0.09212 | −0.09212 | −0.04420 | −0.04419 |
| 0.020 | −0.2119 | −0.2119 | −0.07503 | −0.07503 | −0.02898 | −0.02897 |
| 0.025 | −0.2030 | −0.2030 | −0.06715 | −0.06714 | — | — |
| 0.050 | −0.1615 | −0.1615 | −0.03383 | −0.03374 | — | — |
| 0.100 | −0.09307 | −0.09289 | — | — | — | — |

Values are in Rydberg units. Agreement is excellent at small screening and worsens near the point where the state ceases to be bound.

### 2.4 The critical screening parameter $\mu_c$

The critical value of $\mu$ above which the Yukawa potential supports **no bound state** has historically been quoted with varying precision:

$$\mu_c \approx 1.19\,\alpha m \quad (\text{ground state}, \alpha=m=1).$$

**Edwards, Gerber, Schubert, Trejo & Weber, *Prog. Theor. Exp. Phys.* **2017**, 083A01** revisit this problem with fifth-order Rayleigh–Schrödinger perturbation theory (using the exactly solvable Coulomb Hamiltonian as the unperturbed system, with a principal-quantum-number cutoff) and a variational calculation using a Coulomb-like trial wavefunction, solving the resulting cubic minimization condition exactly rather than approximately. Their result is presented as **the most precise determination of $\mu_c$ to date (10 significant digits)**, resolving discrepancies among earlier estimates in the literature.

### 2.5 Quarkonium and diatomic-molecule applications

Because the (inverse-)Yukawa / screened-Coulomb form appears as a component of quark–antiquark confinement potentials, numerical eigenvalues are also routinely produced as **mass spectra**. Representative applications include:

- Charmonium ($c\bar c$) and bottomonium ($b\bar b$) mass spectra (1S, 2S, 1P, 2P, 3S, 4S, 1D, 2D, 1F states) computed via the Yukawa + Kratzer combined potential, benchmarked against experimental meson masses.
- Rotational–vibrational energy levels of diatomic molecules, computed via Nikiforov–Uvarov / Bethe-ansatz solutions of the Yukawa (Manning–Rosen-related) potential, agreeing with earlier numerical results to about five decimal digits.

### 2.6 Summary of numerical accuracy across methods

| Method | Typical agreement with exact numerical integration | Domain of validity |
|---|---|---|
| Direct numerical integration (finite difference / shooting) | Reference standard | All $\mu$, all $(n,l)$ |
| Variational (Hulthén / Coulomb trial function) | $10^{-3}$–$10^{-5}$ (l = 0); somewhat worse for $l\neq0$ | Best at small–moderate $\mu$ |
| SUSY-QM induced variational method | Comparable to Hulthén-variational; degrades near critical screening | All $l$, small–moderate $\mu$ |
| 5th-order perturbation theory (Coulomb basis) | High precision at small $\mu$; requires principal-quantum-number cutoff at 2nd order+ | Small $\mu$ |
| Nikiforov–Uvarov / AIM (with Greene–Aldrich approximation) | Good for $l=0$; approximate for $l\neq0$ due to centrifugal-term substitution | All $\mu$ within bound-state regime |
| $1/N$-shifted expansion | Good agreement across states | Moderate/large $n$ |
| Logarithmic perturbation theory (semiclassical) | Good for ground and low excited states | Small–moderate $\mu$ |

---

## 3. Related Publications

### 3.1 Foundational / benchmark numerical studies
- F. J. Rogers, H. C. Graboske Jr., D. J. Harwood, "Bound Eigenstates of the Static Screened Coulomb Potential," *Phys. Rev. A* **1**, 1577 (1970).
- C. S. Lam, Y. P. Varshni, "Energies of Eigenstates in a Static Screened Coulomb Potential," *Phys. Rev. A* **4**, 1875 (1971).
- K. M. Roussel, R. F. O'Connell, *Phys. Rev. A* **4**, 52 (1971).

### 3.2 Modern high-precision / ground-state and critical-screening studies
- J. P. Edwards, U. Gerber, C. Schubert, M. A. Trejo, A. Weber, "The Yukawa potential: ground state energy and critical screening," *Prog. Theor. Exp. Phys.* **2017**, 083A01 (arXiv/DOI: 10.1093/ptep/ptx107).

### 3.3 Variational and supersymmetric-QM approaches
- E. Drigo Filho, R. M. Ricotta, "Induced Variational Method from Supersymmetric Quantum Mechanics and the Screened Coulomb Potential," arXiv:hep-th/0002015.
- R. L. Greene, C. Aldrich, "Variational wave functions for a screened Coulomb potential," *Phys. Rev. A* **14**, 2363 (1976).
- V. Fessatidis, J. Mancini, Q. Haider, Y. Zhou, L. Greco, *Phys. Lett. A* **242**, 74 (1998).
- Y. P. et al., "Calculation of the Energy Eigenvalues of the Yukawa Potential via Variation Principle," *Int. J. Mod. Phys. E* (2020).

### 3.4 Perturbation-theory approaches
- I. V. Dobrovolska, R. S. Tutik, "A new perturbation technique for eigenenergies of the screened Coulomb potential," arXiv:quant-ph/0609148.
- Perturbative treatment of the exponential–cosine-screened Coulomb (ECSC) potential, arXiv:quant-ph/0509004.

### 3.5 Nikiforov–Uvarov / Asymptotic Iteration Method (AIM) and related quasi-analytical solutions
- M. Hamzavi, S. M. Ikhdair, et al., "Approximate Analytical Solution of the Yukawa Potential with Arbitrary Angular Momenta," arXiv:1210.5886.
- "Solution of Radial Schrödinger Equation with Yukawa Potential Using Bethe Ansatz Method" (J. J. Peña, J. García-Martínez, et al.).
- "Eigensolutions, scattering phase shift and thermodynamic properties of Hulthén–Yukawa potential," *Results in Physics* (2019), ScienceDirect.
- "Eigen Solution and Thermodynamic Properties of Manning-Rosen Plus Exponential Yukawa Potential," arXiv:2304.08219.
- T. Barakat et al. and related authors, "An Improvement of the Asymptotic Iteration Method for Exactly Solvable Eigenvalue Problems," arXiv:0711.4502.
- "Topological Effects With Inverse Quadratic Yukawa Plus Inverse Square Potential on Eigenvalue Solutions," arXiv:2305.04823.
- "Bound states of the Yukawa potential via the shifted 1/N expansion technique."

### 3.6 Relativistic extensions (Dirac / Klein–Gordon / spinless Salpeter)
- "Eigensolutions of the Schrödinger equation with a class of Yukawa potentials via supersymmetric approach" (also covers Dirac spin/pseudospin symmetric solutions for the inversely-quadratic Yukawa potential).
- "Approximate k-state solutions to the Dirac–Yukawa problem based on the spin and pseudospin symmetry," arXiv:1203.2023.
- "The Spinless Relativistic Yukawa Problem," arXiv:1410.5241.

### 3.7 Exponential-potential auxiliary field methods
- "Auxiliary field method and analytical solutions of the Schrödinger equation with exponential potentials," arXiv:0811.0287.

### 3.8 Momentum-space treatments
- "The Yukawa potential in momentum space: Analytic behavior of the eigenfunctions" (E. N. Lassettre and collaborators; iterative solution in momentum representation).

### 3.9 Applications: heavy quarkonia and molecular spectroscopy
- "Screened Coulomb potential applied to the Quarkonium systems," arXiv:2101.01174 — Kratzer + screened-Coulomb potential fit to charmonium/bottomonium mass spectra.
- "Formation of Antihydrogen ion in Positronium–Antihydrogen collision with screened Coulomb Potential," arXiv:2201.09225.

---

## 4. Key Takeaways

1. **No closed-form solution exists** for the Yukawa-potential Schrödinger equation at nonzero screening; all "exact" values in the literature trace back to direct numerical integration, historically anchored by Rogers, Graboske & Harwood (1970).
2. **Approximate analytic methods (NU, AIM, SUSY-QM, variational)** now reproduce the numerical benchmark to 4–5 significant figures for low-lying states and small-to-moderate screening, with accuracy degrading near the critical screening parameter $\mu_c$, where the bound state becomes very shallow.
3. **The critical screening parameter** has been pinned down to unprecedented precision (10 digits) only recently (Edwards et al., 2017), resolving long-standing small discrepancies between earlier variational and numerical estimates.
4. **The potential's cross-disciplinary relevance** (nuclear, plasma/Debye–Hückel, solid-state/Thomas–Fermi, and quarkonium spectroscopy) continues to drive new approximate-eigenvalue papers, typically validated against the same core numerical datasets discussed above.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Conduct a thorough review of the numerical values of the eigenvalues of the Schrödinger equation with a Yukawa potential. Also, compile a list of related publications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
