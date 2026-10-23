---
title: "Photoinduced Electron Transfer under Vibrational Strong Coupling"
date: 2025-07-31
summary: "Summer research at the Indian Institute of Science, Bangalore (June–July 2025) on photoinduced electron transfer in hydrogen-bonded donor–acceptor systems placed inside an infrared optical cavity."
tags: ["Vibrational Strong Coupling", "Electron Transfer", "Polaritons", "Spectroscopy", "Experiment"]
---

{{< katex >}}

<div class="project-meta">
  <p><strong>Institution:</strong> Indian Institute of Science, Bangalore</p>
  <p><strong>Group:</strong> Quantum Light Matter Science (QLiMS)</p>
  <p><strong>Duration:</strong> June – July 2025</p>
  <p><strong>Supervisor:</strong> Dr Anoop Thomas</p>
</div>

## Overview

Photoinduced electron transfer (PET) is one of the basic steps of photochemistry: a
photoexcited donor hands an electron to an acceptor. In hydrogen-bonded donor–acceptor
complexes the hydrogen bond both fixes the donor–acceptor distance and acts as a conduit for
the electron, which makes these systems unusually clean places to test electron transfer
theory.

Separately, **vibrational strong coupling (VSC)** — placing molecules in an infrared
Fabry–Pérot cavity tuned to one of their vibrations — is known to change ground-state
chemical reactivity without touching the molecules chemically. This project asked what happens
when the two are combined: can PET in a hydrogen-bonded complex be enhanced or suppressed by
strongly coupling a vibration to a cavity field?

## Background

### Marcus theory and the Rehm–Weller puzzle

Marcus theory describes the electron transfer rate through three parameters: the driving
force \(\Delta G^\circ\), the reorganisation energy \(\lambda\), and the electronic coupling
\(H_{el}\). Its most striking prediction is the **inverted region**, where the rate *falls*
once \(\Delta G^\circ < -\lambda\).

Solution-phase fluorescence quenching studies, summarised by the empirical Rehm–Weller model,
stubbornly failed to show it: the rate rose with exergonicity and then plateaued at the
diffusion limit. The resolution is that Rehm–Weller behaviour is the diffusion-limited
special case of Marcus theory — averaging over donor–acceptor distances in bimolecular
encounters washes the inverted region out.

Hydrogen-bonded complexes settle the argument because both regimes appear in the *same*
sample. Prasad and Gopidas showed that carboxylic acid dimers with a fixed 9.4 Å
donor–acceptor separation and \(H_{el} \approx 5\text{–}50\ \mathrm{cm^{-1}}\) give clean
Marcus behaviour including the inverted region, while the unassociated molecules diffusing in
the same solution follow Rehm–Weller kinetics.

### Reading the two populations off a fluorescence decay

Because the two populations coexist, the fluorescence decay is biexponential,

$$
I(t) = A_1 e^{-t/\tau_1} + A_2 e^{-t/\tau_2},
$$

with the short component \(\tau_1 \approx 1\text{–}10\ \mathrm{ns}\) coming from donors inside
hydrogen-bonded complexes and the long component from unassociated donors undergoing
collisional quenching. The electron transfer rate within the complex follows directly:

$$
k_{\mathrm{et}} = \frac{1}{\tau_1} - \frac{1}{\tau_0},
$$

where \(\tau_0\) is the unquenched donor lifetime. The amplitude ratio \(A_1/A_2\) tracks the
association equilibrium, so a single time-resolved measurement reports on both the kinetics
and how much of the sample is actually complexed. A monoexponential decay, by contrast, means
one homogeneous population.

### Light–matter coupling in a Fabry–Pérot cavity

A cavity of length \(L\) quantises the field into standing-wave modes
\(k_n = n\pi/L\), with free spectral range \(\Delta\omega = \pi c/L\) and mode linewidth
\(\delta\omega = \omega/Q\). A molecular vibration at \(\omega_m\) resonant with a cavity mode
\(\omega_c\) couples with single-molecule strength \(g = \mu E_0/\hbar\).

Strong coupling is reached when the collective coupling \(\Omega = g\sqrt{N}\) exceeds both
the cavity decay rate \(\kappa\) and the molecular linewidth \(\gamma\), i.e.
\(\Omega > (\kappa + \gamma)/2\). The vibration and the photon then hybridise into two
**vibrational polaritons** separated by the Rabi splitting \(\hbar\Omega\), which shows up in
FTIR as an avoided crossing: the bare vibration and cavity resonance disappear and two new
bands take their place. For a typical C=O stretch at \(1700\ \mathrm{cm^{-1}}\), Rabi
splittings of \(100\text{–}500\ \mathrm{cm^{-1}}\) are achievable.

## What I worked on

I put together the theoretical background for the project — Marcus and Rehm–Weller kinetics,
the dual behaviour of hydrogen-bonded complexes, the analysis of mono- and biexponential
fluorescence decays, and the cavity QED description of vibrational strong coupling — and
worked through the design of a cavity able to support it.

The practical half of the problem is cavity fabrication. A VSC cavity is two highly reflective
mirrors (\(>99\%\) in the mid-IR; typically a \(100\ \mathrm{nm}\) evaporated gold bottom
mirror plus a metallic or Bragg top mirror) separated by a spin-coated polymer matrix holding
the molecules. The polymer does three jobs at once: it keeps the mirrors parallel, it sets the
effective refractive index \(n\) (≈ 1.4–1.6 for polymers such as PMMA), and it fixes the
molecular concentration \(N\) available for coupling.

Resonance with a vibration at \(\nu_0\) requires \(L = m\lambda_0 / 2n\). Working this through
for first-order coupling (\(m=1\)) to a C=O stretch at \(1700\ \mathrm{cm^{-1}}\)
(\(\lambda_0 \approx 5.88\ \mu\mathrm{m}\)) in a polymer with \(n = 1.5\) gives
\(L \approx 1.96\ \mu\mathrm{m}\), and a free spectral range
\(\Delta\nu = c/2nL \approx 5100\ \mathrm{cm^{-1}}\) — wide enough that the target vibration is
cleanly isolated from neighbouring cavity modes. Film thickness, and hence the FSR, is tuned
through spin speed (3000–6000 rpm) and spin time (30–60 s). Since the standing wave makes the
coupling spatially varying, molecules sitting at the antinodes interact most strongly with the
field.

## Skills & methods

- Cavity QED and vibrational strong coupling
- FTIR spectroscopy and polariton (Rabi splitting) analysis
- Fabry–Pérot cavity design and fabrication: gold evaporation, spin coating, FSR control
- Time-resolved fluorescence: mono- and biexponential decay fitting, Stern–Volmer analysis
- Marcus and Rehm–Weller electron transfer kinetics
