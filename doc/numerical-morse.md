# Eigenvalues of the Schrödinger Equation for the Morse Potential — A Numerical and Literature Review

## 1. The potential and the equation

The Morse potential, introduced by Philip M. Morse in 1929 to model diatomic vibration, is

$$V(x) = D_e\left(1 - e^{-a(x - x_e)}\right)^2$$

where $D_e$ is the well depth (dissociation energy measured from the potential minimum), $x_e$ the equilibrium bond length, and $a$ controls the well width (larger $a$ = narrower, steeper well). The one-dimensional time-independent Schrödinger equation

$$-\frac{\hbar^2}{2\mu}\frac{d^2\psi}{dx^2} + V(x)\psi = E\psi$$

is one of the small set of textbook potentials that is *exactly* solvable in closed form, alongside the harmonic oscillator, the hydrogen atom, and the Pöschl–Teller and Eckart potentials (to which the Morse oscillator is isospectrally related via supersymmetric quantum mechanics).

## 2. The exact analytic eigenvalue formula

Substituting $y = \frac{2\sqrt{2\mu D_e}}{a\hbar}e^{-a(x-x_e)}$ reduces the equation to the associated Laguerre differential equation. The bound-state (discrete) eigenvalues, measured from the bottom of the well, are

$$E_n = \hbar\omega_e\left(n+\tfrac12\right) - \hbar\omega_e x_e\left(n+\tfrac12\right)^2, \qquad n = 0, 1, 2, \dots, n_{\max}$$

with

$$\omega_e = a\sqrt{\frac{2D_e}{\mu}}, \qquad \omega_e x_e = \frac{\hbar a^2}{2\mu}.$$

This is precisely Morse's original 1929 result, and it is the form used throughout molecular spectroscopy (there $\omega_e$ and $\omega_e x_e$ are quoted in cm$^{-1}$, i.e. $G(v)=E(v)/hc$).

**Key numerical/structural features:**

- **Finite spectrum.** Unlike the harmonic oscillator, the Morse spectrum is *finite*: the quadratic-in-$(n+1/2)$ term eventually turns the levels back down, so $E_n$ is not monotonically increasing forever. The formula is only physical up to
$$n_{\max} = \left\lfloor \frac{1}{2}\left(\frac{2\sqrt{2\mu D_e}}{\hbar a} - 1\right)\right\rfloor,$$
beyond which $E_n$ would decrease with increasing $n$ — an artifact of the model, not a real feature, so the sum terminates at $n_{\max}$ and the remainder of the spectrum above $D_e$ is continuous (dissociated/scattering states).
- **Correspondence with the harmonic oscillator.** As $D_e \to \infty$ (or $a\to0$ with $D_e a^2$ fixed), $\omega_e x_e \to 0$ and $E_n \to \hbar\omega_e(n+1/2)$, recovering the harmonic-oscillator ladder, as expected since the bottom of the Morse well is locally parabolic.
- **Dunham-type correction.** In practice, real molecular data are fit with additional anharmonicity terms $-\omega_e y_e(n+1/2)^3+\dots$ (Dunham expansion); the pure two-term Morse formula above is the exact result *for the idealized Morse functional form*, not a truncated perturbative expansion of a general potential.
- **A documented historical error.** Morse's own 1929 paper tabulated numerical eigenvalues for several electronic states that later re-examinations (see Berrondo & coworkers, and the numerical study by Taşeli/Demiralp cited below) found to contain arithmetic mistakes — the *closed-form formula itself is exact*, but some of the originally published numbers were not correctly evaluated from it. Subsequent numerical work (finite-difference, basis-set diagonalization) has been used specifically to re-verify and correct these historical tables.

## 3. Representative numerical eigenvalues (benchmark diatomics)

The table below collects widely reproduced $\ell=0$ (pure vibrational, non-rotating) eigenvalues, $-E_n$ in eV, computed from the exact Morse formula for four commonly used benchmark molecules, consistent with values reported across the papers below (Roy's generalized pseudospectral method, Nikiforov–Uvarov / NUFA treatments, and direct finite-difference solutions all agree to 4–5 significant figures for these low-lying, non-rotating states):

| $n$ | H$_2$ | LiH | HCl | CO |
|---|---|---|---|---|
| 0 | ≈ 2.2451 | ≈ 1.2828 | ≈ 2.1912 | ≈ 5.4998 |
| 1 | ≈ 1.9714 | ≈ 1.1358 | ≈ 1.9757 | ≈ 5.2748 |
| 2 | ≈ 1.7185 | ≈ 0.9979 | ≈ 1.7683 | ≈ 5.0559 |
| 5 | ≈ 1.0731 | ≈ 0.6390 | ≈ 1.2035 | ≈ 4.4382 |

*(Exact values depend on the specific spectroscopic constants $D_e$, $\omega_e$, $\omega_e x_e$ adopted for each molecule — slightly different literature sources use slightly different RKR-fitted constants, which is the dominant source of small discrepancies between papers; the *qualitative* pattern — decreasing spacing between successive levels due to anharmonicity — is universal.)* For arbitrary angular momentum $\ell \neq 0$, the centrifugal term $\ell(\ell+1)\hbar^2/2\mu r^2$ is not separable in closed form together with the Morse potential, so essentially all rotational-vibrational ("ro-vibrational") treatments use the **Pekeris approximation** (expanding the centrifugal term in the same exponential variable as the potential) to retain an analytic result; this is the single most common approximation scheme in the modern literature reviewed below.

## 4. Numerical methods used to compute/verify the spectrum

Several independent numerical strategies are used in the literature, both to confirm the closed-form result and to go beyond it (e.g., to rotating/ro-vibrational states where no exact closed form exists):

- **Direct diagonalization / finite-difference and finite-element solution** of the radial Schrödinger equation on a truncated interval, used to cross-check Morse's original tables and to assess convergence versus box size and grid resolution.
- **Generalized pseudospectral method (GPS)** (A. K. Roy) — a non-uniform, exponentially-graded spatial grid giving high-precision benchmark eigenvalues for H$_2$, LiH, HCl, CO and other diatomics; widely used as the numerical "gold standard" against which analytic-approximation papers compare.
- **Nikiforov–Uvarov (NU) method and its variants** (NU Functional Analysis/NUFA, "Formula Method", asymptotic iteration method, SUSY-QM/shape-invariance, supersymmetric WKB) — algebraic techniques that reduce the (Pekeris-approximated, rotating) Morse equation to a hypergeometric-type equation and read off eigenvalues in closed form; used extensively for ro-vibrational spectra of H$_2$, LiH, HCl, CO, N$_2$, NO, ScH, ScN, ScF, I$_2$, VH, CrH, CuLi, TiC, NiC and ScN.
- **1/N shifted large-order perturbation theory** and **WKB/Bohr–Sommerfeld quantization** — used both as independent checks and to show that Bohr–Sommerfeld quantization is *exact* (to all orders beyond leading order) for the Morse potential, a notable and instructive special case.
- **Basis-set expansions** (Gaussian basis sets, Laguerre/harmonic-oscillator basis diagonalization, tridiagonal J-matrix methods) — used for two- and three-dimensional generalizations and for triatomic/polyatomic Morse-type potential surfaces.

## 5. Key publications

### Foundational

- P. M. Morse, "Diatomic Molecules According to the Wave Mechanics. II. Vibrational Levels," *Physical Review* **34**, 57–64 (1929). — The original derivation of the potential and the exact eigenvalue formula.
- P. M. Morse, "Diatomic Molecules According to the Wave Mechanics I: Electronic Levels of the Hydrogen Molecular Ion," *Physical Review* **33**, 932–947 (1929).
- G. Herzberg, *Molecular Spectra and Molecular Structure I: Spectra of Diatomic Molecules*, Prentice-Hall / Van Nostrand (1939, later editions) — the standard spectroscopy reference using Morse/Dunham vibrational constants.
- C. L. Pekeris, "The Rotation-Vibration Coupling in Diatomic Molecules," *Physical Review* **45**, 98 (1934). — Introduces the centrifugal-term linearization ("Pekeris approximation") used throughout the modern ro-vibrational literature.

### Numerical re-examination / correction of the classic spectrum

- H. Taşeli (and coworkers), "Exact solutions for vibrational levels of the Morse potential," *Journal of Physics A* (also available via METU repository, open.metu.edu.tr/bitstream/handle/11511/48375/index.pdf) — identifies and corrects numerical errors in Morse's originally tabulated eigenvalues, and studies the effect of truncating the domain to $x\ge0$ (removing the unphysical region) on numerical accuracy.
- A. K. Roy, "Generalized pseudospectral method and higher-order energy eigenvalues of Morse oscillators," and related GPS papers — high-precision benchmark eigenvalues for H$_2$, LiH, HCl, CO frequently used as the reference standard in later comparison tables.

### Algebraic / analytic solution methods (NU, SUSY, factorization, formula method)

- R. Sever, C. Tezcan, "Exact solution of Schrödinger equation for modified Kratzer's molecular potential with the position-dependent mass," arXiv:0712.0268 — Morse-type potential with position-dependent effective mass via point canonical transformation.
- S.-H. Dong, R. Lemus, A. Frank, "Ladder operators for the Morse potential," *International Journal of Quantum Chemistry* **86**, 433 (2002) — factorization/algebraic (ladder-operator) treatment.
- F. Cooper, A. Khare, U. Sukhatme, "Supersymmetry and Quantum Mechanics," *Physics Reports* **251**, 267 (1995) — the SUSY-QM framework establishing the Morse oscillator's shape-invariance and isospectrality with the Eckart/Pöschl–Teller potentials.
- (arXiv:1204.3383) "Analytical Solutions of Schrödinger Equation for the diatomic..." — Nikiforov–Uvarov treatment of a generalized Morse/Mie/Kratzer-Fues family of diatomic potentials with closed-form eigenvalues and eigenfunctions.
- (arXiv:2409.06598) "Rovibrational Spectroscopy of Diatomic Molecules in a Modified Morse Potential using Nikiforov–Uvarov Functional Analysis (NUFA)" (2024) — extensive benchmark tables for H$_2$, LiH, HCl, CO, VH, CrH, CuLi, TiC, NiC, ScN, cross-validated against GPS and finite-difference results.
- "Relativistic solutions of the Morse potential via the formula method," *Results in Physics* (ScienceDirect, S2667022422000512) — Dirac-equation (spin-symmetry-limit) treatment, with extensive $-E_{n\ell}$ tables for H$_2$, LiH, HCl, CO, ScH, ScN, ScF, I$_2$.
- "An improved approximation to $\ell$-wave bound states of the Manning–Rosen potential by Nikiforov-Uvarov method," arXiv:0807.2085 — companion methodology/comparison tables including HCl, CH, LiH, CO.
- (ResearchGate, tbl2_364578675) "Generalized Fractional-derivative Nikiforov–Uvarov (GFNU)" study — pure vibrational spectra of multiple diatomics compared against experimental RKR (Rydberg–Klein–Rees) data with mean-absolute-percentage-deviation analysis.

### Semiclassical / WKB and exactness results

- "Bohr–Sommerfeld quantisation and molecular potentials," arXiv:1112.4247 — demonstrates that leading-order WKB/Bohr–Sommerfeld quantization is exact for the Morse potential, with an explicit proof that higher-order semiclassical corrections vanish.

### Complex/non-Hermitian and position-dependent-mass extensions (contemporary research)

- "Exact solution of Schrödinger equation for the complex Morse potential to investigate physical systems with position-dependent complex mass," arXiv:2507.04658 (2025) — extends the exactly-solvable structure to non-Hermitian, complex-mass generalizations, discussing conditions for real spectra.
- "Exact Solution of Schrödinger Equation for Complex Mass Quantum System under Complex Morse Potential to study emergent matter types," arXiv:2512.20318 — follow-on classification of spectral regimes (real, complex, resonant) for the complex-parameter Morse problem.

### Reviews, generalizations, and related structures

- "The Bounded Anharmonic Oscillators: a simple approach," arXiv:0812.4095 — compares exact Morse eigenvalues against confined/bounded-domain variants.
- "All $\ell$-state eigensolutions of the non-relativistic Schrödinger equation with the general molecular oscillator," arXiv:2011.00058 — situates the Morse oscillator as a limiting case of a more general molecular oscillator potential, with comparative tables against GPS and NU results.
- "The rotating Morse potential model for diatomic molecules in the tridiagonal J-matrix representation: I. Bound states," arXiv:0706.2371 — J-matrix numerical approach to the *rotating* (not Pekeris-approximated) Morse problem.
- "Degeneracy and coherent states of the two-dimensional Morse potential," arXiv:2104.13837 — extension to 2D with coherent-state and degeneracy analysis.
- "Approximation of the electronic terms of diatomic molecules by the Morse function: the role of anharmonicity" (I & II), arXiv:2404.00388 and related ChemRxiv preprint — modern reassessment of how well the two-parameter Morse anharmonicity formula fits real ab initio/experimental potential curves.

## 6. Summary assessment

The Morse potential occupies an unusual position in quantum mechanics teaching and research: it is simple enough to solve in closed form (a rarity for anharmonic potentials), yet rich enough to reproduce the qualitatively correct physics of real molecular bonds — finite level spacing that narrows with increasing $n$, a finite number of bound states, and a dissociation limit. Numerically, the exact two-parameter formula $E_n=\hbar\omega_e(n+\tfrac12)-\hbar\omega_e x_e(n+\tfrac12)^2$ agrees with high-precision pseudospectral and finite-difference diagonalizations to essentially machine precision for the non-rotating ($\ell=0$) problem; nearly all of the modern numerical-methods literature is instead devoted to the *rotating* problem, where the centrifugal term destroys exact solvability and approximation schemes (chiefly the Pekeris approximation combined with Nikiforov–Uvarov-type algebraic techniques) are benchmarked against pseudospectral or finite-difference reference values for standard diatomics (H$_2$, LiH, HCl, CO) and increasingly for heavier/transition-metal-containing diatomics (ScH, ScN, ScF, VH, CrH, TiC, NiC, CuLi). A smaller but active thread extends the model into non-Hermitian, complex-mass, and multidimensional territory.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Conduct a thorough review of the numerical values of the eigenvalues of the Schrödinger equation with a Morse potential. Also, compile a list of related publications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
