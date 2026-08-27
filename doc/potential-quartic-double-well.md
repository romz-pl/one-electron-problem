# Evaluation of Eigenvalues of the Schrödinger Equation with a Quartic Double-Well Potential: A Review

## 1. Introduction and Physical Motivation

The one-dimensional quartic double-well potential is one of the most extensively studied non-trivial model systems in quantum mechanics. In its most common symmetric form it is written as

$$V(x) = -\Lambda x^2 + x^4 \qquad \text{or equivalently} \qquad V(x) = \frac{1}{2}m\omega^2\left(\frac{x^2}{4a^2}-1\right)^2 a^2,$$

with two degenerate minima separated by a central barrier. A commonly used one-parameter rescaled form is

$$V(u) = u^2(1-u)^2,$$

which reduces both the quartic single-well anharmonic oscillator and the quartic double-well problem to a single dimensionless coupling. Asymmetric variants,

$$V(x) = x^4 - ax^2 + bx, \qquad a>0,$$

are used to model tilted or biased double wells, relevant to Bose–Einstein condensates in tilted traps, magnetic molecules, and asymmetric hydrogen bonds.

Physically, this potential is the canonical model for **quantum tunneling between two degenerate (or nearly degenerate) classical configurations**. Its eigenvalue spectrum underlies the description of:

- Inversion (umbrella) vibration of the ammonia molecule (NH₃)
- Proton and hydrogen-bond tunneling (e.g., in malonaldehyde, carboxylic acid dimers)
- Ring-puckering vibrations in ring molecules (1,3-dioxole, 2,3-dihydrofuran)
- Macroscopic quantum tunneling and coherence in SQUIDs and magnetic molecules (e.g., Fe₈ spin clusters)
- Symmetry breaking and instanton physics in quantum field theory, where the double well is the textbook model for vacuum tunneling and the dilute instanton gas
- Bose–Einstein condensates in symmetric and tilted double-well traps
- Large-order behavior of perturbation theory and resurgence (Bender–Wu type analysis)

The Schrödinger equation with this potential,

$$-\frac{\hbar^2}{2m}\frac{d^2\psi}{dx^2} + V(x)\psi(x) = E\psi(x),$$

has **no closed-form analytic solution** in terms of elementary or standard special functions for generic parameters. This has made it a long-standing testbed for essentially every analytic, semiclassical, and numerical technique developed for one-dimensional Schrödinger problems, and it remains an active benchmark problem today.

---

## 2. Structure of the Spectrum

Key qualitative features that any method must reproduce:

1. **Near-degenerate doublets.** For sufficiently high or wide barriers, eigenstates below the barrier top form nearly degenerate pairs (even/odd, or symmetric/antisymmetric combinations), split by an exponentially small energy gap $\Delta E = E_{2n+1}-E_{2n}$ due to tunneling.
2. **Exponential sensitivity.** The splitting $\Delta E$ depends exponentially on the barrier height and width, so naive numerical schemes (finite differences, low-order variational bases) can lose all significant figures unless extended/quadruple precision or specialized techniques are used.
3. **Crossover regime.** Near and above the barrier top, the doublet structure disappears smoothly into a single quartic-oscillator-like spectrum; a uniform treatment across this crossover is nontrivial.
4. **Non-perturbative character.** The splitting is not analytic in the coupling constant at weak coupling (it behaves like $\sim e^{-c/g}$), so ordinary Rayleigh–Schrödinger perturbation theory around either minimum entirely misses it — a famous illustration of the limits of perturbation theory and a motivation for resurgent/trans-series analysis.

---

## 3. Analytic and Semiclassical Methods

### 3.1 WKB Approximation and Connection Formulas
The standard semiclassical approach constructs WKB wavefunctions in the classically allowed regions around each minimum and under the barrier, matching them via Airy-function connection formulas at the turning points. The classic result (Landau–Lifshitz form) for the ground-state splitting is

$$\Delta \approx \frac{\hbar\omega}{\sqrt{e\pi}}\exp\left[-\frac{1}{\hbar}\int_{-a}^{a}|p(x)|\,dx\right].$$

Limitations: the ordinary connection formula is known to have systematic errors near the barrier top and for shallow/asymmetric wells; several refinements exist (higher-order WKB expansions, Garg's formula, anharmonicity-corrected WKB).

### 3.2 Instanton (Path-Integral) Method
The imaginary-time path-integral approach evaluates the splitting via the "instanton" (bounce) trajectory connecting the two minima in Euclidean time. For the symmetric quartic double well this gives, to leading order, a result that coincides with the WKB prediction when the correct connection formula is used, and it is generally regarded as more systematically improvable (via a dilute instanton gas expansion and multi-instanton corrections) than plain WKB.

### 3.3 Zinn-Justin Conjecture / Exact Quantization Conditions
Zinn-Justin's generalized Bohr–Sommerfeld quantization condition unifies perturbative (large-order) and non-perturbative (instanton) information into a single exact quantization formula for the double well, connecting to resurgence theory and the large-order growth of Rayleigh–Schrödinger perturbation series (Bender–Wu analysis). This conjecture has been tested against high-precision numerics with excellent agreement.

### 3.4 Quasi-Exact Solvability (Lie-Algebraic / Hidden sl(2) Methods)
Certain double-well potentials (and their multi-parameter generalizations) are **quasi-exactly solvable (QES)**: a finite subset of eigenstates can be obtained in closed algebraic form because the Hamiltonian, after a similarity/gauge transformation, lies in the universal enveloping algebra of $sl(2,\mathbb{R})$ acting on a finite-dimensional space of polynomials. Turbiner's original 1988 construction founded this framework, later extended to double-well and asymmetric double-well potentials, with the "hidden algebra" acting on the lowest $N$ states while the rest of the spectrum remains inaccessible algebraically.

### 3.5 Asymptotic/Uniform Approximations from the Anharmonic Oscillator
A recent approach exploits the fact that the single-well quartic anharmonic oscillator $V=u^2+u^4$ and the double-well $V=u^2(1-u)^2$ are related by an effective one-parameter reduction; a uniformly accurate approximate eigenfunction for the anharmonic oscillator can be recombined ($\Psi_{dw}(u)=\Psi_{ao}(u)\pm\Psi_{ao}(u-1)$) to produce highly accurate double-well eigenfunctions and eigenvalues without full diagonalization.

### 3.6 Asymptotic Iteration Method (AIM) and Related Iterative Schemes
The Asymptotic Iteration Method converts the Schrödinger equation into an iterative algebraic recursion for polynomial coefficients and has been applied successfully to symmetric and asymmetric anharmonic and double-well oscillators, offering an alternative to matrix diagonalization for moderate-precision eigenvalue extraction.

### 3.7 Green's Function / Lippmann–Schwinger Approaches
Formulating the problem via an energy-dependent Green's function and matching conditions at the boundary of a compact interval converts eigenvalue determination into locating the zeros/extrema of an "energy function," providing an alternative root-finding-based route that separates naturally into even- and odd-parity branches.

### 3.8 Wronskian / Canonical-Function Methods
Constructing two independent solutions of the Schrödinger equation (regular at $-\infty$ and at $+\infty$, or regular at the two turning points) and demanding continuity of the logarithmic derivative yields an eigenvalue function $F(E)$ whose zeros are the bound-state energies. This underlies several "exact" (numerically converged) treatments of both symmetric and asymmetric double-well and double-square-well potentials.

---

## 4. Numerical Methods

### 4.1 Diagonalization in a Harmonic-Oscillator Basis
The most widely used numerical approach expands $\psi(x)$ in eigenstates of an auxiliary harmonic oscillator and diagonalizes the resulting (banded, parity-decomposed) Hamiltonian matrix. Because tunneling splittings are exponentially small, **standard double precision is insufficient** for barrier parameters of practical interest; published high-accuracy benchmark calculations use **quadruple precision (32 significant digits)** arithmetic to resolve splittings down to $10^{-10}$ or smaller relative to the mean level spacing. Parity symmetry (for symmetric wells) allows the matrix to be block-diagonalized into even/odd sectors, which is essential both for efficiency and for numerical stability of the splitting extraction.

### 4.2 Variational Methods with Physically-Motivated Trial Functions
Supersymmetric-QM-inspired trial wavefunctions (e.g., Broges *et al.*) have been used for variational estimates of the ground and low excited states; these can be inaccurate compared to properly converged numerical benchmarks and are best used as qualitative or starting-point estimates.

### 4.3 Basis-Set Methods in Confined Geometries: Legendre / DVR Bases
An alternative "economical" numerical procedure expands the wavefunction in Legendre polynomials (or another orthogonal basis) on a large but finite interval $[-T_M, T_M]$, exploiting the exponential decay of bound states to control truncation error; comparative studies show excellent agreement (to several significant figures in the splitting $\Delta E$) between this approach, an "improved" relaxation-type iterative eigenvalue method, and direct numerical integration.

Discrete Variable Representation (DVR) methods, standard in molecular spectroscopy (e.g., ammonia inversion, ring-puckering problems), are also routinely applied and are numerically robust because they diagonalize a simple, sparse, real-symmetric matrix built from a spatial grid.

### 4.4 Embedding in an Infinite Square Well
A pedagogically important numerically-exact formulation embeds the double well inside an infinite square well of large width, converts the problem into diagonalization of a simple analytic matrix (with closed-form matrix elements for quadratic and quartic embedded wells), and recovers both the below-barrier doublet structure and the above-barrier continuum-like spectrum from a single truncated matrix, cross-validated against WKB predictions in all three physical regimes (deep doublets, near-barrier states, above-barrier states).

### 4.5 Direct Numerical Integration / Shooting Methods
Direct numerical integration (e.g., Numerov or Runge–Kutta shooting from both boundaries with matching at an interior point) remains a standard cross-check, particularly for asymmetric or non-quartic double wells where basis-set methods are less naturally adapted, though achieving the precision needed for exponentially small splittings requires care (adaptive step size, extended precision, or Richardson extrapolation).

### 4.6 Power-Series / Frobenius Methods with Enclosing Walls
A high-precision technique encloses the system between two infinite walls separated by a large finite distance and constructs a power-series (Frobenius-type) solution of the Schrödinger equation matched at the walls; results for the symmetric double well have been benchmarked directly against the Zinn-Justin conjecture with excellent agreement, providing one of the most precise fully numerical cross-checks of the semiclassical/resurgent predictions available in the literature.

---

## 5. Comparative Assessment of Methods

| Method family | Typical accuracy regime | Strengths | Limitations |
|---|---|---|---|
| Ordinary WKB / connection formulas | Good for deep levels, moderate for near-barrier states | Simple, physically transparent, closed-form | Systematic errors near barrier top; connection-formula ambiguities in asymmetric case |
| Instanton / path integral | Matches WKB at leading order; improvable via multi-instanton corrections | Systematic non-perturbative expansion; connects to field-theory intuition | Requires dilute-instanton-gas assumption (well-separated wells) |
| Zinn-Justin exact quantization / resurgence | Extremely high precision when combined with large-order perturbative data | Unifies perturbative and non-perturbative sectors | Requires input from Bender–Wu large-order coefficients; mathematically involved |
| Quasi-exact solvability (hidden sl(2)) | Exact (closed form) for a finite subset of states, for special potential families | Genuinely exact, not approximate, for the accessible states | Only applies to special (algebraic) parameter families / low-lying subset of the spectrum |
| Harmonic-oscillator-basis diagonalization (extended precision) | Numerically "exact" to any desired precision given enough digits/basis size | General purpose, systematically convergent, benchmark-quality | Requires quadruple/arbitrary precision arithmetic for exponentially small splittings; basis truncation |
| Legendre/DVR basis on finite domain | Numerically exact given sufficient basis size and domain | Efficient, simple to implement, good cross-check | Domain-size/truncation dependence must be checked |
| Embedded infinite square well | Numerically exact; unifies below-, near-, and above-barrier regimes | Simple matrix elements, pedagogically transparent | Wall effects must be controlled for weakly bound / high states |
| Power-series with enclosing walls | Extremely high precision (matches Zinn-Justin conjecture to many digits) | Very high accuracy achievable | More involved implementation than basis diagonalization |
| Asymptotic Iteration Method (AIM) | Moderate to good | No matrix diagonalization required; algebraic recursion | Convergence and stability can be delicate for highly excited or near-degenerate states |
| Variational (trial wavefunction) methods | Qualitative to moderate | Fast, physically motivated | Can be substantially less accurate than claimed if not benchmarked carefully |

**General consensus in the literature:** for genuinely high-precision eigenvalues and splittings (needed, e.g., to test the Zinn-Justin conjecture or resurgent trans-series predictions), numerically-exact basis-diagonalization or power-series methods in extended (quadruple or higher) precision are the gold standard, with semiclassical/instanton methods providing physical insight and useful analytic approximations that are cross-validated against these numerical benchmarks.

---

## 6. List of Related Publications

1. A. V. Turbiner, "From quartic anharmonic oscillator to double well potential," *arXiv:2111.01546* (2021).
2. G. Álvarez, "A basis for variational calculations in *d* dimensions," *arXiv:math-ph/0410035* — includes discussion of $V(r) = -\gamma r^2 + r^4$.
3. R. Koç and D. Haydargil, "Solution of the Schrödinger equation with one and two dimensional double-well potentials," *arXiv:quant-ph/0410067*.
4. "An economical method to calculate eigenvalues of the Schrödinger Equation," *arXiv:physics/0606030* (Legendre-basis and relaxation-method comparison for the double well).
5. Wikipedia, "Double-well potential" — overview of instanton, WKB, and Lamé-function approaches (https://en.wikipedia.org/wiki/Double-well_potential).
6. "The Extended Wronskian Determinant Approach and the Iterative Solutions of One-Dimensional Dirac Equation," *arXiv:nucl-th/0306010* (includes non-relativistic double-well benchmark).
7. J. Cioslowski, "Calculation of eigenvalues by Green's functions and the Lippmann-Schwinger equation," *arXiv:1902.01624*.
8. F. M. Fernández and J. Garcia, "Exact Solutions of the Quantum Double-Square-Well Potential" (Academia.edu preprint).
9. Dae-Yup Song, "Tunneling and energy splitting in an asymmetric double-well potential," *Annals of Physics*, and *arXiv:0803.3113* (2008).
10. M. Robnik, L. Salasnich, and M. Vraničar, "High order WKB prediction of the energy splitting in the symmetric double well potential," *arXiv:nlin/0003050* (2000).
11. M. Robnik, L. Salasnich, and M. Vraničar, "Accuracy of the WKB approximation: the case of general quartic potential," *arXiv:nlin/0003051* (2000).
12. "Effect of Anharmonicity on the WKB Energy Splitting in a Double Well Potential," *arXiv:quant-ph/9609008*.
13. R. W. Robinett, "The double-well potential in quantum mechanics: a simple, numerically exact formulation," *arXiv:1209.2521* (2012); also published in *American Journal of Physics*.
14. H. A. Alhendi and E. I. Lashin, "High-Precision Numerical Determination of Eigenvalues for a Double-Well Potential Related to the Zinn-Justin Conjecture," *arXiv:quant-ph/0402101* (2004).
15. B. Midya and B. Roy, "Quantum confinement in an asymmetric double-well potential through energy analysis and information entropic measure," *arXiv:1904.06076*.
16. "Exactly solvable piecewise analytic double well potential," *arXiv:2209.09445* (piecewise-analytic exact quartic-type double well).
17. Y.-Q. Ma and collaborators, "Macroscopic quantum tunneling and quantum-classical phase transitions of the escape rate in large spin systems," *arXiv:1403.4208* (instanton treatment of the double well applied to spin tunneling).
18. A. V. Turbiner, "Quasi-exactly-solvable problems and $sl(2)$ algebra," *Communications in Mathematical Physics* **118**, 467 (1988) — foundational QES paper underlying algebraic double-well solutions.
19. "Quasi-Exactly Solvable Double-Well Potential and Polynomial Deformations of sl(2) Lie Algebra" (Academia.edu preprint), applying hidden-algebra methods explicitly to the double well.
20. A. V. Turbiner, "One-dimensional quasi-exactly solvable Schrödinger equations," *Physics Reports* **642**, 1–71 (2016) — comprehensive review covering double-well and related QES potentials.
21. "Entropic characterization of Tunneling and State Pairing in a Quasi-Exactly Solvable Sextic Potential," *arXiv:2506.22684* (methodologically adjacent QES multi-well treatment).
22. J. Zinn-Justin and U. D. Jentschura, works developing the Zinn-Justin conjecture and resurgent trans-series for the symmetric double well (see references within Alhendi & Lashin, item 14, and Physics Reports reviews on multi-instanton physics).
23. C. M. Bender and T. T. Wu, "Anharmonic Oscillator," *Physical Review* **184**, 1231 (1969), and "Anharmonic Oscillator. II. A Study of Perturbation Theory in Large Order," *Physical Review D* **7**, 1620 (1973) — foundational large-order perturbation theory results underpinning resurgence-based double-well analyses.
24. Lecture notes: "115C (QM III): The Double Well," UC Santa Barbara — pedagogical WKB/instanton treatment (https://web.physics.ucsb.edu/~davidgrabovsky/files-teaching/Double%20Well%20Solutions.pdf).
25. "Appendix G: Double-Well Potential: Symmetry and Tunnelling," University of Maryland Chem 691 notes — DVR-based numerical treatment (https://www2.chem.umd.edu/groups/alexander/chem691/Double_well.pdf).

---

## 7. Summary

The quartic double-well Schrödinger eigenvalue problem sits at the intersection of semiclassical analysis, non-perturbative field-theoretic methods (instantons, resurgence), algebraic quasi-exact-solvability, and high-precision numerical linear algebra. No single method is universally optimal: WKB and instanton methods give fast, physically transparent estimates and organize the non-perturbative structure of the spectrum; the Zinn-Justin conjecture and resurgence theory provide a unifying analytic framework connecting perturbative and non-perturbative data; quasi-exact solvability gives genuinely closed-form results for special potential families and a finite subset of states; and extended-precision numerical diagonalization or power-series methods remain the indispensable benchmark against which all approximate schemes are validated, owing to the exponentially small energy splittings that define the problem's defining physical phenomenon — quantum tunneling between degenerate wells.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Quartic double well potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
