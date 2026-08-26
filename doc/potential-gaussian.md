# Evaluation of Eigenvalues of the Schrödinger Equation with a Gaussian Potential: An Exhaustive Review

## 1. Introduction and Physical Motivation

The Gaussian potential

$$V(r) = -A\,e^{-\lambda r^2}, \qquad A>0,\ \lambda>0$$

(with $A$ the well depth and $\lambda$ the inverse-square range parameter) is one of the most widely used short-range attractive model potentials in quantum mechanics. Its physical appeal comes from several directions:

- **Nuclear physics.** It was historically used to model the nucleon–nucleon interaction and effective $\alpha$–$\alpha$ potentials (e.g. the Buck–Friedrich–Wheatley potential), since a smooth, finite-range, exponentially decaying well captures the essential short-range character of the strong interaction without the singularities of Coulomb- or Yukawa-type forms.
- **Molecular and atomic physics.** Combinations of Gaussian functions are the standard basis for representing arbitrary short-range interactions (via Gaussian-fitted potentials) and for confinement models of atoms and ions.
- **Condensed-matter / nanostructure physics.** The Gaussian well is a natural, smooth model for the confining potential of a quantum dot or a shallow impurity, and it appears in exciton-binding and donor-impurity problems in semiconductor heterostructures.
- **Optical/nonlinear physics.** In the analysis of the semiclassical (zero-dispersion) limit of the focusing nonlinear Schrödinger equation, the associated Zakharov–Shabat spectral problem is frequently studied with Gaussian initial data, connecting the eigenvalue problem to soliton-counting formulas.

The central difficulty is that, unlike the Coulomb, harmonic-oscillator, Morse, Pöschl–Teller, Eckart, Hulthén, or Kratzer potentials, **the Gaussian potential does not belong to the class of exactly solvable (shape-invariant / hypergeometric-reducible) potentials**. Substitution of $V(r)=-Ae^{-\lambda r^2}$ into the radial Schrödinger equation

$$\frac{d^2R_{n\ell}(r)}{dr^2}+\frac{2m}{\hbar^2}\left(E - V(r) - \frac{\ell(\ell+1)\hbar^2}{2mr^2}\right)R_{n\ell}(r)=0$$

does not yield an equation reducible by elementary coordinate changes to a known special-function (hypergeometric-type) equation. Consequently, over the past five decades a very large number of **approximate analytical and numerical techniques** have been developed and cross-validated against one another for this specific potential, making it a standard benchmark problem in the "quasi-exact" and "approximate methods" literature of quantum mechanics.

This review is organized by methodological family, follows the historical development of the problem, and closes with a comprehensive bibliography.

---

## 2. Formulation of the Problem

### 2.1 The radial equation

For a particle of mass $m$ in three dimensions with orbital angular-momentum quantum number $\ell$, writing $R_{n\ell}(r)=u_{n\ell}(r)/r$, the problem reduces to

$$-\frac{\hbar^2}{2m}u_{n\ell}''(r) + \left[-Ae^{-\lambda r^2} + \frac{\hbar^2\ell(\ell+1)}{2mr^2}\right]u_{n\ell}(r) = E_{n\ell}\,u_{n\ell}(r),$$

subject to $u_{n\ell}(0)=0$ and $u_{n\ell}(r)\to 0$ as $r\to\infty$. In natural units ($\hbar=2m=1$, and often $\lambda=1$ absorbed by rescaling $r$), this is usually written as

$$u''(r) + \left(E + Ae^{-r^2} - \frac{\ell(\ell+1)}{r^2}\right)u(r) = 0.$$

### 2.2 Why exact solution fails

The obstruction is that the Gaussian is not one of the potentials for which the Schrödinger equation reduces, via the Nikiforov–Uvarov (NU) scheme, to a generalized equation of hypergeometric type with polynomial coefficients $\sigma(s)$, $\tilde\sigma(s)$, $\tilde\tau(s)$ of degree $\le 2$. All exactly solvable radial potentials (Coulomb, harmonic oscillator, Kratzer, Hulthén, Eckart, Pöschl–Teller, Morse) admit a change of variable $s=s(r)$ that maps them onto such an equation; $e^{-\lambda r^2}$ does not. This is the reason the literature is dominated by:

1. Series/perturbative expansions of the Gaussian about $r=0$ (Taylor-expanding the exponential and truncating to a polynomial, then treating the residual terms perturbatively or via an oscillator basis);
2. Reductions to *approximately* solvable forms (Pekeris-type approximations of the centrifugal term, or approximating the Gaussian itself by an exactly-solvable potential of similar shape);
3. Genuinely non-perturbative semi-analytical iteration schemes (Asymptotic Iteration Method, Nikiforov–Uvarov with approximations, SWKB);
4. Direct numerical diagonalization / shooting / mesh methods used either as the primary tool or as a benchmark ("exact" numerical reference) against which approximate formulas are validated.

### 2.3 Bound-state existence criteria

Before any specific eigenvalue method, a basic question is *whether a bound state exists at all* for given $A,\lambda$. Classical one-dimensional criteria are relevant here:

- A 1D potential well supports at least one bound state if $V(x)\le 0$ everywhere (trivially true for the attractive Gaussian).
- Simon's theorem: a bound state exists in 1D if $\int V(x)\,dx \le 0$ — again automatically satisfied by any attractive Gaussian well, however shallow.
- In three dimensions (relevant to the radial problem with $\ell=0$), by contrast, an arbitrarily weak Gaussian well does **not** always bind — there is a finite threshold depth for binding, and determining the exact critical combination of $(A,\lambda)$ at which the ground state binding energy passes through zero has itself been the subject of dedicated study (relevant, e.g., to weakly-bound systems such as the deuteron modeled by a Gaussian well).

---

## 3. Historical Development and Methodological Survey

### 3.1 Early numerical benchmarks (1970s)

The earliest reference eigenvalues for the 3D radial Gaussian potential are generally attributed to **Buck** (unpublished, 1977, referenced in the nucleon–nucleon scattering context of Buck, Friedrich, and Wheatley), obtained by **direct numerical integration** of the radial Schrödinger equation. These numbers subsequently served, and continue to serve, as the reference values against which essentially every later approximate analytical technique is validated.

### 3.2 Semiclassical / uniform asymptotic methods

**Stephenson** applied the **Liouville–Green (WKB-type) uniform asymptotic method** to obtain eigenvalues of the 3D radial Gaussian potential, providing one of the first analytic approximations complementary to Buck's numerics.

### 3.3 Perturbative and variational treatments on non-oscillator bases

**Bessis, Bessis, and Joulakian** (1982) treated the problem via a **perturbational and variational expansion on a basis of transformed Jacobi functions**, rather than the more common harmonic-oscillator basis, obtaining accurate energies and eigenfunctions and establishing one of the benchmark high-precision datasets for the problem.

### 3.4 Hypervirial–Padé and scaled-oscillator perturbation approaches

- **Lai** (1983) used the **hypervirial theorem combined with Padé resummation** ("hypervirial–Padé" scheme) to obtain eigenvalues for various radial and angular quantum numbers, a technique originally developed for anharmonic oscillators and successfully transplanted to the Gaussian well.
- **Cohen** (1984) obtained eigenvalues and approximate eigenfunctions from a **first-order perturbation theory built on a scaled harmonic-oscillator reference**, exploiting the fact that near its minimum the Gaussian is harmonic to leading order, $V(r)\approx -A(1-\lambda r^2+\tfrac{\lambda^2}{2}r^4-\cdots)$, and treating the quartic and higher terms, together with the depth mismatch, perturbatively.
- **Chatterjee** (1985) applied the **large-$N$ (1/N) expansion** method, which treats the spatial dimensionality $N$ as a large parameter and expands the energy in inverse powers of an effective $N$, a technique well-suited to spherically symmetric short-range wells and later extended to the **shifted 1/N expansion** for improved accuracy (also used for related Gaussian-confinement problems such as excitons in Gaussian quantum dots).

### 3.5 Supersymmetric quantum mechanics (SUSY QM) and combined SUSY–perturbative schemes

**Köksal** (2012) proposed **"A simple analytical expression for bound state energies for an attractive Gaussian confining potential"** (*Physica Scripta* **86**, 035006), combining Rayleigh–Schrödinger perturbation theory around the harmonic-oscillator minimum with a resummation motivated by supersymmetric quantum mechanics, casting the energy as an exponential function of the harmonic-oscillator perturbation series to better capture anharmonic and confinement-threshold behavior for an electron bound in an attractive Gaussian well.

This paper attracted a direct **comment**:

- **Fernández and García** (2012, arXiv:1210.0273) critically re-derived Köksal's formula, compared it against the elementary variational method using the simplest (Gaussian) trial wavefunction, and showed that the simple variational bound is in fact **more accurate** than Köksal's more elaborate analytical expression — a cautionary and pedagogically important result illustrating that algebraic sophistication does not guarantee numerical superiority in this problem. This exchange is itself a useful case study in benchmarking practice for the field.

### 3.6 Asymptotic Iteration Method (AIM) and combined AIM–variational treatments

The **Asymptotic Iteration Method**, introduced by Ciftci, Hall, and Saad (2003) for general second-order linear homogeneous ODEs of the form $y''=\lambda_0(r)y'+s_0(r)y$, has become one of the dominant modern tools for the Gaussian potential specifically because it does not require the equation to be of hypergeometric type — it works by iterative differentiation and a termination (quantization) condition $s_n/\lambda_n = s_{n-1}/\lambda_{n-1}$.

Key contributions:

- **Karakoc and Boztosun** (2006) were among the first to apply AIM directly to the Gaussian potential.
- **Mutuk** (2019), *"Asymptotic iteration and variational methods for Gaussian potential,"* *Pramana – J. Phys.* **92**, 66, solved the radial Gaussian potential for arbitrary $n,\ell$ using **both AIM and an independent variational calculation**, cross-checking the two families of results against each other and against the older Bessis, Lai, Cohen, Chatterjee, and Köksal values; this paper (and its companion long-form arXiv version, arXiv:1805.00006) is one of the most complete modern single-source summaries of the eigenvalue history of the problem, including an explicit historical citation chain from Buck (1977) onward.
- Related AIM applications to structurally similar problems — e.g. the **rotating Morse potential** (Bayrak, Kocak, Boztosun) and general **confining potentials** (tridiagonal-representation-approach cross-checks against AIM for Alhaidari-type confining potentials) — demonstrate the same AIM-plus-independent-numerical-diagonalization cross-validation methodology that is standard practice in this literature.
- An **improvement/simplification of the AIM formulation**, connecting it explicitly to the Nikiforov–Uvarov energy equation, was given by Barakat and others, clarifying the mathematical equivalence of AIM and NU for exactly solvable cases and providing guidance on convergence acceleration for the non-exactly-solvable (e.g. Gaussian) case.

### 3.7 Nikiforov–Uvarov (NU) method with approximation schemes

Since the Gaussian potential is not exactly NU-solvable, applications of the NU method require an auxiliary approximation, most commonly:

- Taylor-expanding $e^{-\lambda r^2}$ about $r=0$ and truncating to low order so the resulting potential (typically approximated by a Pöschl–Teller-, Kratzer-, or exponential-type surrogate) *is* NU-solvable; or
- Applying the **generalized parametric NU method** directly with an exponential-type ansatz.

The paper *"Bound-States Solutions of the Radial Schrödinger Equation for a Gaussian Potential within the Framework of the Nikiforov–Uvarov Method"* obtains closed-form ground- and first-excited-state energies for sufficiently deep wells and reports good agreement with AIM and variational results, consistent with the broader "Nikiforov–Uvarov Functional Analysis (NUFA)" family of techniques used across many non-exactly-solvable exponential-type potentials.

### 3.8 Direct numerical methods

For high accuracy and as a check on all analytic/semi-analytic schemes, several numerically exact approaches are standard:

1. **Shooting method** with Numerov-type propagation — the classical approach for 1D/radial bound-state problems, integrating from both ends and matching at a turning point.
2. **Finite-difference discretization + matrix diagonalization** (e.g. Jacobi method or standard dense eigensolvers), converting the ODE into a large sparse/banded eigenvalue problem. This is the generic strategy used across many "numerical solution of the Schrödinger equation" papers for non-exactly-solvable potentials (Woods–Saxon, generalized Woods–Saxon, Gaussian, etc.).
3. **Basis-set (Galerkin/Rayleigh–Ritz) diagonalization**, typically in a harmonic-oscillator basis, exploiting the fact that the Gaussian potential matrix elements between oscillator states can be computed in closed form (Gaussian integrals), making this one of the most efficient "exact" numerical references for the problem.
4. **Lagrange-mesh method (LMM)**, developed extensively by **Baye** and collaborators (*Phys. Rep.* **565**, 1 (2015)). The LMM combines a variational (Rayleigh–Ritz) basis of Lagrange functions with a Gauss-quadrature approximation of the potential matrix elements, so that only potential-function values at mesh points are needed. The Gaussian potential is one of the two standard test potentials (together with the Yukawa potential) used to validate new variants of the LMM (configuration-space, momentum-space, semirelativistic, and regularized Lagrange–Laguerre versions), consistently converging to high accuracy with modest mesh sizes.
5. **Variational Gaussian-basis methods (VGM) / stochastic variational method** and the **hyperspherical-harmonics method (HHM)**, compared systematically against the Lagrange-mesh method for realistic nuclear $\alpha$–$\alpha$ potentials, including the deep Buck–Friedrich–Wheatley Gaussian-type potential, in benchmark studies of three-$\alpha$ bound states.
6. **Complex/localized Gaussian wave-packet basis diagonalization** (Davis and Heller-type methods) and **Gaussian-basis variational eigensolvers** more broadly (Garashchuk–Light adaptive Gaussian bases, and subsequent refinements), used for general (often multi-dimensional) potentials but directly applicable as a numerically exact cross-check for the pure Gaussian-well problem.

### 3.9 Recent developments (2020s): weakly bound states and threshold behavior

A recent and particularly relevant contribution is:

- **Rodriguez-Espejo, Segura-Landa, Ortiz-Monfil, and Nader**, *"The Weakly Bound States in Gaussian Wells: From the Binding Energy of Deuteron to the Electronic Structure of Quantum Dots"* (arXiv:2311.03404). This work focuses specifically on the **near-threshold (weakly bound) regime**, where standard perturbative/variational schemes are least reliable because the wavefunction develops a long exponential tail. The authors:
  - analyze the exact short- and long-distance asymptotic behavior of the true wavefunction;
  - construct a compact, few-parameter Ansatz that is locally accurate and yields a rapidly convergent basis;
  - validate the approach on a nuclear-physics toy model for the deuteron (modeled as a particle in a Gaussian well);
  - derive an analytic threshold expansion for the binding energy that becomes increasingly accurate as the well approaches the critical depth for binding;
  - apply the resulting orbital as a basis function in electronic-structure calculations of a two-electron Gaussian quantum dot.

  This paper is useful both as a state-of-the-art reference eigenvalue source and as an entry point to the still-active quantum-dot/exciton confinement literature (magnetic-field-dressed excitons in Gaussian quantum dots via Ritz variational, 1/N, and shifted 1/N expansion methods, benchmarked against exact diagonalization).

- Related applications of the Gaussian confinement model appear in **atomic Stark-effect studies** — e.g. hydrogen-atom polarizabilities and hyperpolarizabilities in an external field superposed on a confining Gaussian potential — which rely on precisely the Köksal and Mutuk eigenvalue formulas as their zero-field reference energies, illustrating the continuing downstream use of these eigenvalue results.

### 3.10 Non-standard/complex-spectral contexts

The Gaussian potential also appears as a standard test case in the **non-self-adjoint Zakharov–Shabat spectral problem** associated with the semiclassical (zero-dispersion) limit of the focusing nonlinear Schrödinger equation, where numerically computed eigenvalues for Gaussian initial data are compared against WKB-type semiclassical approximations to test convergence-rate conjectures — a different but closely related eigenvalue-evaluation context (the eigenvalue problem is linear but non-self-adjoint, and "bound states" correspond to solitons in the associated NLS soliton-ensemble description).

---

## 4. Comparative Summary of Methods

| Method family | Representative works | Nature of result | Typical strength | Typical limitation |
|---|---|---|---|---|
| Direct numerical integration (shooting) | Buck (1977) | "Exact" reference numbers | Arbitrary accuracy | No closed form; case-by-case |
| Liouville–Green / WKB | Stephenson | Semiclassical closed form | Simple, good for high $n$ | Poor for low-lying/near-threshold states |
| Perturbation + Jacobi-function basis | Bessis, Bessis & Joulakian (1982) | High-precision variational/perturbative energies | Systematic, high accuracy | Nontrivial basis construction |
| Hypervirial–Padé | Lai (1983) | Resummed perturbation series | Fast convergence via Padé | Requires many perturbative orders |
| Scaled-oscillator perturbation theory | Cohen (1984) | Closed-form perturbative energies | Simple, intuitive (harmonic reference) | Breaks down for shallow/weak wells |
| Large-$N$ / shifted 1/N expansion | Chatterjee (1985); shifted-1/N quantum-dot studies | Semi-analytic expansion in $1/N$ | Good across wide parameter range | Algebraically involved at higher orders |
| SUSY-based perturbative resummation | Köksal (2012) | Simple closed-form formula | Very simple to evaluate | Shown to be less accurate than elementary variational estimate (Fernández & García, 2012) |
| Elementary variational (single Gaussian trial function) | Fernández & García (2012) | Closed-form upper bound | Extremely simple, surprisingly accurate | Upper bound only; less flexible for excited states |
| Asymptotic Iteration Method (AIM) | Karakoc & Boztosun (2006); Mutuk (2019) | Semi-analytic iterative scheme, arbitrary $n,\ell$ | General-purpose, no basis choice needed | Convergence/termination criterion needs care |
| Nikiforov–Uvarov with approximation | NU-Gaussian bound-state papers | Closed-form via auxiliary approximation | Fast, systematic | Only accurate for sufficiently deep wells / low states |
| Basis-set (oscillator) diagonalization | Standard "exact numerical" cross-checks | Numerically exact (to convergence) | High accuracy, closed-form matrix elements | Basis truncation error must be controlled |
| Lagrange-mesh method | Baye and collaborators | Numerically exact via Gauss quadrature | Very accurate with small mesh; standard test potential | Formalism less familiar outside few-body physics |
| Weak-binding threshold expansion | Rodriguez-Espejo et al. (2023) | Analytic near-threshold formula + fast basis | Excellent for near-critical, weakly bound states | Tailored to threshold regime specifically |

---

## 5. Key Take-Aways

1. **No exact closed-form solution exists** for the Gaussian potential in the radial Schrödinger equation; every "analytical" result in the literature is an approximation, expansion, or a numerically-exact reference computed by direct integration, matrix diagonalization, or the Lagrange-mesh method.
2. The **historical validation chain is unusually well documented**: nearly every paper on the topic (from 1982 to the present) explicitly benchmarks its own results against Buck's 1977 numbers and against each subsequent method, making the Gaussian potential a textbook case study in comparative numerical/approximate quantum mechanics.
3. A recurring and pedagogically important theme is that **simpler methods sometimes outperform more sophisticated ones** — the Fernández–García critique of Köksal's SUSY-motivated formula, showing the plain single-Gaussian variational trial function is more accurate, is the clearest example.
4. The **weakly bound (near-threshold) regime** remains the most delicate; recent work (2023) specifically targets this regime with tailored asymptotic Ansätze, connecting the problem to deuteron physics and quantum-dot electronic structure.
5. The **Lagrange-mesh method** has emerged as the community's preferred "numerically exact" cross-check because the Gaussian potential is one of its two canonical test cases (together with the Yukawa potential), giving high accuracy with very small basis sizes.

---

## 6. List of Publications

### 6.1 Foundational / classical papers

- Buck, B. (1977). *Unpublished* — first numerical (direct integration) eigenvalues of the 3D radial Gaussian potential; referenced via Buck, Friedrich & Wheatley nucleon–nucleon/α–α scattering work.
- Stephenson, G. — eigenvalues of the 3D Schrödinger equation with a radial Gaussian potential via the Liouville–Green (uniform asymptotic/WKB) method.
- Bessis, N., Bessis, G., & Joulakian, B. (1982). *J. Phys. A: Math. Gen.* **15**(12), 3679. Perturbational and variational treatment of the Gaussian potential on a basis of transformed Jacobi functions.
- Lai, C. S. (1983). *J. Phys. A: Math. Gen.* **16**(6), L181. Hypervirial–Padé eigenvalues of the Gaussian potential.
- Cohen, M. (1984). *J. Phys. A: Math. Gen.* **17**(3), L101. First-order perturbation theory for the Gaussian potential based on a scaled harmonic-oscillator model.
- Chatterjee, A. (1985). *J. Phys. A: Math. Gen.* **18**(12), 2403. Large-$N$ (1/N) expansion applied to the Gaussian potential.

### 6.2 Supersymmetric / perturbative resummation and its critique

- Köksal, K. (2012). "A simple analytical expression for bound state energies for an attractive Gaussian confining potential." *Physica Scripta* **86**, 035006.
- Fernández, F. M., & Garcia, J. (2012). "Comment on: 'A simple analytical expression for bound state energies for an attractive Gaussian confining potential.'" arXiv:1210.0273.

### 6.3 Asymptotic Iteration Method and Nikiforov–Uvarov approaches

- Ciftci, H., Hall, R. L., & Saad, N. (2003). "Asymptotic iteration method for eigenvalue problems." *J. Phys. A: Math. Gen.* **36**, 11807.
- Karakoc, M., & Boztosun, I. (2006). "Exact solution of the Klein–Gordon equation for the PT-symmetric generalized Woods–Saxon potential by the AIM." *Int. J. Mod. Phys. E* **15**(6), 1253. (Foundational AIM application context cited by later Gaussian-potential AIM papers.)
- Barakat, T. et al. "An Improvement of the Asymptotic Iteration Method for Exactly Solvable Eigenvalue Problems." arXiv:0711.4502.
- Mutuk, H. (2018/2019). "Asymptotic Iteration and Variational Methods for Gaussian Potential." arXiv:1805.00006; published as *Pramana – J. Phys.* **92**, 66 (2019).
- "Bound-States Solutions of the Radial Schrödinger Equation for a Gaussian Potential within the Framework of the Nikiforov–Uvarov Method" (NUFA-family treatment of the Gaussian potential).

### 6.4 Numerical / mesh / basis-set methods (general and applied to Gaussian potentials)

- Baye, D. (2015). "The Lagrange-mesh method." *Phys. Rep.* **565**, 1–107.
- Baye, D., & Heenen, P.-H. (1986). Foundational Lagrange-mesh method paper (quantum-mechanical bound-state problems).
- "Lagrange-mesh calculations in momentum space" — momentum-space LMM tested on Gaussian and Yukawa potentials.
- "Lagrange-Mesh Method in Momentum Space: an Alternative Formulation." arXiv:2510.03015.
- "A regularized Lagrange-mesh method based on an orthonormal Lagrange-Laguerre basis." arXiv:1610.01021.
- Semay, C. (2006). "Bound state equivalent potentials with the Lagrange mesh method." arXiv:physics/0611146.
- Tursunov, E. M., Baye, D., & Descouvemont, P. (2005). "Comparative variational studies of $0^+$ states in three-$\alpha$ models." arXiv:nucl-th/0501058. (Benchmarks LMM, hyperspherical-harmonics, and Gaussian-basis variational methods against the deep Buck–Friedrich–Wheatley Gaussian-type $\alpha$–$\alpha$ potential.)
- Davis, M. J., & Heller, E. J. — localized complex Gaussian wave-packet basis diagonalization methods for vibrational eigenstates (general non-analytically-solvable potentials).
- Degani, I. (2007). "Observations on Gaussian Bases for Schrödinger's Equation." arXiv:0707.4587. (Adaptive Gaussian basis construction for multi-D Schrödinger eigenproblems, building on Garashchuk & Light, *J. Chem. Phys.* **114**, 3929 (2001).)

### 6.5 Recent developments (weak binding, quantum dots, applications)

- Rodriguez-Espejo, G., Segura-Landa, J. A., Ortiz-Monfil, J., & Nader, D. J. (2023). "The Weakly Bound States in Gaussian Wells: From the Binding Energy of Deuteron to the Electronic Structure of Quantum Dots." arXiv:2311.03404.
- Jahan, K. L., Boda, A., Shankar, I. V., Raju, Ch. N., & Chatterjee, A. (2018). "Magnetic field effect on the energy levels of an exciton in a GaAs quantum dot: Application for excitonic lasers." *Scientific Reports* **8**, 4798. (Ritz variational, 1/N, and shifted 1/N methods for a Gaussian quantum-dot confinement, benchmarked against exact diagonalization.)
- Zhou et al. (2025). "Hydrogen Atom Confined in Gaussian Potential: Polarizabilities, Hyperpolarizabilities, and Stark Shifts in an External Electric Field." *Int. J. Quantum Chem.* (Wiley), using Köksal (2012) and Mutuk (2019) as reference zero-field eigenvalues.

### 6.6 Related non-self-adjoint / soliton-theory eigenvalue context

- Kim, Y., Lee, L., & Lyng, G. D. "The WKB Approximation of Semiclassical Eigenvalues of the Zakharov–Shabat Problem." arXiv:1310.4145. (Numerically computed eigenvalues of the non-self-adjoint Zakharov–Shabat problem for a Gaussian potential, compared to semiclassical WKB approximations relevant to the focusing NLS equation.)

### 6.7 General background / method references cited across the above works

- Ciftci, H., Hall, R. L., & Saad, N. — Asymptotic Iteration Method, original and follow-up papers.
- Nikiforov, A. F., & Uvarov, V. B. — *Special Functions of Mathematical Physics* (foundational text for the NU method).
- Cooper, F., Khare, A., & Sukhatme, U. — supersymmetric quantum mechanics review (large-$N$/SWKB/variational approximate methods within SUSY QM), *Phys. Rep.* **251**, 267 (1995).
- Fernández, F. M. — *Introduction to Perturbation Theory in Quantum Mechanics* (CRC Press), and related papers on tight upper/lower eigenvalue bounds (with Ma & Tipping, *Phys. Rev. A* **39**, 1605 (1989)).

---

*Note: several of the pre-2000 journal references above (Bessis et al. 1982, Lai 1983, Cohen 1984, Chatterjee 1985) are drawn from consistent secondary citation in the Mutuk (2019) and Fernández–García (2012) papers rather than from independently retrieved primary bibliographic records; page/volume details should be cross-checked against the original journals (J. Phys. A: Math. Gen.) if used for formal citation purposes.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Gaussian potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
