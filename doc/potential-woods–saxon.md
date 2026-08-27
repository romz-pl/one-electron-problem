# Eigenvalues of the Schrödinger Equation with the Woods–Saxon Potential: An Exhaustive Review

## 1. Introduction and Physical Motivation

The Woods–Saxon (WS) potential, introduced by Roger D. Woods and David S. Saxon in 1954 to model the nuclear mean field, is one of the most widely used short-range potentials in theoretical physics. In its standard spherical form it reads

$$
V(r) = -\frac{V_0}{1 + \exp\!\left(\dfrac{r - R_0}{a}\right)},
$$

where $V_0$ is the well depth, $R_0$ the nuclear (or system) radius, and $a$ the surface diffuseness parameter ($a \ll R_0$). The potential smoothly interpolates between a flat interior ($V \to -V_0$ as $r \to 0$) and a vanishing exterior ($V \to 0$ as $r \to \infty$), reproducing the empirically observed nuclear density profile far better than square-well or harmonic-oscillator models.

Beyond nuclear structure, the same functional form (and its generalizations) appears in:

- **Nuclear shell-model mean-field calculations** (single-particle spectra, magic numbers, drip lines);
- **Heavy-ion and nucleon–nucleus elastic/quasi-elastic scattering** (optical model potentials, often with an added imaginary absorptive term);
- **Cluster and alpha-decay physics** (two-center shell models, fission/fusion barriers);
- **Atomic and molecular physics** (electronic structure of metallic clusters, diatomic molecule vibrational–rotational spectra when combined with other short-range terms);
- **Relativistic extensions**: the Dirac and Klein–Gordon equations with WS scalar/vector couplings, used to study spin and pseudospin symmetry in nuclei;
- **Non-Hermitian/PT-symmetric quantum mechanics**, where complex or deformed WS forms serve as solvable toy models.

A central and recurring theoretical fact governs almost the entire methodological literature: **the radial Schrödinger equation with the Woods–Saxon potential has no closed-form analytical solution for nonzero orbital angular momentum** ($\ell \neq 0$), because the centrifugal term $\ell(\ell+1)/r^2$ is not compatible with the natural variable substitution $y = 1/[1+\exp((r-R_0)/a)]$ that linearizes the exponential terms. Only the $s$-wave ($\ell = 0$) case admits an exact solution in terms of hypergeometric functions. This single fact is the taxonomic root from which nearly all eigenvalue-evaluation techniques in the literature branch: they are either (i) purely numerical methods that solve the full problem without approximation, or (ii) semi-analytical methods that substitute an approximation for the centrifugal term (most commonly the **Pekeris approximation** or the **Greene–Aldrich approximation**) and then solve the resulting exactly solvable equation.

This review is organized around that taxonomy.

---

## 2. Mathematical Setting

### 2.1 The radial equation

For a particle of mass $m$ (or reduced mass $\mu$) in three dimensions, writing $\psi(\mathbf r) = \dfrac{u(r)}{r}Y_{\ell m}(\theta,\varphi)$, the radial Schrödinger equation is

$$
-\frac{\hbar^2}{2m}\frac{d^2u(r)}{dr^2} + \left[V(r) + \frac{\hbar^2\ell(\ell+1)}{2mr^2}\right]u(r) = E\,u(r), \qquad u(0)=0,\ u(r\to\infty)\to 0 .
$$

With $V(r)$ the Woods–Saxon potential above, this is a singular Sturm–Liouville eigenvalue problem on $[0,\infty)$ whose discrete spectrum (for $E<0$) constitutes the bound-state energies.

### 2.2 The $\ell = 0$ exact solution

Introducing $x = (r-R_0)/a$ and $y = 1/(1+e^{x})$ maps the equation onto the hypergeometric/Gauss equation, whose polynomial solutions are Jacobi polynomials $P_n^{(\alpha,\beta)}$. The bound-state condition yields a transcendental (or, in convenient parameter regimes, closed-form) quantization condition for $E_{n,0}$. This is the only rigorously exact non-trivial case.

### 2.3 The $\ell \neq 0$ problem and the centrifugal approximation

Since $1/r^2$ cannot be expressed as a finite combination of $e^{(r-R_0)/a}$ terms, essentially every semi-analytical treatment replaces the centrifugal term with an approximation expanded about $r = R_0$:

- **Pekeris approximation**:
$$
\frac{1}{r^2} \approx \frac{1}{R_0^2}\left[c_0 + \frac{c_1}{1+e^{x}} + \frac{c_2}{(1+e^{x})^2}\right],
$$
with $c_0, c_1, c_2$ fixed by matching value and derivatives at $r=R_0$ (or by a least-squares/Taylor criterion). This is by far the most common device, tracing back to Pekeris's 1934 treatment of the Morse oscillator and adapted to WS-type potentials from the 1980s onward.
- **Greene–Aldrich approximation**, originally devised for the Hulthén potential, of similar structure and frequently used interchangeably with the Pekeris scheme in this literature.

Both approximations are accurate only when $a/R_0 \ll 1$ (thin surface diffuseness, the physically relevant nuclear regime) and become increasingly unreliable for excited states with large $\ell$ or for potentials where $a$ is not small — a caveat emphasized repeatedly in the more careful papers (see §4.2 and §6).

A documented pitfall: several early applications of the Nikiforov–Uvarov (NU) method to the *generalized* Woods–Saxon (GWS) potential for $\ell \neq 0$ mis-implemented the required boundary conditions at $r \to 0$ (where the GWS potential, unlike the standard WS potential, is finite but non-zero), producing eigenvalue formulas that disagree with direct numerical integration. This error, identified explicitly by Berkdemir, Berkdemir and Sever (Erratum, *Phys. Rev. C* **74**, 039902 (2006)) and later re-examined by Guo and Sever (arXiv:1501.02948) and by Durmus (arXiv:1711.10322), propagated into several follow-up papers using NU and asymptotic-iteration methods before being corrected. This is a useful cautionary marker for anyone using older GWS closed-form eigenvalue expressions for $\ell\neq0$: they should be checked against a numerical benchmark before use.

---

## 3. Purely Numerical Methods (No Centrifugal Approximation)

These methods solve the full radial equation (exact potential, exact $1/r^2$ term) by direct discretization, and are the appropriate reference/benchmark class against which all semi-analytical formulas should be validated.

### 3.1 Finite-difference discretization + matrix diagonalization

The interval $[0, r_{\max}]$ is discretized on a uniform (or non-uniform) mesh; the second derivative is replaced by a three-point (or higher-order Numerov-type) finite-difference formula, converting the differential eigenvalue problem into a real symmetric (or tridiagonal) matrix eigenvalue problem $H\mathbf{u} = E\mathbf{u}$, solved by standard dense-matrix diagonalization (Jacobi rotations, QR algorithm, or Householder tridiagonalization followed by QL). This is the method used, e.g., in the FORTRAN program of Ikot *et al.* (arXiv:1910.03808) which explicitly benchmarks Jacobi-method diagonalization against known analytical potentials before applying it to WS, generalized WS, and $D$-dimensional WS cases.

### 3.2 Numerov / extended-Numerov and embedded Runge–Kutta–Fehlberg methods

A long research program by **G. Vanden Berghe, V. Fack, and H. De Meyer** (University of Ghent, 1980s–1990s) systematically developed and benchmarked high-order finite-difference and embedded-RK schemes specifically tuned to WS-type potentials (finite at the origin, decaying at infinity):

- The (extended) Numerov method for eigenvalues of specific Schrödinger equations;
- A shooting-type algorithm (revisiting the method of Brown, Bloch, Rosenzweig et al.) generalized to arbitrary $V(r)$;
- Comparative studies of four-step and embedded Runge–Kutta–Fehlberg schemes with minimal phase-lag, later extended by Simos, Anastassi, and coworkers.

The **Vanden Berghe–Fack–De Meyer parameterization** ($V_0 = -50$ MeV, $R_0 = 7$ fm, $a = 0.6$ fm) has become a de facto numerical benchmark: subsequent independent codes (e.g., the "hardwall method" of Chin and Massey, arXiv:1901.10607) report their computed eigenvalues directly against this reference table, achieving agreement to five significant digits.

### 3.3 The hardwall / node-counting (shooting) method

Chin and Massey (arXiv:1901.10607) revisit the classic shooting-method idea: for a trial energy $E$, integrate the radial equation outward from $r=0$ and record the "hardwall radius" at which the wavefunction first crosses zero; scanning $E$ and tracking this radius as a function of energy (a "C-scan") automatically reveals the entire discrete spectrum without needing an initial guess for each state, and elegantly exposes near-degeneracies and hidden approximate symmetries of the WS well. Convergence to $\Delta E = 0.0005$ MeV was demonstrated against the Vanden Berghe benchmark values.

### 3.4 Basis-expansion / diagonalization in a harmonic-oscillator or Woods–Saxon eigenbasis

For applications requiring many bound and quasi-bound (resonance) states simultaneously — e.g., nuclear structure codes — the Hamiltonian is diagonalized in a truncated harmonic-oscillator basis or in a WS eigenbasis obtained from a spherical-box discretization. This underlies large-scale shell-model single-particle-basis codes (Schwierz, Wiedenhöver & Volya, arXiv:0709.3525) and two-center shell-model implementations for heavy-ion/cluster-decay physics (Mirea, *Rom. Rep. Phys.* **59**, 2007), where the WS well is deformed (two smoothly-joined ellipsoids) and no analytic route exists at all.

### 3.5 Continuum / box discretization for the Dirac equation with WS potential

For the relativistic (Dirac) problem, direct spatial discretization is complicated by spurious/"pathological" states arising from naive finite-difference treatment of the coupled first-order Dirac radial equations. The **staggered-grid method (SGM)**, compared against the alternative-direction finite-difference (ADF) scheme and against shooting-method reference values, was shown to resolve this spurious-state problem for WS wells representing heavy/exotic nuclei (e.g., $^{132}$Sn), agreeing with shooting-method benchmarks to $\sim 10^{-3}$ MeV (arXiv:2510.19201).

### 3.6 General-purpose Sturm–Liouville numerical software

Because the WS radial problem is a regular instance of a singular Sturm–Liouville eigenvalue problem, general shooting/matching codes developed for such problems (e.g., the classical SL-family solvers, and comparative shooting-vs-finite-difference studies for related periodic/semi-periodic Sturm–Liouville eigenvalue problems) are directly transferable, though these are less commonly cited in the WS-specific nuclear-physics literature than the dedicated codes above.

---

## 4. Semi-Analytical Methods (Centrifugal-Term Approximation)

These methods trade exactness in $\ell$ for closed-form (or near closed-form) eigenvalue expressions, at the price of the approximation errors discussed in §2.3.

### 4.1 Nikiforov–Uvarov (NU) method

The NU method reduces a generalized hypergeometric-type second-order ODE,

$$
u'' + \frac{\tilde\tau(s)}{\sigma(s)}u' + \frac{\tilde\sigma(s)}{\sigma^2(s)}u = 0,
$$

to a form solvable via Rodrigues-type polynomial solutions (classical orthogonal polynomials — here, Jacobi polynomials, since the natural variable transformation for WS-type exponentials is $s = 1/(1+qe^{x})$ or $s=-e^{x}$, giving Jacobi-polynomial eigenfunctions). Applied to the WS problem this became, from the mid-2000s, probably the single most productive technique in the literature:

- **Berkdemir, Berkdemir & Sever (2005–2006)** first obtained bound-state energies and Jacobi-polynomial eigenfunctions for the *generalized* Woods–Saxon (GWS) potential via NU, for $\ell = 0$ exactly and $\ell \neq 0$ approximately, later issuing an erratum after an inconsistency was found for the $\ell \neq 0$ case (see §2.3).
- The technique was then extended to: the standard WS potential (Ikhdair & Sever and others); the WS potential plus modified Coulomb, Mie-type, Hulthén-hybrid, and ring-shaped terms; $q$-deformed WS potentials; $D$-dimensional (hyper-radial) WS problems; and PT-/non-PT-symmetric complex WS potentials (Berkdemir, Berkdemir & Sever, *J. Phys. A* and related preprints), where the discrete spectrum acquires an imaginary part in the non-PT-symmetric case while remaining real in the genuinely PT-symmetric case.
- Corrections and re-derivations: Guo & Sever (arXiv:1501.02948) and Durmus (arXiv:1711.10322) carefully re-examined the boundary-condition treatment at $r=R_0$ and produced corrected $\ell\neq0$ eigenvalue formulas, showing that the NU and SUSY-QM routes, correctly implemented, yield identical energy expressions.
- Pahlavani & Alavi (*Commun. Theor. Phys.* **58**, 739 (2012)) applied the NU method including both the centrifugal and spin-orbit terms simultaneously, relevant for realistic nuclear mean-field spectra.

### 4.2 Asymptotic Iteration Method (AIM)

Introduced by Ciftci, Hall & Saad (2003) for general second-order linear homogeneous ODEs $y'' = \lambda_0(x)y' + s_0(x)y$, AIM generates the eigenvalue quantization condition through a termination criterion on iteratively generated coefficient sequences, without an explicit reduction to classical orthogonal polynomials. Falaye, Hamzavi & Ikhdair applied AIM (with the Pekeris approximation) to the *deformed* Woods–Saxon (dWS) potential for arbitrary $\ell$ (arXiv:1207.1218; *Chin. Phys. Lett.* **30**, 020305 (2013)), obtaining energy levels and hypergeometric-function eigenfunctions, and cross-checked results against NU-based formulas from Badalov *et al.* AIM has also been used for the $s$-wave relativistic (Klein–Gordon) WS problem.

### 4.3 Supersymmetric Quantum Mechanics (SUSY QM)

The SUSY-QM factorization/shape-invariance method constructs a superpotential $W(r)$ such that $V_\pm(r) = W^2(r) \mp W'(r)$ are "partner potentials" with identical spectra apart from the ground state; for WS-type potentials under the Pekeris approximation the partner-potential structure is shape-invariant, giving the spectrum algebraically via the standard SUSY ladder-operator formula. Durmus (arXiv:1711.10322) showed the $D$-dimensional GWS energy formulas obtained via SUSY QM and via (correctly implemented) NU coincide exactly, providing mutual validation of both routes. SUSY QM has also been used to construct Hamiltonian hierarchies exposing "hidden" shape-invariance symmetry structure of the WS well for $\ell \neq 0$ states.

### 4.4 Shifted large-$N$ (1/N) expansion and other perturbative/semiclassical routes

Less prominent but historically important for exponential-type potentials generally, shifted $1/N$-expansion and related semiclassical (WKB, modified-WKB) techniques have been applied to WS-type wells, typically as an independent cross-check of NU/AIM/SUSY closed-form results rather than as the primary tool in the modern (post-2005) WS literature.

### 4.5 Relativistic extensions (Dirac and Klein–Gordon equations)

A large sub-literature parallels the non-relativistic NU/AIM/SUSY programs above but for the **Dirac equation** (spin-1/2, with spin-symmetry and pseudospin-symmetry limits, i.e. $\Sigma(r)=V(r)-S(r)=$ const or $\Delta(r)=V(r)+S(r)=$ const) and the **Klein–Gordon equation** (spin-0), both with WS scalar and/or vector couplings, sometimes supplemented with a WS-shaped tensor potential to reproduce spin-orbit splitting. Representative threads include Aydoğdu & Sever (pseudospin/spin symmetry, tensor potential, *Eur. Phys. J. A* **43**, 73 (2010)); Ikhdair & Sever (Klein–Gordon, PT-symmetric GWS, *Ann. Phys.* (Berlin) **16**, 218 (2007)); Arda & Sever and others (effective-mass Dirac equation for WS, scattering and bound-state analysis); and comment/reply exchanges correcting sign and boundary-condition errors in early Dirac-WS NU derivations (e.g., the *Phys. Lett. A* **338**, 90 (2005) paper and its published Comment).

---

## 5. Practical Evaluation and Benchmarking Considerations

1. **Benchmark tables exist and should be used.** The Vanden Berghe–Fack–De Meyer parameter set is the standard numerical cross-check (see Table IV of Chin & Massey, arXiv:1901.10607, reproducing eigenvalues to 5 significant figures against independent finite-difference and hardwall calculations).
2. **Closed-form $\ell \neq 0$ formulas are approximations, not exact results**, and their accuracy degrades as $a/R_0$ grows or as $\ell$ and $n$ increase; always state which centrifugal approximation (Pekeris vs. Greene–Aldrich) and which specific coefficient-fitting prescription was used, since different fitting choices give numerically different (though qualitatively similar) formulas.
3. **Cross-validate independent semi-analytical routes against each other and against direct numerics.** The NU/SUSY-QM agreement demonstrated for the GWS potential (post-correction) is a useful template: if two independently-derived closed-form spectra disagree, suspect a boundary-condition or centrifugal-approximation implementation error before suspecting the physics.
4. **For the relativistic problem, watch for spurious states** arising from naive discretizations of the coupled Dirac radial system; staggered-grid or otherwise stabilized discretizations are needed for direct numerical work, while the analytic spin-symmetry/pseudospin-symmetry limits used in most closed-form Dirac-WS papers avoid this issue by construction but only cover a restricted (exact-symmetry) subspace of realistic nuclear physics.
5. **Higher-dimensional and deformed generalizations** (D-dimensional hyper-radial WS, double-ring-shaped WS, two-center deformed WS) require either numerical diagonalization from the outset (deformed case, no separability) or a case-specific re-derivation of the Pekeris/NU/AIM/SUSY machinery (D-dimensional spherically symmetric case).

---

## 6. Summary Taxonomy

| Category | Representative technique | Handles $\ell \neq 0$ exactly? | Typical use case |
|---|---|---|---|
| Numerical | Finite-difference + matrix diagonalization | Yes | General-purpose, benchmarking |
| Numerical | Numerov / embedded RK(F) schemes | Yes | High-accuracy, small systems |
| Numerical | Shooting / hardwall (node-counting) | Yes | Full-spectrum scan, symmetry analysis |
| Numerical | Basis-expansion diagonalization | Yes | Shell-model codes, deformed potentials |
| Numerical | Staggered-grid Dirac discretization | Yes (relativistic) | Relativistic mean-field, avoiding spurious states |
| Semi-analytical | Nikiforov–Uvarov (NU) | Approximate (Pekeris/Greene–Aldrich) | Closed-form spectra, many generalized WS variants |
| Semi-analytical | Asymptotic Iteration Method (AIM) | Approximate | Closed-form spectra, cross-check of NU |
| Semi-analytical | Supersymmetric QM (SUSY) | Approximate | Closed-form spectra, shape-invariance/hidden symmetry |
| Semi-analytical | Shifted 1/N, WKB | Approximate | Historical/independent cross-checks |
| Exact (special case) | Hypergeometric/Jacobi-polynomial solution | Only $\ell = 0$ | Reference exact solution |

---

## 7. Publications

### 7.1 Foundational and numerical-methods literature

- R. D. Woods and D. S. Saxon, "Diffuse Surface Optical Model for Nucleon-Nuclei Scattering," *Phys. Rev.* **95**, 577 (1954).
- V. Fack and G. Vanden Berghe, "A finite difference approach for the calculation of perturbed oscillator energies," *J. Phys. A: Math. Gen.* **18**, 3355 (1985).
- V. Fack and G. Vanden Berghe, "A programme for the calculation of energy eigenvalues and eigenstates of a Schrödinger equation," *Comput. Phys. Commun.* **39**, 187 (1986).
- V. Fack, H. De Meyer and G. Vanden Berghe, "Some finite difference methods for computing eigenvalues and eigenvectors of special two-point boundary value problems," *J. Comput. Appl. Math.* **20**, 211 (1987).
- V. Fack and G. Vanden Berghe, "(Extended) Numerov method for computing eigenvalues of specific Schrödinger equations," *J. Phys. A: Math. Gen.* **20**, 4153 (1987).
- G. Vanden Berghe, V. Fack and H. De Meyer, "Numerical solution of radial Schrödinger equations for spherically symmetric potentials," *J. Comput. Appl. Math.* **28**, 391 (1989) (parameterization widely used as the WS numerical benchmark).
- G. Vanden Berghe, M. Van Daele and H. De Meyer, "A modified difference scheme for periodic and semiperiodic Sturm–Liouville problems," *Appl. Numer. Math.* **18**, 69 (1995).
- T. E. Simos and coworkers; Z. A. Anastassi and T. E. Simos, "Some embedded modified Runge–Kutta methods for the numerical solution of some specific Schrödinger equations," *J. Math. Chem.* (2005), and related embedded-method papers for Morse/WS-type potentials, *Comput. Phys. Commun.* / *J. Comput. Appl. Math.* (various years).
- N. Schwierz, I. Wiedenhöver and A. Volya, "Parameterization of the Woods-Saxon Potential for Shell-Model Calculations," arXiv:0709.3525 (2007).
- M. Mirea, "Two center shell model with Woods-Saxon potentials," *Rom. Rep. Phys.* **59**, 523 (2007).
- S. A. Chin and J. Massey, "The hardwall method of solving the radial Schrödinger equation and unmasking hidden symmetries," arXiv:1901.10607 (2019).
- I. G. Ikot *et al.*, "Numerical solution of the Schrödinger equation for types of Woods-Saxon potential," arXiv:1910.03808 (2019).
- Authors of the staggered-grid Dirac study, "Resolving the spurious-state problem in Dirac equation by using the staggered-grid method," arXiv:2510.19201 (2025).
- R. Romaniega, "An approximation to the Woods–Saxon potential based on a delta-shell model," *Eur. Phys. J. Plus* (2020).

### 7.2 Nikiforov–Uvarov method

- C. Berkdemir, A. Berkdemir and R. Sever, "Polynomial solutions of the Schrödinger equation for the generalized Woods-Saxon potential," *Phys. Rev. C* **72**, 027001 (2005); Erratum, *Phys. Rev. C* **74**, 039902 (2006).
- A. Berkdemir, C. Berkdemir and R. Sever, "Eigenvalues and eigenfunctions of Woods–Saxon potential in PT-symmetric quantum mechanics," *Mod. Phys. Lett. A* **21**, 2087 (2006); arXiv:quant-ph/0410153.
- C. Berkdemir, A. Berkdemir and R. Sever, "Polynomial solution of PT-/non-PT-symmetric and non-Hermitian generalized Woods-Saxon potential via Nikiforov-Uvarov method," *Mod. Phys. Lett. A* (2006).
- S. M. Ikhdair and R. Sever, "Exact solution of the Klein-Gordon equation for the PT-symmetric generalized Woods-Saxon potential by the Nikiforov-Uvarov method," *Ann. Phys. (Berlin)* **16**, 218 (2007); arXiv:quant-ph/0610183.
- V. H. Badalov, H. I. Ahmadov and A. I. Ahmadov, "Analytical solutions of the Schrödinger equation with the Woods-Saxon potential for arbitrary $\ell$ state," *Int. J. Mod. Phys. E* **18**, 631 (2009).
- V. H. Badalov, H. I. Ahmadov and S. V. Badalov, "Any $l$-state solutions of the Klein-Gordon equation for the Woods-Saxon potential," *Int. J. Mod. Phys. E* **19**, 1463 (2010).
- O. Aydoğdu and R. Sever, "Pseudospin and spin symmetry in the Dirac equation with Woods-Saxon potential and tensor potential," *Eur. Phys. J. A* **43**, 73 (2010).
- M. R. Pahlavani and S. A. Alavi, "Solutions of Woods-Saxon potential with spin-orbit and centrifugal terms through Nikiforov-Uvarov method," *Commun. Theor. Phys.* **58**, 739 (2012).
- M. R. Pahlavani and S. A. Alavi, "Study of nuclear bound states using mean-field Woods-Saxon and spin-orbit potentials," *Mod. Phys. Lett. A* **27**, 1250161 (2012).
- Generalized Nuclear Woods-Saxon Potential under Relativistic Spin Symmetry Limit, *ISRN High Energy Physics* / Hindawi (2013).
- J. Y. Guo and R. Sever, "Corrected analytical solution of the generalized Woods-Saxon potential for arbitrary $\ell$ states," arXiv:1501.02948 (2015).
- S. Durmus, "Bound states of the D-dimensional Schrödinger equation for the generalized Woods-Saxon potential," arXiv:1711.10322 (2017).
- A. N. Ikot *et al.*, "The Fractional Schrödinger Equation with the Generalized Woods-Saxon Potential," arXiv:2302.03060 (2023).
- Eigensolutions and thermodynamic properties of generalized hyperbolic Hulthén and Woods-Saxon potential, arXiv:2412.18637 (2024).
- Various authors, "Exact bound state solution of q-deformed Woods-Saxon plus modified Coulomb potential using conventional Nikiforov-Uvarov method" (conference proceedings / preprint literature, 2015).
- W. C. Qiang and S. H. Dong and collaborators, various NU-method papers on Woods-Saxon-related and Manning–Rosen/Hulthén-hybrid potentials with Pekeris-type approximations (2007–2012, multiple journals).

### 7.3 Asymptotic Iteration Method (AIM)

- H. Ciftci, R. L. Hall and N. Saad, "Asymptotic iteration method for eigenvalue problems," *J. Phys. A: Math. Gen.* **36**, 11807 (2003).
- N. Saad, R. L. Hall and H. Ciftci, "Sextic anharmonic oscillators and orthogonal polynomials," *J. Phys. A: Math. Gen.* **39**, 8477 (2006).
- B. J. Falaye, M. Hamzavi and S. M. Ikhdair, "Approximate bound state solutions of the deformed Woods-Saxon potential using asymptotic iteration method," arXiv:1207.1218 (2012).
- S. M. Ikhdair, B. J. Falaye and M. Hamzavi, "Approximate eigensolutions of the deformed Woods-Saxon potential via AIM," *Chin. Phys. Lett.* **30**, 020305 (2013); arXiv:1307.8318.
- Bound-state solution of s-wave Klein–Gordon equation for Woods-Saxon potential via AIM (various proceedings, ca. 2008–2010).
- "Asymptotic Iteration Method Solution of the Supersymmetric Schrödinger Equation" (application to WS/Morse-type potentials).

### 7.4 Supersymmetric Quantum Mechanics (SUSY) and shape-invariance

- F. Cooper, A. Khare and U. Sukhatme, "Supersymmetry and quantum mechanics," *Phys. Rep.* **251**, 267 (1995) (general foundational reference used throughout the WS-SUSY literature).
- Durmus, S. and collaborators — SUSY QM treatment cross-validated against NU results for the D-dimensional generalized Woods-Saxon potential, arXiv:1711.10322 (2017).
- "Supersymmetric Solutions of D-Dimensional Dirac Equation for Woods-Saxon Potential in Minimal Length Formalism," arXiv:2101.00881 (2021).
- Shape-invariance approach and Hamiltonian hierarchy method on the Woods–Saxon potential for $\ell \neq 0$ states (various journal papers, 2000s).

### 7.5 PT-symmetric and non-Hermitian Woods–Saxon studies

- A. Berkdemir, C. Berkdemir and R. Sever, "Eigenvalues and eigenfunctions of Woods–Saxon potential in PT-symmetric quantum mechanics," *Mod. Phys. Lett. A* **21**, 2087 (2006).
- C. M. Bender and S. Boettcher, "Real spectra in non-Hermitian Hamiltonians having PT symmetry," *Phys. Rev. Lett.* **80**, 5243 (1998) (foundational PT-symmetry reference).
- C. M. Bender, G. V. Dunne and P. N. Meisinger, "Complex periodic potentials with real band spectra," *Phys. Lett. A* **252**, 272 (1999).
- K. C. Shin, "On the reality of the eigenvalues for a class of PT-symmetric oscillators," *Commun. Math. Phys.* **229**, 543 (2002); *J. Math. Phys.* **42**, 2513 (2001).
- "A note on the Woods-Saxon potential" and associated Klein–Gordon PT-symmetric extensions (academia.edu preprint compilation, various authors, ca. 2006–2010).

### 7.6 Relativistic (Dirac / Klein–Gordon) treatments

- O. Aydoğdu and R. Sever, "Pseudospin and spin symmetry in the Dirac equation with Woods-Saxon potential and tensor potential," *Eur. Phys. J. A* **43**, 73 (2010).
- Comment on: "Solution of the Dirac equation for the Woods–Saxon potential with spin and pseudospin symmetry" [*Phys. Lett. A* **338**, 90 (2005)] and the corresponding Reply (correction of sign/boundary-condition errors).
- "Effective-Mass Dirac Equation for Woods-Saxon Potential: Scattering, Bound States and Resonances" (NU-method treatment with numerical benchmarking).
- "New exact solution of the one-dimensional Dirac equation for the Woods–Saxon potential within the effective mass case."
- Resolving the spurious-state problem in Dirac equation by using the staggered-grid method, arXiv:2510.19201 (2025).

### 7.7 Deformed, ring-shaped, and higher-dimensional generalizations

- S. M. Ikhdair, B. J. Falaye and M. Hamzavi, "Approximate eigensolutions of the deformed Woods-Saxon potential via AIM," arXiv:1307.8318.
- "Closed analytical solutions of the d-dimensional Schrödinger equation with deformed Woods-Saxon potential plus double ring-shaped potential," arXiv:1511.00484.
- "Dirac bound state solutions of spherically ring-shaped q-deformed Woods-Saxon potential for any L-state," arXiv:1308.0005.
- S. Durmus, "Bound states of the D-dimensional Schrödinger equation for the generalized Woods-Saxon potential," arXiv:1711.10322.

### 7.8 Reference works

- A. F. Nikiforov and V. B. Uvarov, *Special Functions of Mathematical Physics*, 2nd ed., Birkhäuser, Basel (1988).
- L. I. Schiff, *Quantum Mechanics*, 3rd ed., McGraw-Hill, New York (1968).
- L. D. Landau and E. M. Lifshitz, *Quantum Mechanics: Non-Relativistic Theory*, 3rd ed., Pergamon, New York (1977).

---

*Note: entries in §7 drawn from preprint/aggregator sources (arXiv, academia.edu, ResearchGate) are cited with the identifiers available at the time of writing; where a peer-reviewed journal version exists it is given preferentially. Given the size and fragmentation of this literature (several hundred papers across nuclear, atomic, molecular, and mathematical-physics journals since 1954), this bibliography should be read as a representative and methodologically organized core rather than a fully exhaustive census of every Woods–Saxon eigenvalue paper published.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Woods–Saxon potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
