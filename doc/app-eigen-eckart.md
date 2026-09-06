# Applications of Eigenvalues and Eigenfunctions of the Eckart Potential: A Review

## 1. Introduction

The Eckart potential, introduced by Carl Eckart in 1930 in the context of electron penetration through a potential barrier, is one of the classic exactly (or quasi-exactly) solvable potentials of quantum mechanics. Two related forms are used in the literature:

- **The Eckart barrier** (open, scattering problem), typically written as
$$
V(x) = \frac{A e^{x/a}}{1+e^{x/a}} + \frac{B e^{x/a}}{\left(1+e^{x/a}\right)^{2}},
$$
or in the symmetric case $V(x) = V_0 \,\mathrm{sech}^2(x/a)$.

- **The Eckart well/potential** (bound-state problem), typically written in hyperbolic form as
$$
V(r) = A(A-1)\,\mathrm{csch}^2 r - 2B\,\coth r, \qquad 0<r<\infty,
$$
or, in molecular-physics form, as a combination of $\mathrm{sech}^2$ and $\tanh$ terms used to model diatomic interaction curves.

Because the corresponding Schrödinger, Klein–Gordon, and Dirac equations can be reduced to hypergeometric-type or Jacobi-polynomial equations, the Eckart potential admits closed-form (or accurately approximate, once an approximation for the centrifugal term is introduced) energy eigenvalues $E_n$ and eigenfunctions $\psi_n$. This analytic tractability has made it a recurring workhorse across several distinct areas of physics and chemistry. This review organizes those applications into major thematic groups, summarizing what the eigenvalues/eigenfunctions are used for in each, and lists representative publications for each group.

---

## 2. Molecular and Chemical Physics: Vibration–Rotation Spectra of Diatomic Molecules

The bound-state (well) form of the Eckart potential is used as an anharmonic model for the internuclear interaction in diatomic molecules, playing a role similar to the Morse or Kratzer potentials.

**How the eigenvalues/eigenfunctions are used:**
- Solving the radial Schrödinger equation (usually via the Nikiforov–Uvarov (NU) method, asymptotic iteration method (AIM), SUSYQM, or the parametric NU method) with the Eckart potential — after approximating the centrifugal $\ell(\ell+1)/r^2$ term (Pekeris-type or Greene–Aldrich approximations) — yields analytic ro-vibrational energy levels $E_{n\ell}$.
- These energy levels are fitted/compared against spectroscopic data for real diatomic molecules (e.g., H₂, HCl, CO, N₂, LiH, ScH, ScN, ScF) to test the potential's accuracy relative to the Morse potential and to extract spectroscopic constants.
- The normalized eigenfunctions are used to compute expectation values, transition-related quantities, and to build the vibrational partition function.
- Extensions combine the Eckart potential with other terms (Hellmann, Deng–Fan, Varshni) to improve agreement with experimental dissociation energies and equilibrium bond lengths.

**Key publications:**
- C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Phys. Rev.* **35**, 1303 (1930).
- B. J. Falaye, "Any ℓ-state solutions of the Eckart potential via asymptotic iteration method," *Central European Journal of Physics* **10**, 960 (2012).
- K. J. Oyewumi et al., "Bound state solutions of the Deng–Fan molecular potential with the Pekeris-type approximation using the Nikiforov–Uvarov method," *J. Math. Chem.* **51**, 976 (2013).
- Application of Eckart–Hellmann potential to selected diatomic molecules using NUFA method, *arXiv:2204.04264* (2022).
- G. Valencia-Ortega & L. A. Arias-Hernandez, "Thermodynamic properties of diatomic molecules systems under anharmonic Eckart potential," *arXiv:1708.00926* (2017).
- Theoretical study of the Varshni–Eckart potential model in cosmic-string topological-defect geometry for selected diatomic molecules (E. S. William, S. O. Inyang, O. O. Ekerenam, A. N. Ikot et al.).
- Thermal Properties of Deng–Fan–Eckart Potential model using Poisson Summation Approach, *arXiv:2009.09292*.

---

## 3. Thermodynamic Properties of Molecular/Quantum Systems

Once the Eckart-potential energy spectrum $E_n$ is known, the vibrational partition function
$$
Z(\beta) = \sum_{n=0}^{n_{\max}} e^{-\beta E_n}
$$
(often evaluated in closed form via the Poisson summation formula or an $SO(2,1)$ algebraic treatment) allows derivation of standard thermodynamic quantities.

**How the eigenvalues are used:**
- The discrete eigenvalue spectrum of the Eckart (or Eckart-hybrid, e.g., Deng–Fan–Eckart, Eckart–Hellmann) potential feeds directly into $Z(\beta)$.
- From $Z(\beta)$ one derives the vibrational mean energy $U$, Helmholtz free energy $F$, entropy $S$, and specific heat $C$ as functions of temperature, for gaseous diatomic systems (H₂, N₂, CO, Cl₂, Na₂, Li₂, HCl).
- Comparative studies contrast Eckart-derived thermodynamic functions against those from the Morse potential and other exponential-type potentials to test high-temperature limits and molecular-parameter sensitivity.

**Key publications:**
- G. Valencia-Ortega & L. A. Arias-Hernandez, "Thermodynamic properties of diatomic molecule systems under SO(2,1)-anharmonic Eckart potential," (2018).
- Thermal Properties of Deng–Fan–Eckart Potential model using Poisson Summation Approach, *arXiv:2009.09292*.
- U. S. Okorie, A. N. Ikot, E. O. Chukwuocha, "Thermodynamic Properties of Improved Deformed Exponential-type Potential (IDEP) for some Diatomic Molecules," *arXiv:2001.04799*.
- A. N. Ikot, W. Azogor, U. S. Okorie et al., "Exact and Poisson Summation thermodynamic properties for diatomic molecules with shifted Tietz potential," *Indian J. Phys.* **93**, 1179 (2019) (methodologically parallel treatment, frequently cited alongside Eckart-type studies).
- F. M. Fernández, "On the screened Kratzer potential and its variants," *arXiv:2405.19451* (2024) — critical discussion of parameter-fitting pitfalls relevant to Eckart-type thermodynamic modeling.

---

## 4. Quantum Tunneling and Chemical Reaction Rate Theory (Eckart Barrier)

This is historically the most important application of the Eckart potential: the barrier form is the standard analytically solvable model for the reaction-path potential energy surface in transition-state theory (TST).

**How the eigenvalues/eigenfunctions (scattering states) are used:**
- The Eckart barrier admits an **exact analytic transmission (tunneling) probability** $G(\varepsilon)$ as a function of incident energy, derived from the continuum (scattering) solutions of the Schrödinger equation for this potential.
- This closed-form transmission coefficient is used to compute **tunneling corrections** $\kappa(T)$ to classical/TST reaction rate constants, which is essential for accurately predicting rates of hydrogen-atom transfer and other light-particle transfer reactions, including kinetic isotope effects (H vs. D transfer).
- The (a)symmetric Eckart barrier is used as a benchmark potential against which more sophisticated tunneling approximations (Wigner correction, WKB, SCTST, quantum instanton method) are validated, because the Eckart barrier is one of the few barrier shapes with an exact quantum solution.
- Multi-humped/unsymmetrical Eckart barriers model reaction paths with intermediate wells, capturing resonance tunneling effects in more complex reaction coordinates.
- Low-energy/ultracold limits of Eckart-barrier tunneling are used to model rate coefficients for barrierless or near-barrierless atom–atom and atom–molecule reactions (e.g., F + H₂) at ultracold temperatures.

**Key publications:**
- C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Phys. Rev.* **35**, 1303 (1930).
- H. S. Johnston & D. Rapp, "Large Tunnelling Corrections in Chemical Reaction Rates," *J. Am. Chem. Soc.* **83**, 1 (1961) (classic unsymmetrical Eckart tunneling-correction paper; cited via OSTI record on "Tunneling corrections for unsymmetrical Eckart potential energy barriers," *J. Phys. Chem.* **66** (1962)).
- W. H. Miller, "Quantum mechanical transition state theory and a new semiclassical model for reaction rate constants," *J. Chem. Phys.* **61**, 1823 (1974) (uses Eckart barrier as an exactly solvable test case).
- "Consequences of resonance tunnelling in chemical kinetics" — multi-centered unsymmetrical Eckart potential barrier study of resonance tunneling in bimolecular atom-transfer reactions.
- E. Pollak, "The power-law TST reaction rate coefficient with tunneling correction," *arXiv:1407.0012*.
- R. C. Forrey, "Low-energy limit for tunnelling subject to an Eckart potential barrier," *Molecular Physics* **108**, 7–9 (2010).
- "Activation volume and quantum tunneling in the hydrogen transfer reaction between methyl radical and methane," *J. Chem. Phys.* **160**, 104103 (2024) — composite Eckart potential energy surfaces for H-transfer under pressure.
- P. Goel & J. F. Stanton, "Model system studies beyond symmetric Eckart barrier," *J. Chem. Phys.* **149**, 134109 (2018) — asymmetric Eckart barrier as benchmark for VPT-SCTST tunneling methods.
- "Direct evaluation of the temperature dependence of the rate constant based on the quantum instanton approximation," *arXiv:1004.0201* — Eckart barrier as an exactly solvable test system for the quantum instanton method.

---

## 5. Condensed Matter and Mesoscopic Physics: Electron/Particle Transmission

Because the Eckart barrier was originally derived to describe electron penetration through a potential step/barrier, it continues to serve as a tractable model in condensed-matter and cold-atom contexts.

**How the eigenvalues/eigenfunctions are used:**
- Its exact scattering (transmission/reflection amplitude) solutions model electron transmission through metal-surface potential steps and through Coulomb-like barriers in nuclear/atomic collision problems.
- In cold-atom/superfluid physics, the (symmetric) Eckart potential $V(x)=V_0\,\mathrm{sech}^2(x/d)$ is used as an analytically tractable approximation to Gaussian optical-barrier profiles, enabling closed-form transmission amplitudes for bosonic pairs in Josephson-junction-type superfluid setups.
- Time-dependent ("fast-forward") control of tunneling states uses the exact Eckart transmission solution as the reference against which adiabatic/shortcut-to-adiabaticity protocols are validated.

**Key publications:**
- C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Phys. Rev.* **35**, 1303 (1930).
- "Strongly correlated superfluid order parameters from dc Josephson supercurrents," *arXiv:1908.09696* — Eckart barrier as an analytic approximation to a Gaussian barrier for computing bosonic-pair transmission.
- "Fast forward of adiabatic control of tunneling states," *arXiv:1706.03966* — Eckart-type potential used for adiabatically tunable tunneling barriers.

---

## 6. Relativistic Quantum Mechanics: Klein–Gordon and Dirac Equations

The Eckart potential (and Eckart–Hellmann/Eckart–Manning–Rosen hybrids) has been widely used as a scalar and/or vector coupling potential in relativistic wave equations, particularly to study spin and pseudospin symmetry.

**How the eigenvalues/eigenfunctions are used:**
- Solving the Klein–Gordon equation with an Eckart-type scalar/vector potential yields relativistic bound-state energies and radial wavefunctions used to study nuclear and hadronic bound systems, with a well-defined non-relativistic limit that reproduces the Schrödinger-equation results.
- Solving the Dirac equation with equal (or related) scalar and vector Eckart potentials under **spin symmetry** and **pseudospin symmetry** limits (via the parametric Nikiforov–Uvarov method or SUSYQM) produces relativistic energy spectra and spinor wavefunctions, relevant to nuclear shell-model degeneracies and to hypernuclei.
- These relativistic solutions are also the starting point for the information-theoretic and thermodynamic studies described in Sections 7 and 3.

**Key publications:**
- W. A. Yahya, K. J. Oyewumi, C. O. Akoshile, T. T. Ibrahim, "Bound state solutions of the relativistic Dirac equation with equal scalar and vector Eckart potentials using the Nikiforov–Uvarov method," *African Review of Physics* **6**, 211 (2011).
- Solving the s-wave Dirac equation for the Eckart potential with spin and pseudospin symmetry using SUSYQM and the function analysis method (cited in AIM/Eckart review literature, *ResearchGate* 257907613).
- "Application of Eckart-Hellmann potential to study selected diatomic molecules using Nikiforov-Uvarov-Functional analysis method" (Klein–Gordon treatment), *arXiv:2204.04264*.
- Assimiou M. Yarou, Daniel T. Sabi, Anselme F. Dossa, G. Y. H. Avossevou, "Exact Solution of the Dirac–Weyl Equation in Graphene under Magnetic Field Applied to Molecules" — Dirac electron bound states for graphene with Eckart-plus-Hulthén and Rosen–Morse-plus-Woods–Saxon potentials, applied to HCl, ScH, ScN, ScF.

---

## 7. Quantum Information-Theoretic Measures: Shannon Entropy, Fisher Information, Complexity

A more recent line of applications uses the closed-form Eckart eigenfunctions to compute information-theoretic diagnostics of the resulting quantum probability densities.

**How the eigenvalues/eigenfunctions are used:**
- The position-space probability density $|\psi_n(r)|^2$ built from Eckart (or Eckart–Manning–Rosen, Eckart–Hellmann) eigenfunctions is used to compute **Shannon entropy** (position and momentum space), testing the Beckner–Bialynicki-Birula–Mycielski (BBM) entropic uncertainty inequality.
- The same densities give the **Fisher information** and **Onicescu information energy**, used to test the Stam–Cramér–Rao inequality and to quantify the localization/delocalization of quantum states as a function of quantum number and potential parameters.
- Combinations of Shannon entropy with Fisher information or with information energy define **statistical complexity measures** (Fisher–Shannon complexity, LMC-type complexity), used to characterize how "ordered" vs. "disordered" a bound or resonance state is.
- These calculations have been extended to the relativistic (Klein–Gordon) Eckart-type problem, connecting Section 6 and Section 7.

**Key publications:**
- J. B. Ojonubah, "Eigen solutions, Shannon entropy and Fisher information under the Eckart Manning–Rosen potential model," *Journal of the Korean Physical Society* **70**, 339 (2017).
- "Entropic system in the relativistic Klein-Gordon Particle," *Journal of the Nigerian Society of Physical Sciences* (2021) — discusses Shannon entropy/Fisher information complexity measures in Eckart-type relativistic contexts and cites the Eckart–Manning–Rosen entropy work directly.
- C. A. Onate & J. O. A. Idiodi, "Fisher Information and Complexity Measure of Generalized Morse Potential Model," *Commun. Theor. Phys.* **66**, 275 (2016) (methodological companion, same research cluster).
- J. S. Dehesa, A. Martinez-Finkelshtein, J. Sánchez-Ruiz, "Quantum information entropies and orthogonal polynomials," *J. Comput. Appl. Math.* **133**, 23 (2001) (foundational method used in Eckart-type entropy calculations).

---

## 8. Mathematical Physics: Exact Solvability, Shape Invariance, and SUSY QM

The Eckart potential is a canonical example in the theory of exactly solvable and shape-invariant potentials, and a testbed for extensions using supersymmetric quantum mechanics (SUSY QM) and exceptional orthogonal polynomials.

**How the eigenvalues/eigenfunctions are used:**
- The Eckart potential is one of the standard shape-invariant potentials (alongside Coulomb, harmonic oscillator, Morse, Pöschl–Teller) for which SUSY QM gives the full bound-state spectrum and eigenfunctions algebraically via the factorization method and ladder operators.
- Quasi-exactly solvable (QES) generalizations of the Eckart potential are constructed by mapping its eigenvalue problem onto orthogonal-polynomial recursion relations, connecting it to QES Hultén, Rosen–Morse, and Coulomb potentials.
- "Rational extensions" of the Eckart potential — obtained via first-order SUSY QM using seed solutions built from Jacobi-polynomial eigenfunctions — produce new exactly solvable potentials that are isospectral (or nearly isospectral) to the conventional Eckart potential; their scattering amplitudes have also been derived analytically.
- The Eckart potential's shape invariance underlies its use in exactness proofs for approximate quantization methods, such as the supersymmetric WKB (SWKB) approximation.
- The Hulthén potential is recognized as a special/limiting case of the Eckart potential within this shape-invariant framework, linking the two potentials' solution theories.

**Key publications:**
- L. E. Gendenshtein, "Derivation of exact spectra of the Schrödinger equation by means of supersymmetry," *JETP Lett.* **38**, 356 (1983) (origin of shape invariance concept, foundational for all Eckart SUSY work).
- A. Khare & U. P. Sukhatme, "New Shape Invariant Potentials in Supersymmetric Quantum Mechanics," *arXiv:hep-th/9212147*.
- Y.-F. Cheng & T.-Q. Dai, "A Unified Treatment of Quasi-Exactly Solvable Potentials II: Eckart Type Potentials," *arXiv:math-ph/0505004*.
- C. Quesne, "Novel Enlarged Shape Invariance Property and Exactly Solvable Rational Extensions of the Rosen–Morse II and Eckart Potentials," *SIGMA* **8**, 080 (2012).
- "The Scattering amplitude for Rationally extended shape invariant Eckart potentials," *arXiv:1309.6755*.
- C. Quesne, "Solvable rational potentials and exceptional orthogonal polynomials in supersymmetric quantum mechanics," *SIGMA* **5**, 084 (2009).
- E. Drigo Filho, "Ladder operators for subtle hidden shape invariant potentials," *arXiv:hep-th/0405013* (relates Hulthén potential to the Eckart potential as a special case).

---

## 9. Higher-Dimensional and External-Field Extensions

More recent work generalizes the Eckart eigenvalue problem to $D$-dimensional space and to systems in external electromagnetic/topological-defect backgrounds, extending its domain of application in condensed matter and molecular physics.

**How the eigenvalues/eigenfunctions are used:**
- $D$-dimensional analytic solutions (via the NU method with improved centrifugal-term approximations) generalize the standard 3D Eckart results and test the potential's behavior and accuracy across dimensions.
- The Eckart potential combined with Aharonov–Bohm flux and external magnetic fields is solved to study **magneto-transport and thermal properties of 2D electron systems**, relevant to mesoscopic/nanostructure physics.
- Eckart-type potentials embedded in **cosmic-string topological-defect geometries** are solved to study how spacetime topology modifies bound-state spectra of diatomic-molecule analogs.

**Key publications:**
- "Analytical solution of D dimensional Schrödinger equation for Eckart potential with a new improved approximation in centrifugal term," *ScienceDirect* (2021).
- "Approximate Solutions of the Schrödinger Equation for the Eckart Potential and Its Parity-Time-Symmetric Version Including Centrifugal Term" (NU method, PT-symmetric Eckart potential).
- "Investigating the magneto-transport and thermal properties of 2D electron systems under the influence of the Aharonov–Bohm field and Eckart potential interaction," *ScienceDirect* (2023).
- E. S. William, S. O. Inyang, O. O. Ekerenam et al., "Theoretic analysis of non-relativistic equation with the Varshni-Eckart potential model in cosmic string topological defects geometry and external fields for the selected diatomic molecules."

---

## 10. Summary Table

| Application Domain | Role of Eigenvalues/Eigenfunctions | Section |
|---|---|---|
| Diatomic molecular spectroscopy | Fit/predict ro-vibrational energy levels | 2 |
| Statistical thermodynamics | Build partition function → U, F, S, C | 3 |
| Chemical kinetics / tunneling | Exact transmission probability → rate corrections | 4 |
| Condensed matter / mesoscopics | Electron/atom transmission through barriers | 5 |
| Relativistic quantum mechanics | Klein–Gordon/Dirac bound states, spin symmetry | 6 |
| Quantum information theory | Shannon entropy, Fisher information, complexity | 7 |
| Mathematical physics / SUSY QM | Shape invariance, QES extensions, rational extensions | 8 |
| Higher-D / external fields | D-dimensional, magneto-transport, topological defects | 9 |

---

## 11. Consolidated Reference List

1. C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Phys. Rev.* **35**, 1303 (1930).
2. H. S. Johnston & D. Rapp, "Large Tunnelling Corrections in Chemical Reaction Rates," *J. Am. Chem. Soc.* **83**, 1 (1961).
3. "Tunneling corrections for unsymmetrical Eckart potential energy barriers," *J. Phys. Chem.* **66** (1962), OSTI ID 4803276.
4. W. H. Miller, "Quantum mechanical transition state theory and a new semiclassical model for reaction rate constants," *J. Chem. Phys.* **61**, 1823 (1974).
5. L. E. Gendenshtein, "Derivation of exact spectra of the Schrödinger equation by means of supersymmetry," *JETP Lett.* **38**, 356 (1983).
6. A. Khare & U. P. Sukhatme, "New Shape Invariant Potentials in Supersymmetric Quantum Mechanics," *arXiv:hep-th/9212147*.
7. B. J. Falaye, "Any ℓ-state solutions of the Eckart potential via asymptotic iteration method," *Central European Journal of Physics* **10**, 960 (2012).
8. W. A. Yahya, K. J. Oyewumi, C. O. Akoshile, T. T. Ibrahim, "Bound state solutions of the relativistic Dirac equation with equal scalar and vector Eckart potentials using the Nikiforov–Uvarov method," *African Review of Physics* **6**, 211 (2011).
9. Y.-F. Cheng & T.-Q. Dai, "A Unified Treatment of Quasi-Exactly Solvable Potentials II: Eckart Type Potentials," *arXiv:math-ph/0505004*.
10. C. Quesne, "Solvable rational potentials and exceptional orthogonal polynomials in supersymmetric quantum mechanics," *SIGMA* **5**, 084 (2009).
11. C. Quesne, "Novel Enlarged Shape Invariance Property and Exactly Solvable Rational Extensions of the Rosen–Morse II and Eckart Potentials," *SIGMA* **8**, 080 (2012).
12. "The Scattering amplitude for Rationally extended shape invariant Eckart potentials," *arXiv:1309.6755*.
13. K. J. Oyewumi, O. J. Oluwadare, K. D. Sen, O. A. Babalola, "Bound state solutions of the Deng-Fan molecular potential with the Pekeris-type approximation using the Nikiforov–Uvarov method," *J. Math. Chem.* **51**, 976 (2013).
14. "Application of Eckart-Hellmann potential to study selected diatomic molecules using Nikiforov-Uvarov-Functional Analysis (NUFA) method," *arXiv:2204.04264* (2022).
15. G. Valencia-Ortega & L. A. Arias-Hernandez, "Thermodynamic properties of diatomic molecules systems under anharmonic Eckart potential," *arXiv:1708.00926* (2017).
16. G. Valencia-Ortega & L. A. Arias-Hernandez, "Thermodynamic properties of diatomic molecule systems under SO(2,1)-anharmonic Eckart potential" (2018).
17. "Thermal Properties of Deng-Fan-Eckart Potential model using Poisson Summation Approach," *arXiv:2009.09292*.
18. U. S. Okorie, A. N. Ikot, E. O. Chukwuocha, "Thermodynamic Properties of Improved Deformed Exponential-type Potential (IDEP) for some Diatomic Molecules," *arXiv:2001.04799*.
19. F. M. Fernández, "On the screened Kratzer potential and its variants," *arXiv:2405.19451* (2024).
20. "Analytical solution of D dimensional Schrödinger equation for Eckart potential with a new improved approximation in centrifugal term," *ScienceDirect* (2021).
21. "Approximate Solutions of the Schrödinger Equation for the Eckart Potential and Its Parity-Time-Symmetric Version Including Centrifugal Term."
22. "Investigating the magneto-transport and thermal properties of 2D electron systems under the influence of the Aharonov–Bohm field and Eckart potential interaction," *ScienceDirect* (2023).
23. E. S. William, S. O. Inyang, O. O. Ekerenam et al., "Theoretic analysis of non-relativistic equation with the Varshni-Eckart potential model in cosmic string topological defects geometry and external fields for the selected diatomic molecules."
24. E. Pollak, "The power-law TST reaction rate coefficient with tunneling correction," *arXiv:1407.0012*.
25. R. C. Forrey, "Low-energy limit for tunnelling subject to an Eckart potential barrier," *Molecular Physics* **108**, 7–9 (2010).
26. "Activation volume and quantum tunneling in the hydrogen transfer reaction between methyl radical and methane: A first computational study," *J. Chem. Phys.* **160**, 104103 (2024).
27. P. Goel & J. F. Stanton, "Model system studies beyond symmetric Eckart barrier," *J. Chem. Phys.* **149**, 134109 (2018).
28. "Consequences of resonance tunnelling in chemical kinetics" (multi-centered unsymmetrical Eckart potential barrier).
29. "Direct evaluation of the temperature dependence of the rate constant based on the quantum instanton approximation," *arXiv:1004.0201*.
30. "Strongly correlated superfluid order parameters from dc Josephson supercurrents," *arXiv:1908.09696*.
31. "Fast forward of adiabatic control of tunneling states," *arXiv:1706.03966*.
32. J. B. Ojonubah, "Eigen solutions, Shannon entropy and Fisher information under the Eckart Manning-Rosen potential model," *Journal of the Korean Physical Society* **70**, 339 (2017).
33. "Entropic system in the relativistic Klein-Gordon Particle," *Journal of the Nigerian Society of Physical Sciences* (2021).
34. C. A. Onate & J. O. A. Idiodi, "Fisher Information and Complexity Measure of Generalized Morse Potential Model," *Commun. Theor. Phys.* **66**, 275 (2016).
35. J. S. Dehesa, A. Martinez-Finkelshtein, J. Sánchez-Ruiz, "Quantum information entropies and orthogonal polynomials," *J. Comput. Appl. Math.* **133**, 23 (2001).
36. Assimiou M. Yarou, Daniel T. Sabi, Anselme F. Dossa, G. Y. H. Avossevou, "Exact Solution of the Dirac-Weyl Equation in Graphene under Magnetic Field Applied to Molecules."
37. E. Drigo Filho, "Ladder operators for subtle hidden shape invariant potentials," *arXiv:hep-th/0405013*.

---

*Note: Several sources above (arXiv preprints, ResearchGate listings) were accessed via web search; where a formal journal citation could be identified it is given, otherwise the preprint/repository identifier is provided for traceability.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of eigenvalues and eigenfunctions of the Eckart potential. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
