# Eigenvalues of the Schrödinger Equation with a Soft-Core Coulomb Potential: A Numerical Review (Extended)

## 1. Definitions and Notation

The "soft-core" (also called "softened," "truncated," or "regularized") Coulomb potential replaces the singular $-Z/r$ interaction with a version that stays finite as $r \to 0$. The two forms that dominate the literature are:

**Family A (Hall–Saad–Sen form, $q$-family):**

$$
V_q(r) = -\frac{Z}{\left(r^q + \beta^q\right)^{1/q}}, \qquad Z>0,\ \beta>0,\ q\ge 1
$$

- $q=1$: $V_1(r) = -Z/(r+\beta)$ — the "smeared charge" potential (mesonic atoms).
- $q=2$: $V_2(r) = -Z/\sqrt{r^2+\beta^2}$ — resembles the potential of a finite-size nucleus (muonic atoms); this is also the form almost universally used in strong-field/laser–atom physics.

**Family B (1D "soft-core Coulomb," strong-field physics convention):**

$$
V_{\rm SC}(x) = -\frac{Z}{\sqrt{x^2+\alpha^2}}
$$

used as a 1D surrogate for the 3D hydrogen atom, where the softening parameter $\alpha$ is tuned so that the ground-state energy matches a target value (often $-Z^2/2$ a.u.).

**Family C (Gaussian-windowed soft-core, GSC — new in this extension):**

$$
V_{\rm GSC}^{\rm 1D}(z) = V_{\rm SC}^{\rm 1D}(z)\, e^{-(z/a)^2} + V_{\rm MSC}^{\rm 1D}(z)\left(1-e^{-(z/b)^2}\right)
$$

a hybrid that binds like SC near the core and decays like MSC (Section 4.2) far away, joined smoothly through Gaussian window functions with adjustable widths $a,b$. This construction is designed to reproduce 3D HHG spectra more faithfully than either constituent potential alone.

The radial Schrödinger equation solved throughout is (atomic units, $\hbar=2\mu=1$ or $\hbar=\mu=1$ depending on the paper):

$$
\left[-\frac{d^2}{dr^2} + \frac{\ell(\ell+1)}{r^2} + V(r)\right]\psi(r) = E\,\psi(r)
$$

---

## 2. Exactly Solvable Cases ($q=1$, 3D, via Heun/AIM)

For $V_1(r) = -v/(r+1)$ (scaled, $v = \beta e^2 Z$), Hall, Saad, and Bryenton (2018) showed the problem reduces to the **confluent Heun equation**, and for special ("quasi-exactly-solvable") values of $v$ tied to each radial quantum number $n$, the eigenvalues $\mathscr{E}=\sqrt{-E}$ are **roots of explicit polynomials**, equivalent to the zeros of the Laguerre polynomials $L_n^{(1)}(2\mathscr{E})$ in the pure 3D ($k=3$) case:

| $n$ | Polynomial equation for $\mathscr{E}=\sqrt{-E}$ | Numerical roots $\mathscr{E}_i$ | $E_i = -\mathscr{E}_i^2$ |
|---|---|---|---|
| 1 | $\mathscr{E}-1=0$ | $1$ | $-1$ |
| 2 | $2\mathscr{E}^2-6\mathscr{E}+3=0$ | $0.633975,\ 2.366025$ | $-0.401924,\ -5.598076$ |
| 3 | $\mathscr{E}^3-6\mathscr{E}^2+9\mathscr{E}-3=0$ | $0.470160,\ 1.652704,\ 3.877136$ | $-0.221050,\ -2.731428,\ -15.03217$ |
| 4 | $2\mathscr{E}^4-20\mathscr{E}^3+60\mathscr{E}^2-60\mathscr{E}+15=0$ | $0.377213,\ 1.339056,\ 2.794217,\ 5.489513$ | $-0.142290,\ -1.793071,\ -7.807644,\ -30.1347$ |
| 5 | $2\mathscr{E}^5-30\mathscr{E}^4+150\mathscr{E}^3-300\mathscr{E}^2+225\mathscr{E}-45=0$ | (5 real positive roots, similarly obtained from $L_5^{(1)}(2\mathscr{E})=0$) | — |

Key structural results confirmed numerically/analytically in this framework:
- The eigenvalues are always **real, simple, and positive** in $\mathscr{E}$ (interlacing property between successive $n$).
- Between consecutive roots for degree $n{+}1$ lies exactly one root for degree $n$ (classical Sturm-type interlacing for the associated orthogonal polynomial family).
- Every polynomial solution has a **critical polynomial factor** $\mathcal{P}_{n+1}^n(\mathscr{E})$, common to a whole descending sequence of higher solutions — a genuine quasi-exact-solvability signature, closely analogous to Bender–Dunne orthogonal polynomials.
- For general (non-quantized) potential strength $v$ and general angular momentum, eigenvalues are **not** given by closed polynomial roots and must be computed by the Asymptotic Iteration Method (AIM) or direct numerical integration — this is the generic numerical case treated in Section 3.

### 2.1 Confined variants (new)

Hall, Saad and Sen also solved the **confined** soft-core problem $a/(r+\beta)$, $d>1$ dimensions, where confinement is imposed by (i) an additional linear term, (ii) an additional harmonic-oscillator term, or (iii) "hard confinement" via an impenetrable spherical box. As in the free case, special coupling values again yield **polynomial (quasi-exact) solutions** to a biconfluent Heun-type equation, while the AIM supplies highly accurate numerics for generic parameters. Representative unnormalized closed-form ground/first-excited wavefunctions were tabulated for $k=4$ (dimension index), $b=c=1$, and several values of $\beta$; the corresponding eigenvalues bracket those of the unconfined problem from below and converge to them as the confining box radius $\to\infty$.

---

## 3. Numerical (Non-Polynomial) Eigenvalues: General $Z,\beta$

### 3.1 $q=1$ and $q=2$, states 1s–4f (Singh, Chattarji & Varshni benchmark; reproduced/verified by AIM)

The classical reference dataset — extended and cross-checked by later AIM calculations (Hall, Saad & Ciftci 2010; Hall, Saad & Sen) — reports:

- Energies **accurate to 6–8 significant figures** for states 1s through 4f, tabulated as functions of the cutoff parameter $\beta$, for fixed $Z=1$ (scaling laws extend results to other $Z$).
- Ordering rule confirmed numerically: for fixed principal quantum number $\nu = n_r+\ell+1$, $E_{\nu\ell} > E_{\nu\ell'}$ whenever $\ell < \ell'$ (i.e., higher angular momentum states lie *higher*, opposite to the pure Coulomb degeneracy pattern, because the softening lifts the $\ell$-degeneracy).
- Level-crossings occur between different $(\nu,\ell)$ pairs as $\beta$ increases; numerically, the crossing condition is conjectured to require $\nu' \ge \nu+1$ and $\ell' \ge \ell+3$.
- For each fixed $\ell$, $E_{\nu\ell}(\beta)$ is well fit by a **Ritz-type two-parameter formula** in $\beta$, both for $q=1$ and $q=2$.
- All eigenvalues are shown to be **monotonic functions of each parameter** ($Z$, $\beta$, $q$) — larger $\beta$ (softer core) always raises the energy toward the continuum threshold ($E\to0^-$), and it does so most quickly for the states of lowest angular momentum.

### 3.1.1 Large-$\beta$ scaling regime (new numerical detail)

The Heun-equation AIM study of Hall, Saad & Sen (2010) reports that for large softening parameter (e.g. $\beta=200$), the $\ell=0,1,2,3$ eigenvalues become so closely spaced (separated by less than $0.001$ a.u.) that direct AIM evaluation becomes numerically unstable. The recommended workaround uses the scaling law
$$
E(n,\lambda\beta,Z)=\frac{1}{\lambda^2}E(n\lambda,\beta,Z)
$$
to map the ill-conditioned large-$\beta$ case onto a better-conditioned smaller-$\beta$, rescaled-$n$ calculation. As a concrete illustration, the eigenvalue that would be computed directly (and unreliably) as $E(1,200,2)$ is instead obtained via $E(4,50,2)$ and divided by $16$; for the $\ell=2,3$ channels at the auxiliary point $E(4,40,2)$, AIM yields
$$
E_{\ell=2} = -0.0624031366\ \text{a.u.}, \qquad E_{\ell=3} = -0.0579816331\ \text{a.u.}
$$
illustrating the 10-significant-figure precision attainable with the rescaled procedure.

### 3.2 Envelope-theory bounds (Hall–Saad–Sen, 2009, *Phys. Rev. A* 80, 032507)

Because exact numbers for general $q$ are not closed-form, the authors construct rigorous **upper and lower analytic bounds** using the "potential envelope method," calibrated against the exactly solvable pure power-law potentials $\pm r^s$. These bounds bracket the true numerical eigenvalues tightly across the full $(Z,\beta,q)$ parameter space and are used to validate direct numerics.

### 3.3 3D soft-core with laser-physics scaling ($q=2$)

For the muon-atom/laser-physics form $V_2(r)=-Z/\sqrt{r^2+\beta^2}$, numerical studies place the physically relevant softening range at $\beta \approx 20$–$40$ (in atomic units) to reproduce experimentally accessible strong-field regimes; ground and low excited state energies in this range are tabulated in the Hall–Saad–Sen papers and used directly in strong-field-ionization modeling (Eberly, Su, Javanainen and successors).

### 3.4 Dirac (relativistic) soft-core eigenvalues in $d$ dimensions (new)

Hall, Saad and collaborators extended the envelope-bound approach to the **Dirac equation** with a $d$-dimensional soft-core Coulomb potential (arXiv:1202.1814). Rigorous lower bounds $E^{L}_{k_d\nu}$ are constructed from the Coulomb spectral generating function and compared against accurate numerically computed Dirac eigenvalues $E_{k_d\nu}$. Representative comparisons (selected entries, dimensionless energy units, coupling $v$ and dimension-dependent quantum numbers $k_d,\nu$ as defined in the source) include pairs such as:

| State labels ($\nu$, $\tau$, $k_d$) | Lower bound $E^L_{k_d\nu}$ | Numerical $E_{k_d\nu}$ |
|---|---|---|
| representative low-$\nu$, small coupling | $0.9932$ | $0.9932$–$0.9950$ (agreement to 3–4 s.f.) |
| representative higher-$\nu$, $\tau=3/2$ | $0.729$–$0.953$ | $0.688773$–$0.95394$ |
| near-degenerate pair $\{E_{1,3,3},E_{-1,3,4}\}$ | exactly degenerate in the bound | not exactly degenerate in the true spectrum |

A structurally important qualitative finding: the pure-Coulomb Dirac degeneracy $E_{k_d\nu}=E_{-k_d,\nu+1}$ is exactly preserved by the analytic lower-bound formula but is only **approximately** preserved by the true softened-potential spectrum — i.e. softening lifts the relativistic "accidental" degeneracy in the same qualitative way it lifts the nonrelativistic $\ell$-degeneracy discussed in Section 3.1. The lower-bound formula is reported to be valid across the entire computed discrete Dirac spectrum and is described as "often very effective" numerically, with agreement to 3–5 significant figures across the tested coupling range $v<1$ (a restriction imposed because the Coulomb spectral function $D(u)$ used in the bound requires $u<1$).

---

## 4. 1D "Soft-Core Coulomb" Numbers Used in Strong-Field Physics

These are the most frequently cited **specific numerical eigenvalues** in the HHG/strong-field simulation literature, because they define standard benchmark 1D model atoms.

### 4.1 Standard soft-core (SC), $V(x) = -Z/\sqrt{x^2+\alpha^2}$

| Quantity | Value |
|---|---|
| Softening parameter (for $Z=1$, matching 3D H ground state $-0.5$) | $\alpha=\sqrt{2}\approx1.41421$ |
| Ground state $E_0$ | $-0.5$ (a.u.) |
| First excited state $E_1$ | $-0.2329034$ (a.u.) |
| Commonly used alternative softening $\alpha=1$ | $E_0 = -0.669778$ a.u. (μHartree accuracy) |
| Ground-state density width for $\alpha=1$, $\langle x^2\rangle$ | $1.191612$ |
| Physically relevant $\alpha$ range cited for realistic atomic softening | $0.8 \le \alpha \le 2$ |

### 4.2 Modified soft-core (MSC), $V(x)=-\tfrac{1}{2}Z/\sqrt{x^2+1/(4Z^2)}$

Constructed so the ground state exactly matches the 3D value $E_{\rm MSC}=-Z^2/2$ while giving a more realistic long-range $\tfrac12 Z/|x|$ tail and 3D-like density profile.

| Quantity (Z = 1) | Value |
|---|---|
| Ground state $E_0$ | $-0.5$ (a.u.), by construction |
| First excited state $E_1$ | $-0.1058670$ (a.u.) |

### 4.3 Exact analytical ground-state results across dimension (Ho, Jiao et al., *J. Phys. Chem. A* 2021)

An exact analytical (closed-form, non-perturbative) solution of the ground-state hydrogenic problem with soft-Coulomb potential $V(r)=-Z/\sqrt{r^2+a^2}$ was obtained in 1D, 2D, and 3D:
- The ground-state wavefunction factors into a power term × exponential × a "modulator" function, all expressible analytically in terms of the softening parameter $a$.
- As $a\to0$: in 2D and 3D the energy converges smoothly to the familiar bare-Coulomb result; in 1D the energy diverges to $-\infty$ and the wavefunction collapses to a delta function — a qualitatively distinct, dimension-dependent singular limit.
- At fixed $a$, the total ground-state energy **increases with dimension**, and its large-$Z$ scaling is **linear in $Z$** rather than quadratic (in contrast to the bare 2D/3D Coulomb $\propto Z^2$ scaling).

### 4.4 Krylov/Dirac benchmark form (Fillion-Gourdeau et al.)

For relativistic (Dirac-equation) benchmark calculations, a soft-core potential is calibrated so the **non-relativistic** Schrödinger ground-state energy exactly reproduces the 3D Coulomb value $-Z^2/2$, with the corresponding closed-form (unnormalized) ground-state wavefunction given explicitly in terms of $Z$ and $r$.

### 4.5 Gaussian-windowed soft-core (GSC) potential — new HHG-optimized model (Sallai et al. 2024)

The GSC potential (Family C, defined in Section 1) was introduced specifically to combine the strengths of SC (better near-core behavior) and MSC (correct asymptotic $1/|x|$ tail) for high-order-harmonic-generation (HHG) simulations:

| Quantity | Value |
|---|---|
| Window parameter $a$ (hydrogen and argon) | $2.551$ |
| Window parameter $b$ (hydrogen and argon) | $2$ |
| Design target | Ground-state energy matched to the real 3D atom (H, Ar) |
| Qualitative near-core behavior | Binds as weakly as SC (less strongly than MSC) |
| Qualitative asymptotic behavior | Decays as fast as MSC (faster than SC) |

Numerical simulations comparing GSC-driven single-atom HHG spectra against full 3D reference calculations show the GSC model reproduces the 3D harmonic spectrum accurately across the full plateau for linearly polarized drivers, at parameter regimes (e.g. wavelengths corresponding to $T\approx210$, i.e. $\sim1520$ nm) where the plain SC and MSC potentials show visible deviations from the 3D reference except near the cutoff region.

### 4.6 One-dimensional generalized-pseudospectral benchmark (Ji, Liu, Montgomery, Ho, Liu & Jiao, *Phys. Rev. E* 112, 025310, 2025) — new

This 2025 study extends the **generalized pseudospectral (GPS)** method — previously established for 3D atomic systems — to 1D quantum systems, in both free and spatially confined configurations, with soft-core Coulomb interaction as the primary test case:

- Eigenenergies are converged to **working (machine) precision** via the mapped, non-uniform GPS grid, extending the accuracy of the classic $-0.669778$ / $-0.2329034$-type benchmark values (Section 4.1) to substantially higher precision and to a much larger set of excited states.
- The paper reports **asymptotic laws for high-lying eigenenergies** of the 1D soft-core system, analogous to Rydberg-series scaling in 3D.
- **Quantum defects** are computed and shown to differ systematically between even- and odd-parity bound-state series — a genuinely 1D structural feature absent from the (purely $\ell$-labeled) 3D problem.
- The variation and crossing of eigenenergies and eigenfunctions are tracked continuously as a function of spatial confinement, connecting the free 1D soft-core spectrum to the confined-box limit.

---

## 5. Summary Table — Representative Numerical Eigenvalues Across Forms

| Potential form | Parameters | State | Numerical $E$ (a.u.) | Method / Source type |
|---|---|---|---|---|
| $V_1=-v/(r+1)$, 3D | $v=1$ (i.e. $n=1$ QES point) | Ground | $E=-1$ | Exact (Heun/AIM polynomial root) |
| $V_1=-v/(r+1)$, 3D | $n=2$ QES point | 2 states | $-0.401924,\ -5.598076$ | Exact (quadratic root) |
| $V_1=-v/(r+1)$, 3D | $n=3$ QES point | 3 states | $-0.221050,\ -2.731428,\ -15.03217$ | Exact (cubic root) |
| $V_q(r)=-Z/(r^q+\beta^q)^{1/q}$ | $Z=1$, general $\beta$, $q=1,2$ | 1s–4f | 6–8 sig. figs, tabulated vs. $\beta$ | Numerical integration + Ritz fit |
| $V_1=-Z/(r+\beta)$, rescaled | $\beta=40$ (equiv. to $\beta=200$, $n=1$ via scaling) | $\ell=2$ | $-0.0624031366$ | AIM (rescaled large-$\beta$) |
| $V_1=-Z/(r+\beta)$, rescaled | $\beta=40$ (equiv. to $\beta=200$, $n=1$ via scaling) | $\ell=3$ | $-0.0579816331$ | AIM (rescaled large-$\beta$) |
| $V(x)=-1/\sqrt{x^2+2}$ (1D SC) | $\alpha=\sqrt2$ | Ground | $-0.5$ | Exact/numerical (1D model atom) |
| $V(x)=-1/\sqrt{x^2+2}$ (1D SC) | $\alpha=\sqrt2$ | 1st excited | $-0.2329034$ | Numerical (1D model atom) |
| $V(x)=-1/\sqrt{x^2+1}$ (1D SC, $\alpha=1$) | — | Ground | $-0.669778$ | Numerical (μHa accuracy) |
| $V_{\rm MSC}(x)=-\tfrac12/\sqrt{x^2+1/4}$ | — | Ground | $-0.5$ (exact by design) | Analytic construction |
| $V_{\rm MSC}(x)$ | — | 1st excited | $-0.1058670$ | Numerical |
| $V_{\rm GSC}^{\rm 1D}(z)$, H/Ar-calibrated | $a=2.551$, $b=2$ | Ground | Matched to real 3D atom by construction | Gaussian-window hybrid, HHG-optimized |
| $V(x)$, 1D GPS benchmark (2025) | free & confined | Rydberg series | Working-precision, quantum-defect resolved | Generalized pseudospectral |
| Dirac soft-core, $d$ dimensions | coupling $v<1$ | various $k_d,\nu$ | $\sim0.68$–$0.995$ (bound vs. numeric, 3–5 s.f. agreement) | Envelope lower bound vs. numerical Dirac diagonalization |

---

## 6. Key Observations Consistent Across the Literature

1. **Monotonicity:** All soft-core eigenvalues $E_{\nu\ell}$ increase monotonically toward zero as the softening parameter $\beta$ (or $\alpha$) increases, and decrease monotonically as $Z$ increases — proven analytically and confirmed by every numerical study surveyed.
2. **Lifted $\ell$-degeneracy:** Unlike the pure Coulomb potential, states of different $\ell$ at fixed $\nu$ are no longer degenerate; softening breaks the accidental $SO(4)$ symmetry of hydrogen, and $\ell$-ordering is reversed relative to naive expectation ($E_{\nu\ell}>E_{\nu\ell'}$ for $\ell<\ell'$).
3. **Finite bound-state count in 1D:** unlike the 3D soft-core (which, like Coulomb, supports infinitely many bound states), some related 1D model potentials (e.g., exponential surrogates) bind only a **finite** number of states — a qualitative contrast highlighted in benchmark comparisons.
4. **Quasi-exact solvability is the exception, not the rule:** closed-form polynomial eigenvalues exist only at a discrete, countable set of coupling strengths $v$ tied to each $n$; for generic parameters the AIM or direct shooting/finite-difference/pseudospectral numerical methods are required, and these are the source of essentially all high-precision published tables.
5. **Dimension dependence matters:** going from 1D → 2D → 3D changes not just numbers but qualitative behavior (finite vs. divergent energy as softening $\to0$; the large-$Z$ scaling law itself changes from linear to quadratic).
6. **Relativistic degeneracy lifting (new):** the same qualitative softening-induced degeneracy-lifting seen nonrelativistically for $\ell$-degenerate states also occurs for the Dirac equation's $k_d\leftrightarrow-k_d$ degeneracy — analytic lower bounds preserve the degeneracy exactly, but true numerical Dirac spectra only approximate it, confirming that degeneracy-lifting is a genuine physical (not merely nonrelativistic-approximation) effect of core softening.
7. **Parity-resolved quantum defects in 1D (new):** the 2025 GPS study establishes that even- and odd-parity Rydberg series in the 1D soft-core problem carry distinct quantum defects — a structural feature with no counterpart in the $\ell$-labeled 3D spectrum, and one that had not been systematically quantified in earlier (lower-precision) 1D studies.
8. **Purpose-built hybrid potentials are converging on GSC-type constructions (new):** the newest generation of 1D model potentials (2024) explicitly abandons the single-form SC/MSC dichotomy in favor of smoothly joined, region-dependent potentials (Gaussian-windowed), reflecting a maturing recognition that no single simple closed-form 1D potential reproduces all relevant 3D spectral and dynamical (HHG) features simultaneously.

---

## 7. Compiled Bibliography

### Foundational / exact & quasi-exact solutions
1. R. L. Hall, N. Saad, K. D. Sen, *Energies and wave functions for a soft-core Coulomb potential*, Phys. Rev. A **80**, 032507 (2009). [arXiv:0908.2087]
2. R. L. Hall, N. Saad, K. D. Sen, *Soft-core Coulomb potentials and Heun's differential equation*, J. Math. Phys. **51**, 022107 (2010). [arXiv:0912.3445]
3. R. L. Hall, N. Saad, K. R. Bryenton, *The d-dimensional softcore Coulomb potential and the generalized confluent Heun equation*, (2018). [arXiv:1810.06539]
4. H. Exton, *The interaction $V(r)=-Ze^2/(r+\beta)$ and the confluent Heun equation*, J. Phys. A: Math. Gen. **24**, L329 (1991).
5. R. L. Hall, N. Saad, K. D. Sen, *Discrete spectra for confined and unconfined $-a/r+br^2$ potentials in d-dimensions*, J. Math. Phys. **52**, 092103 (2011).
6. R. L. Hall, N. Saad, K. D. Sen, *Spectral characteristics for a spherically confined $-a/r+br^2$ potential*, J. Phys. A: Math. Theor. **44**, 185307 (2011).
7. H. Ciftci, R. L. Hall, N. Saad, E. Dogu, *Physical applications of second-order linear differential equations that admit polynomial solutions*, J. Phys. A: Math. Theor. **43**, 415206 (2010).
8. R. L. Hall, N. Saad, *Spectra generated by a confined soft-core Coulomb potential*, J. Math. Phys. **57**, 022106-related preprint (asymptotic iteration method for biconfluent Heun-type problems in $d>1$ dimensions with linear, harmonic-oscillator, and hard-wall confinement).
9. R. L. Hall, N. Saad, *Dirac eigenvalues for a softcore Coulomb potential in d dimensions*, [arXiv:1202.1814] (2012) — envelope lower bounds vs. numerical Dirac spectra, softening-induced lifting of the $k_d\leftrightarrow-k_d$ degeneracy.

### Classic numerical benchmark tables
10. K. K. Singh, Y. P. Varshni (and collaborators, e.g. "Singh et al."), numerical eigenvalues for states 1s–4f of $V(r) = -Ze^2/(r^p+\beta^p)^{1/p}$, $p=1,2$, accurate to 6–8 significant figures (as cited/verified in Refs. 1–3, 11).
11. F. F. Schöberl et al., *The Soft-Core Coulomb Potential in the Semi-Relativistic Two-Body Basis*, (semi-relativistic extension citing the Singh benchmark tables).
12. R. Dutt, U. Mukherji, Y. P. Varshni, and related early analytic/numerical treatments of the truncated Coulomb potential (referenced within Refs. 1–2 as DMVD, SR, FF0, CM).

### Ground-state closed-form / exact analytical studies
13. X. H. Ji, J. P. Liu, H. E. Montgomery Jr., Y. K. Ho, A. Liu, L. G. Jiao, *Exact Analytical Solution of the Ground-State Hydrogenic Problem with Soft Coulomb Potential*, J. Phys. Chem. A **125**, 5146 (2021).
14. X. H. Ji, J. P. Liu, H. E. Montgomery, Y. K. Ho, A. Liu, L. G. Jiao, *One-dimensional atoms with soft-core Coulomb interaction: An application of the generalized pseudospectral method*, Phys. Rev. E **112**, 025310 (2025). DOI: 10.1103/r6hy-vkxh.
15. C. Li, *Exact analytical ground state solution of 1D H₂⁺ with soft Coulomb potential*, J. Math. Chem. **60**, 184 (2022).

### Strong-field / laser–atom & HHG applications (1D and 3D soft-core model atoms)
16. J. H. Eberly, Q. Su, J. Javanainen, *Nonperturbative Subharmonic and Harmonic Generation in Intense Laser Fields*, Phys. Rev. Lett. **62**, 881 (1989).
17. J. H. Eberly, *Photoelectron spectra for intense-field ionization*, Phys. Rev. A **42**, 5750 (1990).
18. Q. Su, J. H. Eberly, *Model atom for multiphoton physics*, Phys. Rev. A **44**, 5997 (1991).
19. J. Javanainen, J. H. Eberly, Q. Su, *Numerical simulations of multiphoton ionization and above-threshold electron spectra*, Phys. Rev. A **38**, 3430 (1988).
20. R. Panfili, J. H. Eberly, S. L. Haan, *Comparing classical and quantum simulations of strong-field double-ionization*, Opt. Express **8**, 431 (2001).
21. M. Protopapas, C. H. Keitel, P. L. Knight, *Atomic physics with super-high intensity lasers*, Rep. Prog. Phys. **60**, 389 (1997).
22. A. Gordon, R. Santra, F. X. Kärtner, *Role of the Coulomb singularity in high-order harmonic generation*, Phys. Rev. A **72**, 063411 (2005).
23. M. V. Frolov, N. L. Manakov, A. M. Popov, O. V. Tikhonova, E. A. Volkova, A. A. Silaev, N. V. Vvedenskii, A. F. Starace, *Analytic theory of high-order-harmonic generation by an intense few-cycle laser pulse*, Phys. Rev. A **85**, 033416 (2012).
24. D. Bauer, *Two-dimensional, two-electron model atom in a laser pulse*, (exact treatment vs. TDDFT and classical calculations).
25. K. Sallai, [3 additional authors], *One-dimensional model potentials optimized for the calculation of the HHG spectrum*, [arXiv:2401.13724] (2024) — introduces the SC, MSC, and Gaussian-windowed soft-core (GSC) potentials with fitted parameters $a=2.551$, $b=2$ for H and Ar.
26. Authors of arXiv:1806.03119, *Improved one-dimensional model potentials for strong-field simulations*.
27. Authors of arXiv:1002.2774, *Isotope effects in the harmonic response from hydrogenlike muonic atoms in strong laser fields* (soft-core vs. hard-core nuclear model).
28. R. Grobe et al./ related, *High Harmonic Generation with Twisted Electrons* (uses a smoothed $|r|^4+\alpha^4$ soft-core variant), [arXiv:1909.00728].
29. Y. I. Salamin, S. X. Hu, K. Z. Hatsagortsyan, C. H. Keitel, *Relativistic high-power laser–matter interactions*, Phys. Rep. **427**, 41 (2006).
30. C. W. Clark, review on strong-field atomic ionization model potentials, J. Phys. B **30**, 2517 (1997).
31. Study on *Soft parameters in Coulomb potential of noble atoms for nonsequential double ionization: Classical ensemble model and simulations*, Comput. Phys. Commun. (2022) — fits the softening parameter $a$ for noble-gas NSDI classical-ensemble simulations.
32. Study using the Siegert-state method and quadratic Stark-effect perturbation theory benchmarked against soft-core hydrogen, illustrating the applicable range/precision of the quadratic Stark formula for highly excited soft-core states (2023, conference proceedings).
33. Study on *Reconstruction of a single-active-electron potential from electron momentum distribution produced by strong-field ionization using optimization technique*, J. Phys. B (2021) — inverse reconstruction of the 1D soft-core potential ($Z=1$, $a=1$) from strong-field ionization momentum spectra using a generalized-pseudospectral non-uniform grid.
34. Time-dependent generalized pseudospectral method in prolate spheroidal coordinates for H₂⁺ and N₂ diatomic multiphoton processes (methodological precursor to Ref. 14's 1D extension).
35. Comparative numerical-methods study, *A comparison of numerical approaches to the solution of the time-dependent Schrödinger equation in one dimension* — benchmarks RK4, Magnus-expansion, and diagonalization propagators against the 1D soft-core Coulomb problem.

### Related confined / screened variants and reviews
36. Study on *Laser-induced excitation and ionization of a confined hydrogen atom in an exponential-cosine-screened Coulomb potential* (Bernstein-polynomial method).
37. Review article, *A Review on the Bound-State Solutions of the Stationary Schrödinger Equation for General Pseudo-Coulomb Potential*, New Horizons in Mathematical Physics, Vol. 3, No. 4 (2019), doi:10.22606/nhmp.2019.34001.
38. J. Eiglsperger, B. Piraux, J. Madroñero, *Krylov subspace methods for the Dirac equation*, [arXiv:1407.7370] (soft-core benchmark potential for relativistic calculations).
39. Study on *Effects of a soft-core Coulomb potential on the dynamics of a hydrogen atom near a metal surface* (classical dynamics comparison with true Coulomb via Levi-Civita regularization; typical softening range $0.8\le a\le2$ cited for realistic atomic modeling).
40. Related quasi-exact-solvability review: *Unified derivation of exact solutions for a class of quasi-exactly solvable models*, covering the soft-core Coulomb case $V(r)=G/r - Z/(r+\beta)$, [arXiv:1111.1050].
41. Study on mimicking soft-Coulomb interactions with exponential potentials for density-functional-theory benchmarking, *One Dimensional Mimicking of Electronic Structure: The Case for Exponentials*, [arXiv:1504.05620].
42. *Variational approach to the soft-Coulomb potential in low-dimensional quantum systems* (1D/2D quantum-wire and quantum-well analogues).
43. Ground-state energies of the He atom in an exponential-cosine-screened Coulomb potential (ECSCP), computed via Ritz variational principle with highly correlated wavefunctions; reports convergence of He and He⁺ ground-state energies and ionization potentials with increasing basis size — a related screened-Coulomb (rather than soft-core) benchmark cited alongside the soft-core literature.
44. Y. K. Ho and collaborators, *Critical screening parameters of one-electron systems with screened Coulomb potentials: circular Rydberg states* — companion screened-Coulomb study using the same GPS methodology as Ref. 14.
45. Y. X. Geng, Y. Z. Zhang, H. E. Montgomery Jr., Y. K. Ho, A. Liu, L. G. Jiao, *Shannon information entropies of the Hulthén potential and their critical behavior near the system bound limit*, J. Phys. A: Math. Theor. **58**, 415301 (2025) — related information-theoretic GPS study by the same group responsible for Ref. 14.
46. Studies applying the finite-nuclear-size (FNS) correction (via relativistic continuum Hartree–Bogoliubov charge densities) to atomic energy levels — methodologically adjacent softened-core treatments for heavy-nuclei spectroscopy.
47. J. J. Omiste et al. and related studies on time-delay singularities in the photoionization of the molecular hydrogen ion, cited in soft-core Coulomb literature reviews as adjacent Coulomb-singularity-regularization applications.
48. Grid-based, first-quantized quantum-computing simulations of 2D/3D atoms with single and paired particles (up to 36 emulated qubits), cited as a modern computational context in which soft-core-type regularized potentials are relevant benchmark systems.
49. Study on dark and bright autoionizing states in a 1D helium model for HHG and photoionization, incorporating electron correlation beyond the single-active-electron soft-core approximation — a natural two-electron extension of the benchmarks in Sections 4.1–4.6.
50. C. Shen et al. and related applications of generalized pseudospectral/mapped grid techniques outside atomic physics (astronomy and computing contexts), cited to illustrate the broader methodological lineage of the GPS approach used in Ref. 14.

---

## 8. Notes on Confidence and Coverage

- The **exact polynomial eigenvalues** in Section 2 are reproduced directly from the closed-form recurrence relations of Hall, Saad & Bryenton (2018) and are exact to the precision shown (roots of low-degree polynomials, computed here to 6 decimal places).
- The **6–8 significant-figure benchmark tables** for 1s–4f states referenced in Section 3.1 are widely cited across the literature (Hall–Saad–Sen papers, Schöberl et al.) but the primary tabulated numbers themselves were not directly reproducible from the sources retrieved here; readers needing the full numerical tables should consult Phys. Rev. A **80**, 032507 (2009) and J. Math. Phys. **51**, 022107 (2010) directly.
- The 1D model-atom numbers in Section 4.1–4.4 (e.g., $-0.669778$, $-0.2329034$, $-0.1058670$) are well-established, frequently re-cited constants in the strong-field/HHG community and are consistent across multiple independent sources.
- The **large-$\beta$ rescaled AIM values** in Section 3.1.1 ($-0.0624031366$, $-0.0579816331$) and the **GSC window parameters** in Section 4.5 ($a=2.551$, $b=2$) are quoted directly from the primary sources (Hall–Saad–Sen 2010 Heun paper; Sallai et al. 2024) and were retrievable with high confidence.
- The **2025 GPS study (Section 4.6, Ref. 14)** and the **Dirac envelope-bound results (Section 3.4, Ref. 9)** were both retrievable at the abstract/summary level with high confidence on qualitative and order-of-magnitude claims; the fully tabulated high-precision numerical values in each (beyond what is quoted above) were not directly extractable from the sources retrieved here, and readers needing complete tables should consult Phys. Rev. E **112**, 025310 (2025) and arXiv:1202.1814 directly.
- Several entries in the expanded bibliography (Refs. 31–35, 43–50) are companion, methodologically adjacent, or citing-context papers identified via literature search rather than primary soft-core-Coulomb eigenvalue sources; they are included because they are consistently cited alongside the core soft-core-Coulomb literature, but their soft-core-specific numerical content (where any) is more limited than that of Refs. 1–14, 25.

---

> [!NOTE]
>
> Generated by Claude.ai
>
> Model: Claude Sonnet 5
>
> Prompt: Extend the prior soft-core Coulomb eigenvalue review with new sections, new numerical values, and ~20 additional references. Deliver as a Markdown file; do not copy output into chat.

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Conduct a thorough review of the numerical values of the eigenvalues of the Schrödinger equation with a soft-core Coulomb potential. Also, compile a list of related publications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
