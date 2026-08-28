# The Eckart Potential: Applications in Physics and Chemistry

## 1. Origin and Mathematical Form

The Eckart potential was introduced by Carl Eckart in 1930 in the context of one-dimensional quantum-mechanical barrier penetration. The general (asymmetric) form is

$$V(x) = \frac{A\,e^{x/a}}{1+e^{x/a}} + \frac{B\,e^{x/a}}{\left(1+e^{x/a}\right)^{2}}$$

where $A$ and $B$ set the asymmetry and height of the barrier and $a$ sets its width. Two limiting cases are used constantly in the literature:

- **Barrier form** (repulsive, used for reaction dynamics): a smooth, asymmetric hump between two asymptotic plateaus, used to model the potential energy profile along a reaction coordinate near a transition state.
- **Well form** (attractive, used for bound-state/molecular problems): often written as
$$V(r) = -D\,\frac{e^{-r/a}}{1-e^{-r/a}} + \frac{\hbar^2}{2\mu a^2}\frac{e^{-r/a}}{\left(1-e^{-r/a}\right)^2}$$
which behaves qualitatively like a Morse-type potential and is used to model the internuclear interaction of diatomic molecules.

Eckart's original paper showed the associated Schrödinger equation is exactly solvable in terms of hypergeometric functions, which is the mathematical property that has kept the potential in continuous use for nearly a century.

## 2. Applications in Chemistry

### 2.1 Quantum tunnelling corrections in reaction-rate theory
This is the potential's single most widespread chemical application. In transition-state theory (TST), the reaction path near the saddle point is approximated by a one-dimensional Eckart barrier fitted to the barrier height (forward and reverse), and the curvature (imaginary frequency) at the saddle point. Because the barrier-penetration problem for this potential has a closed-form transmission probability, it allows an analytic "tunnelling correction factor" κ(T) to be computed and multiplied onto the classical TST rate constant, without needing a full-dimensional dynamics calculation.

- This approach was formalized by Harold Johnston and coworkers and remains the default tunnelling correction in many computational-kinetics packages (e.g., KiSThelP and similar rate-constant codes) because of its low computational cost relative to instanton or full quantum-dynamical treatments.
- It is used extensively in **combustion and atmospheric chemistry** (e.g., pyrolysis, oxidation, and tropospheric radical reactions) to correct calculated rate constants for hydrogen-atom and other light-particle transfer reactions where tunnelling matters at low temperature.
- It is a standard tool in **astrochemistry** for estimating rate coefficients of grain-surface and gas-phase reactions relevant to interstellar/protostellar ice chemistry (e.g., H-atom addition reactions forming water and methanol on ices), where reaction temperatures are very low and tunnelling dominates.
- Comparative studies have tested how well the one-dimensional Eckart tunnelling correction reproduces more rigorous variational-TST or quantum-dynamical tunnelling factors for benchmark systems such as H + H₂, D + H₂, and H + D₂, generally finding good agreement above ~300 K and increasing deviation at very low temperature where multidimensional tunnelling becomes important.

### 2.2 Vibrational and rotational spectroscopy of diatomic molecules
In its attractive/well form, the Eckart potential (and combinations of it with other exactly or quasi-exactly solvable potentials) is used as a model internuclear potential for diatomic molecules, playing a role similar to the Morse or Kratzer potentials.

- The exact and approximate (for nonzero angular momentum, ℓ ≠ 0) bound-state solutions of the radial Schrödinger equation for the Eckart potential have been derived using methods such as the Nikiforov–Uvarov (NU) method, the Nikiforov–Uvarov Functional Analysis (NUFA) method, the asymptotic iteration method (AIM), and supersymmetric quantum mechanics, typically combined with the Greene–Aldrich approximation to handle the centrifugal term.
- These solutions are used to compute vibrational–rotational energy levels, wavefunctions, and spectroscopic constants for real diatomic molecules (e.g., CO, N₂, NO, HCl, LiH, CuLi, TiH, VH, TiC and alkali dimers such as Na₂ and Li₂), and to compute derived thermodynamic functions (vibrational partition function, internal energy, free energy, entropy, specific heat) at finite temperature.
- Expectation values (⟨r⁻¹⟩, ⟨r⁻²⟩, kinetic energy, etc.) obtained via the Hellmann–Feynman theorem for Eckart-type potentials are used to characterize molecular structure and to benchmark approximation schemes against spectroscopic data.

### 2.3 Combined/generalized potentials for improved chemical accuracy
Because a pure Eckart potential does not reproduce every feature of a real molecular potential energy curve, it is frequently summed with other analytically solvable potentials to widen its applicability:

- Eckart–Hellmann potential
- Eckart plus Hellmann potential in hyperspherical coordinates
- Deng–Fan–Eckart potential
- Yukawa–Eckart and Hulthén–Eckart type combinations
- Möbius-square-plus-Eckart potential
- Improved deformed generalized Deng–Fan plus deformed Eckart potential (used with the Klein–Gordon and Schrödinger equations under noncommutative quantum mechanics symmetries)

These hybrids are used to better fit experimental dissociation energies and equilibrium bond lengths, and to extend applications into information-theoretic measures of molecular quantum states (Shannon entropy, Fisher information, quantum-information "complexity" measures) for selected diatomics.

## 3. Applications in Physics

### 3.1 Original context: electron barrier penetration
Eckart's 1930 paper solved the barrier-penetration (reflection/transmission) problem for electrons incident on a smooth potential barrier of this shape, motivated by earlier work (Fowler and others) on electron emission and barrier problems, and derived an approximate exponential (quasi-classical/WKB-like) formula for the reflection coefficient that he showed agreed well with the exact hypergeometric solution in the appropriate limit. This established Eckart's potential as one of the standard exactly solvable barrier models in quantum mechanics, alongside the rectangular barrier and later potentials such as Pöschl–Teller, Woods–Saxon, and Rosen–Morse.

### 3.2 Bound-state and scattering problems in atomic, molecular, and mathematical physics
Beyond chemistry-specific molecular spectroscopy, the Eckart potential (and its generalized/deformed/combined forms) is used broadly as a testbed and application vehicle in:

- **Atomic and quantum-mechanical bound-state theory**: solving the nonrelativistic Schrödinger equation and relativistic wave equations (Klein–Gordon, Dirac, Duffin–Kemmer–Petiau) for Eckart-type and Eckart-combination potentials, often as part of a broader program comparing exactly solvable potential models (Hulthén, Pöschl–Teller, Kratzer, Hylleraas, Scarf, Rosen–Morse, Manning–Rosen, etc.).
- **Quantum information theory applied to model systems**: computing Shannon entropy, Rényi entropy, Fisher information, and statistical complexity for particles bound in Eckart or modified-Eckart potentials, used to probe localization and information-theoretic uncertainty relations in model quantum systems.
- **Molecular/rotational dynamics — the "Eckart frame"**: a distinct but historically related use of Eckart's name is the *Eckart frame* (or Eckart conditions), a body-fixed reference frame that minimizes the coupling between overall rotation and internal vibration of a polyatomic system. This construction (from a separate 1935 Eckart paper) is used in vibration–rotation spectroscopy, molecular dynamics simulations, structural-isomerization dynamics of atomic clusters, and more recently in soft-matter physics to define an unambiguous "internal" rotation frequency for flexible objects such as star polymers under shear flow.
- **Nuclear and condensed-matter potential modeling**: exponential/Fermi-type potential forms mathematically related to the Eckart potential (and to the closely related Woods–Saxon potential) appear in phenomenological nuclear optical-model potentials for nucleon and heavy-ion elastic scattering, and in effective potential models used across nuclear, atomic, and condensed-matter physics wherever a smooth, saturating potential well or barrier with an exactly or quasi-exactly solvable Schrödinger equation is needed.

## 4. Summary Table

| Domain | Typical use of the Eckart potential |
|---|---|
| Chemical kinetics / TST | Analytic tunnelling correction factor for reaction rate constants |
| Combustion & atmospheric chemistry | Correcting rate constants for H-transfer reactions |
| Astrochemistry | Tunnelling-corrected rates for grain-surface/gas-phase reactions at low T |
| Molecular spectroscopy | Model diatomic internuclear potential; vibrational–rotational energy levels |
| Molecular thermodynamics | Vibrational partition functions, thermodynamic properties of diatomics |
| Atomic/mathematical physics | Exactly solvable bound-state/scattering benchmark potential |
| Relativistic quantum mechanics | Klein–Gordon, Dirac, DKP equations with Eckart-type potentials |
| Quantum information theory | Shannon entropy, Fisher information, complexity of Eckart-bound states |
| Molecular/rotational dynamics | Eckart frame — separating vibration from rotation |
| Soft matter physics | Eckart frame applied to polymer rotation under shear flow |
| Nuclear/condensed matter (related forms) | Smooth saturating potential wells/barriers (Woods–Saxon-type kinship) |

## 5. Publications by Application Area

### Foundational
- C. Eckart, "The Penetration of a Potential Barrier by Electrons," *Physical Review* **35**, 1303–1309 (1930).

### Reaction-rate tunnelling corrections
- H. S. Johnston, J. Heicklen, "Tunnelling Corrections for Unsymmetrical Eckart Potential Energy Barriers," *Journal of Physical Chemistry* **66**(3), 532–533 (1962).
- H. S. Johnston, *Gas Phase Reaction Rate Theory*, Ronald Press, New York (1966).
- R. L. Brown, "A Method of Calculating Tunneling Corrections for Eckart Potential Barriers," *Journal of Research of the National Bureau of Standards* **86**(4), 357 (1981).
- J. Espinosa-García, "Transition State Theory and Eckart's Tunnelling Factor: A Good Approximation for the Calculation of Bimolecular Rate Constants?" (H + H₂, D + H₂, H + D₂ benchmark study).
- L. Vereecken, D. R. Glowacki, M. J. Pilling, "Theoretical Chemical Kinetics in Tropospheric Chemistry: Methodologies and Applications," *Chemical Reviews* **115**(10), 4063–4114 (2015).
- S. Canneaux, F. Bohr, E. Hénon et al., "KiSThelP: A Program to Predict Thermodynamic Properties and Rate Constants from Quantum Chemistry Results" (uses Eckart tunnelling correction).

### Astrochemistry / low-temperature kinetics
- Article on interstellar water-ice deuteration chemistry using the Eckart model for transmission probabilities of H-transfer reactions on ices (arXiv:1211.0514).
- Study of D + H₃⁺ → H₂D⁺ + H reaction using the Eckart (1930)/Johnston (1966) tunnelling-corrected rate coefficient (arXiv:1904.02955).

### Diatomic molecule spectroscopy and bound states
- S.-H. Dong, W.-C. Qiang, G.-H. Sun, V. B. Bezerra, "Analytical Approximations to the l-Wave Solutions of the Schrödinger Equation with the Eckart Potential," *Journal of Physics A: Mathematical and Theoretical* **40**, 10535 (2007).
- B. J. Falaye, "Any l-State Solutions of the Eckart Potential via Asymptotic Iteration Method," *Central European Journal of Physics* **10**, 965 (2012).
- E. P. Inyang, E. S. William, E. Omugbe et al., "Application of Eckart–Hellmann Potential to Study Selected Diatomic Molecules Using Nikiforov–Uvarov-Functional Analysis Method," *Revista Mexicana de Física* (2022); also on arXiv:2204.04264.
- Study on "Energy Spectrum and Applications of Eckart plus Hellmann Potential in Hyperspherical Coordinates," *ScienceDirect* (2024).
- E. P. Inyang, J. E. Ntibi, E. P. Inyang, E. S. William, C. C. Ekechukwu, "Any L-State Solutions of the Schrödinger Equation Interacting with Class of Yukawa–Eckart Potentials," *International Journal of Innovative Research in Science, Engineering and Technology* (2020).
- Study on Deng–Fan–Eckart potential thermal properties via Poisson summation (arXiv:2009.09292).
- Study on "Diatomic Molecules with the Improved Deformed Generalized Deng–Fan Potential Plus Deformed Eckart Potential Model through the Solutions of the Modified Klein–Gordon and Schrödinger Equations within NCQM Symmetries."

### Quantum information / complexity measures
- I. Njoku, M. Onuoha, E. K. Egeonu, P. Nwaokafor et al., "Quantum Information of the Modified Möbius Squared Plus Eckart Potential," *International Journal of Quantum Chemistry* (2023).
- C. O. Edet, A. N. Ikot, "Shannon Information Entropy in the Presence of Magnetic and Aharonov–Bohm (AB) Fields," *European Physical Journal Plus* **136**, 432 (2021).

### Eckart frame (vibration–rotation separation) and soft matter
- Paper on "Application of the Eckart Frame to Soft Matter: Rotation of Star Polymers under Shear Flow" (arXiv:1707.09170).

### Related nuclear/optical-potential context (kinship of functional form)
- Review-type sources on heavy-ion elastic-scattering optical potentials and folding models employing Fermi/Woods–Saxon-type smooth potential forms mathematically related to the Eckart function.

---
*Note: Several of the diatomic-molecule and quantum-information articles above originate from a cluster of closely related papers by overlapping author groups (Inyang, Edet, Ikot, Onate, Abu-Shady and collaborators) that have driven much of the recent (2017–2024) literature applying combined Eckart-type potentials to specific diatomic molecules; consult the reference lists within these papers for further, more specialized citations.*

---

> [!NOTE]
> 
> Generated by Claude.ai
>
> Model: Sonet 5
>
> Prompt: Prepare a thorough review of the applications of the Eckart potential in physics and chemistry. Also provide a list of publications related to the listed applications. Show the output in Markdown format. Do not copy the output of the exported files into the chat.
