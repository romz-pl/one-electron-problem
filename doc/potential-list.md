# Well-Known Potentials in the One-Electron Problem

This is a survey of the standard potentials $V(\mathbf{r})$ (or $V(x)$ ) that appear in the single-particle (one-electron) Schrödinger equation across textbook quantum mechanics, atomic physics, solid-state physics, and quantum chemistry.

$$
-\frac{\hbar^2}{2m}\nabla^2\psi + V(\mathbf{r})\psi = E\psi
$$

---

## 1. Exactly Solvable 1D Model Potentials

- **Free particle** ($V=0$): No potential at all; plane-wave / wave-packet solutions. Serves as the baseline reference problem.
- **Infinite square well (particle in a box)**: $V=0$ inside $[0,L]$, $V=\infty$ outside. Produces discrete $\sin(n\pi x/L)$ eigenstates; the canonical introductory bound-state problem.
- **Finite square well**: Finite depth $-V_0$ over a finite width. Illustrates tunneling into classically forbidden regions and a finite number of bound states.
- **Square (rectangular) barrier**: A finite-height, finite-width barrier used to demonstrate quantum tunneling and transmission/reflection coefficients.
- **Step potential**: A single discontinuous jump in $V(x)$; used to study partial reflection at an energy threshold.
- **Delta-function potential (Dirac comb / single delta well)**: $V(x) = -\alpha\,\delta(x)$; supports exactly one bound state and is a limiting case of the finite well.
- **Kronig–Penney potential**: A periodic array of delta functions or square barriers, modeling a 1D crystal lattice and producing energy bands.
- **Linear potential (uniform field)**: $V(x) = Fx$; leads to Airy-function solutions, relevant to a charged particle in a uniform electric field or a particle bouncing off a hard floor under gravity.
- **Quantum bouncer**: $V(x) = mgx$ for $x>0$, $V=\infty$ for $x<0$; the linear potential combined with an infinite wall (Airy-function eigenstates).
- **Harmonic oscillator potential**: $V(x) = \tfrac12 m\omega^2x^2$; exactly solvable with Hermite-polynomial eigenfunctions and equally spaced levels — a template for molecular vibrations and field quantization.
- **Morse potential**: $V(x) = D_e\left(1-e^{-a(x-x_0)}\right)^2$; an anharmonic, exactly solvable model for diatomic molecular bond vibration, including dissociation.
- **Pöschl–Teller potential**: $V(x) = -\dfrac{\hbar^2 a^2}{2m}\dfrac{\lambda(\lambda-1)}{\cosh^2(ax)}$ (hyperbolic-secant well); exactly solvable, often used as a reflectionless potential for special parameter values.
- **Eckart potential**: A smooth barrier/well of the form combining $\mathrm{sech}^2$ and $\tanh$ terms; exactly solvable and used to model reaction barriers in chemical dynamics.
- **Rosen–Morse potential**: A combination of a $\tanh$ term and a $\mathrm{sech}^2$ term; another exactly solvable "shape-invariant" potential from supersymmetric QM.
- **Double-well potential (quartic)**: $V(x) = -ax^2+bx^4$; the standard model for tunneling splitting, molecular inversion (e.g., ammonia), and symmetry breaking.
- **Triangular potential well**: Linear confining potential used at semiconductor heterojunction interfaces (e.g., the 2D electron gas at a MOSFET interface).
- **Periodic (sinusoidal) potential**: $V(x)=V_0\cos(2\pi x/a)$; the basis of the Mathieu-equation treatment of electrons in a periodic lattice/optical lattice.

## 2. Central (Radial) Potentials in 3D

- **Coulomb potential**: $V(r) = -\dfrac{Ze^2}{4\pi\epsilon_0 r}$; the exactly solvable hydrogen-atom/hydrogenic-ion potential, giving the Rydberg spectrum and degenerate $n^2$ levels.
- **Isotropic 3D harmonic oscillator**: $V(r) = \tfrac12 m\omega^2 r^2$; exactly solvable in spherical coordinates, used in nuclear shell-model and quantum-dot contexts.
- **Spherical (3D) square well**: A finite or infinite spherical well; used to model deuteron-like nuclear binding and idealized quantum dots.
- **Spherical infinite well**: $V=0$ for $r<a$, $V=\infty$ otherwise; eigenfunctions are spherical Bessel functions.
- **Yukawa (screened Coulomb) potential**: $V(r) = -\dfrac{g^2}{r}e^{-r/\lambda}$; models a nuclear/screened electrostatic interaction with finite range, requires numerical or perturbative treatment.
- **Hulthén potential**: $V(r) = -\dfrac{V_0\, e^{-r/a}}{1-e^{-r/a}}$; an exactly solvable screened-Coulomb-like potential, often used as a Yukawa approximation with closed-form solutions.
- **Kratzer potential**: $V(r) = -\dfrac{2D_e a}{r} + \dfrac{D_e a^2}{r^2}$; exactly solvable, used for diatomic molecular vibration–rotation spectra.
- **Pseudoharmonic potential**: $V(r) = D_e\left(\dfrac{r}{r_e}-\dfrac{r_e}{r}\right)^2$; another exactly solvable molecular potential combining oscillator and centrifugal-like terms.
- **Woods–Saxon potential**: $V(r) = \dfrac{-V_0}{1+e^{(r-R)/a}}$; a smoothed finite well used extensively to model the nuclear mean-field potential felt by a nucleon.
- **Modified Pöschl–Teller / radial hyperbolic potentials**: Radial generalizations of the 1D $\mathrm{sech}^2$ potential, exactly solvable via the factorization method.
- **Coulomb-plus-linear (Cornell) potential**: $V(r) = -\dfrac{a}{r}+br$; a phenomenological potential (better known from quarkonium physics) sometimes applied to one-electron-like confinement problems.
- **Power-law potential**: $V(r) = A r^{k}$; a generic family including the linear ($k=1$) and harmonic ($k=2$) cases, studied via WKB approximations for general $k$.

## 3. Angular / Centrifugal Contributions (accompanying radial potentials)

- **Centrifugal barrier term**: $V_{\ell}(r) = \dfrac{\hbar^2 \ell(\ell+1)}{2mr^2}$; not a standalone potential but the effective angular-momentum contribution added to any central potential in the radial Schrödinger equation.

## 4. Atomic and Molecular Physics Potentials

- **Hydrogenic potential with finite nuclear size**: A Coulomb potential regularized at short distance (e.g., uniformly charged sphere) to account for the finite size of the nucleus; used in precision spectroscopy and muonic-atom calculations.
- **Screened hydrogenic / effective one-electron potential (e.g., Hartree, Hartree–Fock-derived, or model potentials like Green–Sellin–Zachor or Chen–Cheng)**: Empirical or self-consistent-field-derived central potentials representing the net effect of nucleus plus other electrons on the "active" (one) electron in multi-electron atoms.
- **Muffin-tin potential**: A piecewise potential — spherically symmetric near each nucleus and constant in interstitial regions — widely used in band-structure and scattering calculations for solids.
- **Stark potential**: $V(\mathbf r) = -\dfrac{Ze^2}{4\pi\epsilon_0 r} + eFz$; the hydrogen atom in a uniform external electric field, solvable exactly in parabolic coordinates.
- **Zeeman-type magnetic potential term**: The vector-potential-modified kinetic term $(\mathbf{p}-q\mathbf{A})^2/2m$ for a charged particle in a magnetic field (e.g., Landau-level problem); often paired with a Coulomb potential for the hydrogen atom in a magnetic field.
- **Landau-level (parabolic magnetic confinement) potential**: Effective harmonic-oscillator-like potential arising from a uniform magnetic field via minimal coupling, giving equally spaced Landau levels.

## 5. Solid-State / Condensed-Matter One-Electron Potentials

- **Periodic crystal (Bloch) potential**: Any lattice-periodic $V(\mathbf r)=V(\mathbf r+\mathbf R)$; underlies Bloch's theorem and band-structure theory (the Kronig–Penney model above is its simplest 1D realization).
- **Quantum well / quantum wire / quantum dot confinement potentials**: Piecewise-constant or parabolic potentials used to model electron confinement in semiconductor heterostructures.
- **Parabolic confinement potential (quantum dot model)**: $V(r) = \tfrac12 m\omega^2 r^2$, the standard idealization for lateral confinement in gated semiconductor quantum dots.
- **Random/disordered (Anderson) potential**: A spatially random on-site potential used in Anderson localization studies; not exactly solvable but a standard model potential.

## 6. Singular / Special-Purpose Model Potentials

- **Inverse-square potential**: $V(r) = \dfrac{\alpha}{r^2}$; exhibits scale invariance and anomalous quantization, a benchmark example in the study of self-adjoint extensions.
- **Dirac comb (periodic delta functions)**: An infinite periodic array of $\delta$-function spikes; the exactly solvable prototype for band formation (Kronig–Penney's delta-function limit).
- **Reflectionless (soliton) potentials**: Special $\mathrm{sech}^2$-based potentials (a subclass of Pöschl–Teller) engineered so that all incident waves are perfectly transmitted, related to solitons in the KdV equation.
- **PT-symmetric potentials**: Complex, non-Hermitian potentials $V(-x) = V^*(x)$ (e.g., $V(x)=ix^3$) studied in the context of PT-symmetric quantum mechanics; included here as a well-known extension beyond standard Hermitian one-electron potentials.

---

### Notes

- "Exactly solvable" means closed-form eigenfunctions exist (often special functions: Hermite, Laguerre, Bessel, hypergeometric, Airy).
- Several potentials above (Morse, Pöschl–Teller, Eckart, Rosen–Morse, Kratzer, Hulthén, pseudoharmonic) belong to the broader class of **shape-invariant potentials** studied via supersymmetric quantum mechanics and the factorization method.
- The list favors potentials that appear as standard named problems in quantum mechanics, atomic physics, molecular physics, nuclear physics, and solid-state physics textbooks; it is representative rather than infinite, since arbitrary numerical potentials are not "well-known" in the named sense requested.



---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Create an exhaustive list of the well-known potentials used in the one-electron problem in quantum mechanics. Each potential should be accompanied by a brief description. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
