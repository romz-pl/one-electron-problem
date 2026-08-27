# Evaluation of Eigenvalues of the Schrödinger Equation with the Hellmann Potential: A Comprehensive Review

## Abstract

The Hellmann potential — a superposition of an attractive Coulomb term and a Yukawa (screened Coulomb) term — has become one of the most widely studied model potentials in molecular, atomic, and nuclear physics because it interpolates between short-range screened interactions and the exactly solvable Coulomb problem. Since the radial Schrödinger equation with this potential is not exactly solvable for arbitrary angular momentum $\ell$, a large body of literature has developed around approximate analytical and numerical techniques for extracting its energy eigenvalues. This review surveys the physical origin of the potential, the mathematical structure of the eigenvalue problem, the principal solution methods (perturbation theory, the Nikiforov–Uvarov method and its parametric/functional-analysis variants, the asymptotic iteration method, supersymmetric quantum mechanics, the exact/proper quantization rule, the shifted $1/N$ expansion, the WKB approach, and fully numerical schemes), the centrifugal-term approximations that make analytic progress possible, extensions to relativistic wave equations and to superpositions with other potentials, and applications to diatomic molecules, entropy/information measures, and thermodynamic properties. A curated bibliography of the key publications is provided at the end.

---

## 1. Introduction

### 1.1 Historical background

The potential was introduced by **Hans Hellmann** in the 1930s as a simple model for the effective interaction between a valence electron and an atomic core, combining a point-charge Coulomb attraction with a short-range exponential (Yukawa-type) correction that mimics core-penetration and screening effects. Hellmann originally proposed the form to reproduce alkali-metal term values and ionization energies without resorting to full self-consistent-field calculations. In more recent decades the same functional form re-emerged independently in nuclear and molecular physics as a two-parameter screened Coulomb model, and it is now generally referred to as the **Hellmann potential**.

### 1.2 Functional form

The (three-dimensional, spherically symmetric) Hellmann potential is usually written as

$$
V(r) = -\frac{A}{r} + \frac{B\,e^{-\delta r}}{r},
$$

or, in an equivalent notation frequently used in the Nikiforov–Uvarov literature,

$$
V(r) = -\frac{V_0}{r} + \frac{V_1\, e^{-\alpha r}}{r},
$$

where:
- $A$ (or $V_0$) is the strength of the attractive Coulomb term,
- $B$ (or $V_1$) is the strength of the Yukawa term (can be positive or negative, giving either an additional attractive or repulsive short-range contribution),
- $\delta$ (or $\alpha$) is the **screening parameter**, with dimension of inverse length.

Two limiting/special cases are physically important and serve as consistency checks for any solution method:

- **$B \to 0$:** the potential reduces to the pure **Coulomb potential**, for which the Schrödinger equation is exactly solvable and $E_{n\ell} = -\dfrac{A^2 \mu}{2\hbar^2 n^2}$ (in the usual notation, $n$ = principal quantum number).
- **$A \to 0$:** the potential reduces to the pure **Yukawa (screened Coulomb) potential**, itself famously *not* exactly solvable for $\ell \neq 0$, and historically one of the first potentials treated by the approximation techniques later applied to Hellmann's potential.

Because of this dual limiting structure, the Hellmann potential is often described as a natural "bridge" between the exactly solvable Coulomb problem and the analytically intractable Yukawa problem, which is precisely what makes it a good testbed for approximate methods.

### 1.3 Why the eigenvalue problem is nontrivial

The radial Schrödinger equation for a particle of reduced mass $\mu$ in the potential $V(r)$ reads

$$
-\frac{\hbar^2}{2\mu}\left[\frac{d^2 R_{n\ell}(r)}{dr^2} + \frac{2}{r}\frac{dR_{n\ell}(r)}{dr}\right] + \left[V(r) + \frac{\hbar^2 \ell(\ell+1)}{2\mu r^2} - E_{n\ell}\right] R_{n\ell}(r) = 0,
$$

or, after substituting $R_{n\ell}(r) = u_{n\ell}(r)/r$,

$$
\frac{d^2 u_{n\ell}(r)}{dr^2} + \frac{2\mu}{\hbar^2}\left[E_{n\ell} - V(r) - \frac{\hbar^2 \ell(\ell+1)}{2\mu r^2}\right]u_{n\ell}(r) = 0.
$$

For $\ell = 0$ this equation can, in certain formulations, be handled in closed form; but for $\ell \neq 0$ the combination of the centrifugal term $\ell(\ell+1)/r^2$ with the exponential Yukawa piece $e^{-\delta r}/r$ prevents an exact analytic solution in terms of elementary or standard special functions for arbitrary quantum numbers. This is the central technical obstruction that the methods reviewed below are designed to overcome.

---

## 2. The Centrifugal-Term Approximation

Almost every semi-analytical treatment of the Hellmann (and Yukawa, Hulthén, exponential-cosine-screened-Coulomb, etc.) potential relies on replacing the exact centrifugal term by an approximation that has the same short-range singularity structure as the rest of the potential, so that the resulting equation becomes exactly solvable by hypergeometric-type methods. The two most common schemes are:

**Greene–Aldrich approximation:**
$$
\frac{1}{r^2} \approx \frac{\delta^2}{(1-e^{-\delta r})^2}, \qquad (\delta r \ll 1)
$$

**Pekeris-type / improved approximation** (expansion of $1/r$ and $1/r^2$ in powers of $e^{-\delta r}$ about the equilibrium or reference point), used especially when high accuracy is required over a wider range of the screening parameter or for excited states.

The accuracy of virtually all "approximate analytical" energy formulas quoted in the literature is contingent on the validity of this substitution, which holds best for **small screening parameter $\delta$** (weak screening) and deteriorates for large $\delta$ or high $\ell$. This is a recurring caveat throughout the literature and a common point of comparison between papers.

---

## 3. Principal Solution Methods

### 3.1 Perturbation theory

The earliest modern treatments (Ikhdair & Sever) treated the Yukawa (screened) part of the Hellmann potential as a perturbation on the exactly solvable Coulomb problem, expanding the energy in powers of the screening parameter using standard Rayleigh–Schrödinger perturbation theory (sometimes supplemented by a hypervirial/Hellmann–Feynman-theorem-based recursive scheme). This approach is transparent and reduces correctly to the Coulomb limit but is only reliable for weak screening ($\delta$ small) and low quantum numbers.

### 3.2 Nikiforov–Uvarov (NU) method and its parametric generalization

The NU method reduces a second-order differential equation of hypergeometric type,
$$
\psi''(s) + \frac{\tilde{\tau}(s)}{\sigma(s)}\psi'(s) + \frac{\tilde{\sigma}(s)}{\sigma^2(s)}\psi(s) = 0,
$$
to a form solvable via a generating function and Rodrigues-type formula. After applying the Greene–Aldrich approximation to the centrifugal term and a change of variable $s = e^{-\delta r}$, the Hellmann-potential radial equation is cast into exactly this form, from which a closed-form transcendental (or, after further approximation, fully closed-form polynomial) expression for $E_{n\ell}$ is obtained together with the eigenfunctions in terms of Jacobi or hypergeometric polynomials.

The **parametric NU method** (a streamlined bookkeeping version introduced by Tezcan and Sever) is now the dominant technique in this literature because it reduces the derivation to substitution into a small set of universal parameter formulas, and it is the method used in most of the papers on generalized/superposed Hellmann-type potentials (Hellmann–Kratzer, Hellmann–Morse, Hulthén–Hellmann, Manning-Rosen plus Hellmann, etc.).

### 3.3 Asymptotic Iteration Method (AIM)

The AIM converts the Schrödinger equation into the form $y'' = \lambda_0(x) y' + s_0(x) y$ and generates the eigenvalue condition from the termination condition $\delta_n(x) = \lambda_n s_{n-1} - \lambda_{n-1}s_n = 0$ after successive differentiation. For the Hellmann potential the AIM has been shown to reproduce the bound-state spectrum for arbitrary $n$ and $\ell$ without further approximation of the resulting recursion (beyond the initial centrifugal-term treatment), converging numerically after a modest number of iterations (of order 10–20 for typical screening parameters). AIM results are frequently used as an accuracy benchmark against NU and SUSY results.

### 3.4 Supersymmetric Quantum Mechanics (SUSYQM) and shape invariance

In the SUSY approach, a superpotential $W(r)$ is constructed such that the partner Hamiltonians $H_\pm = -\frac{d^2}{dr^2} + W^2(r) \mp W'(r)$ reproduce the effective potential after the centrifugal approximation. When the shape-invariance condition is satisfied, the bound-state energies follow immediately from the shape-invariance algebra without solving a differential equation directly. This method has been applied to the Hellmann potential (Onate, Onyeaju, Ikot and collaborators) and used, together with its associated eigenfunctions, to compute information-theoretic quantities (Shannon, Tsallis, Rényi entropies) in position and momentum space.

### 3.5 Exact/Proper Quantization Rule (EQR/PQR)

The exact quantization rule states that
$$
\int_{r_1}^{r_2} k(r)\, dr = n\pi - \left[\phi(r_2) - \phi(r_1)\right],
$$
where $k(r)$ is the local (classical) momentum and $\phi(r)$ is a quantum correction term related to the logarithmic derivative of the wavefunction, which is an invariant for exactly solvable potentials and can be evaluated exactly at the ground state and then extended to all $n$. Ikhdair, Sever, and later authors (e.g., for Manning–Rosen plus Hellmann superpositions) applied this rule to obtain closed-form eigenvalue expressions that agree closely with NU/AIM results.

### 3.6 Other approaches

- **Formula method** — a unified closed-form recipe (Falaye) for any Schrödinger-like equation reducible to a standard second-order form with specified singular-point structure; applied to Hellmann-type superpositions.
- **Nikiforov–Uvarov Functional Analysis (NUFA)** — a hybrid of NU and the functional analysis approach that further streamlines eigenvalue extraction for multi-term potentials.
- **WKB (semiclassical) method** — used for cross-checking bound-state energies, particularly for "inversely quadratic Yukawa plus inversely quadratic Hellmann" type superpositions.
- **Generalized pseudospectral (fully numerical) method** — Roy, Jalbout & Proynov obtained essentially "exact" non-relativistic eigenvalues (accurate to 13–14 significant figures) via optimal nonuniform radial-grid discretization, without invoking any centrifugal-term approximation; this provides the most reliable benchmark against which all approximate analytic energy formulas are ultimately checked.
- **Shifted $1/N$ expansion, exact solution of the pure Coulomb limit, ansatz methods** — used mainly for combined potentials such as the Varshni–Hellmann potential.

### 3.7 Relativistic extensions

Beyond the non-relativistic Schrödinger treatment, the Hellmann potential (and its superpositions) has been inserted into the **Dirac equation** (spin and pseudospin symmetry limits, with and without tensor interactions such as Coulomb-like, Yukawa-like, and Hulthén-type tensor terms) and the **Klein–Gordon equation**, again typically solved via the (parametric) NU method or SUSYQM after applying an appropriate centrifugal/Pekeris-type approximation. These relativistic treatments reduce correctly to the corresponding non-relativistic Hellmann-potential results in the proper limit, which serves as an important consistency check.

### 3.8 Fractional and topological-defect generalizations

Most recently, the eigenvalue problem has been generalized to a **fractional Schrödinger equation** (using conformable or generalized fractional derivatives) and to curved space-times containing **topological defects** (e.g., a point-like global monopole), typically for the combined **Hulthén–Hellmann potential**. These studies use a generalized fractional Nikiforov–Uvarov method and recover the standard (integer-order, flat-space) Hellmann-potential energy levels as a limiting case.

---

## 4. Superpositions and Generalizations of the Hellmann Potential

A significant fraction of the literature does not treat the "pure" two-term Hellmann potential in isolation but combines it with other exactly- or quasi-exactly-solvable potentials to build richer models, most of which reduce back to the Hellmann potential (and further to Yukawa/Coulomb) as special cases. Notable combinations include:

| Combined potential | Also reduces to |
|---|---|
| Hellmann + generalized Morse (Deng–Fan) | Hellmann, Yukawa, Coulomb, Deng-Fan, Morse |
| Hellmann–Kratzer potential | Hellmann, Kratzer |
| Hulthén–Hellmann potential | Hulthén, Hellmann, Yukawa, Coulomb |
| Hellmann–Frost–Musulin potential | Hellmann, Yukawa, Coulomb, Frost–Musulin |
| Manning–Rosen plus Hellmann potential | Manning–Rosen, Hellmann |
| Varshni–Hellmann potential | Varshni, Hellmann |
| Eckart–Hellmann potential | Eckart, Hellmann |
| Inversely quadratic Yukawa plus inversely quadratic Hellmann | quadratic Yukawa, quadratic Hellmann |
| Ring-shaped Hellmann potential | Hellmann (non-central extension) |
| Hellmann potential with three tensor interactions (Dirac equation) | Hellmann (non-relativistic limit) |

The strategy in essentially all these papers is the same: write down the composite potential, apply a suitable centrifugal-term approximation, cast the radial equation into NU (or parametric-NU/AIM/SUSY) canonical form, extract $E_{n\ell}$, and then set the "extra" potential parameters to zero one at a time to recover each constituent potential's known energy spectrum as a check.

---

## 5. Applications

1. **Atomic and molecular physics** — bound-state normalizations and energy levels of neutral atoms and diatomic molecules (H₂, LiH, HCl, CO, NiC, CuLi, TiH, VH, TiC, CrH, I₂, etc.), often using experimentally fitted spectroscopic (Rydberg–Klein–Rees or Dunham) parameters mapped onto the Hellmann-potential parameters $A$, $B$, $\delta$.
2. **Nuclear and high-energy physics** — used as a screened effective potential in heavy-quarkonium and meson mass-spectrum calculations, analogous to the role played by the Cornell potential.
3. **Thermodynamic properties** — once $E_{n\ell}$ is known in closed form, the vibrational partition function $Z(\beta)$ is constructed (via direct summation or an Euler–Maclaurin/Poisson-resummation approximation) and used to derive the mean energy $U$, free energy $F$, entropy $S$, and specific heat $C$ of the corresponding diatomic system.
4. **Expectation values via the Hellmann–Feynman theorem** — used to compute $\langle r^{-1}\rangle$, $\langle r^{-2}\rangle$, $\langle T\rangle$ (kinetic energy), and $\langle p^2\rangle$ for various diatomic molecules directly from the parametric dependence of $E_{n\ell}$, without needing the explicit wavefunction.
5. **Information-theoretic measures** — Shannon, Tsallis, and Rényi entropies in position and momentum space, and their dependence on the angular momentum quantum number and potential parameters, computed from the SUSY-derived eigenfunctions.
6. **Scattering-state analysis** — phase shifts and scattering-state solutions for Hellmann-type and Hellmann-superposed potentials.

---

## 6. Cross-Method Comparison

A consistent qualitative picture emerges across the literature:

- All approximate analytic methods (NU, parametric NU, AIM, SUSYQM, EQR, formula method) agree closely with each other and with the essentially numerically exact pseudospectral results of Roy, Jalbout & Proynov **in the weak-screening regime** ($\delta$ small relative to the Coulomb strength) and for **low-lying states**.
- Agreement degrades for **large screening parameter $\delta$** and for **higher $n$, $\ell$**, because the Greene–Aldrich/Pekeris-type substitution for the centrifugal term becomes progressively less accurate as $\delta r$ departs from the small-argument regime the approximation assumes.
- The **AIM** and **pseudospectral** methods are generally regarded as the most reliable "exact within the model" benchmarks, since AIM in principle requires no centrifugal approximation beyond what is unavoidable, and the pseudospectral method requires none at all.
- **Perturbative** treatments are the least accurate outside the weak-coupling/weak-screening regime but remain useful for establishing the correct Coulomb limit analytically.

---

## 7. Open Issues and Outlook

- There remains no **exact, closed-form** solution of the Hellmann-potential radial equation for arbitrary $\ell \neq 0$; all "exact" analytic results in the literature are exact solutions of an *approximated* equation (via the centrifugal-term substitution).
- Extending high-accuracy benchmark calculations (of the Roy–Jalbout–Proynov pseudospectral type) to a wider parameter range, and to the many Hellmann-superposed potentials now in the literature, would help quantify precisely where each approximate method breaks down.
- The **fractional-derivative** and **topological-defect** generalizations are a comparatively recent and still-active direction, with open questions about the physical interpretation of the fractional order parameter.
- Continued interest in **machine-learning** and other purely numerical eigenvalue solvers for screened Coulomb-type potentials may eventually supersede some of the approximate analytic techniques for high-precision applications, while the analytic methods retain pedagogical and parameter-scaling value.

---

## 8. Bibliography

### 8.1 Foundational / origin of the potential

1. Hellmann, H. (1935). *A New Approximation Method in the Problem of Many Electrons.* J. Chem. Phys. 3, 61.
2. Hellmann, H., Kassatotschkin, W. (1936). *Metallic Binding According to the Combined Approximation Procedure.* J. Chem. Phys. 4, 324.

### 8.2 Perturbative and early treatments

3. Ikhdair, S.M., Sever, R. (2007). *A perturbative treatment for the bound states of the Hellmann potential.* J. Mol. Struct.: THEOCHEM 809(1–3), 103–113.

### 8.3 Nikiforov–Uvarov / parametric NU method

4. Hamzavi, M., Thylwe, K.-E., Rajabi, A.A. (2013). *Approximate Bound States Solution of the Hellmann Potential.* Commun. Theor. Phys. 60(1), 1–8.
5. Onate, C.A., Onyeaju, M.C., Ikot, A.N., Ebomwonyi, O. (2017). *Eigensolutions of the Schrödinger equation with a class of Yukawa potential via a supersymmetric approach.* (related NU/SUSY comparison work).
6. Ikot, A.N. et al. *Any ℓ-states solutions of the Schrödinger equation interacting with Hellmann–generalized Morse potential model.* Karbala Int. J. Mod. Sci. (ScienceDirect).
7. Onate, C.A. et al. *Any ℓ-state solutions of the Schrödinger equation interacting with Hellmann–Kratzer potential model.*
8. Okon, I.B. et al. (2017). *Approximate Solutions of Schrödinger Equation with Some Diatomic Molecular Interactions Using Nikiforov–Uvarov Method.* Adv. High Energy Phys. 2017, 9671816.
9. Ikot, A.N., Hassanabadi, H., Abbey, T.M. (2015). *Spin and Pseudospin Symmetries of Hellmann Potential with Three Tensor Interactions Using Nikiforov–Uvarov Method.* Commun. Theor. Phys. 64(6), 637.
10. *Analytical solutions of the Dirac equation under Hellmann–Frost–Musulin potential* (spin/pseudospin symmetry, NU method).
11. Louis, H., Ita, B.I., et al. *Approximate solution of the Schrödinger equation with Manning–Rosen plus Hellmann potential and its thermodynamic properties using the proper quantization rule.*

### 8.4 Asymptotic Iteration Method (AIM)

12. *Arbitrary ℓ-state solution of the Hellmann potential* (asymptotic iteration method; convergence study, comparison with SUSY-perturbation, perturbation, and variational methods).
13. Öztemel, Ö., Olğar, E. (2018). *An alternative solution of Diatomic Molecules.* (AIM for $r^{-1}$, $r^{-2}$-type potentials: Mie, Kratzer–Fues, Coulomb, Pseudoharmonic). arXiv:1409.6871.
14. Karakoc, M., Boztosun, I. *Asymptotic iteration method solution of radial Schrödinger equation for Yukawa-type potentials.*

### 8.5 Supersymmetric quantum mechanics and entropy

15. Onate, C.A., Onyeaju, M.C., Ikot, A.N., et al. (2017). *Eigen solutions and entropic system for Hellmann potential in the presence of the Schrödinger equation.* Eur. Phys. J. Plus 132, 462.

### 8.6 Exact / proper quantization rule

16. Ikhdair, S.M., Sever, R. (2007). *Exact quantization rule and its applications to physical potentials.*
17. Ikhdair, S.M., Sever, R. (2009). *Exact quantization rule to the Kratzer-type potentials: an application to the diatomic molecules.* J. Math. Chem. 45, 1137.
18. Ikhdair, S.M. (2011). *Quantization rule solution to the Hulthén potential in arbitrary dimension by a new approximate scheme for the centrifugal term.* arXiv:1104.0302.

### 8.7 Formula method / NUFA / other unified approaches

19. Falaye, B.J., Ikhdair, S.M., Hamzavi, M. (2015). *Formula Method for Bound State Problems.* Few-Body Syst. 56, 63–78.
20. Ikot, A.N. et al. *Nikiforov–Uvarov Functional Analysis (NUFA) method applications.*

### 8.8 WKB and semiclassical treatments

21. *WKB Solutions for Inversely Quadratic Yukawa plus Inversely Quadratic Hellmann Potential.*
22. Gönül, B. et al. *A new approximation scheme to obtain analytic expressions for the bound state energies and eigenfunctions of Yukawa-like potentials.*

### 8.9 High-precision numerical benchmarks

23. Roy, A.K., Jalbout, A.F., Proynov, E.I. (2013). *Accurate calculation of the bound states of Hellmann potential.* arXiv:1307.2983.

### 8.10 Combined / generalized Hellmann-type potentials

24. Tazimi, N. *Determination of the Energy Eigenvalues of the Varshni–Hellmann Potential.* arXiv:2401.11151.
25. *Application of Eckart–Hellmann potential to study selected diatomic molecules.* arXiv:2204.04264.
26. Ushie, P.O. et al. (2021). *Eigen solutions of the Schrödinger equation in the presence of ring-shaped Hellmann potential.* J. Sci. Eng. Res. 8(5), 132–148.
27. *Expectation Values of Some Diatomic Molecules With Hellmann–Feynman Theorem via Conventional Nikiforov–Uvarov Method.* arXiv:1702.03923.
28. *Expectation Values of Some Diatomic Molecules with Deng-Fan Potential Using Hellmann–Feynman Theorem* (comparative Hellmann/Yukawa special cases).

### 8.11 Relativistic (Dirac / Klein–Gordon) extensions

29. Ikot, A.N. et al. *Solution of Klein–Gordon Equation for Some Diatomic Molecules with New Generalized Morse-like Potential Using SUSYQM* (Hellmann/Yukawa/Coulomb reductions).
30. *Analytical solutions of the Dirac equation under Hellmann–Frost–Musulin potential* (see item 10).

### 8.12 Fractional and topological-defect generalizations (recent)

31. Okorie, U.S., Alrebdi, H.I., Ikot, A.N., Rampho, G.J., et al. (2025). *Eigensolutions of generalized fractional Schrödinger equation with Hulthén–Hellmann potential and topological defects.* Sci. Rep. 15, 23481.

### 8.13 Related Yukawa/Hulthén benchmark studies (background/comparison)

32. *A semirelativistic treatment of spinless particles subject to the Yukawa potential with arbitrary angular momenta.* arXiv:1203.1747.
33. Oyewumi, K.J., Oluwadare, O.J. *The scattering phase shifts of the Hulthén-type potential plus Yukawa potential.* arXiv:1604.03618.

---

*Note: Several entries above are drawn from secondary citation contexts (reference lists of related papers) rather than from direct examination of the primary source; volume/page details should be verified against the original journal record before formal citation.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive review about the evaluation of eigenvalues of Schrödinger equation with Hellmann potential. Also provide a list of publications related to the problem. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
