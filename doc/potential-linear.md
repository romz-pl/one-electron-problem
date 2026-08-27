# Evaluation of Eigenvalues of the Schrödinger Equation with a Linear Potential: A Review

## 1. Introduction

The Schrödinger equation with a linear potential, $V(r) = br$ (or, in one dimension, $V(x) = F|x|$), is one of the few genuinely solvable non-trivial potentials in quantum mechanics: its solutions are Airy functions. Despite this apparent simplicity, the *quantitative* evaluation of its eigenvalues — especially in three dimensions, for arbitrary orbital angular momentum $\ell$, and in the physically dominant case where the linear term is combined with a Coulomb term (the **Cornell potential**) — has generated a large and still-active body of literature spanning nearly a century. This review surveys the mathematical structure of the problem, the exact and approximate solution techniques that have been developed, and the physical contexts (Stark effect, quantum bouncer, quark confinement, holographic QCD) that motivate the calculation.

## 2. The Governing Equation

### 2.1 One dimension / $\ell=0$ radial problem

Consider the radial Schrödinger equation obtained after substituting $\psi_{n\ell m}(\mathbf r) = \dfrac{R_{n\ell}(r)}{r}Y_{\ell m}(\theta,\varphi)$ for a particle of reduced mass $\mu$ in the potential $V(r) = br - \alpha/r - C$:

$$\left[-\frac{d^2}{dr^2} + \frac{\ell(\ell+1)}{r^2} + 2\mu\left(br - \frac{\alpha}{r} - C\right)\right]R_{n\ell}(r) = 2\mu E\, R_{n\ell}(r).$$

When the Coulomb term $\alpha$ and the centrifugal term vanish ($\alpha = 0,\ \ell = 0$), the equation reduces to the **Airy equation**

$$-R''(r) + 2\mu b\, r\, R(r) = 2\mu E\, R(r),$$

whose regular solution is $R(r) \propto \mathrm{Ai}\!\left[(2\mu b)^{1/3}r + \varrho_n\right]$, with $\varrho_n$ the $n$-th zero of the Airy function $\mathrm{Ai}$. The corresponding eigenvalues are

$$E_n = -(2\mu b)^{-2/3}\,\varrho_n ,$$

i.e., **the eigenvalues are directly proportional to the (negative of the) zeros of the Airy function**. This is the unique case in which the linear-potential spectrum is known in fully closed form.

### 2.2 The symmetric (two-sided) linear potential

For the one-dimensional "V"-shaped potential $V(x) = F|x|$ (the quantum analogue of a ball bouncing under gravity, hence "quantum bouncer"), parity splits the spectrum into even and odd sectors:

- Odd-parity (equivalently, the half-line "bouncer" problem with a hard wall at $x=0$) eigenvalues equal $-a_n$, the zeros of $\mathrm{Ai}$.
- Even-parity eigenvalues equal $-a_n'$, the zeros of the derivative $\mathrm{Ai}'$.

Tabulated zeros (Abramowitz & Stegun) give, e.g., the first even/odd pairs $\lambda_0=1.01879,\ \lambda_1=2.33811,\ \lambda_2=3.24820,\ \lambda_3=4.08795,\dots$ This case underlies the **Stark effect** in a uniform field and the **quantum bouncer** (particle in a uniform gravitational field above a floor).

### 2.3 The general case: $\ell \neq 0$ and/or Coulomb term present

For $\ell \neq 0$, or once a Coulomb term is added (the physically important **Cornell potential**, $V(r) = br - \alpha/r$), the equation is no longer exactly an Airy equation and **no closed-form solution is known**. This is the central difficulty the literature addresses, because the Cornell potential is the workhorse potential of non-relativistic quarkonium spectroscopy: it reproduces the short-distance one-gluon-exchange Coulombic behavior and the long-distance linear confinement predicted (and lattice-verified) for the static quark–antiquark potential.

## 3. Physical Motivation

| Context | Role of the linear potential |
|---|---|
| Stark effect | Linear potential from a uniform external electric field |
| Quantum bouncer | Particle under uniform "gravity" above a hard floor |
| Quark confinement (QCD) | Long-distance, area-law/Wilson-loop behavior of the static $q\bar q$ potential, confirmed by lattice QCD |
| Cornell / Cornell-type potential | $V(r) = -\alpha/r + br$: short-range Coulombic gluon exchange + long-range linear confinement, used for charmonium, bottomonium, and heavy-light mesons |
| Light-front holographic QCD / AdS-QCD | Effective confining potential arising from soft-wall holographic duals reproduces a Schrödinger-like equation whose high-lying spectrum matches a linear-potential problem |
| Baryon spectroscopy (quark–diquark models) | Two-body Schrödinger equation with Coulomb-plus-linear potential fitted to $\Lambda_c,\Lambda_b$ excitation spectra |

A further reason for sustained interest is the shape of Regge trajectories: solving the Schrödinger equation with a *purely linear* confining potential produces **convex** Regge trajectories, whereas relativistic wave equations (Dirac, Klein–Gordon, spinless Salpeter) with the same potential produce linear or concave trajectories — a qualitative fact used to discriminate between dynamical frameworks when confronting meson spectroscopy data.

## 4. Exact and Semi-Exact Approaches

### 4.1 Airy-function solution ($\ell=0$, no Coulomb term)
As above; eigenvalues are Airy-function zeros. This remains the only fully closed-form sector.

### 4.2 Power-series / combinatorial method for the Coulomb-plus-linear ($\ell$ arbitrary)
Antippa and Phares developed a formalism for multi-term linear recursion relations, expressing the wavefunction of the Coulomb-plus-linear (Cornell) potential as a **power-series expansion with coefficients given by combinatorial functions**, and the energy eigenvalues as roots of an (in principle infinite-order) polynomial. This yields an essentially exact — though not closed-form — characterization valid for any $\ell$.

### 4.3 Laplace-transform and Nikiforov–Uvarov / asymptotic-iteration families
A family of related techniques — the **Nikiforov–Uvarov (NU) method**, the **asymptotic iteration method (AIM)**, and the **Laplace transformation (LT) method** — have been applied to the (generalized) Cornell potential by approximating the centrifugal term $\ell(\ell+1)/r^2$ with a suitable expansion (e.g., a Greene–Aldrich-type approximation) that restores exact solvability. These methods produce closed-form (but approximate, due to the centrifugal-term substitution) energy formulas valid for arbitrary $n,\ell$, and have been extended to $N$-dimensional generalizations and to finite-temperature/finite-chemical-potential quarkonium studies.

### 4.4 Exact quantization via zeros of Airy-type special functions with Coulomb correction
Some analytic treatments retain the Airy structure but add correction terms required for a non-trivial (non-zero) ground-state energy, showing that an asymptotically linear potential augmented with an appropriate short-distance term admits an analytic solution while the purely linear case alone is degenerate in this respect.

## 5. Approximate / Numerical Methods

Given the general non-solvability of the Cornell/linear problem for $\ell \ne 0$, a wide toolbox of numerical and semi-analytical methods has been used:

1. **Variational method with Airy trial functions.** Since the exact $\ell=0$ solution is an Airy function, a natural variational ansatz for the general problem is
 $$\psi(r) \propto \frac{1}{r}\,\mathrm{Ai}\!\left[(2\mu b')^{1/3} r + \varrho_{0n}\right],$$
 with $b'$ (and sometimes additional linear-combination coefficients) treated as variational parameters optimized via the Rayleigh–Ritz principle. This approach has been used extensively in heavy-quarkonium mass/decay-constant calculations and can be systematically improved (Variationally Improved Perturbation Theory, VIPT) by including corrections from neighboring Airy eigenstates.
2. **Numerov / finite-difference matrix methods.** The radial equation is discretized on a grid; the second derivative is approximated by a finite-difference stencil (often tridiagonal), converting the eigenvalue problem into a standard matrix diagonalization. Widely used for Cornell-potential charmonium/bottomonium spectra.
3. **Shooting methods** integrate the radial equation from small and large $r$ and match logarithmic derivatives at a matching point, iterating the trial energy until continuity is achieved.
4. **Discrete Variable Representation (DVR).** The Hamiltonian is represented in a discretized position basis (Colbert–Miller DVR), producing a matrix that is diagonalized directly; applied to charmonium spectroscopy with good agreement to experiment.
5. **Lagrange-mesh method (LMM).** Uses Gauss-type quadrature (e.g. Gauss–Laguerre) associated with a mesh of "Lagrange functions" to compute the kinetic- and potential-energy matrix elements semi-analytically; by MacDonald's theorem the resulting eigenvalues are variational upper bounds, and increasing the mesh size converges rapidly, making this one of the most efficient high-precision techniques for the Cornell/linear potential.
6. **Momentum-space methods.** The Fourier transform of the linear potential requires care (it is not an ordinary function but involves a derivative of a delta function / requires regularization); high-precision momentum-space treatments recast the problem using Legendre functions of the second kind $Q_\ell$ and Landé-subtraction techniques to handle this singular kernel.
7. **Airy-function/piecewise-linearization approach for general potentials.** More broadly, an arbitrary potential can be approximated locally by a piecewise-linear function, each segment solved exactly in terms of Airy functions, and continuity conditions across segments used to build up a quantization condition — a technique originally developed for anharmonic oscillators but directly rooted in the linear-potential solution.
8. **WKB / Bohr–Sommerfeld quantization.** For large quantum number $n$, the eigenvalues follow the semiclassical quantization condition
 $$\int_{r_1}^{r_2}\sqrt{2\mu\bigl(E_n-V(r)\bigr)}\,dr \approx \left(n+\tfrac12\right)\pi,$$
 giving the well-known result that for a purely linear potential $E_n \propto n^{2/3}$ asymptotically — consistent with the leading large-$n$ behavior of Airy zeros. WKB has also been extended to relativistic (Klein–Gordon-type) treatments of a particle in a linear potential, and to holographic/AdS-QCD confining backgrounds where the same quantization integral governs the large-$n$ Regge behavior.
9. **Hill-determinant, envelope-function, and sum-rule bounding methods.** Techniques that produce rigorous upper and lower bounds on the Cornell/linear-potential eigenvalues without needing to solve the full equation, useful for benchmarking other numerical schemes.
10. **Machine-learning / neural-network approaches.** More recent work has framed the Cornell-potential eigenvalue problem as a function-approximation task solved by artificial neural networks trained to satisfy the Schrödinger equation and boundary conditions, as exact analytic solutions of the full Cornell potential remain unknown.
11. **Effectively-relativistic / semi-relativistic treatments.** For the "spinless Salpeter" or effective semi-relativistic Hamiltonians with a linear potential, eigenvalues away from $\ell=0$ are again generally unknown in closed form; auxiliary-field / variational techniques reduce the problem to solving algebraic (e.g., cubic) equations for expectation values combined with numerical root-finding.

## 6. Method Comparison (Qualitative)

| Method | Exactness | Handles $\ell \neq 0$ | Typical accuracy | Notes |
|---|---|---|---|---|
| Airy closed form | Exact | Only $\ell=0$, no Coulomb term | Exact | Baseline/reference case |
| Power series (Antippa–Phares) | Formally exact | Yes | Limited by series truncation | Combinatorial coefficients |
| NU / AIM / Laplace-transform | Approximate (centrifugal term approximated) | Yes | Good for low-lying states, degrades for large $\ell$ | Closed-form energy formulas |
| Variational (Airy trial function) | Upper bound | Yes | Good, improvable (VIPT) | Physically motivated ansatz |
| Numerov / finite difference | Numerical | Yes | High, mesh-dependent | Standard workhorse |
| DVR | Numerical | Yes | High | No explicit basis functions needed |
| Lagrange-mesh | Numerical, variational | Yes | Very high, fast convergence | Efficient quadrature-based matrix elements |
| Momentum-space (Q-function) | Numerical | Yes | High-precision | Handles singular linear-potential kernel |
| WKB/Bohr–Sommerfeld | Asymptotic | Yes (large $n$) | Good for excited states, poor for ground state | Gives $n^{2/3}$ scaling |
| Neural network | Numerical/variational | Yes | Competitive with classical numerics | Emerging approach |

## 7. Summary

The linear-potential Schrödinger eigenvalue problem occupies an unusual position: its purely one-dimensional, zero-angular-momentum realization is exactly solvable in terms of Airy functions and their zeros, yet essentially every physically relevant generalization — non-zero orbital angular momentum, three dimensions, or the addition of a Coulomb term to form the Cornell potential — destroys exact solvability. This tension has driven nearly a century of methodological development, from early WKB and variational treatments, through combinatorial power-series solutions and Hill-determinant bounds, to modern Numerov, DVR, Lagrange-mesh, and neural-network techniques. The problem remains a standard benchmark for new numerical and semi-analytical quantum-mechanical methods, precisely because the well-understood Airy-function limit provides an exact case against which every generalization can be validated, while the Cornell-potential extension continues to underpin quantitative quarkonium spectroscopy.

## 8. List of Related Publications

1. Antippa, A. F., & Phares, A. J. — *Analytic solution of the Schrödinger equation for the Coulomb-plus-linear potential. I. The wave functions.* J. Math. Phys.
2. Plante, G., & Antippa, A. F. — Wavefunctions and energy eigenvalues (power-series/combinatorial method) for the quark–antiquark Coulomb-plus-linear (Cornell) potential.
3. Ikhdair, S. M., & Sever, R. — Asymptotic Iteration Method (AIM) studies of the Schrödinger equation for the Cornell potential and related quark–antiquark potentials.
4. Ciftci, H., & Kisoglu, H. F. — Non-relativistic arbitrary-$\ell$ states of the quark–antiquark system via the Asymptotic Iteration Method.
5. Abu-Shady, M., Abdel-Karim, T. A., & Khokha, E. M. — *Exact Solution of the N-dimensional Radial Schrödinger Equation via Laplace Transformation Method with the Generalized Cornell Potential*, arXiv:1802.02092.
6. Abu-Shady, M. — *Binding Energies and Dissociation Temperatures of Heavy Quarkonia at Finite Temperature and Chemical Potential in the N-dimensional space*, arXiv:1708.03865.
7. Chung, W.-S. (and related authors) — *The eigenvalue of the confined potential* (exact formula for the eigenvalues of the linear part of the Cornell potential), arXiv:2010.10512.
8. Kumar, R., et al. — *An Improved Analysis of Masses and Decay Constants of Heavy Flavour Mesons within Variational Approach* (Airy trial wavefunction), arXiv:1902.02070.
9. — *Form factors and charge radii in a QCD inspired potential model using the Variationally Improved Perturbation Theory (VIPT)*, arXiv:1112.1477.
10. Silvestre-Brac, B., & Semay, C. — *Testing confining potentials through meson/baryon hyperfine splitting ratio* (Airy-function solution for the two-body linear potential; Hylleraas-type variational treatment), arXiv:hep-ph/0703011.
11. Lucha, W., & Schöberl, F. F. — *Semi-Relativistic Hamiltonians of Apparently Nonrelativistic Form* / *Effectively Semi-Relativistic Hamiltonians of Nonrelativistic Form* (linear potential, Airy zeros, variational/numerical treatment), arXiv:hep-ph/9501278, arXiv:hep-ph/9401268.
12. Semay, C., et al. — *Handling the Cornell potential within the Lagrange-mesh method*, arXiv:2510.03015.
13. Bhaghyesh — *Charmonium Properties Using the Discrete Variable Representation (DVR) Method*, arXiv:2103.06445.
14. — *High-precision methods for Coulomb, linear confinement and Cornell potentials in momentum space*, arXiv:1709.06059.
15. — *Puzzle of the Cornell potential on the heavy and heavy-light meson spectra*, IOPscience, Phys. Scr. (2024), DOI: 10.1088/1402-4896/ad741b.
16. — *Cornell Potential Parameters for S-Wave Heavy Quarkonia*, Phys. Rev. D.
17. — *Cornell Potential: A Neural Network Approach*, arXiv:1812.06802.
18. Whiting, B. F., & Ohanian, H. C. (and related authors) — *The Stark effect in linear potentials* (symmetric linear/quantum-bouncer potential, Airy zero classification), arXiv:0909.2209.
19. — *Sum rules for Confining Potentials* (Airy-function eigenvalues for the linear potential, even/odd sector zeros), arXiv:quant-ph/0611066.
20. Chettri, D., et al. — *Concavity of the meson Regge trajectories* (comparative review of dynamical equations with a linear confinement potential and resulting Regge-trajectory shapes), arXiv:1807.11003.
21. — *Nonrelativistic meson masses from the Curci-Ferrari model* (numerical Schrödinger solution with a Cornell-type linear confinement term), arXiv:2509.04365.
22. Brodsky, S. J., & de Téramond, G. F. — *Light-Front Holographic QCD and the Confinement Potential*, arXiv:1308.5251.
23. Jido, D., & Sakashita, M. — *Quark confinement potential examined by excitation energy of the Λc and Λb baryons in a quark–diquark model*, Prog. Theor. Exp. Phys. 2016, 083D02, DOI: 10.1093/ptep/ptw113.
24. Aitchison, I., & Dudek, J. (and related authors) — *Quark-Antiquark Effective Potential in Symplectic Quantum Mechanics* (phase-space Schrödinger equation with a linear potential), arXiv:2110.12223.
25. Bezerra, V. B., et al. — Klein–Gordon oscillator and confinement by hard-wall and linear scalar potentials in topological-defect spacetimes (related linear-potential confinement problem).
26. Adawi, I. — *Analytical solution of the Schrödinger equation with linear confinement potential* (asymptotically linear potential with Coulomb-type correction for non-zero eigenvalues), J. Phys. A 24 (1991) L1051, DOI: 10.1088/0305-4470/24/22/010.
27. Fakhri, H., & Sadeghi, J. — WKB and related asymptotic treatments of relativistic particles in linear potentials (Klein–Gordon/spinless-Salpeter linear-potential WKB eigenenergies).
28. Vall, S. N., & Buldyrev, V. S. — *Scattering problem for the Schrödinger equation in the case of a potential linear in time and coordinate. I. Asymptotics in the shadow zone*, J. Math. Sci. 32 (1986) 103–112, DOI: 10.1007/BF01084146.
29. Bender, C. M., et al. — General WKB/Bohr–Sommerfeld asymptotic analysis of Schrödinger eigenvalue problems (large-$n$ behavior applicable to linear and other confining potentials), arXiv:1401.6161.
30. Improved holographic QCD reviews — large-$n$ mass asymptotics and linear confinement via WKB quantization of the dual Schrödinger-like equation, arXiv:0707.1349.
31. Bouzenada, A., et al. — *Airy function approach and Numerov method to study the anharmonic oscillator potentials* (piecewise-linear/Airy-function approximation method rooted in the exact linear-potential solution), AIP Advances 6, 065323 (2016).
32. — *Quantum anharmonic oscillator: The Airy function approach*, ScienceDirect (piecewise-linearization method built on Airy-function solution of the linear potential).

*Note: several entries above are drawn from review/survey articles that themselves cite the original primary sources (e.g., Hall's potential-envelope bounds, the Hill-determinant method of Chaudhuri et al., and Crank–Nicolson imaginary-time solutions), which the interested reader can trace through the reference lists of items 17 and 20 in this list.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Linear potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
