---
title: "The Jaynes–Cummings Model in Five Minutes"
date: 2026-09-15
summary: "A two-level atom in a single-mode cavity: the Hamiltonian, the rotating-wave approximation and vacuum Rabi splitting."
tags: ["Quantum Optics", "Cavity QED"]
---

{{< katex >}}

The Jaynes–Cummings model is the simplest fully quantum description of light–matter
interaction: one two-level atom coupled to one mode of the electromagnetic field. It is a
good starting point for more realistic models such as Tavis–Cummings, which has many emitters,
or models with vibronic structure.

## The Hamiltonian

Let the atom have ground and excited states \(|g\rangle, |e\rangle\) separated by
\(\hbar\omega_a\), and let the cavity mode have frequency \(\omega_c\) and annihilation
operator \(a\). Within the dipole approximation, the light–matter coupling is
\(\hbar g\,(a + a^\dagger)(\sigma_+ + \sigma_-)\).

## The rotating-wave approximation

Expanding the product gives four terms. Two of them, \(a\sigma_+\) and \(a^\dagger\sigma_-\),
conserve the number of excitations and oscillate slowly in the interaction picture. The other
two, \(a^\dagger\sigma_+\) and \(a\sigma_-\), oscillate at \(\omega_a + \omega_c\). When
\(g \ll \omega_a, \omega_c\) these fast terms average out, and dropping them gives

$$
H_{\mathrm{JC}} = \hbar\omega_c\, a^\dagger a + \frac{\hbar\omega_a}{2}\,\sigma_z
  + \hbar g\left(a\,\sigma_+ + a^\dagger \sigma_-\right).
$$

## Dressed states

\(H_{\mathrm{JC}}\) conserves the total excitation number, so it only couples
\(|e, n\rangle\) with \(|g, n+1\rangle\). Diagonalising each \(2\times 2\) block with detuning
\(\Delta = \omega_a - \omega_c\) gives

$$
E_{n,\pm} = \hbar\omega_c\left(n + \tfrac{1}{2}\right)
  \pm \frac{\hbar}{2}\sqrt{\Delta^2 + 4g^2(n+1)}.
$$

The eigenstates \(|n, \pm\rangle\) are the *dressed states*, which are entangled
superpositions of atom and photon.

## Vacuum Rabi splitting

On resonance \((\Delta = 0)\), even the single-excitation manifold \((n = 0)\) splits by
\(2\hbar g\). An excited atom in an empty cavity therefore exchanges its energy with the
field coherently, oscillating at the vacuum Rabi frequency \(2g\). This is observable when \(g\)
exceeds the cavity and atomic loss rates, which is the **strong-coupling regime**. Because the
splitting grows as \(\sqrt{n+1}\), the spectrum is anharmonic, which is a direct signature of
field quantisation.

## From one atom to many

With \(N\) identical atoms the coupling to the symmetric state is enhanced to \(g\sqrt{N}\).
This collective enhancement makes strong coupling reachable with molecular ensembles, and it
is the starting point for the physics of molecular polaritons.
