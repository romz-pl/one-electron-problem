# Evaluation of Eigenvalues of the Schrödinger Equation with a Sextic Oscillator Potential: A Review

## 1. Introduction

The sextic anharmonic oscillator is one of the most extensively studied nonlinear potentials in quantum mechanics. Its Hamiltonian, in one dimension, is generally written as

$$H = -\frac{d^2}{dx^2} + \alpha x^2 + \beta x^4 + \gamma x^6, \qquad \gamma > 0,$$

or, in radial form with a centrifugal barrier,

$$V(x) = V_{-2}x^{-2} + V_2 x^2 + V_4 x^4 + V_6 x^6, \qquad x \in [0,\infty).$$

Because the potential grows as $x^6$ at large $|x|$, the spectrum is discrete and unbounded, and the associated Schrödinger equation has no closed-form solution for generic parameter values. The sextic oscillator therefore occupies a special place in mathematical physics: it is simultaneously (i) the prototypical example of a **quasi-exactly solvable (QES)** potential, for which a finite subset of eigenvalues and eigenfunctions can be obtained algebraically when the coupling constants satisfy certain constraints, and (ii) a long-standing testing ground for essentially every perturbative, semiclassical, and numerical method developed for anharmonic problems. Its structural link to the biconfluent Heun equation, its role as the only one-dimensional polynomial potential that is QES for suitably chosen parameters, and its appearance in nuclear collective models (Bohr Hamiltonian, X(5) models) and in the Rabi/quantum-optics literature make it a recurring reference potential across several subfields.

This review surveys (1) the physical and mathematical origin of the problem, (2) the quasi-exact solvability framework and its algebraic machinery, (3) the principal families of numerical and semi-analytical techniques developed to evaluate eigenvalues for arbitrary (non-QES) parameters, (4) extensions to the radial/centrifugal and multi-well cases, and (5) applications outside atomic physics. A curated bibliography is provided at the end.

---

## 2. The Sextic Oscillator Problem

### 2.1 General form and physical origin

The most general sextic oscillator potential considered in the literature is

$$V(x) = V_{-2}x^{-2} + V_2x^2 + V_4x^4 + V_6x^6, \qquad V_6>0. \tag{1}$$

Setting $V_{-2}=0$ extends the domain to the full real line, with even and odd bound-state sectors; keeping $V_{-2}\neq 0$ turns $x$ into a radial coordinate ($x\in[0,\infty)$) with $V_{-2}$ fixed by the dimensionality $D$ and orbital angular momentum $\ell$ of the associated $D$-dimensional isotropic problem. Physically, the sextic term appears whenever a quartic (Landau-type) double-well or bistable potential needs stabilization at large field/coordinate values, in effective descriptions of molecular vibrations beyond the quartic approximation, in the Rabi and Dicke models of quantum optics (via bosonic realizations), and — importantly — in nuclear structure physics, where it replaces the harmonic term in the Bohr collective Hamiltonian to interpolate between vibrational (harmonic), γ-unstable, and rotational (X(5)-type) nuclei.

### 2.2 Why the sextic oscillator resists exact solution

Unlike the harmonic ($\beta=\gamma=0$) case, the sextic problem is not exactly solvable for arbitrary $(\alpha,\beta,\gamma)$: the recursion relation obtained by substituting a power-series ansatz into the Schrödinger equation does not terminate after finitely many terms except along special algebraic surfaces in parameter space. This is the origin of the distinction between:

- **Exactly solvable (ES)** potentials — infinite spectrum available in closed form (e.g., harmonic oscillator, Morse, Pöschl–Teller);
- **Quasi-exactly solvable (QES)** potentials — a finite number of eigenstates available in closed form, the rest requiring numerics;
- **Non-solvable** potentials — no eigenstate available in closed form; the entire spectrum must be computed numerically or perturbatively.

The sextic oscillator is the canonical one-dimensional example straddling categories (b) and (c): for special one-parameter families of $(\alpha,\beta,\gamma)$ it is QES, while for generic parameters it falls into category (c).

---

## 3. Quasi-Exact Solvability of the Sextic Oscillator

### 3.1 The Turbiner–Ushveridze construction

The QES sector of the sextic oscillator was discovered by **Turbiner and Ushveridze (1987)**. The key result is that the family of potentials

$$P_{m,p,b}(z) = z^6 + 2bz^4 + \left(b^2 - 4m - 2p - 3\right)z^2, \qquad m \in \mathbb{Z}_{\ge 0},\ p\in\{0,1\},\ b\in\mathbb{R},$$

admits exactly $m+1$ eigenfunctions of the closed form

$$y(z) = z^{p}\,Q_{k,m,p,b}(z^2)\,\exp\!\left(\frac{z^4}{4} - \frac{b z^2}{2}\right), \qquad 0\le k\le m,$$

where $Q_{k,m,p,b}$ is a polynomial of degree $m$. Equivalently, in the radial/centrifugal-barrier form,

$$V(x) = \left(2s-\tfrac12\right)\left(2s-\tfrac32\right)x^{-2} + \left[b^2 - 2a(2s+1+2M)\right]x^2 + 2ab\,x^4 + a^2x^6, \tag{2}$$

the four coefficients reduce to three continuous parameters $(a,b,s)$ and a non-negative integer $M$ fixing the number $M+1$ of algebraically obtainable states. The corresponding wavefunctions take the form

$$\psi(x) = (x^2)^{s-1/4}\exp\!\left(-\frac{ax^4}{4}-\frac{bx^2}{2}\right)F(x^2),$$

with $F$ a finite-degree polynomial in $x^2$ whose coefficients obey a three-term recurrence relation. Substituting the ansatz reduces the eigenvalue problem to finding the roots of a **finite secular (Bender–Dunne) polynomial** $P_{M+1}(\varepsilon)=0$, algebraic in the energy $\varepsilon$.

### 3.2 The $\mathfrak{sl}(2,\mathbb{R})$ algebraization

The deeper reason for quasi-exact solvability is that, after a suitable gauge transformation, the sextic Hamiltonian restricted to the $(M+1)$-dimensional solvable subspace can be written as a quadratic combination of the generators of the $\mathfrak{sl}(2,\mathbb{R})$ (or $\mathfrak{sl}(2,\mathbb{C})$) Lie algebra acting on the space of polynomials of degree $\le M$. This is the unifying algebraic framework developed by Turbiner, Shifman, and later systematized by Gonzalez-Lopez, Kamran and Olver, and reviewed comprehensively by Turbiner (*Phys. Rep.* 642, 2016) and in Ushveridze's monograph.

### 3.3 Bender–Dunne polynomials

**Bender and Dunne (1996)** showed that the secular equation for the sextic QES sector can be recast as an orthogonal polynomial system $P_n(E)$ in the energy variable $E$, satisfying a three-term recurrence relation analogous to that of classical orthogonal polynomials. The roots of $P_{M+1}(E)$ give the $M+1$ algebraic eigenvalues; the asymptotic distribution and analytic structure of the roots (studied via moment problems, Hankel determinants and orthogonality measures) have since been analyzed in detail, including by **Handy** and collaborators using the moment-based "Eigenvalue Moment Method" and by **Finkel, González-López, and Rodríguez**, who generalized Bender–Dunne polynomials to all $\mathfrak{sl}(2)$-based QES models.

### 3.4 Bethe-ansatz and Heun-equation approaches

An alternative closed-form route uses the **Bethe ansatz method**: the QES eigenfunctions are written as products over their zeros, $\psi(x)=\prod_i (x^2-x_i^2)\,e^{-ax^4/4-bx^2/2}$, and the zeros $x_i$ are shown to satisfy a system of Bethe-like algebraic equations, providing both the eigenvalues and an $\mathfrak{sl}(2)$-algebraic interpretation in a unified treatment of even and odd sectors (Zhang and collaborators; Agboola–Zhang).

Separately, the sextic oscillator can be derived from the **bi-confluent Heun equation** by a change of variable. Expanding the Heun-equation solution in a series of (shifted, scaled) Hermite functions with a three-term recurrence relation reproduces the QES sextic form exactly when a free parameter is tuned so that the recurrence truncates; the truncation condition is itself a polynomial equation whose roots are the QES energies. This Heun-equation viewpoint (Ishkhanyan and collaborators) also extends naturally to the arbitrary-parameter (non-QES) case, where the biconfluent Heun equation is instead solved via the asymptotic iteration method (AIM), giving series solutions valid for arbitrary $\mu_2,\mu_4$.

### 3.5 Symmetrized and generalized QES sextic potentials

More recent work (Quesne, 2017) has introduced **symmetrized quartic and sextic polynomial oscillators**, shown to be QES via the functional Bethe ansatz, encompassing both the classical QES sextic family as a special case and a genuinely new class of QES potentials with no counterpart among ordinary polynomial oscillators.

---

## 4. Numerical and Semi-Analytical Methods for the General (Non-QES) Sextic Oscillator

For arbitrary coupling constants — the overwhelming majority of physically relevant cases — the full spectrum must be computed numerically. A very large methodological literature has accumulated; the principal families are summarized below.

### 4.1 Hill-determinant method

Historically the most widely used approach: the wavefunction is expanded as $\psi(x) = e^{-\gamma x^2}\sum_n c_n x^n$ (or with an extended prefactor $e^{-\gamma x^2 + \rho x^4}$), substitution into the Schrödinger equation yields a linear recursion for $c_n$, and requiring a non-trivial truncated solution gives a determinant ("Hill determinant") whose zeros approximate the eigenvalues.

- The **basic Hill-determinant method** (Biswas *et al.*) suffers from spurious ("false") roots and poor convergence for higher states and strong couplings, as demonstrated rigorously by **Tater** and by **Tater and Turbiner**, who showed the method can fail outright for the sextic oscillator in certain parameter regimes.
- The **Improved Hill-determinant method**, introducing an adjustable variational exponential parameter $\gamma$ (Chaudhuri and Mondal; Agrawal and Varma), significantly improves convergence and removes many spurious roots.
- Further convergence acceleration techniques were proposed by **Drozdov**.

### 4.2 Asymptotic Iteration Method (AIM)

The AIM (Ciftci, Hall, and Saad) transforms the second-order ODE $y'' = \lambda_0(x)y' + s_0(x)y$ into an iterative scheme; the termination condition $\lambda_n s_{n-1} - \lambda_{n-1}s_n = 0$ at sufficiently large iteration order $n$ yields the quantization condition. AIM has been applied extensively to the sextic (and quartic, octic) oscillators:

- Direct application to symmetric and asymmetric sextic anharmonic oscillators $V=Ax^2+Bx^4+Cx^6$, with an adjustable parameter $\beta$ introduced to accelerate convergence, giving results matching numerically exact benchmarks over wide ranges of couplings.
- A **Closed-form Quasi-Exact AIM** treatment for the general sextic oscillator (Kisoglu, 2025) merges the AIM machinery with the QES structure to extract algebraic eigenvalues directly.
- AIM combined with the biconfluent Heun-equation formulation handles the fully general (non-QES) sextic potential $V(r) = r^6+\mu_4 r^4+\mu_2 r^2$ in arbitrary spatial dimension $d$.

### 4.3 Riccati–Padé method

**Fernández, Ma and Tipping** introduced the Riccati–Padé method, converting the Schrödinger equation into a Riccati equation for the logarithmic derivative of the wavefunction and applying Padé approximants; this method has proven highly effective and numerically stable for anharmonic (including sextic) oscillators and Coulombic anharmonic problems, largely avoiding the spurious-root problem of the Hill-determinant approach.

### 4.4 Variational and perturbative methods

- **Variational-perturbation** expansions and **coupled-cluster** methods have been used to obtain high-precision eigenvalues, particularly benchmarking against the strong-coupling regime.
- Convergent renormalized perturbation schemes (order-dependent mappings, non-trivial Hamiltonian decompositions à la **Ushveridze**'s "new perturbation method") allow use of any approximate zeroth-order solution while guaranteeing convergence.
- Riccati/logarithmic perturbation theory and the **Bessis–Bessis "open perturbation"** algebraic approach give closed algebraic expressions for perturbative coefficients of quartic (and, by extension, sextic-type) anharmonic energies.

### 4.5 WKB / semiclassical and Lanczos-based approaches

The JWKB expansion provides an asymptotic series for the eigenvalues of $x^{2N}$-type and mixed anharmonic potentials; several works derive the leading WKB coefficients analytically via contour-integral techniques and use a WKB-seeded, shifted **Lanczos algorithm** to achieve extremely high precision (tens of correct digits within a handful of iterations) for the sextic potential.

### 4.6 Finite-difference, collocation, and spectral methods

- **Killingbeck's** accurate finite-difference eigenvalue technique.
- The **double exponential Sinc collocation method**, shown to give highly accurate eigenvalues for quartic and sextic anharmonic oscillators, benchmarked against Hill-determinant and WKB/Lanczos results.
- **Refinable interpolating scale functions** (wavelet-type basis), applied to sextic and decatic oscillators, yielding fast convergence for both eigenvalues and eigenfunctions without restricting the potential parameters to the QES surface.
- The **Airy-function approach** and the **Numerov method**, applied to $V(x)=Ax^{2\alpha}+Bx^2$ for $\alpha=2,3,4$ (quartic, sextic, octic), replacing the true potential locally by a piecewise-linear approximation solvable in terms of Airy functions, or discretizing the Schrödinger equation directly; both agree well with AIM benchmarks.
- The **asymptotic Taylor expansion method (ATEM)**, based on symbolic Taylor-series recursions implementable in a short Mathematica routine, applied to both quartic and sextic oscillators.

### 4.7 Exact-solvability constraints and analytic special cases

Several studies determine the specific algebraic relations among $(\alpha,\beta,\gamma)$ for which a finite number of *exact* polynomial solutions exist (beyond the general QES parametrization), deriving explicit closed-form expressions for the lowest eigenstates and their eigenfunctions' zero structure, and connecting the number/location of nodes to the corresponding energy level (Singh, Singh and Singh; Chhajlany, Letov and Malnev; Skála, Dvořák and Kapsa).

### 4.8 Analytic structure of the spectrum

Beyond numerics, the analytic continuation of sextic QES eigenvalues in the complex coupling plane has been studied by **Turbiner and Ushveridze**, who showed the Riemann surface of the relevant coupling constant splits into two sheets, connecting to the broader study of spectral singularities, level crossings, and $\mathcal{PT}$-symmetric extensions of anharmonic oscillators.

---

## 5. Extensions and Related Problems

### 5.1 Radial sextic oscillator with centrifugal barrier

Including the $V_{-2}x^{-2}$ centrifugal term generalizes the QES construction to $D$-dimensional problems and provides the natural setting for applications to nuclear structure (below). The QES energy formula and Bender–Dunne-type secular polynomials extend directly, with the angular-momentum-dependent term shifting the effective quantum numbers.

### 5.2 Multi-well structure

Depending on the sign and relative magnitude of $\alpha,\beta$ for fixed $\gamma>0$, the sextic potential can be single-, double-, or triple-well shaped. The QES sector persists in all these regimes, and the associated bound-state tunneling-splitting phenomena between wells have been studied via the QES machinery and instanton/perturbative methods.

### 5.3 Nuclear collective (Bohr) Hamiltonian applications

Replacing the harmonic $\beta^2$ potential of the Bohr Hamiltonian with a sextic potential (with centrifugal barrier in the collective coordinate $\beta$) gives an analytically/quasi-exactly solvable model interpolating between vibrational and rotational nuclear collective structure:

- **Lévai and Arias** proposed the sextic potential as a QES benchmark for the Bohr Hamiltonian, deriving closed-form expressions for the lowest eigenvalues $E_{n,\tau}$.
- **Raduta and Buganu**, and related works, apply the sextic-oscillator-with-centrifugal-barrier plus a periodic potential in the $\gamma$ collective variable to X(5)-candidate nuclei, connecting the $\beta$-equation solution to E2 transition-probability predictions and comparing to experimental nuclear spectra.
- Companion studies treat the $\gamma$-rigid prolate case, reducing the $\beta$-equation once more to the QES sextic form.

### 5.4 Rabi Hamiltonian and quantum optics

The Rabi Hamiltonian (a two-level system coupled to a single bosonic mode) can, in appropriate limits/representations, be mapped onto a QES sextic-type oscillator problem; generalized Bender–Dunne polynomials and the asymptotic iteration method have both been used to extract its QES spectrum.

### 5.5 Dunkl–Schrödinger and other deformed settings

More recent work extends the sextic-oscillator eigenvalue problem to **Dunkl (reflection-deformed) derivatives**, obtaining bound-state solutions of the Dunkl–Schrödinger equation for the sextic anharmonic potential, broadening the QES/AIM toolkit to non-standard differential-operator settings.

### 5.6 N-fold supersymmetry

The sextic QES sector has also been reformulated within the framework of **type-A N-fold supersymmetric quantum mechanics**, generalizing Bender–Dunne polynomials to arbitrary $\mathfrak{sl}(2)$-based QES Hamiltonians and clarifying the algebraic origin of the finite solvable subspace.

---

## 6. Summary and Outlook

The sextic oscillator problem sits at a productive intersection of exact algebra and numerical analysis. Its QES structure — rooted in the $\mathfrak{sl}(2,\mathbb{R})$ algebraization discovered by Turbiner and Ushveridze and encoded compactly in Bender–Dunne orthogonal polynomials — gives closed-form access to a finite (but arbitrarily large, by tuning $M$) subset of the spectrum along specific parameter surfaces. Away from these surfaces, an extensive toolbox of numerical and semi-analytical techniques — Hill determinants (basic and improved), the Riccati–Padé method, the asymptotic iteration method, WKB/Lanczos hybrids, finite-difference/Numerov schemes, Sinc and wavelet-based collocation, and Taylor-expansion methods — has been benchmarked against exact and high-precision reference values. The problem's reach extends well beyond one-dimensional molecular/atomic physics, informing nuclear collective models (Bohr Hamiltonian, X(5) nuclei), the Rabi Hamiltonian in quantum optics, $\mathcal{PT}$-symmetric and Dunkl-deformed extensions, and general QES classification programs (symmetrized potentials, Heun-equation correspondences). Active research continues on (i) generalizing symmetrized/novel QES sextic families, (ii) sharpening high-precision numerical benchmarks for the non-solvable sector, and (iii) extending the algebraic and Heun-equation machinery to higher-dimensional and deformed-derivative settings.

---

## 7. Bibliography

### Foundational quasi-exact-solvability papers
1. A. V. Turbiner and A. G. Ushveridze, *Spectral singularities and quasi-exactly solvable quantal problem*, Phys. Lett. A **126**, 181 (1987).
2. A. V. Turbiner, *Quasi-exactly-solvable problems and the $\mathfrak{sl}(2)$ algebra*, Commun. Math. Phys. **118**, 467 (1988).
3. A. V. Turbiner, Sov. Phys. JETP **67**, 230 (1988).
4. M. A. Shifman and A. V. Turbiner, Commun. Math. Phys. **126**, 347 (1989).
5. A. González-López, N. Kamran, and P. J. Olver, Commun. Math. Phys. **153**, 117 (1993).
6. A. G. Ushveridze, *Quasi-Exactly Solvable Models in Quantum Mechanics* (IOP Publishing, Bristol, 1994).
7. A. V. Turbiner, *One-Dimensional Quasi-Exactly Solvable Schrödinger Equations*, Phys. Rep. **642**, 1–71 (2016).

### Bender–Dunne polynomials and algebraic structure
8. C. M. Bender and G. V. Dunne, *Quasi-exactly solvable systems and orthogonal polynomials*, J. Math. Phys. **37**, 6 (1996).
9. C. M. Bender, G. V. Dunne, and M. Moshe, Phys. Rev. A **55**, 2625 (1997).
10. F. Finkel, A. González-López, and M. A. Rodríguez, J. Math. Phys. **37**, 3954 (1996).
11. A. Krajewska, A. Ushveridze, and Z. Walczak, Mod. Phys. Lett. A **12**, 1131 (1997); **12**, 1225 (1997).
12. F. H. L. Essler and V. E. Korepin (Bethe ansatz context); D. Agboola and Y.-Z. Zhang, Mod. Phys. Lett. A **27**, 1250112 (2012); Ann. Phys. (N.Y.) **330**, 246 (2013).
13. D. Agboola, J. Links, I. Marquette, and Y.-Z. Zhang, J. Phys. A **47**, 395305 (2014).
14. *Bethe ansatz solutions and hidden $\mathfrak{sl}(2)$ algebraic structure for a class of quasi-exactly solvable systems*, arXiv:2309.11731.
15. *Type A N-fold Supersymmetry and Generalized Bender–Dunne Polynomials*, arXiv:hep-th/0212276.
16. *A Moments' Analysis of Quasi-Exactly Solvable Systems: A New Perspective on the Sextic Anharmonic and Bender-Dunne Potentials*, arXiv:1402.5868.
17. *Zeros of eigenfunctions of some anharmonic oscillators*, arXiv:math-ph/0612039.
18. C. Quesne, *Quasi-exactly solvable symmetrized quartic and sextic polynomial oscillators*, Eur. Phys. J. Plus (2017); arXiv:1607.02929.
19. *A Unified Treatment of Quasi-Exactly Solvable Potentials I*, arXiv:math-ph/0505002.

### Heun-equation and biconfluent Heun connections
20. *Exact solutions of the sextic oscillator from the bi-confluent Heun equation*, arXiv:1904.09488.
21. *Sextic anharmonic oscillators and Heun differential equations*, Eur. Phys. J. Plus (2022), Springer.
22. B. Léauté and G. Marcilhacy, J. Phys. A **19**, 3527 (1986).
23. P. Maroni, C. R. Acad. Sc. Paris **264A**, 503 (1967); Ann. Inst. Henri Poincaré A **30**, 315 (1979).
24. F. Batola, thesis, Université Pierre et Marie Curie, Paris (1977).
25. H. F. Kisoglu, *A Closed-form Quasi-exact Eigenvalues of Schrödinger Equation for a General Sextic Oscillator via Asymptotic Iteration Method*, Int. J. Theor. Phys. **64**, No. 12 (2025).

### Hill-determinant method and its limitations/improvements
26. S. N. Biswas *et al.*, Hill-determinant method (original formulation).
27. M. Tater, *The Hill determinant method in application to the sextic oscillator: limitations and improvement*, J. Phys. A: Math. Gen. **20**, 2483 (1987).
28. M. Tater and A. V. Turbiner, *Failure of the Hill determinant method for the sextic anharmonic oscillator*, J. Phys. A: Math. Gen. **26**, 697 (1993).
29. R. N. Chaudhuri and M. Mondal, *Improved Hill determinant method: General approach to the solution of quantum anharmonic oscillators*, Phys. Rev. A **43**, 3241 (1991).
30. R. K. Agrawal and V. S. Varma, *Improved Hill determinant method for the solution of quantum anharmonic oscillators*, Phys. Rev. A **49**, 5089 (1994).
31. A. N. Drozdov, *On the improvement of convergence of Hill determinants*, J. Phys. A: Math. Gen. **28**, 445 (1995).
32. U. B. Kaulfuss, improved Hill-determinant applications with variational parameter (supersymmetric benchmarking).

### Asymptotic Iteration Method (AIM) and related iterative/series methods
33. H. Ciftci, R. L. Hall, and N. Saad, J. Phys. A: Math. Gen. **36**, 11807 (2003).
34. H. Ciftci, R. L. Hall, and N. Saad, J. Phys. A: Math. Gen. **38**, 1147 (2005).
35. H. Ciftci, R. L. Hall, and N. Saad, Phys. Lett. A **340**, 388 (2005).
36. R. L. Hall, N. Saad, and K. D. Sen, *Asymptotic iteration method for eigenvalue problems*, arXiv:math-ph/0309066.
37. *The asymptotic iteration method for the eigenenergies of the anharmonic oscillator potential* (asymmetric quartic/sextic AO), incl. treatment via Wronskian-based quantization.
38. *Quantum anharmonic oscillators: a new approach* (Wronskian-based eigenenergy determination).
39. H. Ciftci, R. I. Hall, N. Saad, and E. Doğu, J. Phys. A **43**, 415206 (2010).
40. *Bender-Dunne Orthogonal Polynomials, Quasi-Exact Solvability and Asymptotic Iteration Method for Rabi Hamiltonian*, arXiv:1003.3212.

### Riccati–Padé, perturbative, and variational methods
41. F. M. Fernández, Q. Ma, and R. H. Tipping, *Eigenvalues of the Schrödinger equation via the Riccati-Padé method*, Phys. Rev. A **40**, 6149 (1989).
42. N. Bessis and G. Bessis, *Open perturbation and the Riccati equation: Algebraic determination of the quartic anharmonic oscillator energies and eigenfunctions*, J. Math. Phys. **38**, 5483 (1997).
43. A. G. Ushveridze, non-trivial Hamiltonian decomposition / convergent perturbation method for anharmonic oscillators.
44. L. Skála, J. Dvořák, and V. Kapsa, *Analytic solutions of the Schrödinger equation for the modified quartic oscillator*, Int. J. Theor. Phys. **36**, 2953 (1997).
45. C. A. Singh, S. B. Singh, and K. D. Singh, *Quantum mechanical sextic anharmonic oscillators: normalisability of wavefunctions and some exact eigenvalues*, Phys. Lett. A **148**, 389 (1990).
46. S. C. Chhajlany, D. Letov, and V. Malnev, *Energy spectrum of the potential $V=ax^2+x^4$*, J. Phys. A: Math. Gen. **24**, 2731 (1991).
47. M. Znojil, *Asymmetric anharmonic oscillators in the Hill-determinant picture*, J. Math. Phys. **33**, 213 (1992); Mod. Phys. Lett. A **31**, 1650088 (2016); **31**, 1650195 (2016).
48. R. Sasaki and M. Znojil, J. Phys. A **49**, 445303 (2016).
49. F. M. Fernández and coworkers, various asymptotic-expansion/JWKB treatments.
50. *An Alternative Approach to Energy Eigenvalue Problems of Anharmonic Potentials* (asymptotic Taylor expansion method), Adv. Math. Phys. (2014).

### WKB, Lanczos, spectral/collocation, and finite-difference methods
51. J. Killingbeck, *Accurate finite difference eigenvalues*, Phys. Lett. A **115**, 301 (1986).
52. *Computing Energy Eigenvalues of Anharmonic Oscillators using the Double Exponential Sinc Collocation Method*, arXiv:1411.2089; Appl. Math. Comput. (2015).
53. WKB-expansion and shifted Lanczos algorithm applications to sextic-type potentials (high-precision, tens of correct digits).
54. N. Al Sdran and F. Maiz, *Airy function approach and Numerov method to study the anharmonic oscillator potentials $V(x)=Ax^{2\alpha}+Bx^2$*, AIP Advances **6**, 065323 (2016).
55. *Quantum anharmonic oscillator: The Airy function approach* (sextic/decatic potentials, exact-solvability conditions and node structure).
56. *Quasi-exactly solvable models in quantum mechanics* (refinable interpolating scale-function method for sextic/decatic oscillators).
57. *On the Computation of Eigenvalues of the Anharmonic Coulombic Potential*, arXiv:1511.04654.
58. *An extended scenario for the Schrödinger equation* (sextic oscillator applications to bistable systems), arXiv:1110.2664.
59. *Conformal mappings versus other power series methods for solving ordinary differential equations: illustration on anharmonic oscillators*, arXiv:0812.2262.

### Nuclear collective (Bohr Hamiltonian) applications
60. J. M. Arias and G. Lévai, Phys. Rev. C **69**, 014304 (2004).
61. *Solutions of the Bohr Hamiltonian, a compendium*, arXiv:nucl-th/0411087.
62. A. A. Raduta and P. Buganu, *Application of the sextic oscillator with centrifugal barrier and the spheroidal equation for some X(5) candidate nuclei*, arXiv:1301.6025.
63. *Sextic potential for γ-rigid prolate nuclei*, arXiv:1508.00728.

### Other extensions
64. Bound state solutions of the Dunkl–Schrödinger equation for the sextic anharmonic oscillator potential (recent Dunkl-deformed extension).
65. S. Konstantogiannis, *Quasi-exact Solution of Sextic Anharmonic Oscillator Using a Quotient Polynomial*, J. Found. Appl. Phys. **6**(1), 17 (2019).
66. S. M. Blinder, *Quasi-Exact Solutions of Schrödinger Equation: Sextic Anharmonic Oscillator*, Wolfram Demonstrations Project (2020).
67. *Duality and Self-Duality (Energy Reflection Symmetry) of Quasi-Exactly Solvable Periodic Potentials*, arXiv:hep-th/0204224.

---

*Note: Some entries above are drawn from reference lists embedded in the surveyed papers rather than independently verified against original publication venues; page/volume details should be cross-checked against the original journals before formal citation.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Sextic oscillatorpotential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
