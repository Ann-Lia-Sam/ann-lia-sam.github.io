---
title: "Bright and Dark States, and What Disorder Does to Them"
date: 2026-08-10
summary: "Why N molecules in a cavity give one bright state and N−1 dark ones, and how the random arrowhead matrix explains what happens when the molecules are not identical."
tags: ["Quantum Optics", "Cavity QED", "Polaritons", "Disorder"]
---

{{< katex >}}

The collective enhancement \(g\sqrt{N}\) is what makes strong coupling reachable with molecular
ensembles. The price is that most of the ensemble stops talking to light at all. This note is
the short version of why, and of what goes wrong when the molecules are not identical.

## One bright state, N−1 dark ones

Take \(N\) identical two-level emitters coupled to one cavity mode with equal strength \(g\).
In the single-excitation subspace the cavity only ever couples to the symmetric combination

$$
|B\rangle = \frac{1}{\sqrt{N}}\sum_{n=1}^{N} \sigma_n^+ |G\rangle ,
$$

with enhanced strength \(\sqrt{N}g\). The two polaritons are
\(|\pm\rangle = (|G,1_{\mathrm{ph}}\rangle \pm |B\rangle)/\sqrt{2}\), split by \(2\sqrt{N}g\).
The remaining \(N-1\) orthogonal combinations carry **no photon weight whatsoever** — the
**dark states**. They are degenerate, they sit at the bare molecular energy, and they are
invisible in absorption.

This separation is exact, and it rests entirely on permutation symmetry: it needs the emitters
to be identical. Real ensembles are not.

## The arrowhead matrix

With static energy disorder — each molecule's transition energy drawn as
\(\epsilon_n = \epsilon + \delta_n\) — the single-excitation Hamiltonian becomes an
\((N+1) \times (N+1)\) **arrowhead matrix**: the random molecular energies on the diagonal, and
the photon coupled to every one of them with strength \(g_c/\sqrt{N}\),

$$
H =
\begin{pmatrix}
\epsilon_1 & & & g \\
 & \ddots & & \vdots \\
 & & \epsilon_N & g \\
g & \cdots & g & \omega_c
\end{pmatrix}.
$$

Two facts follow, and they are the whole story.

**Dark states brighten.** The photon weight \(\mathrm{PW}_a = |\langle G, 1_{\mathrm{ph}} | \psi_a \rangle|^2\)
is \(O(1)\) for each of the two polaritons but \(O(1/N)\) for each dark state — so \(O(1)\) in
total. The dark manifold collectively steals a finite share of the photon, and states that were
strictly invisible **appear in absorption**. To leading order the stolen weight goes as
\(W^2/g_c^2\).

**Polaritons stay protected, until they don't.** The dark eigenvalues *interlace* the bare
molecular energies, so the two polaritons are the only outliers of the band. They are pushed
outside it by \(\pm g_c\) and survive as well-defined hybrid modes as long as
\(W \lesssim g_c\). Once the disorder width exceeds the collective splitting they sink into
the band and lose their photon weight.

The crossover sits around \(W \sim 2g_c\). Note what this means: since the absorption intensity
of an eigenstate *is* its photon weight, the measured spectrum is exactly the photon spectral
function \(A(\omega) = \sum_a \mathrm{PW}_a\, \delta(\omega - \varepsilon_a)\).

## Disorder is not simply detrimental

The tempting conclusion — more disorder, worse physics — is wrong. Wellnitz, Pupillo and
Schachenmayer found the effect to be **non-monotonic**: disorder-enhanced excitation transfer
and vibrational entanglement *peak* at \(W \sim g_c\) rather than decaying from zero.

The mechanism is bright/dark mixing. Pushing the bright polariton *towards* a dense manifold of
otherwise-dark states lets many of them borrow photon weight and light up. Pushing it *away* —
or mixing far too strongly — destroys the hybridisation instead. Which of the two happens is
governed by proximity to cavity resonance and to the collective coupling scale, not by the
disorder magnitude alone. I ran into exactly this in my
[cavity Jahn–Teller work]({{< ref "research/cavity-jahn-teller-disorder" >}}), where two
realisations with very different mismatches could be equally dead, and two with similar
magnitudes could be enhanced or destroyed depending on direction.
