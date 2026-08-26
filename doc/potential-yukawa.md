# Evaluation of Eigenvalues of the Schrödinger Equation with the Yukawa Potential: A Review

## 1. Introduction and Physical Context

The Yukawa potential,

$$V(r) = -\frac{\alpha\, e^{-\mu r}}{r},$$

was introduced by Yukawa in 1935 as an effective description of the short-range nuclear force mediated by massive mesons, with $1/\mu$ setting the interaction range and $\alpha$ its strength. The same functional form recurs across physics under different names: the **Debye–Hückel potential** in plasma physics and electrolytes (screening of a charge by a cloud of mobile carriers), the **Thomas–Fermi screened Coulomb potential** in solid-state and atomic physics (screening of a nucleus by bound/conduction electrons), and, in a purely mathematical sense, as the prototypical short-range perturbation of the exactly solvable Coulomb problem. Because of this ubiquity the potential is often called the **static screened Coulomb potential (SSCP)**.

Unlike the Coulomb problem, the radial Schrödinger equation

$$-\frac{\hbar^2}{2m}\left[\frac{1}{r^2}\frac{d}{dr}\left(r^2\frac{dR}{dr}\right)-\frac{\ell(\ell+1)}{r^2}R\right] - \frac{\alpha e^{-\mu r}}{r}R = E R$$

has **no closed-form analytic solution** for arbitrary $\ell$ and $\mu$. This single fact is the reason the Yukawa potential has generated one of the longest-running methodological literatures in quantum mechanics: it is simple enough to write down but resistant enough to solve that it has served for nine decades as a testbed for essentially every technique devised for approximate or numerical eigenvalue computation. This review organizes that literature by method, tracing the historical arc from early numerical integration through modern algebraic and hybrid approaches, and closes with a curated bibliography.

## 2. The Physical and Mathematical Origin of the Difficulty

Rescaling to dimensionless variables ($x = \mu r$, and the dimensionless coupling $\delta = m\alpha/(\hbar^2\mu)$, sometimes called the *screening parameter*) shows that the physics depends on a single ratio between the Bohr-like length scale of the attraction and the screening length. Two structural features drive the mathematical difficulty:

- **Finite bound-state spectrum.** Unlike the Coulomb potential, which supports infinitely many bound states accumulating at $E=0$, the Yukawa potential supports only a *finite* number of bound states for any $\mu>0$, and none at all once $\mu$ exceeds a **critical screening value** $\mu_c$. Determining $\mu_c(n,\ell)$ precisely is itself a distinct sub-problem in the literature (Section 4.4).
- **Non-separability of the exponential screening term.** The $e^{-\mu r}/r$ term does not admit the substitutions that make the Coulomb, harmonic oscillator, Morse, or Pöschl–Teller potentials exactly solvable via factorization or hypergeometric reduction. Approximate solutions therefore typically require either (a) expanding around the solvable Coulomb limit, (b) replacing the troublesome $1/r$ or centrifugal $1/r^2$ terms with an exponential approximant that restores solvability, or (c) direct numerical attack.

## 3. Numerical (Essentially Exact) Methods

These methods make no analytic approximation to the potential and are used both to obtain benchmark eigenvalues and to test the accuracy of approximate analytic schemes.

### 3.1 Direct numerical integration / finite-difference shooting
The earliest high-accuracy results came from direct numerical integration of the radial equation on a mesh (Numerov-type or finite-difference shooting methods), matching interior and exterior solutions at a trial energy and iterating to the bound-state condition. Rogers, Graboske, and Harwood (1970) produced what became the standard reference dataset: eigenvalues for 45 eigenstates ($1s$ through $n=9,\ell=8$) over a wide range of screening lengths, computed with a simple, accurate one-dimensional difference method. These values (often called the "RGH" results) have been used for decades as the benchmark against which every new approximate method is checked.

### 3.2 Basis-set diagonalization
A second numerically exact route expands the wavefunction in a large basis (Coulomb–Sturmian, Laguerre, or even-tempered Gaussian/Slater sets) and diagonalizes the resulting Hamiltonian matrix. This approach is prominent in scattering and collision contexts (e.g., antiproton–hydrogen ionization studies), where bound and pseudo-continuum states are needed simultaneously and convergence with basis size is explicitly checked.

### 3.3 Shooting methods to arbitrary precision
More recent work (e.g., high-precision shooting-method studies of critical screening parameters) pushes numerical integration to tens of significant digits, primarily to resolve small discrepancies between competing semi-analytic predictions of $\mu_c$.

### 3.4 Monte Carlo Hamiltonian approaches
Independent cross-checks of bound-state energies and of the critical exponent behavior near $\mu_c$ have been obtained via Monte Carlo Hamiltonian methods, providing an algorithmically distinct confirmation of finite-difference results.

## 4. Perturbative Methods

### 4.1 Rayleigh–Schrödinger perturbation theory about the Coulomb limit
Because the Yukawa potential reduces exactly to the Coulomb potential as $\mu\to0$ (at fixed $\alpha$), it is natural to treat $\mu$ (or $\delta$) as a perturbation parameter around the exactly known Coulomb eigenstates. This yields a power series for $E_{n\ell}(\delta)$ whose coefficients can be generated to very high order using recursion relations built from Coulomb Green's functions or hypervirial/logarithmic-perturbation techniques.

A key subtlety, resolved from the 1970s onward, is that the raw perturbation series for excited-state energies **diverges or requires regularization**, because the sum over intermediate principal quantum numbers must be truncated or resummed; the treatment of this truncation is a recurring technical theme (see Section 4.3).

### 4.2 Large-order perturbation theory and Padé/continued-fraction resummation
Because the perturbation series is only asymptotic (and shown *not* to be of Stieltjes type), large-order studies (to 100th order for the $1s$, $2s$, $2p$ levels) combined with Padé approximants and continued-fraction representations were used to extract accurate $E(\lambda)$ values and the critical coupling threshold from a divergent series — a technique borrowed from the anharmonic-oscillator resummation literature.

### 4.3 Logarithmic perturbation theory
An alternative organizing scheme expands the logarithm of the wavefunction rather than the energy directly, which improves convergence properties and has been applied specifically to the screened Coulomb and charmonium-type potentials.

### 4.4 Fifth-order perturbation theory with variational cross-check (modern benchmark)
A 2017 study pushed perturbation theory for the ground state to fifth order using exact Coulomb wavefunctions with a principal-quantum-number cutoff, and compared the result against a variational calculation using a Coulomb-like trial function whose minimization condition (a cubic equation) was solved exactly rather than approximately. The two approaches were shown to agree closely except very near the critical screening point, and the study produced the currently most precise value of the critical screening parameter, $\mu_c/(\alpha m) = 1.1906122105(5)$, to ten digits, resolving earlier discrepancies in the literature.

## 5. Variational Methods

### 5.1 Coulomb/hydrogenic trial functions
The oldest variational treatments (Harris, 1962) built trial wavefunctions from combinations of $1s$, $2s$, $3s$ hydrogenic orbitals with adjustable coefficients and effective charges, obtaining accurate ground- and excited-state energies for a grid of screening lengths — a precursor to the modern basis-diagonalization approach.

### 5.2 Hulthén-type trial functions via variation principle
More recent variational work uses trial wavefunctions borrowed from the (exactly solvable) Hulthén potential — itself obtained via the Nikiforov–Uvarov method — as an ansatz for the Yukawa problem, including the centrifugal term in the effective potential for arbitrary $\ell$. The variational energies obtained this way show excellent agreement with earlier numerical benchmarks and require no ad hoc approximation of the centrifugal term.

### 5.3 Single-parameter variational estimates of the critical screening length
Simple one- or few-parameter hydrogenic trial functions have also been used specifically to bound and estimate the critical screening parameter $\mu_c$, complementing the perturbative determinations above.

## 6. Algebraic / Quasi-Analytic Methods Requiring an Auxiliary Approximation

This is the largest and most active branch of the modern literature (particularly since the early 2000s), driven by the popularization of the **Nikiforov–Uvarov (NU) method** and supersymmetric quantum mechanics (SUSYQM) as systematic machinery for solving Schrödinger-like second-order ODEs of hypergeometric type. None of these methods solve the $\ell\neq0$ Yukawa problem exactly; they all rely on replacing the problematic centrifugal or $1/r$ term with an exponential-type approximant that keeps the equation in the solvable (hypergeometric) class.

### 6.1 The centrifugal-term approximation problem
For $\ell\neq0$, the term $\ell(\ell+1)/r^2$ combined with $e^{-\mu r}/r$ is not amenable to exact hypergeometric reduction. Two approximation schemes dominate the literature:

- **Greene–Aldrich approximation**: $\dfrac{1}{r^2} \approx \dfrac{\mu^2 e^{-\mu r}}{(1-e^{-\mu r})^2}$, valid for short-range (small $\mu$, i.e., weakly screened / near-Coulomb) potentials. Originally proposed for variational wavefunctions of the screened Coulomb potential.
- **Pekeris-type / improved approximations**, expanding $1/r$ and $1/r^2$ in series of $e^{-\mu r}$ about a reference point, used when a more accurate centrifugal treatment across a wider range of $\mu$ is required.

These approximations are explicitly noted in the literature to work best for **small screening parameters** (short-range limit close to Coulomb) and to degrade for strongly screened, near-critical potentials — a limitation acknowledged repeatedly and checked against exact numerical solutions.

### 6.2 Nikiforov–Uvarov (NU) method
The NU method reduces a generalized hypergeometric-type equation to standard form via a suitable variable transformation and yields eigenvalues from a polynomial (Rodrigues-type) condition. Applied to the Yukawa potential (with the centrifugal approximation above), it yields closed-form approximate energy eigenvalue expressions and eigenfunctions in terms of Jacobi or generalized Laguerre polynomials, valid for arbitrary $n,\ell$. This approach has been:
- applied directly to the pure Yukawa potential for arbitrary angular momentum;
- extended to **generalized/"class of" Yukawa potentials** that combine Yukawa with inverse-square (inversely quadratic Yukawa), Hellmann, Coulomb, Manning–Rosen, Möbius-square, and other exponential-type terms in a single "mixed" potential, from which the pure Yukawa, Coulomb, and Hellmann cases are recovered as limits;
- extended relativistically to the **Dirac equation** (spin/pseudospin symmetry limits) and the **Klein–Gordon equation**, with the nonrelativistic Yukawa Schrödinger results recovered in the appropriate limits;
- extended to **deformed (noncommutative-geometry) quantum mechanics**, producing energy shifts from Bopp-shift-based perturbation theory on top of the NU solution.

### 6.3 Supersymmetric quantum mechanics (SUSYQM) / shape invariance
An alternative to NU that reaches essentially the same class of closed-form results uses the superpotential/shape-invariance formalism: constructing a superpotential whose associated partner potentials reproduce the (approximated) Yukawa effective potential, then reading off the spectrum from the shape-invariance condition. This has been applied to the Yukawa potential itself and to the broader "class of Yukawa potentials" (Yukawa, inversely quadratic Yukawa, Hellmann, Coulomb) as a unified family, and — in a more recent hidden-supersymmetry formulation — used to obtain a Taylor series in the screening parameter for each eigenstate whose radius of convergence is extended via Padé approximants to reach the critical screening lengths $\delta_{n\ell}$ with high precision, reproducing Coulomb-like eigenstates with polynomial corrections.

### 6.4 Asymptotic Iteration Method (AIM) and exact quantization conditions
The Asymptotic Iteration Method solves the Schrödinger equation by iterating a first-order recursion on the logarithmic derivative until a termination (quantization) condition is met; it has been applied to the Yukawa and generalized-Yukawa families as an alternative to NU/SUSYQM that sometimes avoids explicit special-function bookkeeping.

### 6.5 Shifted $1/N$ expansion (large-dimension expansion)
Treating the number of spatial dimensions $N$ (or equivalently $1/N$) as an expansion parameter, the shifted $1/N$ expansion technique gives analytic expressions for $E_{n\ell}$ and radial wavefunctions of the general class $V(r) = -A e^{-\beta r}/r$ that converge rapidly across a wide range of $n$, $\ell$, and screening strength, and were among the first techniques to map out the critical screening curve $\delta_c(\ell)$ as a smooth function of angular momentum.

### 6.6 Complete/closed-form treatments via hidden symmetry
A distinct and more recent line of work claims a "complete analytical solution" to the quantum Yukawa potential by exploiting a hidden dynamical (supersymmetric) structure of the problem, expressing the wavefunctions as generalizations of Coulomb eigenstates with polynomial corrections in the screening parameter, rather than relying on an auxiliary centrifugal-term approximation.

## 7. Renormalization-Group and Field-Theoretic Approaches
Renormalization-group (RG) techniques have been applied to sum classes of terms in the perturbative expansion for $E_{n\ell}(\delta)$ to all orders, extending the range of screening parameters over which accurate eigenvalues can be obtained beyond what bare perturbation theory allows, and connecting the bound-state problem to RG flow language more familiar from field theory.

## 8. The Critical Screening Parameter as a Sub-Problem
Because bound states disappear altogether above a threshold screening $\mu_c(n,\ell)$, determining this threshold precisely has become a specialized strand of the literature in its own right, with methods including:
- direct numerical (shooting) determination to high precision;
- variational bounds and estimates;
- perturbative/Padé-resummed determination (the ten-digit 2017 result cited above);
- empirical/semi-analytic fitting formulas for $\mu_c$ as a function of $\ell$ (e.g., a two-exponential fit form calibrated against Monte Carlo and direct numerical solutions);
- studies of the critical exponents governing the vanishing of the bound-state wavefunction as $\mu\to\mu_c^-$.

Reported values for the ground-state critical screening parameter across different methods and eras generally cluster near $\mu_c/(\alpha m) \approx 1.19$, with the modern high-precision perturbative/variational study resolving small numerical disagreements among earlier estimates.

## 9. Physical Applications Driving the Choice of Method

The methodological diversity above is closely tied to the breadth of physical contexts in which the Yukawa/screened-Coulomb potential appears, each of which has favored particular techniques:
- **Nuclear physics** (original motivation): meson-exchange nucleon–nucleon interaction; one-boson-exchange potential models.
- **Plasma physics**: Debye–Hückel screening in weakly non-ideal plasmas, relevant to pressure-ionization and equation-of-state calculations — a major driver of the classic numerical benchmark work (Rogers–Graboske–Harwood) and of high-throughput eigenvalue tabulations.
- **Atomic and solid-state physics**: Thomas–Fermi screening of impurities and donor states in semiconductors, and modeling of atoms/ions embedded in dense environments.
- **Molecular physics**: diatomic-molecule vibrational spectra, where "Yukawa plus" combination potentials (Yukawa + Manning–Rosen, Yukawa + exponential screened Coulomb, Hellmann potential as a Yukawa/Coulomb combination) are fitted to reproduce spectroscopic data for molecules such as HCl, CO, HF, HBr, N₂, and various metal hydrides.
- **Relativistic quantum mechanics / particle physics**: Dirac and Klein–Gordon equations with Yukawa-type scalar/vector couplings, spin and pseudospin symmetry studies.
- **Ion–atom collision physics**: antiproton/proton–hydrogen ionization and charge-transfer cross sections computed with screened (Yukawa-type) interactions.
- **Cosmology**: Yukawa-type quintessence interaction potentials (a more exotic, less central application, included here for completeness of the term's reach).

## 10. Comparative Assessment

| Method family | Handles arbitrary $\ell$ exactly? | Typical accuracy regime | Main limitation |
|---|---|---|---|
| Direct numerical integration / shooting | Yes (numerically) | Reference-grade, essentially exact | Computationally case-by-case; no closed-form insight |
| Basis-set diagonalization | Yes | Reference-grade, controllable via basis size | Convergence must be checked; costly for high precision near threshold |
| Rayleigh–Schrödinger perturbation theory | Yes (via Coulomb basis) | Excellent for weak screening; needs resummation for larger $\mu$ | Series is asymptotic/divergent; truncation of intermediate states needed |
| Padé/continued-fraction resummation | Yes | Extends validity close to critical coupling | Requires very high perturbation order for full accuracy |
| Variational (Coulomb/Hulthén trial functions) | Yes, approximately | Good for ground and low excited states | Accuracy depends on trial-function flexibility |
| Nikiforov–Uvarov / SUSYQM (with centrifugal approximation) | Approximately, via auxiliary approximation | Good for small–moderate screening; closed-form | Centrifugal-term approximation breaks down near critical screening |
| Asymptotic Iteration Method | Approximately | Comparable to NU | Same centrifugal-approximation caveat |
| Shifted $1/N$ expansion | Yes | Good across a wide $(n,\ell,\delta)$ range | Accuracy set by expansion order |
| Hidden-symmetry / complete analytical solution | Yes | High precision via Padé-extended series | Relatively new; less independently cross-validated |
| Renormalization-group resummation | Yes (via perturbative input) | Extends perturbative reach | Inherits complexity of underlying perturbation series |

The overall picture that emerges is one of convergent validation: numerically exact shooting/diagonalization results from the 1960s–70s (Harris; Rogers–Graboske–Harwood) remain the benchmark against which essentially every subsequent perturbative, variational, and algebraic (NU/SUSYQM/AIM/$1/N$) method is still checked, and the modern literature's main advances lie in (i) extending closed-form accuracy to arbitrary $\ell$ via better centrifugal approximations or hidden-symmetry constructions, (ii) pushing precision on the critical screening parameter to many significant digits, and (iii) porting the same machinery to relativistic (Dirac/Klein–Gordon) and generalized "class of Yukawa" potentials relevant to molecular and nuclear spectroscopy.

## 11. List of Related Publications

**Foundational and classic numerical works**
- H. Yukawa, "On the Interaction of Elementary Particles," *Proc. Phys. Math. Soc. Jpn.* **17**, 48 (1935).
- P. Debye and E. Hückel, *Physik. Z.* **24**, 185 (1923).
- R. Jost and A. Pais, *Phys. Rev.* **82**, 840 (1951).
- V. Bargmann, *Proc. Natl. Acad. Sci.* **38**, 961 (1952).
- L. Hulthén and K. V. Laurikainen, *Rev. Mod. Phys.* **23**, 1 (1951).
- J. Schwinger, *Proc. Natl. Acad. Sci.* **47**, 122 (1960).
- G. M. Harris, "Attractive Two-Body Interactions in Partially Ionized Plasmas," *Phys. Rev.* **125**, 1131 (1962).
- H. M. Schey and J. L. Schwartz, "Counting the Bound States in Short-Range Central Potentials," *Phys. Rev.* **139**, B1428 (1965).
- F. J. Rogers, H. C. Graboske Jr., and D. J. Harwood, "Bound Eigenstates of the Static Screened Coulomb Potential," *Phys. Rev. A* **1**, 1577 (1970).
- C. S. Lai, *Phys. Rev. A* **23**, 455 (1981).

**Perturbative and resummation methods**
- J. McEnnan, L. Kissel, and R. H. Pratt, "Analytic Perturbation Theory for Screened Coulomb Potentials: Nonrelativistic Case," *Phys. Rev. A* **13**, 532 (1976).
- R. H. Pratt and H. K. Tseng, *Phys. Rev. A* **5**, 1063 (1972).
- B. G. Adams, J. Čížek, and J. Paldus, *Int. J. Quantum Chem.* **21**, 153 (1982).
- J. Čížek and E. R. Vrscay, *Int. J. Quantum Chem.* **21**, 27 (1982).
- E. R. Vrscay, "Hydrogen Atom with a Yukawa Potential: Perturbation Theory and Continued-Fractions–Padé Approximants at Large Order," *Phys. Rev. A* **33**, 1433 (1986).
- V. Vainberg, V. Eletskii, and V. Popov, "Logarithmic Perturbation Theory for a Screened Coulomb Potential and a Charmonium Potential," *Sov. Phys. JETP* **54**, 833 (1981).
- A. D. Dolgov and V. S. Popov, "Modified Perturbation Theories for an Anharmonic Oscillator," *Phys. Lett. B* **79**, 403 (1978).
- S. K. Bandyopadhyay and K. Bhattacharyya, "Logarithmic Perturbation Theory: A Reappraisal," *Int. J. Quantum Chem.* **90**, 27 (2002).
- V. I. Yukalov, E. P. Yukalova, and F. A. Oliveira, "Renormalization-Group Solutions for Yukawa Potential," *J. Phys. A* **31**, 4337 (1998).
- A. Weber, "The Yukawa Potential: Ground State Energy and Critical Screening," *Prog. Theor. Exp. Phys.* **2017**, 083A01 (2017); arXiv:1706.09979.

**Variational methods**
- O. A. Gomes, H. Chacham, and J. R. Mohallem, "Variational Calculations for the Bound–Unbound Transition of the Yukawa Potential," *Phys. Rev. A* **50**, 228 (1994).
- S. L. Garavelli and F. A. Oliveira, *Phys. Rev. Lett.* **66**, 1310 (1991).
- C. R. Gerry, "Estimates of the Ground States of the Yukawa Potential from the Bogoliubov Inequality," *J. Phys. A* (various years).
- W. Yao et al., "Calculation of the Energy Eigenvalues of the Yukawa Potential via Variation Principle," *Int. J. Mod. Phys. E* **29**, 2050067 (2020).

**Nikiforov–Uvarov, SUSYQM, and related algebraic methods**
- M. Hamzavi et al., "Approximate Analytical Solution of the Yukawa Potential with Arbitrary Angular Momenta," *Chin. Phys. Lett.* **29**, 080302 (2012); arXiv:1210.5886.
- C. A. Onate and J. O. Ojonubah, "Eigensolutions of the Schrödinger Equation with a Class of Yukawa Potentials via Supersymmetric Approach," *J. Theor. Appl. Phys.* **10**, 21 (2016).
- S. M. Ikhdair, "Approximate k-State Solutions to the Dirac–Yukawa Problem Based on the Spin and Pseudospin Symmetry," arXiv:1203.2023.
- S. M. Ikhdair, "A Semirelativistic Treatment of Spinless Particles Subject to the Yukawa Potential with Arbitrary Angular Momenta," arXiv:1203.1747.
- S. M. Ikhdair, "Relativistic New Yukawa-like Potential and Tensor Coupling," arXiv:1210.1406.
- S. M. Ikhdair, "Spinless Particles in the Field of Unequal Scalar–Vector Yukawa Potentials," arXiv:1307.8309.
- E. P. Inyang et al., "Analytical Bound State Solutions of the Dirac Equation with the Hulthén Plus a Class of Yukawa Potential Including a Coulomb-like Tensor Interaction," arXiv:2101.01050.
- E. S. Eyube et al., "The Investigation of Approximate Solutions of Deformed Klein–Gordon and Schrödinger Equations Under Modified More General Exponential Screened Coulomb Potential Plus Yukawa Potential in NCQM Symmetries," *Few-Body Syst.* **62**, 55 (2021).
- E. E. Ituen et al., "Bound State Solutions of the Klein–Gordon Equation with Manning–Rosen Plus Yukawa Potential Using Pekeris-Like Approximation of the Coulomb Term and Parametric Nikiforov–Uvarov," *Phys. Sci. Int. J.* **15**(3), 1 (2017).
- E. E. Ituen et al., "Bound State Solutions of the Schrödinger Equation with Manning–Rosen Plus a Class of Yukawa Potential Using Pekeris-like Approximation of the Coulomb Term and Parametric Nikiforov–Uvarov," (2017).
- Nzeata, "Bound State Solutions of the Schrödinger Equation for the More General Exponential Screened Coulomb Potential Plus Yukawa (MGESCY) Potential Using Nikiforov–Uvarov Method," *J. Quantum Inf. Sci.* **8**, 24 (2018).
- Various authors, "Bound State Solutions and Thermodynamic Properties of Modified Exponential Screened Plus Yukawa Potential," *J. Egypt. Math. Soc.* **30**, 6 (2022).
- R. L. Greene and C. Aldrich, "Variational Wave Functions for a Screened Coulomb Potential," *Phys. Rev. A* **14**, 2363 (1976). *(source of the Greene–Aldrich centrifugal-term approximation widely used in NU/SUSYQM treatments)*
- C. Berkdemir and J. Han, "Any $\ell$-State Solution of Morse Potential Through the Pekeris Approximation and Nikiforov–Uvarov Method," *Chem. Phys. Lett.* **409**, 203 (2005).

**Hidden supersymmetry / complete analytic solutions**
- M. Napsuciale and S. Rodríguez, "Complete Analytical Solution to the Quantum Yukawa Potential," *Phys. Lett. B* **816**, 136218 (2021).
- M. Napsuciale and S. Rodríguez, "Bound States of the Yukawa Potential from Hidden Supersymmetry," *Prog. Theor. Exp. Phys.* **2021**, 073B03 (2021); arXiv:2102.07160.

**Shifted $1/N$ expansion and related large-order expansions**
- Bound states of the Yukawa potential via the shifted $1/N$ expansion technique (various authors; results benchmarked against Rogers–Graboske–Harwood).

**Critical screening parameter studies**
- H. S. Bennett, "Upper Limits for the Number of Bound States Associated with the Yukawa Potential," *J. Res. Natl. Bur. Stand.* **86**, 5 (1981).
- H. Taseli and M. Demiralp, *Theor. Chim. Acta* **71**, 315 (1987).
- M. Demiralp, N. A. Baykara, and H. Taseli, "Convergent Perturbation Studies in Screened Coulomb Potential Systems: A High Precision Numerical Algorithm via Laguerre Basis Set," *Theor. Chim. Acta* **74**, 39 (1988).
- "Rapidly Converging Threshold Value Calculations in Screened Coulomb Potential Systems: Critical Values of the Screening Parameter for the Yukawa Case," *Theor. Chem. Acc.* (various years).
- "Bound States and Critical Behavior of the Yukawa Potential," *Sci. China Phys. Mech. Astron.* **47**, 508 (2004) — Monte Carlo Hamiltonian approach.
- "Critical Properties of Bound States with One-Boson-Exchange Potential," arXiv:2510.10420 (high-precision shooting-method study).

**Applications and extended contexts**
- B. Ya. Yavidov, Sh. S. Djumanov, and S. Dzhumanov, "Mass of a Lattice Polaron from an Extended Holstein Model Using the Yukawa Potential," *Phys. Lett. A* **374**, 2772 (2010).
- A. A. Costa, L. C. Olivari, and E. Abdalla, "Quintessence with Yukawa Interaction," *Phys. Rev. D* **92**, 103501 (2015).
- "Antiproton-Impact Ionization of Hydrogen Atom with Yukawa Interaction," *Eur. Phys. J. D* **72**, 8 (2018).
- "Relativistic Quantum Theory and Algorithms: A Toolbox for Modeling Many-Fermion Systems in Different Scenarios," arXiv:2110.00775 (review context for Coulomb/Yukawa potentials in atomic/nuclear applications).
- "Auxiliary Field Method and Analytical Solutions of the Schrödinger Equation with Exponential Potentials," arXiv:0811.0287.
- "Two-Dimensional Yukawa Interaction Driven by a Nonlocal-Proca Quantum Electrodynamics," arXiv:1712.06401.
- "Supersymmetric Expansion Algorithm and Complete Analytical Solution for the Hulthén and Anharmonic Potentials," arXiv:2405.01367.

---

*Note on scope: this review focuses specifically on eigenvalue (bound-state energy) determination for the Yukawa/screened-Coulomb potential in nonrelativistic quantum mechanics, with pointers to the closely related relativistic (Dirac/Klein–Gordon) and molecular-spectroscopy extensions. Scattering-theory treatments of the Yukawa potential (phase shifts, Born series) are referenced only where they intersect directly with bound-state/critical-screening determinations.*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Yukawa potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
