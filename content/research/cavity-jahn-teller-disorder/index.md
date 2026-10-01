---
title: "Disorder in Cavity-Coupled Jahn–Teller Active Molecules"
date: 2026-07-31
summary: "Summer research at IIT Madras (May–July 2026) on how disorder affects polaritons formed by Jahn–Teller active molecules inside an optical cavity."
tags: ["Quantum Electrodynamics", "Cavity QED", "Polaritons", "Jahn–Teller Effect"]
---

{{< katex >}}

<div class="project-meta">
  <p><strong>Institution:</strong> Indian Institute of Technology Madras</p>
  <p><strong>Duration:</strong> May – July 2026</p>
  <p><strong>Supervisors:</strong> Dr. Krishna Nandipati &amp; Dr. Athreya Shankar</p>
</div>

## Overview

When an ensemble of molecules is placed inside an optical cavity and coupled strongly enough
to a confined electromagnetic mode, the molecular excitations and cavity photons hybridise into
new light–matter states called **polaritons**. In this project I studied what happens when the
molecules are *Jahn–Teller active*, so that their electronic and vibrational motion is
strongly entangled, and when the ensemble is **disordered**, as it always is in real samples.

<!-- TODO: Add a two- or three-sentence summary of your main finding here. -->

## Background

### Light–matter coupling in a cavity

A common starting point is the Tavis–Cummings model, in which \(N\) emitters couple to a
single cavity mode:

$$
H = \hbar\omega_c\, a^\dagger a + \sum_{i=1}^{N} \hbar\omega_i\, \sigma_i^\dagger \sigma_i
  + \sum_{i=1}^{N} \hbar g_i \left( a^\dagger \sigma_i + a\, \sigma_i^\dagger \right)
$$

For identical emitters the cavity couples to a single symmetric "bright" superposition with
collective strength \(g\sqrt{N}\), leaving \(N-1\) "dark" states uncoupled from light.

### The Jahn–Teller effect

In the \(E \otimes e\) Jahn–Teller problem, a doubly degenerate electronic state couples
linearly to a doubly degenerate vibrational mode \((x, y)\):

$$
H_{\mathrm{JT}} = \frac{\hbar\omega}{2}\left(p_x^2 + p_y^2 + x^2 + y^2\right)\mathbb{1}
  + k\left(x\,\sigma_z + y\,\sigma_x\right)
$$

The resulting "Mexican-hat" potential energy surface has a conical intersection at the
symmetric point. Because of this, electronic and nuclear motion cannot be separated, and
the molecule's coupling to light changes accordingly.

### Why disorder matters

Real molecular ensembles have **energetic disorder** (a spread in transition energies
\(\omega_i\)) and **orientational disorder** (a spread in couplings
\(g_i \propto \boldsymbol{\mu}_i \cdot \mathbf{E}\)). Disorder mixes the bright and dark
states, which changes polariton linewidths, localisation and how energy moves through
the system.

## What I worked on

<!-- TODO: Describe your specific contributions, for example:
  - the model Hamiltonian you set up and which kinds of disorder you included
  - the numerical methods you used (exact diagonalisation, spectra, dynamics…)
  - key plots: drop images in this folder and use {{</* figure src="plot.png" caption="..." */>}}
  - what you found and what open questions remain
-->

## Skills & methods

<!-- TODO: edit to match what you actually used -->
- Cavity QED and open quantum system models
- Vibronic coupling and the Jahn–Teller effect
- Numerical simulation of light–matter Hamiltonians
