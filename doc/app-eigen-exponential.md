# Eigenvalues and Eigenfunctions of the Exponential Potential: A Review of Applications

## 1. Introduction and Definitions

The term "exponential potential" refers to a family of one-dimensional and radial potentials of the general form

$$V(x) = V_0\, e^{-\alpha x}, \qquad V(x) = -V_0\, e^{-\alpha |x|}, \qquad V(x) = V_0\, e^{2x/a},$$

or combinations/generalizations thereof (screened exponential potentials, multi-parameter exponential-type potentials, Hulthén, Manning–Rosen, Eckart, and Morse-type potentials, all of which reduce to or are built from exponential functions of the coordinate). The associated time-independent Schrödinger equation,

$$-\frac{\hbar^2}{2m}\psi''(x) + V(x)\psi(x) = E\,\psi(x),$$

is one of the classic exactly (or quasi-exactly) solvable problems of quantum mechanics. Its importance stems from the fact that a change of variable $z \propto e^{-\alpha x/2}$ transforms the equation into **Bessel's equation**, so that eigenfunctions are expressed in terms of ordinary or modified Bessel functions $J_\nu, Y_\nu, I_\nu, K_\nu$, and the discrete eigenvalues correspond to the **zeros of Bessel functions**, while resonances/virtual states correspond to poles of related scattering amplitudes.

This review surveys the principal physical and mathematical contexts in which the eigenvalue problem for the exponential potential (and its generalizations) has found application, together with representative publications for each area.

---

## 2. Mathematical Structure of the Eigenvalue Problem

For the potential $V(x) = A e^{-\alpha x}$, the substitution $z = \frac{2\sqrt{A}}{\alpha} e^{-\alpha x/2}$ converts the Schrödinger equation into Bessel's equation

$$z^2 Y''(z) + zY'(z) + (z^2 - \nu^2)Y(z) = 0, \qquad \nu^2 = -\frac{4E}{\alpha^2},$$

so that eigenfunctions satisfying a boundary condition at the origin (e.g. $\psi(0)=0$) are combinations of $J_{\pm\nu}(z)$, and the allowed energies are fixed by requiring $J_\nu\!\left(2\sqrt{A}/\alpha\right)=0$ — i.e., the eigenvalues are determined by the **zeros of the Bessel function with respect to its order**, a problem that is itself the subject of dedicated asymptotic and numerical study. For the "wall + exponential wall" or symmetric exponential well/barrier problems, modified Bessel functions $I_\nu, K_\nu$ appear instead, and bound-state energies correspond to zeros of these functions or to poles of Jost functions.

This structural link — **exponential potential ⇄ Bessel functions ⇄ zeros/poles as eigenvalues** — is the unifying mathematical thread running through nearly all of the applications below.

---

## 3. Molecular and Atomic Physics: Diatomic Molecular Spectroscopy

The most extensive modern application area is the use of exponential-type potentials (Hulthén, Hellmann, Manning–Rosen, Eckart, Morse, deformed/generalized/multi-parameter exponential potentials, exponential-screened Coulomb, and combinations such as exponential-cosine-screened Coulomb plus Yukawa or plus Morse) as **empirical models for the internuclear interaction in diatomic molecules**.

**Key uses:**
- Solving the radial Schrödinger equation (often after a Pekeris-type or Greene–Aldrich approximation to handle the centrifugal term for $\ell \neq 0$) to obtain closed-form ro-vibrational energy eigenvalues $E_{n\ell}$ and eigenfunctions (typically hypergeometric or Jacobi/Laguerre polynomials) for real diatomic molecules (H₂, HCl, CO, N₂, LiH, HF, HBr, HgH, ZnH, CdH, ScN, TiH, CrH, NO, etc.).
- Extraction of **spectroscopic constants**, vibrational and rotational energy levels, and comparison against Rydberg–Klein–Rees (RKR) experimental potential curves.
- Computation of **thermodynamic functions** (vibrational partition function, mean energy, specific heat, entropy, free energy) from the derived energy spectrum via the exact or approximate partition function.
- Calculation of **Franck–Condon factors** and **r-centroids** for electronic transitions using derived eigenfunctions.
- Determination of **thermal and magnetic properties** (e.g., magnetization, susceptibility) in generalized/deformed exponential-type potentials, sometimes combined with an Aharonov–Bohm flux field and external magnetic fields (2D problems).

**Representative publications:**
- Ikot, A. N., Awoga, O. A., Ita, B. I., "Bound State Solutions of Exponential-Cosine Screened Coulomb plus Morse Potential," *arXiv:1110.3630*.
- Onate, C. A. et al., "Eigen-solutions and thermal properties of multi-parameter exponential potential," *PMC* (open access), 2022.
- "Bound state solutions and thermodynamic properties of modified exponential screened plus Yukawa potential," *Journal of the Egyptian Mathematical Society*, 2022.
- Ita, B. I. et al., "Bound Energy for the Exponential-Cosine-Screened Coulomb Potential" and companion paper "Bound State Solutions of the Schrödinger Equation for the More General Exponential Screened Coulomb Potential Plus Yukawa (MGESCY) Potential Using Nikiforov–Uvarov Method."
- "Diatomic molecular energy spectra and thermodynamic properties of exponential inversely quadratic plus improved deformed exponential-type potential," *Results in Physics / ScienceDirect*, 2023.
- Falaye, B. J., et al., solutions for the Feinberg–Horodecki (space-like) equation with improved deformed exponential-type potentials, *arXiv:2007.14789*, with quoted applications to biophysics.
- "Numerical Solution of the Schrödinger Equation for a Short-Range 1/r Singular Potential with any L Angular Momentum," *arXiv:1802.04368* (reviews exponential-type potential families: Hulthén, Manning–Rosen, Eckart).
- Various works using the **Nikiforov–Uvarov (NU) method**, **asymptotic iteration method (AIM)**, and **supersymmetric quantum mechanics (SUSYQM)** as principal solution techniques for these potentials.

---

## 4. Molecular Vibration: The Morse Oscillator

The **Morse potential** $V(r) = D_e\left(1-e^{-a(r-r_e)}\right)^2$ is the historically dominant exponential-type potential in molecular physics, modeling anharmonic vibration of diatomic molecules since 1929. Its eigenvalue problem is exactly solvable in terms of associated Laguerre polynomials, giving the well-known Morse vibrational energy formula $E_v = \hbar\omega_e(v+\tfrac12) - \hbar\omega_e x_e (v+\tfrac12)^2$.

**Applications:**
- Accurate ro-vibrational spectroscopy of diatomic molecules.
- Coherent-state and photon-added coherent-state constructions.
- Series solutions in D-dimensional generalizations.
- Position-dependent mass Schrödinger equations.
- Proper quantization rules referencing only the ground-state energy.
- Momentum-space representations via hypergeometric functions.

**Representative publication:**
- "Accurate ro-vibrational spectroscopy of diatomic molecules in a Morse oscillator potential," *arXiv:1307.4978*.

---

## 5. Repulsive Exponential Potentials, Bound/Resonance/Virtual States, and Nuclear/Molecular Scattering

The pure repulsive exponential potential $V(x) = A e^{-\alpha x}$ (with a hard wall or half-line boundary condition) is a long-studied testbed for methods that compute complex eigenvalues associated with **resonances and virtual states**, and is noted in the literature as "a suitable representation of repulsive molecular interactions."

**Applications:**
- Testing high-precision numerical/perturbative methods (e.g., the **Riccati–Padé method**, RPM) for complex eigenvalues.
- Representing short-range repulsive cores in nuclear and molecular potentials.
- Serving as an exactly solvable reference problem for resonance theory, since eigenvalues reduce to (complex) zeros of Bessel functions of complex order.

**Representative publications:**
- "Accurate calculation of the complex eigenvalues of the Schrödinger equation with an exponential potential," *arXiv:0712.3375*.
- "Asymptotic Estimation for Eigenvalues in the Exponential Potential and for Zeros of $K_{i\nu}(z)$ with Respect to Order," *arXiv:2103.01732*.

---

## 6. Scattering Theory, Jost Functions, and Regge Poles

For potentials of Yukawa/exponential type, $V(r) \sim e^{-\mu r}/r$ or $V(x) = -V_0 e^{-\kappa|x|}$, the **Jost solutions** can be written explicitly in terms of Bessel/Gamma functions, and the analytic structure of the resulting **S-matrix** in the complex angular-momentum plane defines **Regge poles/trajectories**, connecting bound states, virtual states, and resonances into a single analytic framework.

**Applications:**
- Foundational work by Regge on analytic continuation of partial-wave amplitudes to complex angular momentum, using potentials including exponential/Yukawa-type tails, establishing the **Bargmann strip** of analyticity.
- Determination of **resonance spectra** and their distribution for one-dimensional and 3D exponential potentials via Jost/Gamow-state formalism.
- Application to **hadronic/Regge phenomenology** in particle physics (nonperturbative dynamics of hadronic collisions), where Regge trajectories originally derived from Yukawa/exponential-type nonrelativistic potentials underlie the interpretation of high-energy scattering data.
- Rigorous mathematical results on **localization of Regge poles** for potentials with (super-)exponential decay, relevant to inverse scattering theory.
- Scattering length and phase-shift formulas for the attractive exponential potential expressed via Bessel functions of complex order (semi-spectral/Chebyshev numerical schemes benchmark against these closed forms).

**Representative publications:**
- Regge, T., "Mathematical Theory of Potential Scattering," classic lecture notes (CERN archive).
- "Distribution of Resonant Eigenvalues of Quantum Potential Scattering," *arXiv:0909.2463* (Section 4: Exponential potential).
- "Scattering states and bound states of exponential potentials," *arXiv:2102.06095*.
- "Local inverse scattering at a fixed energy for radial Schrödinger operators and localization of the Regge poles," *arXiv:1502.02276*.
- "Nonperturbative Dynamics of Hadronic Collisions," *arXiv:1908.01040* (Section 3.1, Regge Poles).
- "One dimensional scattering from two-piece rising potentials: a new avenue of resonances," *arXiv:1408.0231* (exponential rising potential mapped to modified Bessel equation).
- "Semi-spectral Chebyshev method in Quantum Mechanics," *arXiv:quant-ph/0606100* (Appendix A: exponential potential phase shifts).

---

## 7. Liouville Quantum Mechanics, Dilaton Black Holes, and Quasinormal Modes

The pure exponential potential $M_k = -\partial_x^2 + k^2 e^{2x}$ is precisely the **Liouville quantum-mechanical Hamiltonian**, with eigenfunctions given by (2D) Bessel/Macdonald functions. This structure recurs prominently in:

**Applications:**
- **Liouville conformal field theory (Liouville CFT)** and related exactly solvable models in 2D quantum gravity/string theory.
- Schrödinger operators on **hyperbolic manifolds**.
- **Quasinormal mode (QNM)** spectra of dilatonic and other black holes, where the effective radial potential in the wave equation for perturbations asymptotes to (double) Liouville-type exponential potentials at the horizon(s) and at infinity; the QNM frequencies play the role of (generally complex, non-Hermitian) eigenvalues.
- Exact analytic QNM frequencies for **charged fermionic perturbations of linear-dilaton black holes** obtained via hypergeometric-function solutions tied to Liouville-type potentials.
- More general "Pöschl–Teller-like" toy models with exponentially decaying tails at $\pm\infty$, used to model and compute resonances of Reissner–Nordström–de Sitter black holes via Jost-function methods, directly generalizing the pure exponential-potential Jost solution technology.

**Representative publications:**
- Foundational treatment of $M_k = -\partial_x^2 + k^2 e^{2x}$ and 2D Bessel functions: "Exactly solvable Schrödinger operators related to the confluent equation," *arXiv:2409.14994* (Section 3.2, "Exponential potentials").
- Sakalli, İ., Tokgöz Hyusein, G., "Quasinormal modes of charged fermions in linear dilaton black hole spacetime: Exact frequencies," *Turkish Journal of Physics* / *arXiv:2102.03595*.
- Konoplya, R. A., Zhidenko, A., "Quasinormal modes of black holes and black branes," review, *arXiv:0905.2975*.
- "Quasinormal modes of non-Abelian hyperscaling violating Lifshitz black holes," *arXiv:1510.04605*.
- "Computing resonances of perturbed Schrödinger equations: application to Reissner–Nordström–de Sitter black holes," *arXiv:2606.18770*.
- Dyatlov, S., "Quasinormal modes for Schwarzschild–AdS black holes: exponential convergence to the real axis," *arXiv:1212.1907*.
- Couch, W. E. and collaborators, work on Liouvillian quasinormal modes of black holes (Kovacic algorithm), PhD thesis, University of Calgary.

---

## 8. Exponential Decay of Eigenfunctions: Spectral Theory of Schrödinger Operators

A distinct but related mathematical-physics application concerns not the exponential potential itself but the **exponential decay rate of eigenfunctions** of general Schrödinger operators $H=-\Delta+V$ — a cornerstone result of rigorous spectral theory with implications for perturbation theory, localization, and numerical truncation of domains.

**Applications:**
- Agmon-metric estimates bounding the decay of eigenfunctions associated with discrete eigenvalues below the essential spectrum.
- Absence-of-positive-eigenvalues results and $L^2$-exponential lower/upper bounds for $N$-body Schrödinger operators (used in atomic and molecular many-body theory).
- **Anderson localization** in random Schrödinger operators (condensed matter theory): eigenfunctions in the localized regime decay exponentially, and this underlies the theory of electronic transport (or its suppression) in disordered solids.
- Decay estimates for Schrödinger operators on **infinite metric graphs** (quantum graphs), relevant to nanostructures and network models.

**Representative publications:**
- Agmon, S., *Lectures on Exponential Decay of Solutions of Second-Order Elliptic Equations: Bounds on Eigenfunctions of N-Body Schrödinger Operators*, Princeton University Press (classic monograph).
- Reed, M., Simon, B., *Methods of Modern Mathematical Physics, Vols. I & IV*, Academic Press.
- Deift, P., Hunziker, W., Simon, B., Vock, E., "Exponential bounds and absence of positive eigenvalues for N-body Schrödinger operators," *Communications in Mathematical Physics*, 1978.
- Hislop, P. D., Kirsch, W., Krishna, M., "Eigenfunctions and Quantum Transport with Applications to Trimmed Schrödinger Operators," *arXiv:2401.07262*.
- "Exponential decay of eigenfunctions of Schrödinger operators on infinite metric graphs," *ResearchGate* (weighted $p$-Laplacian on metric graphs).

---

## 9. Feinberg–Horodecki (Space-like) Equation and Interdisciplinary Extensions

Exponential-type potentials inserted into the **Feinberg–Horodecki equation** (the time/momentum analogue of the spatial Schrödinger equation) yield quantized **momentum eigenvalues** rather than energy eigenvalues, extending the exponential-potential eigenvalue problem into a temporal setting with claimed relevance to **biophysics** (e.g., modeling of DNA/biological growth-type processes) via time-dependent supersymmetric quantum mechanics.

**Representative publication:**
- "Feinberg–Horodecki exact momentum states of improved deformed exponential-type potential," *arXiv:2007.14789*.

---

## 10. Summary Table

| Application Domain | Role of Exponential Potential | Typical Eigenfunctions | Representative Method(s) |
|---|---|---|---|
| Diatomic molecular spectroscopy | Empirical internuclear potential | Hypergeometric / Jacobi / Laguerre polynomials | Nikiforov–Uvarov, AIM, SUSYQM |
| Morse oscillator | Anharmonic vibrational potential | Associated Laguerre polynomials | Exact factorization, ladder operators |
| Repulsive exponential wall | Model of short-range repulsion, resonance testbed | Bessel functions $J_\nu$ | Riccati–Padé method, asymptotics of Bessel zeros |
| Scattering / Regge poles | Yukawa-like tail, analytic S-matrix structure | Jost solutions (Bessel/Gamma functions) | Complex angular momentum, Jost function analysis |
| Liouville QM / black hole QNMs | Effective near-horizon/asymptotic potential | Modified Bessel / hypergeometric functions | Kovacic algorithm, Jost functions, AIM |
| Spectral theory (Agmon-type) | General potential decay behavior | Exponentially weighted Sobolev estimates | Agmon metric, Combes–Thomas estimate |
| Feinberg–Horodecki / biophysics | Time-like potential | Special functions in momentum space | NU method |

---

## 11. Consolidated Bibliography

1. Regge, T. *Mathematical Theory of Potential Scattering*. CERN lecture notes archive.
2. Agmon, S. *Lectures on Exponential Decay of Solutions of Second-Order Elliptic Equations: Bounds on Eigenfunctions of N-Body Schrödinger Operators*. Princeton University Press.
3. Reed, M., Simon, B. *Methods of Modern Mathematical Physics*, Vol. I (Functional Analysis) and Vol. IV (Analysis of Operators). Academic Press.
4. Deift, P., Hunziker, W., Simon, B., Vock, E. "Exponential bounds and absence of positive eigenvalues for N-body Schrödinger operators." *Communications in Mathematical Physics*, 64, 1–34 (1978).
5. "Accurate calculation of the complex eigenvalues of the Schrödinger equation with an exponential potential." *arXiv:0712.3375*.
6. "Asymptotic Estimation for Eigenvalues in the Exponential Potential and for Zeros of $K_{i\nu}(z)$ with Respect to Order." *arXiv:2103.01732*.
7. "Exactly solvable Schrödinger operators related to the confluent equation." *arXiv:2409.14994*.
8. "Numerical Solution of the Schrödinger Equation for a Short-Range 1/r Singular Potential with any L Angular Momentum." *arXiv:1802.04368*.
9. Hislop, P. D., Kirsch, W., Krishna, M. "Eigenfunctions and Quantum Transport with Applications to Trimmed Schrödinger Operators." *arXiv:2401.07262*.
10. "Feinberg–Horodecki exact momentum states of improved deformed exponential-type potential." *arXiv:2007.14789*.
11. "Bound state solutions and thermodynamic properties of modified exponential screened plus Yukawa potential." *Journal of the Egyptian Mathematical Society* (2022).
12. "Eigen-solutions and thermal properties of multi-parameter exponential potential." *PMC*, PMC9463593 (2022).
13. Ita, B. I., et al. "Bound energy for the exponential-cosine-screened Coulomb potential" and "Bound State Solutions of the Schrödinger Equation for the More General Exponential Screened Coulomb Potential Plus Yukawa (MGESCY) Potential Using Nikiforov-Uvarov Method."
14. Ikot, A. N., Awoga, O. A., Ita, B. I. "Bound State Solutions of Exponential-Coshine Screened Coulomb plus Morse Potential." *arXiv:1110.3630*.
15. "Accurate ro-vibrational spectroscopy of diatomic molecules in a Morse oscillator potential." *arXiv:1307.4978*.
16. "Diatomic molecular energy spectra and thermodynamic properties of exponential inversely quadratic plus improved deformed exponential-type potential." *ScienceDirect / Results in Physics* (2023).
17. "Modelling of diatomic molecules" (general molecular oscillator, Franck–Condon factors). *ResearchGate*.
18. "Scattering states and bound states of exponential potentials." *arXiv:2102.06095*.
19. "Distribution of Resonant Eigenvalues of Quantum Potential Scattering." *arXiv:0909.2463*.
20. "Local inverse scattering at a fixed energy for radial Schrödinger operators and localization of the Regge poles." *arXiv:1502.02276*.
21. "Nonperturbative Dynamics of Hadronic Collisions." *arXiv:1908.01040*.
22. "One dimensional scattering from two-piece rising potentials: a new avenue of resonances." *arXiv:1408.0231*.
23. "Semi-spectral Chebyshev method in Quantum Mechanics." *arXiv:quant-ph/0606100*.
24. Sakalli, İ., Tokgöz Hyusein, G. "Quasinormal modes of charged fermions in linear dilaton black hole spacetime: Exact frequencies." *arXiv:2102.03595*.
25. Konoplya, R. A., Zhidenko, A. "Quasinormal modes of black holes and black branes." *arXiv:0905.2975*.
26. "Quasinormal modes of non-Abelian hyperscaling violating Lifshitz black holes." *arXiv:1510.04605*.
27. "Computing resonances of perturbed Schrödinger equations: application to Reissner–Nordström–de Sitter black holes." *arXiv:2606.18770*.
28. Dyatlov, S. "Quasinormal modes for Schwarzschild–AdS black holes: exponential convergence to the real axis." *arXiv:1212.1907*.
29. Couch, W. E., et al. "Liouvillian Quasinormal Modes of Black Holes." PhD Thesis, University of Calgary (PRISM repository).
30. "Exponential decay of eigenfunctions of Schrödinger operators on infinite metric graphs." *ResearchGate*.

---

*Note: This review focuses on the exponential potential $V \sim e^{-\alpha x}$ and closely related exponential-type potential families (Hulthén, Manning–Rosen, Eckart, Morse, Liouville) as they appear across quantum mechanics, molecular/nuclear physics, scattering theory, and gravitational physics. Sources were identified via literature search and are current as of the search date; readers should consult the original articles for full technical detail and complete reference lists.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Exponential potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
