# Evaluation of Eigenvalues of the Schrödinger Equation with the Kratzer Potential: An Exhaustive Review

## 1. Introduction and Historical Background

The Kratzer potential is one of the oldest analytically solvable model potentials in molecular quantum mechanics, introduced by Adolf Kratzer in 1920 to describe the rotation–vibration spectra of diatomic molecules, in particular the hydrogen halides. Kratzer, working as an assistant to Arnold Sommerfeld in Munich, proposed the potential in his paper *"Die ultraroten Rotationsspektren der Halogenwasserstoffe"* (Z. Phys. **3**, 289–307, 1920), and elaborated the general theory of band spectra in a companion encyclopedia article the same year. Shortly afterward, Erwin Fues (1926) applied the (old) quantum-mechanical treatment to the same potential form, so that in much of the literature it appears as the **Kratzer–Fues potential**.

The potential is historically significant for two reasons. First, it long predates the Schrödinger equation itself (1926) and was originally solved within the older Bohr–Sommerfeld quantization scheme. Second, together with the Coulomb, harmonic-oscillator, Morse, Pöschl–Teller, and Hulthén potentials, it belongs to the very small set of potentials for which the three-dimensional radial Schrödinger equation admits an **exact, closed-form solution in terms of elementary special functions** for arbitrary radial and angular-momentum quantum numbers. This property has made it a perennial workbench for testing new methods of solving the Schrödinger equation, long after its original spectroscopic motivation.

## 2. The Potential Form

### 2.1 The Original (Pure) Kratzer Potential

$$V(r) = -2D_0\left(\frac{r_0}{r} - \frac{1}{2}\frac{r_0^2}{r^2}\right) = -\frac{2D_0 r_0}{r} + \frac{D_0 r_0^2}{r^2}$$

where $D_0$ is the dissociation energy measured from the bottom of the well and $r_0$ is the equilibrium internuclear distance. This potential vanishes as $r\to\infty$, diverges to $+\infty$ as $r\to 0$ (representing short-range nuclear repulsion), and has a single minimum $V(r_0) = -D_0$.

### 2.2 The Modified Kratzer Potential

A vertically shifted version, widely used in the modern literature so that $V(\infty) = 0$ is replaced by a convenient asymptotic reference and the dissociation limit is built in explicitly, is

$$V(r) = D_e\left(\frac{r - r_e}{r}\right)^2 = D_e - \frac{2D_e r_e}{r} + \frac{D_e r_e^2}{r^2}$$

with $D_e$ the dissociation energy and $r_e$ the equilibrium bond length. This form satisfies $V(r_e) = 0$ (minimum) and $V(\infty) = D_e$, and is the version most commonly fitted to spectroscopic data for diatomic molecules (CO, NO, N$_2$, O$_2$, I$_2$, HCl, LiH, CH, ScF, etc.).

### 2.3 Generalizations Studied in the Literature

Numerous extensions retain the exact-solvability property or admit approximate analytic treatment:

- **Kratzer–Feus (KF) potential** — the generic two-term $1/r$, $1/r^2$ form treated in arbitrary spatial dimension $D$.
- **Screened Kratzer potential** — adds a Yukawa-type screening factor $e^{-\alpha r}$.
- **Shifted / screened-shifted Kratzer potential**.
- **Modified Kratzer plus screened Coulomb potential**.
- **Kratzer plus inversely quadratic Yukawa potential**.
- **Möbius square plus screened Kratzer potential**.
- **Kratzer potential with position-dependent (effective) mass** — relevant to semiconductor quantum wells, quantum dots, and graded heterostructures.
- **Energy-dependent Kratzer potential**.
- **Kratzer potential plus a dipole term**, and Kratzer potential in two dimensions.
- **Kratzer-type potentials in curved/non-Euclidean spacetimes** (de Sitter, anti-de Sitter, global monopole backgrounds) — motivated by analogies between molecular and gravitational/cosmological bound-state problems.
- **Fractional-derivative (conformable fractional) Schrödinger equation with the screened Kratzer potential.**
- **Feinberg–Horodecki (space-to-time-mapped) equation with a time-dependent Kratzer-type potential**, used to model vibrating diatomic systems.

## 3. The Radial Schrödinger Equation

For a particle of reduced mass $\mu$ moving in a central potential $V(r)$, separation of variables in spherical coordinates $\psi(r,\theta,\phi) = \frac{u(r)}{r}Y_{\ell m}(\theta,\phi)$ reduces the problem to the radial equation

$$\frac{d^2 u(r)}{dr^2} + \frac{2\mu}{\hbar^2}\left[E - V(r) - \frac{\hbar^2 \ell(\ell+1)}{2\mu r^2}\right]u(r) = 0$$

For the Kratzer potential the centrifugal term $\ell(\ell+1)/r^2$ and the potential's own $1/r^2$ term combine into a single effective inverse-square term, which is what makes the equation exactly solvable: after substituting $V(r)$, the equation takes the generic **Coulomb-plus-inverse-square (Kratzer-type) form**

$$\frac{d^2 u}{dr^2} + \left[\frac{2\mu E}{\hbar^2} + \frac{4\mu D_0 r_0}{\hbar^2 r} - \frac{\gamma}{r^2}\right]u = 0, \qquad \gamma = \ell(\ell+1) + \frac{2\mu D_0 r_0^2}{\hbar^2}$$

This is structurally identical to the hydrogen-atom radial equation but with a **shifted, non-integer effective angular momentum** $\lambda(\lambda+1) = \gamma$, which is the key mathematical fact exploited by every exact-solution technique below.

## 4. Methods Used to Evaluate the Eigenvalues

A remarkably large number of independent techniques have been applied to this single potential, partly because it serves as a standard benchmark for new methods in mathematical physics. The main families are:

### 4.1 Direct Series-Solution / Frobenius Method (classical approach)
The oldest approach: substitute a power-series ansatz, demand normalizability at infinity (via an asymptotic exponential factor) and regularity at the origin, and truncate the resulting confluent hypergeometric (or Laguerre-type) series to a polynomial. Truncation of the series is precisely the bound-state quantization condition and yields the eigenvalues directly, exactly as in the hydrogen-atom problem. This is how Fues originally solved it in the old quantum theory, and how most modern textbook treatments proceed as well.

### 4.2 Nikiforov–Uvarov (NU) Method
Introduced by Nikiforov and Uvarov, this method reduces a generalized hypergeometric-type differential equation to a self-adjoint form via an appropriate transformation, and obtains eigenvalues from a polynomial condition on the "weight function" parameters. It has become, by a wide margin, the most frequently used method in the post-2005 literature for the Kratzer potential and its many generalizations (screened, shifted, position-dependent mass, N-dimensional, etc.), largely because it is algorithmic and generalizes cleanly to related potentials.

### 4.3 Asymptotic Iteration Method (AIM)
Proposed by Saad and Hall (Ciftci, Hall, Saad), AIM converts the Schrödinger equation into a form $u'' = \lambda_0(r) u' + s_0(r) u$ and imposes a termination (quantization) condition on the iteratively generated coefficients $\lambda_n, s_n$. Bayrak, Boztosun and co-workers applied AIM to the pure Kratzer potential (2006–2007) and obtained closed-form eigenvalues that were subsequently used as reference values by many later papers.

### 4.4 Exact/Improved Quantization Rule (EQR) Method
Based on an exact WKB-like quantization condition (Ma and Xu), which becomes exact rather than approximate for potentials — like the Kratzer potential — whose logarithmic derivative of the wave function has a particularly simple form. Applied to the $D$-dimensional Kratzer/modified Kratzer potential to obtain the hyper-radial energy spectrum for arbitrary $n,\ell$.

### 4.5 Supersymmetric Quantum Mechanics (SUSY QM) and Shape Invariance
The Kratzer potential (like the Coulomb potential) is *shape invariant*, so its superpotential can be constructed explicitly and the full bound-state spectrum generated algebraically from the ground state using the shape-invariance condition, without solving a differential equation at all.

### 4.6 Factorization Method
Closely related to the SUSY approach, this ladder-operator technique (used by Sever, Tezcan, Yeşiltaş, and by Dong) factorizes the Hamiltonian into raising/lowering operators and derives the spectrum from the algebra they satisfy; also used to construct a full **spectrum-generating algebra** (su(1,1)) for the Kratzer and modified Kratzer potentials, giving matrix elements of $r$ and $r^2$ in closed form in addition to the energies.

### 4.7 Point Canonical Transformation (PCT) / Coordinate-Transformation Methods
Used extensively for the **position-dependent effective mass** Schrödinger equation, where a coordinate- and mass-dependent transformation maps the variable-mass problem onto a constant-mass exactly solvable equation of Kratzer type.

### 4.8 Path Integral (Feynman) Methods
The Kratzer/Coulomb correspondence has also been exploited to solve the path integral for the Kratzer potential by mapping it onto the Coulomb path integral via a Duru–Kleinert-type space-time transformation.

### 4.9 WKB and Semiclassical Approximations
Used mainly as a numerical cross-check for the exact/approximate analytic results (e.g., comparisons against Möbius-square-plus-screened-Kratzer NU results).

### 4.10 Numerical Methods
Direct numerical integration (shooting method, matrix diagonalization in a suitable basis, finite-difference or finite-element discretization) is used chiefly for the non-exactly-solvable extensions (screened, fractional-order, or non-central generalizations) and to validate new analytic approximations (e.g., the Pekeris-type or Greene–Aldrich approximation used to handle the extra centrifugal-like terms that appear once screening or additional potential pieces destroy exact solvability).

### 4.11 Lie-Algebraic / Group-Theoretical Approaches
Realizations of the dynamical symmetry group (e.g., $SO(2,1)$/$su(1,1)$) associated with the Kratzer-type radial equation give the spectrum from representation theory alone (Section 4.6 overlaps here).

## 5. The Exact Bound-State Energy Formula

Regardless of the method used, the eigenvalues of the pure Kratzer potential are exactly:

$$E_{n\ell} = -\frac{2\mu D_0^2 r_0^2}{\hbar^2\left[n + \beta_\ell + 1\right]^2}, \qquad n = 0, 1, 2, \ldots$$

with the effective (non-integer) quantum-defect-like parameter

$$\beta_\ell = \frac{1}{2}\left[-1 + \sqrt{(2\ell+1)^2 + \dfrac{8\mu D_0 r_0^2}{\hbar^2}}\right]$$

For the modified Kratzer potential (Section 2.2) the corresponding formula, shifted by the additive constant $D_e$ so that the asymptote sits at $D_e$ rather than $0$, is

$$E_{n\ell} = D_e - \frac{2\mu D_e^2 r_e^2}{2\hbar^2\left[n + \beta_\ell + 1\right]^2}$$

These closed forms are formally identical in structure to the hydrogen-atom Bohr formula $E_n = -\text{Ry}/n^2$, with the integer angular-momentum-dependent quantum defect of hydrogen ($\ell$ itself) replaced by the Kratzer-specific, generally non-integer $\beta_\ell$ that depends on the potential's depth and range as well as on $\ell$. This is the origin of the close, often-remarked mathematical kinship between the Kratzer and Coulomb problems, and it is why so many "new methods" tested on the Coulomb potential are subsequently re-tested on the Kratzer potential as a slightly more intricate benchmark.

The corresponding (unnormalized) radial eigenfunctions are expressed in terms of the confluent hypergeometric function ${}_1F_1$ (equivalently, generalized Laguerre polynomials):

$$R_{n\ell}(r) \propto r^{\beta_\ell} e^{-\alpha r}\, {}_1F_1\!\left(-n,\, 2\beta_\ell + 2;\, 2\alpha r\right), \qquad \alpha = \frac{\sqrt{-2\mu E_{n\ell}}}{\hbar}$$

## 6. Applications of the Spectrum

- **Molecular spectroscopy**: fitting vibration–rotation term values of diatomic molecules (H$_2$, HCl, HF, CO, NO, N$_2$, O$_2$, I$_2$, LiH, CH, ScF, and others), and deriving spectroscopic constants (rotational and centrifugal-distortion constants) in closed analytic form.
- **Thermodynamic properties**: once $E_{n\ell}$ is known in closed form, the vibrational partition function $Z(\beta)$ can be evaluated (often via a Euler–Maclaurin / Poisson-summation approximation), from which mean energy, entropy, free energy, and specific heat of a molecular gas follow analytically; a substantial fraction of the post-2015 literature on Kratzer-type potentials is devoted to exactly this thermodynamic program.
- **Expectation values and Hellmann–Feynman theorem**: closed-form results for $\langle r \rangle$, $\langle r^{-1}\rangle$, $\langle r^{-2}\rangle$, kinetic energy, and $\langle p^2\rangle$ are obtained directly from the energy formula via the Hellmann–Feynman theorem without further integration.
- **Condensed-matter and nanostructure physics**: position-dependent-mass Kratzer-type problems model electrons in graded semiconductor heterostructures, quantum wells, and quantum dots; the "spherical quantum dot in a Kratzer confining potential" line of work studies linear/nonlinear optical absorption and refractive-index changes.
- **Mathematical physics / relativistic extensions**: Klein–Gordon, Dirac (with spin and pseudospin symmetry), and Duffin–Kemmer–Petiau equations have all been solved with Kratzer-type potentials, extending the non-relativistic spectrum program to relativistic quantum mechanics.
- **Gravitational/cosmological analogies**: Kratzer-type potentials embedded in de Sitter, anti-de Sitter, and global-monopole spacetimes are used as solvable toy models for bound states in curved backgrounds.
- **Testbed for new solution techniques**: because the exact answer is known, the Kratzer potential (alongside the Coulomb and harmonic oscillator) is routinely used as the first non-trivial validation case whenever a new method for solving the Schrödinger equation is proposed (NU, AIM, EQR, SUSY QM, factorization, Laplace-transform, series expansion methods, machine-learning based eigensolvers, etc.).

## 7. Summary Assessment

The Kratzer potential occupies a special niche: it is simple enough to be exactly solvable in closed form for arbitrary quantum numbers, yet rich enough (through its many screened, shifted, dimension-generalized, mass-generalized, and spacetime-generalized variants) to remain a subject of active research more than a century after its introduction. The eigenvalue problem itself was solved essentially completely by the late 1920s; what the subsequent — and especially the post-2000 — literature contributes is (i) re-derivation of the same spectrum by an ever-growing list of formal techniques, used as validation exercises for those techniques; (ii) extension to potentials that are *not* exactly solvable (screened, fractional, non-central, deformed), where the Kratzer eigenvalue formula is recovered as a limiting/special case; and (iii) systematic exploitation of the closed-form spectrum to compute thermodynamic and spectroscopic quantities of real diatomic molecules to high precision.

---

## 8. List of Publications

### 8.1 Foundational / Historical

1. A. Kratzer, *Die ultraroten Rotationsspektren der Halogenwasserstoffe*, Z. Phys. **3**, 289–307 (1920).
2. A. Kratzer, *Die Gesetzmäßigkeiten in den Bandspektren*, Enzykl. Math. Wiss. **3**, 821–859 (1920); also Ann. Phys. **67**, 127 (1922).
3. E. Fues, *Das Eigenschwingungsspektrum zweiatomiger Moleküle in der Undulationsmechanik*, Ann. Phys. **80**, 367–396 (1926).
4. H. M. Hulburt, J. O. Hirschfelder, *Potential Energy Functions for Diatomic Molecules*, J. Chem. Phys. **9**, 61 (1941).
5. G. Herzberg, *Molecular Spectra and Molecular Structure I: Spectra of Diatomic Molecules*, 2nd ed. (Van Nostrand Reinhold, New York, 1950).

### 8.2 Exact Solutions via Nikiforov–Uvarov and Related Algebraic Methods

6. C. Berkdemir, A. Berkdemir, J. Han, *Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential*, Chem. Phys. Lett. **417**, 326–329 (2006).
7. C. Berkdemir, J. Han, *Any ℓ-state solutions of the Morse potential through the Pekeris approximation and Nikiforov–Uvarov method*, Chem. Phys. Lett. **409**, 203 (2005).
8. C. Berkdemir, *A novel angle-dependent potential and its solution*, J. Math. Chem. **46**, 492 (2009).
9. C. Berkdemir, R. Sever, *Modified ℓ-states of diatomic molecules subjected to a nonuniform electric field*, J. Math. Chem. **46**, 1122 (2009).
10. R. Sever, C. Tezcan, Ö. Yeşiltaş, O. Bucurgat, *Exact solution of effective mass Schrödinger equation for the Hulthén potential*, J. Math. Chem. **43**, 749 (2007).
11. R. Sever, C. Tezcan, Ö. Aktaş, Ö. Yeşiltaş, *Exact solution of effective-mass Schrödinger equation for the deformed Hulthén potential*, J. Math. Chem. **43**, 845 (2007).
12. R. Sever, C. Tezcan, *Exact solution of Schrödinger equation for the modified Kratzer's molecular potential with position-dependent mass*, Int. J. Mod. Phys. E **17**, 1327 (2008); arXiv:0712.0268.
13. S. M. Ikhdair, R. Sever, *Exact solutions of the modified Kratzer potential plus ring-shaped potential in the D-dimensional Schrödinger equation*, J. Mol. Struct.: THEOCHEM (2007); Chin. J. Phys.; J. Mol. Struct. **806**, 155 (2007).
14. S. M. Ikhdair, *Rotational and vibrational diatomic molecule in the Kratzer-type molecular potential*, Chem. Phys. **361**, 9 (2009).
15. Shi-Hai Dong, Guo-Hua Sun, *The Schrödinger equation with a Kratzer-type potential in D dimensions*, J. Mol. Struct.: THEOCHEM (2003).
16. K. J. Oyewumi, *Analytical Solutions of the Kratzer–Fues Potential in an Arbitrary Number of Dimensions*, Found. Phys. Lett. **18**, 75 (2005).
17. A. Agboola, *Complete Analytic Solutions of the Mie-type Potentials in N-Dimensions*, Acta Phys. Pol. A **120**, 371 (2011).
18. F. Hoseini, J. K. Saha, H. Hassanabadi, *Solutions of Klein–Gordon equation with the modified Kratzer potential*, Commun. Theor. Phys. **65**, 695 (2016).
19. S. A. Najafizade, H. Hassanabadi, S. Zarrinkamar, *Nonrelativistic and relativistic study of a class of Kratzer-type potentials*, Can. J. Phys. **94**, 1085 (2016).
20. F. A. Bayrak et al., *Analytical Solutions of the Molecular Kratzer–Feus Potential by means of the Nikiforov–Uvarov Method*, J. Math. Chem. (2023); doi:10.1007/s10910-023-01462-y.
21. E. P. Inyang et al., *Eigensolution, expectation values and thermodynamic properties of the screened Kratzer potential*, Eur. Phys. J. Plus **134**, 386 (2019).
22. C. O. Edet et al., *Effects of the interaction between screening potential and Kratzer potential on energy levels, thermodynamic properties, and expectation values*, Eur. Phys. J. D **74**, 159 (2020).
23. K. R. Purohit, R. H. Parmar, A. K. Rai, *Solutions of the N-dimensional Schrödinger equation with the shifted Kratzer potential*, Eur. Phys. J. Plus **135**, 286 (2020); J. Mol. Model. **27**, 358 (2021).
24. A. N. Ikot, U. S. Okorie, G. J. Rampho, P. O. Amadi, C. O. Edet, I. O. Akpan, H. Y. Abdullah, R. Horchani, *Thermodynamics properties of diatomic molecules with general molecular potential using Poisson summation approach*, J. Low Temp. Phys. **202**, 269 (2021).
25. G. J. Rampho, A. N. Ikot, C. O. Edet, U. S. Okorie, *Energy spectra and thermal properties of diatomic molecules in the presence of Deng–Fan–Eckart potential*, Mol. Phys. **119**, e1821922 (2021).
26. Solutions of the Schrödinger equation of the shifted screened Kratzer potential and its thermodynamic functions using the extended Nikiforov–Uvarov method, Front. Phys. **10**, 988279 (2022).
27. Thermodynamic properties and bound state solutions of Schrödinger equation with Möbius square plus screened-Kratzer potential using Nikiforov–Uvarov method, Sci. Afr./ Results Phys., ScienceDirect (2020).
28. E. Inyang, I. Okon, E. William, E. Omugbe, C. Onate, A. D. Antia, J. Ntibi, *Approximate Solutions of the N-Dimensional Schrödinger Equation with Modified Screened Kratzer Plus Inversely Quadratic Yukawa Potential*, SSRN (2022); doi:10.2139/ssrn.4165902.
29. C. O. Edet et al., *A study on the applicability of Deng–Fan potential and modified Kratzer plus screened Coulomb potential to obtain bound state solutions*, arXiv:2007.14799.
30. U. S. Okorie et al., *Solutions of Schrödinger equation with the modified Kratzer plus screened Coulomb potential using the modified factorization method*.
31. G. Van Hooydonk, *Ionic Kratzer bond theory and vibrational levels for achiral covalent bond HH*, Z. Naturforsch. A **64**, 801/810 (2009).

### 8.3 Asymptotic Iteration Method (AIM)

32. O. Bayrak, I. Boztosun, *Exact analytical solutions to the Kratzer potential by the asymptotic iteration method*, Int. J. Quantum Chem. **107**, 540 (2007).
33. Bound state solutions of the Schrödinger equation with energy-dependent molecular Kratzer potential via asymptotic iteration method, Eclética Quím. **45**(1), 65–77 (2020).
34. N. Saad, R. L. Hall, *Integrals containing confluent hypergeometric functions with applications to perturbed singular potentials*, J. Phys. A: Math. Gen. **36**, 7771 (2003).
35. H. Ciftci, R. L. Hall, N. Saad, *Asymptotic iteration method for eigenvalue problems*, J. Phys. A: Math. Gen. **36**, 11807 (2003).

### 8.4 Exact Quantization Rule (EQR) and WKB-Type Methods

36. Bound state solutions of the Schrödinger equation for modified Kratzer's molecular potential (via exact quantization rule, D-dimensional hyper-radial equation).
37. Z.-Q. Ma, B.-W. Xu, *Quantum correction in exact quantization rules*, Europhys. Lett. **69**, 685 (2005).

### 8.5 Factorization Method and Spectrum-Generating Algebra

38. *Realization of the spectrum generating algebra for the generalized Kratzer potentials*, arXiv:1008.1515.
39. D. A. Morales, *Supersymmetric improvement of the Pekeris approximation for the rotating Morse potential*, Chem. Phys. Lett. **161**, 253 (1989).

### 8.6 Screened, Fractional, and Time-Dependent Variants

40. Approximate Solutions of the Fractional Schrödinger Equation for the Screened Kratzer Potential, arXiv:2103.14064.
41. Approximate solution of the time-dependent Kratzer plus screened Coulomb potential in the Feinberg–Horodecki equation, arXiv:2007.14799 (related work).
42. On the screened Kratzer potential and its variants, arXiv:2405.19451.

### 8.7 Non-Central, Curved-Space, and Higher-Dimensional Extensions

43. Bound state solutions of the two-dimensional Schrödinger equation with Kratzer-type potentials, arXiv:2311.02694.
44. Non-Relativistic and Relativistic Equations for the Kratzer Potential plus a Dipole in 2D Systems, arXiv:1905.03765.
45. Exact and approximate bound state solutions of the Schrödinger equation with a class of Kratzer-type potentials in the global monopole spacetime, arXiv:2306.09429.
46. Diatomic Molecules in de Sitter and Anti-de Sitter Spaces, arXiv:2405.04502.
47. L. Fortunato, A. Vitturi, *Analytically solvable potentials for gamma unstable nuclei*, J. Phys. G **29**, 1341 (2003).

### 8.8 Spectroscopic Constants and Molecular-Physics Applications

48. P. G. Hajigeorgiou, *Exact analytical expressions for diatomic rotational and centrifugal distortion constants for a Kratzer–Fues oscillator*, J. Mol. Spectrosc. **235**, 111 (2006).
49. R. J. LeRoy, R. B. Bernstein, *Dissociation energy and long-range potential of diatomic molecules from vibrational spacings of higher levels*, J. Chem. Phys. **52**, 3869 (1970).
50. K. Batra, V. Prasad, *Spherical quantum dot in Kratzer confining potential: study of linear and nonlinear optical absorption coefficients and refractive index change*, Eur. Phys. J. B / related journal (2016–2018).
51. International Journal of Modern Physics B article on confined Kratzer oscillators and H$_2$, HF, I$_2$, N$_2$, O$_2$ potential energy curves, IJMPB (2016); doi:10.1142/S0217979216500430.

### 8.9 Relativistic Extensions (Klein–Gordon / Dirac with Kratzer-type Potentials)

52. S. M. Ikhdair, *An approximate κ-state solution of the Dirac equation for the generalized Morse potential under spin and pseudospin symmetry*, J. Math. Phys. **52**, 052303 (2011) (methodologically parallel to Kratzer-type Dirac studies).
53. F. Hoseini, J. K. Saha, H. Hassanabadi, *Klein–Gordon equation for the modified Kratzer potential*, Commun. Theor. Phys. **65**, 695 (2016) (see also entry 18).

---

*Note: entries are grouped thematically rather than strictly chronologically; several works (e.g., screened/shifted Kratzer papers) could be cross-listed in more than one section. DOIs/arXiv identifiers are given where confirmed; readers should verify exact volume/page details against the original source before citing, as some secondary listings in the literature contain minor transcription discrepancies (e.g., Fues' paper is variously cited as Ann. Phys. 80, 367 or 376).*


---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Kratzer potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
