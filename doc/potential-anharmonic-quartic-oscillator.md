# Evaluation of Eigenvalues of the Schrödinger Equation with the Quartic Anharmonic Oscillator Potential: An Exhaustive Review

## 1. Introduction and Statement of the Problem

The quantum anharmonic oscillator with a quartic potential term is one of the most extensively studied non-trivial problems in quantum mechanics. Unlike the harmonic oscillator, it has no closed-form analytic solution, yet it is simple enough to serve as the canonical testing ground for virtually every perturbative, semiclassical, variational, and numerical technique developed for the one-dimensional time-independent Schrödinger equation. Its importance extends well beyond a textbook exercise: it is the quantum-mechanical reduction of $\phi^4$ scalar field theory to zero spatial dimensions, it models molecular vibrations beyond the harmonic approximation, it underlies double-well tunneling problems, and it is a paradigm for the study of divergent (asymptotic) perturbation series in physics.

### 1.1 The Hamiltonian

The one-dimensional quartic anharmonic oscillator is defined by the Hamiltonian (in units $\hbar = m = 1$)

$$H = -\frac{d^2}{dx^2} + x^2 + \lambda x^4,$$

or, in the more general two-parameter form used in many studies,

$$H = -\frac{d^2}{dx^2} + \omega^2 x^2 + \lambda x^4, \qquad \lambda > 0,$$

with the corresponding stationary Schrödinger equation

$$-\psi''(x) + \left(x^2 + \lambda x^4\right)\psi(x) = E\,\psi(x), \qquad \psi(\pm\infty) = 0.$$

For $\lambda < 0$ the potential develops a double-well or unbounded structure, giving rise to related but distinct problems (barrier tunneling, resonance/Siegert states, and $\mathcal{PT}$-symmetric extensions such as $H = p^2 - x^4$ or $H = p^2 + ix^3$), which are touched on below because much of the eigenvalue methodology transfers directly.

### 1.2 Why the Problem Is Nontrivial

The quartic term destroys the exact solvability enjoyed by the harmonic oscillator: the equation is not one of the classical hypergeometric-type equations with polynomial solutions in closed form (except for special quasi-exactly-solvable subfamilies, see Section 6.5). Formal Rayleigh–Schrödinger perturbation theory in the coupling $\lambda$ produces coefficients that **grow factorially and alternate in sign**, so the perturbation series has **zero radius of convergence** — it is an asymptotic, divergent series for every $\lambda \neq 0$. This was rigorously established by Bender and Wu (1969), and it is precisely this pathology that made the quartic oscillator the historical proving ground for the entire field of "large-order perturbation theory" and resummation techniques (Borel summation, Padé approximants, dispersion relations).

---

## 2. Historical Overview

| Period | Development |
|---|---|
| 1920s–1950s | Early Rayleigh–Schrödinger perturbative treatments of anharmonicity in molecular vibration spectroscopy. |
| 1969–1973 | **Bender & Wu** prove divergence of the perturbation series and derive its large-order behavior via analytic continuation in the complex coupling plane and dispersion relations ("Bender–Wu theory"). |
| 1970s | Hill-determinant method (Biswas, Datta, Saxena, Srivastava, Varma, 1971); Padé and Borel–Padé summation of the divergent series (Graffi, Grecchi, Simon); large-order perturbation theory for $\phi^{2N}$ field theories (Brézin, Le Guillou, Zinn-Justin). |
| 1978–1983 | Complex WKB / exact quantization (Voros; Balian–Parisi–Voros); shifted $1/N$ expansion introduced for anharmonic potentials. |
| 1980s–1990s | Supersymmetric WKB (SWKB); variational and renormalized strong-coupling expansions (Weniger, Čížek, Vinette); high-precision numerics via Numerov, shooting, and matrix diagonalization. |
| 2000s | Asymptotic iteration method (AIM); Riccati–Padé method; high-precision arbitrary-order computations (Trott); quasi-exact and Lie-algebraic solutions for special parameter families. |
| 2010s–2020s | Resurgence and exact WKB (trans-series, Bender–Wu Mathematica package); double-exponential Sinc collocation; asymptotic Taylor expansion method (ATEM); machine-learning/neural-network solvers; Fisher-information and information-theoretic approaches; continued extension to complex/$\mathcal{PT}$-symmetric quartic potentials. |

---

## 3. Perturbative Approaches

### 3.1 Rayleigh–Schrödinger Perturbation Theory (RSPT)

Treating $\lambda x^4$ as a perturbation on the harmonic oscillator gives, order by order,

$$E_n(\lambda) = E_n^{(0)} + \lambda E_n^{(1)} + \lambda^2 E_n^{(2)} + \cdots,$$

with coefficients computable via standard formulas or, more efficiently, via the **Hellmann–Feynman and hypervirial theorems**, which allow the perturbative coefficients of the energy to be generated recursively *without* explicit computation of the perturbed eigenfunctions (Rekab & Zenine). This is computationally far cheaper than the conventional RSPT machinery for high orders.

**Fundamental obstruction:** Bender and Wu showed the coefficients $E_n^{(k)}$ grow as $k!$, alternate in sign, and the series diverges for any $\lambda \neq 0$. This divergence is tied to instability of the classical vacuum for $\lambda < 0$: the eigenvalue $E_n(\lambda)$, viewed as a function of complex $\lambda$, has a branch cut along the negative real axis, and the large-order coefficients are governed by the discontinuity of $E_n(\lambda)$ across that cut (a dispersion-relation / instanton argument). This yields the asymptotic large-order estimate

$$a_k \sim \text{const} \times (-1)^{k+1}\, \Gamma(k+\tfrac12)\, c^{k} \quad (k \to \infty),$$

for constants depending on the state and normalization — the celebrated **Bender–Wu large-order formula**.

### 3.2 Resummation of the Divergent Series

Because the raw series is useless numerically beyond a few terms, several resummation techniques recover accurate eigenvalues from the same (divergent) coefficients:

- **Padé approximants** and **Borel–Padé summation** (Graffi & Grecchi; Loeffel, Martin, Simon, Wightman): the Borel transform of the series is analytic in a suitable domain and can be summed and inverse-Borel-transformed to reconstruct $E_n(\lambda)$ to high accuracy, rigorously justified by the Watson–Sokal/Nevanlinna–Sokal criteria for Borel summability of the anharmonic oscillator.
- **Nonlinear sequence transformations** (Weniger, Čížek, Vinette): renormalized strong-coupling expansions and Levin-type transformations dramatically accelerate convergence of both weak- and strong-coupling series and connect them smoothly.
- **Order-dependent mapping / renormalized perturbation theory** (Zamastil, Čížek, Skála): reparametrizes the coupling to produce a convergent (rather than merely Borel-summable) series.
- **Factorial-series summation** (Weniger): reformulates the divergent power series as a convergent factorial series, giving a systematic alternative to Padé/Borel methods.
- **Large-order perturbation theory for $\phi^{2N}$ interactions** (Brézin, Le Guillou, Zinn-Justin) generalizes the Bender–Wu asymptotics to arbitrary even anharmonicities and connects the quantum-mechanical problem to instanton calculus in the associated Euclidean field theory.

### 3.3 Strong-Coupling and Interpolation Expansions

For large $\lambda$, a *strong-coupling expansion* in inverse powers of $\lambda^{1/3}$ is more natural (since rescaling $x \to \lambda^{-1/6}y$ shows $E_n(\lambda) \sim \lambda^{1/3}$ as $\lambda \to \infty$, i.e., the problem asymptotically approaches the pure quartic oscillator $H = p^2 + x^4$). Renormalized strong-coupling expansions (Weniger 1996) and two-point Padé approximants that interpolate between the weak-coupling and strong-coupling regimes give some of the most accurate closed-form-like representations of $E_n(\lambda)$ across the entire coupling range.

---

## 4. Semiclassical (WKB-Type) Approaches

### 4.1 Standard WKB and Bohr–Sommerfeld Quantization

The lowest-order WKB quantization condition,

$$\oint p(x)\,dx = 2\pi\left(n+\tfrac12\right), \qquad p(x)=\sqrt{E-x^2-\lambda x^4},$$

gives a first estimate of $E_n(\lambda)$ that is reasonably good for large $n$ but systematically inaccurate for low-lying states, since it neglects tunneling/tension corrections captured only at higher orders.

### 4.2 Supersymmetric WKB (SWKB)

The SWKB quantization condition, built from the superpotential associated with the ground state, often gives exact results for shape-invariant potentials and substantially improved accuracy for the anharmonic oscillator relative to ordinary WKB, especially when combined with **Padé-averaging of the SWKB series** (Adhikari, Dutt & Varshni).

### 4.3 Exact WKB, Resurgence, and Bender–Wu Theory (Modern Revival)

Beginning with Voros's "return of the quartic oscillator" (1983) and Balian–Parisi–Voros, the *exact* (complex, all-orders) WKB method reformulates the eigenvalue problem via Borel-resummed quantization conditions on the Riemann surface of the classical momentum. Modern developments (2010s–2020s) connect this to:

- **Resurgence theory and trans-series**: the perturbative series is complemented by an infinite tower of exponentially small non-perturbative (instanton) corrections, all encoded in a single trans-series that is Borel summable in appropriate Stokes sectors.
- The **Bender–Wu Mathematica package** (Sulejmanpasic & Ünsal) automates computation of perturbative coefficients to very high order for one-dimensional anharmonic and multi-well oscillators, including the quartic case, enabling numerical exploration of resurgent structure.
- Connections to **topological string theory / Nekrasov–Shatashvili quantization** and holomorphic-anomaly techniques provide yet another route to extremely precise quartic-oscillator spectra (Codesido, Mariño, Schiappa).

---

## 5. Variational and Operator (Algebraic) Methods

### 5.1 Rayleigh–Ritz Variational Method

Choosing a trial wavefunction (often a scaled Gaussian, $\psi_0 = (\beta/\pi)^{1/4}e^{-\beta x^2/2}$, or a linear combination of a few harmonic-oscillator eigenfunctions) and minimizing $\langle H\rangle$ with respect to variational parameters gives rigorous **upper bounds** to each eigenvalue. Accuracy improves rapidly as the trial basis is enlarged; combined with the Hill-determinant matrix diagonalization (Section 6.2) this becomes essentially a finite-basis method.

### 5.2 Shifted $1/N$ Expansion

Introduced for anharmonic oscillators by Imbo, Pagnamenta, Sukhatme and others, this method expands the eigenvalue in inverse powers of a shifted spatial/angular-momentum-like parameter $N$, effectively resumming the leading semiclassical behavior with systematic quantum corrections. It performs well across a wide range of coupling strengths and generalizes naturally to $n$-dimensional and radial anharmonic problems.

### 5.3 Shift-Operator / Algebraic Methods

Operator techniques built from generalized ladder (shift) operators yield closed analytic expressions for the ground-state energy of broad classes of cubic-quartic anharmonic potentials under specific consistency conditions on the potential parameters, providing exact benchmarks in special cases.

### 5.4 Fisher-Information / Information-Theoretic Methods

A more recent, non-standard route (Frieden-type extremal physical information formalism) recasts the ground-state eigenvalue determination as a constrained optimization of the Fisher information functional, bypassing direct solution of the differential equation; results compare favorably with conventional numerical benchmarks for the quartic oscillator.

---

## 6. Direct Numerical / Non-Perturbative Methods

### 6.1 Numerical Integration (Shooting / Numerov)

Direct numerical integration of the Schrödinger ODE using the **Numerov method** (or higher-order Runge–Kutta shooting schemes), matching logarithmic derivatives at a matching point or enforcing correct decay as $x\to\pm\infty$, remains a standard and highly reliable benchmark technique. The **Dirac-operator (matrix) technique** applied in parallel with Numerov integration has been used explicitly for the quartic-perturbed oscillator, with the two methods found to agree closely, especially at higher excitation.

### 6.2 Matrix (Hill-Determinant) Diagonalization in a Harmonic-Oscillator Basis

Expanding $\psi(x)=\sum_k \alpha_k \phi_k(x)$ in harmonic-oscillator eigenfunctions $\phi_k$ converts the Schrödinger equation into a matrix eigenvalue problem for a (banded, since $x^4$ couples $|k\rangle$ to $|k\rangle,|k\pm2\rangle,|k\pm4\rangle$) truncated **Hill determinant**. Diagonalizing sufficiently large truncated matrices gives numerically exact eigenvalues.

- The original Hill-determinant method (Biswas, Datta, Saxena, Srivastava & Varma, 1971) and its Phys. Rev. D companion application achieved close agreement with Borel–Padé perturbative resummations.
- **Variational-parameter (adjustable Gaussian width) versions** of the Hill determinant (introducing $e^{-\gamma x^2}$ or $e^{-\gamma x^2 + \rho x^4}$ prefactors with $\gamma,\rho$ optimized) dramatically accelerate convergence and cure failure modes of the original fixed-width method, including extension to double-well ($\lambda<0$) cases.
- A systematic comparative study of power-series/conformal-mapping-based methods versus the Hill determinant clarifies convergence domains and failure modes (e.g., inability of the "naïve" Hill method to capture quasi-exact spectra in certain parameter regimes).
- The truncated matrix method has also been extended to simultaneously handle quadratic, quartic, sextic, octic, and decic anharmonicities in one unified basis-expansion framework.

### 6.3 Eigenvalue Moment Method (EMM)

Based on the Hamburger moment problem, EMM converts knowledge of a finite set of expectation values $\langle x^{2k}\rangle$ into rigorous, converging upper and lower bounds on the eigenvalues, without diagonalizing an explicit matrix — historically important for establishing certified error bounds on quartic-oscillator eigenvalues.

### 6.4 Riccati–Padé Method

Reformulating the Schrödinger equation as a Riccati equation for the logarithmic derivative of the wavefunction and Padé-approximating its regular solution yields highly accurate eigenvalues and, importantly, extends naturally to complex eigenvalues (resonances, Siegert states) of related anharmonic and multiple-well potentials (Fernández and collaborators).

### 6.5 Asymptotic Iteration Method (AIM) and Asymptotic Taylor Expansion Method (ATEM)

AIM (Ciftci, Hall, Saad) and the closely related ATEM (Koç & Sayın) recast the Schrödinger equation in the form $f'' = \lambda_0(x) f' + s_0(x) f$ (after removing the Gaussian asymptotic factor) and iterate a termination condition $\delta_k(x) = \lambda_k s_{k-1} - \lambda_{k-1} s_k = 0$ evaluated at a conveniently chosen point (typically the potential minimum) to extract eigenvalues to high precision with modest computational effort. Both methods have been benchmarked extensively against direct numerical integration for $H=-d^2/dx^2+x^2+Ax^4$ and generalized to sextic anharmonic oscillators, with good agreement across weak-to-moderate coupling.

### 6.6 Spectral / Collocation Methods

The **double-exponential Sinc collocation method** (Gaudreau, Slevinsky & Safouhi) achieves spectral (exponential) convergence for both real and complex eigenvalues of one-dimensional anharmonic oscillators including the quartic case, outperforming many classical finite-difference and moment-based schemes in accuracy per computational cost, and has been used to compute extremely high-precision benchmark values (cross-checked against Trott's arbitrary-precision ground-state computation).

### 6.7 Ultra-High-Precision Reference Calculations

Trott's arbitrary-precision computation of the quartic-oscillator ground-state energy (hundreds of digits) provides one of the standard high-precision reference values used to validate all subsequent semi-analytic and numerical methods.

### 6.8 Neural-Network / Machine-Learning Solvers

More recent work uses neural-network function approximators trained to satisfy the Schrödinger differential equation and boundary conditions (a physics-informed neural network approach) to obtain energy levels of the one-dimensional quartic anharmonic oscillator, reporting good agreement with established reference values, illustrating the extension of eigenvalue methodology into modern machine-learning territory.

### 6.9 Exact/Quasi-Exact and Polynomial Solutions for Special Parameter Families

While the generic quartic oscillator has no closed-form spectrum, special *generalized* symmetric quartic oscillators (with potential parametrized to match Lie-algebraic "quartic group" structures) admit **polynomial (quasi-exact) solutions** at discrete values of a strength parameter, providing exact closed-form eigenvalues at those special points — useful both as intrinsic exact results and as benchmark anchors for the general numerical methods above.

---

## 7. Physical and Field-Theoretic Context

- **$\phi^4$ scalar field theory**: the one-dimensional quantum quartic oscillator is the zero-dimensional (single-mode) reduction of $\phi^4$ theory, and Bender–Wu large-order perturbation theory directly informed the analogous large-order analysis of $\phi^4$ field theory (Brézin–Le Guillou–Zinn-Justin), tying the oscillator's spectral problem to renormalization-group and critical-phenomena physics.
- **Quantum statistics of radiation fields**: the quartic-perturbed oscillator models nonlinear (Kerr-like) corrections to photon-field oscillator modes.
- **Molecular vibrational spectroscopy**: anharmonic corrections to vibrational energy levels of diatomic and polyatomic molecules are modeled by quartic (and higher) potential terms beyond the harmonic approximation.
- **Double-well and tunneling physics**: for $\lambda<0$ (or in generalized double-well quartic forms $-x^2+\lambda x^4$), the eigenvalue problem connects to instanton physics, level splitting, and metastable-state (resonance) computations, extending naturally to complex eigenvalues via Riccati–Padé and Sinc-collocation methods.
- **$\mathcal{PT}$-symmetric quantum mechanics**: non-Hermitian quartic-type oscillators (e.g. $H=p^2 - x^4$, or complexified quartic potentials) possess real, positive spectra when $\mathcal{PT}$ symmetry is unbroken; Bender–Wu-type large-order and dispersion techniques generalize directly to this setting.
- **Condensed matter and nuclear models**: quartic-anharmonic Hamiltonians appear in lattice vibration/soliton models and in resonating-group-method treatments of light nuclei, where oscillator-basis expansions and convergence-acceleration techniques (Padé averaging of RSPT) are used.

---

## 8. Comparative Summary of Methods

| Method family | Typical accuracy | Strengths | Limitations |
|---|---|---|---|
| Raw RSPT | Poor beyond few terms | Simple, systematic order-by-order | Series diverges for any $\lambda\neq0$ |
| Padé / Borel–Padé resummation | High | Rigorously justified (Borel summability); recovers accurate values from divergent series | Requires many perturbative coefficients; convergence proofs delicate for excited states |
| Hellmann–Feynman/Hypervirial coefficient generation | High (as input to resummation) | Efficient recursive generation of RSPT coefficients without wavefunctions | Still needs resummation for large $\lambda$ |
| Standard WKB | Moderate (good for large $n$) | Simple, physically transparent | Poor for low-lying states; needs higher-order/exact corrections |
| SUSY WKB | Good–High | Exact for shape-invariant potentials; improved low-lying accuracy | Superpotential construction can be nontrivial |
| Exact WKB / resurgence | Very high | Captures full non-perturbative trans-series; deep structural insight | Mathematically demanding; primarily used for benchmarking/structure |
| Variational (Rayleigh–Ritz) | Good–High (rigorous upper bound) | Simple; systematically improvable; rigorous bounds | Convergence can be slow for poor trial basis |
| Shifted $1/N$ expansion | Good | Works across coupling range; generalizes to $n$-D | Accuracy for very low $n$ or very strong coupling needs many terms |
| Hill determinant (harmonic basis diagonalization) | Very high | Conceptually simple; systematically convergent; widely validated | Fixed-Gaussian version can fail for double wells; variational-width version needed |
| Eigenvalue Moment Method | Very high (rigorous bounds) | Certified upper/lower bounds | More involved implementation |
| Riccati–Padé | Very high | Extends to complex/resonance eigenvalues | Requires care in Padé sequence construction |
| AIM / ATEM | High–Very high | Simple recursive algorithm, easy to code (e.g. in Mathematica) | Accuracy depends on iteration order and evaluation point choice |
| Sinc collocation (DESCM) | Spectral (very high) | Exponential convergence; handles complex eigenvalues | More elaborate numerical implementation |
| Direct numerical integration (Numerov/shooting) | Very high (benchmark-grade) | Conceptually simple, reliable "ground truth" | Computationally heavier for very high precision or excited states |
| Neural-network/ML solvers | Good (emerging) | Flexible, mesh-free | Training cost; accuracy/validation still maturing relative to classical methods |

---

## 9. Key Publications

### 9.1 Foundational and Large-Order Perturbation Theory
1. C. M. Bender and T. T. Wu, "Anharmonic Oscillator," *Physical Review* **184**, 1231–1260 (1969).
2. C. M. Bender and T. T. Wu, "Anharmonic Oscillator. II. A Study of Perturbation Theory in Large Order," *Physical Review D* **7**, 1620–1636 (1973).
3. C. M. Bender and T. T. Wu, "Large-Order Behavior of Perturbation Theory," *Physical Review Letters* **27**, 461–465 (1971).
4. E. Brézin, J. C. Le Guillou, and J. Zinn-Justin, "Perturbation Theory at Large Order. I. The $\phi^{2N}$ Interaction," *Physical Review D* **15**, 1544–1557 (1977).
5. E. Brézin, J. C. Le Guillou, and J. Zinn-Justin, "Perturbation Theory at Large Order. II. Role of the Vacuum Instability," *Physical Review D* **15**, 1558–1564 (1977).
6. J. Zinn-Justin, "Perturbation Series at Large Orders in Quantum Mechanics and Field Theories: Application to the Problem of Resummation," *Physics Reports* **70**, 109 (1981).
7. L. N. Lipatov, "Divergence of the Perturbation Theory Series and the Quasiclassical Theory," *Sov. Phys. JETP* **45**, 216 (1977).
8. J. E. Drummond, "The Anharmonic Oscillator: Perturbation Series for Cubic and Quartic Energy Distortion," *Journal of Physics A* **14**, 1651 (1981).
9. S. Rekab and N. Zenine, "Application of Hellmann–Feynman and Hypervirial Theorems to the Eigenvalue Problem: Coulomb plus Linear Term and Quartic Anharmonic Oscillator Potentials," arXiv:math-ph/0602029.

### 9.2 Resummation and Convergent Reformulations
10. E. J. Weniger, "A Convergent Renormalized Strong Coupling Perturbation Expansion for the Ground State Energy of the Quartic, Sextic, and Octic Anharmonic Oscillator," *Annals of Physics* **246**, 133–165 (1996).
11. E. J. Weniger, J. Čížek, and F. Vinette, "The Summation of the Ordinary and Renormalized Perturbation Series for the Ground State Energy of the Quartic, Sextic, and Octic Anharmonic Oscillators Using Nonlinear Sequence Transformations," *Journal of Mathematical Physics* **34**, 571–609 (1993).
12. J. Zamastil, J. Čížek, and L. Skála, "Renormalized Perturbation Theory for Quartic Anharmonic Oscillator," *Annals of Physics* **276**, 39–63 (1999).
13. E. J. Weniger, "Summation of Divergent Power Series by Means of Factorial Series," arXiv:1005.0466.
14. S. Graffi and V. Grecchi, work on Borel–Padé summation of anharmonic-oscillator perturbation series (late 1970s).

### 9.3 Semiclassical, WKB, and Resurgence
15. A. Voros, "The Return of the Quartic Oscillator: The Complex WKB Method," *Annales de l'I.H.P. Physique Théorique* **39**, 211–338 (1983).
16. R. Balian, G. Parisi, and A. Voros, "Discrepancies from Asymptotic Series and their Relation to Complex Classical Trajectories," *Physical Review Letters* **41**, 1141 (1978).
17. R. Adhikari, R. Dutt, and Y. P. Varshni, "On the Averaging of Energy Eigenvalues in the Supersymmetric WKB Method," *Physics Letters A* **131**, 217–221 (1988).
18. T. Sulejmanpasic and M. Ünsal, "Aspects of Perturbation Theory in Quantum Mechanics: The Bender–Wu Mathematica Package," arXiv:1608.08256.
19. S. Codesido and M. Mariño, "Holomorphic Anomaly and Quantum Mechanics," *Journal of Physics A* **51**, 055402 (2018).
20. C. M. Bender, D. C. Brody, and D. W. Hook (and related), *PT-Symmetric Quantum Mechanics*, review, arXiv:2312.17386.

### 9.4 Variational, Algebraic, and $1/N$ Methods
21. P. K. Patnaik, "Rayleigh–Schrödinger Perturbation Theory for the Anharmonic Oscillator," *Physical Review D* **35**, 1234–1238 (1987).
22. B. L. Burrows, M. Cohen, and T. Feldmann, "A Unified Treatment of Schrödinger's Equation for Anharmonic and Double Well Potentials," *Journal of Physics A* **22**, 1303–1313 (1989).
23. "Analytic Expression for Exact Ground State Energy Based on an Operator Method for a Class of Anharmonic Potentials," arXiv:quant-ph/0007031.
24. Studies on the shifted $1/N$ expansion for anharmonic oscillator potentials (Imbo, Pagnamenta, Sukhatme and related literature).

### 9.5 Hill Determinant and Matrix-Diagonalization Methods
25. R. N. Chaudhuri and B. Mukherjee, "The Hill Determinant: An Application to the Anharmonic Oscillator," *Physical Review D* **4**, 3617 (1971) [Biswas, Datta, Saxena, Srivastava, and Varma original Hill-determinant formulation, 1971].
26. "Hill Determinant Method with a Variational Parameter," *Physical Review A* **40**, 6080 (1989).
27. "Modified Hill Determinant Approach to the Eigenvalues of Anharmonic Oscillators," *Pramana – Journal of Physics* **37**, 13–20.
28. "Conformal Mappings versus Other Power Series Methods for Solving Ordinary Differential Equations: Illustration on Anharmonic Oscillators," arXiv:0812.2262.
29. "Study of the Quartic Anharmonic Oscillator Using the System's Wave Function" (oscillator-basis expansion with convergence acceleration via Padé averaging), arXiv:2505.06317.

### 9.6 Riccati–Padé, Moment, and High-Precision Numerical Methods
30. F. M. Fernández, Q. Ma, and R. H. Tipping, "Tight Upper and Lower Bounds for Energy Eigenvalues of the Schrödinger Equation," *Physical Review A* **39**, 1605–1609 (1989).
31. F. M. Fernández, Q. Ma, and R. H. Tipping, "Eigenvalues of the Schrödinger Equation via the Riccati–Padé Method," *Physical Review A* **40**, 6149–6153 (1989).
32. F. M. Fernández, "Direct Calculation of Accurate Siegert Eigenvalues," *Journal of Physics A* **28**, 4043–4051 (1995).
33. F. M. Fernández, "The Accurate Calculation of Resonances in Multiple-Well Oscillators," *Journal of Physics A* **41**, 065202 (2008).
34. P. J. Gaudreau, R. M. Slevinsky, and H. Safouhi, "Computing Energy Eigenvalues of Anharmonic Oscillators Using the Double Exponential Sinc Collocation Method," *Annals of Physics* **360**, 520–538 (2015); arXiv:1411.2089.
35. P. J. Gaudreau, R. M. Slevinsky, and H. Safouhi, "Highly Accurate Calculation of the Real and Complex Eigenvalues of One-Dimensional Anharmonic Oscillators," arXiv:1511.08799.
36. M. Trott, "High-Precision Value for the Quartic Anharmonic Oscillator Ground State," arXiv:quant-ph/0012147 (2000).
37. P. Amore, A. Aranda, A. De Pace, and J. A. López, "Comparative Study of Quantum Anharmonic Potentials," *Physics Letters A* **329**, 451–458 (2004).

### 9.7 Asymptotic Iteration / Asymptotic Taylor Expansion Methods
38. H. Ciftci, R. L. Hall, and N. Saad, "Asymptotic Iteration Method for Eigenvalue Problems," arXiv:math-ph/0309066.
39. R. Koç and H. T. Sayın (asymptotic Taylor expansion method, ATEM) — "Calculation of the Eigenfunctions and Eigenvalues of Schrödinger-Type Equations by Asymptotic Taylor Expansion Method (ATEM)," arXiv:1008.0697.
40. S. Ozer, "An Alternative Approach to Energy Eigenvalue Problems of Anharmonic Potentials," *Advances in Mathematical Physics* (2014), Wiley.

### 9.8 Field-Theoretic, Statistical, and Related Physical Applications
41. "Classical and Quantum Oscillators of Sextic and Octic Anharmonicities," arXiv:quant-ph/0206011.
42. "Correlation Functions of the Anharmonic Oscillator: Numerical Verification of Two-Loop Corrections to the Large-Order Behavior," arXiv:2111.12765.
43. "Thermodynamics of Quantum Oscillators," arXiv:2507.04268.
44. "Direct Fisher Inference of the Quartic Oscillator's Eigenvalues," arXiv:1106.2078.

### 9.9 Exact/Quasi-Exact and Generalized Quartic Families
45. "Polynomial Solutions of Generalized Quartic Anharmonic Oscillators," *European Physical Journal Plus* **138**, 673 (2023), Springer.
46. "Asymptotic Series for the Quantum Quartic Anharmonic Oscillator," *Journal of Mathematical Chemistry* (non-perturbative WKB-consistent numerical method for one- and two-well quartic oscillators).

### 9.10 Recent Applied and Comparative Studies
47. A. Adelaku and D. Abajingin, "Solution of Quantum Anharmonic Oscillator with Quartic Perturbation" (Dirac-operator technique vs. Numerov method comparison).
48. "First and Second-Order Energy Eigenvalues of One-Dimensional Quantum Harmonic and Anharmonic Oscillator with Linear, Quadratic, Cubic and Polynomial Perturbation Potential" (includes a neural-network-based treatment of the quartic anharmonic oscillator).

---

## 10. Concluding Remarks

The quartic anharmonic oscillator occupies a unique position in mathematical physics: it is simple to state, yet its perturbative solution is provably divergent, forcing the development of an entire ecosystem of complementary techniques — Borel/Padé resummation, semiclassical resurgence, variational and algebraic operator methods, moment-problem bounds, spectral collocation, and now machine-learning approaches. Cross-validation across this broad methodological landscape has produced eigenvalues known to extremely high precision (tens to hundreds of significant digits for the ground state), and the problem continues to serve as the benchmark of choice whenever a new eigenvalue technique for the Schrödinger equation is proposed. Its reach extends from molecular spectroscopy and quantum field theory to modern resurgence theory and topological string dualities, cementing its role as one of the most productive "simple" models in the history of quantum mechanics.


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Anharmonic quartic oscillator potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
