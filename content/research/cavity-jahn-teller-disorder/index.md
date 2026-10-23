---
title: "Disorder in Cavity-Coupled Jahn–Teller Active Molecules"
date: 2026-07-31
summary: "Summer research at IIT Madras (May–July 2026): from single-molecule cavity Jahn–Teller polaritons to disorder-averaged collective spectra, and what static energy disorder does to the collective vibronic cascade."
tags: ["Quantum Electrodynamics", "Cavity QED", "Polaritons", "Jahn–Teller Effect", "Disorder", "Numerics"]
---

{{< katex >}}

<div class="project-meta">
  <p><strong>Institution:</strong> Indian Institute of Technology Madras</p>
  <p><strong>Duration:</strong> May – July 2026</p>
  <p><strong>Supervisors:</strong> Prof. Krishna R. Nandipati (Chemistry) &amp; Prof. Athreya Shankar (Physics)</p>
</div>

## Overview

Put \(N\) molecules in a Fabry–Pérot cavity and couple them strongly enough to a confined
field, and molecular excitation and cavity photon hybridise into **polaritons**. For
identical molecules the cavity talks to a single bright symmetric superposition with collective
strength \(\sqrt{N}g\), leaving \(N-1\) **dark states** with no photon weight at all.

This project takes molecules that are **Jahn–Teller (JT) active**, so that electronic and
vibrational motion are inseparable, and asks what **static energy disorder** does to them —
because real ensembles are never identical, and the clean bright/dark split relies on exactly
the permutation symmetry that disorder destroys.

The headline result: **whether disorder destroys the collective physics is not set by how big
the disorder is.** What matters is the *direction* — whether the drawn energies push the bright
polariton towards the dense manifold of otherwise-dark states or pull it away. In the
favourable direction disorder *enhances* the observable cascade; in the unfavourable ones it
kills it, by two distinct routes.

## Background

### The \((E \times e)\) Jahn–Teller problem

The Jahn–Teller theorem says a non-linear molecule in an orbitally degenerate electronic state
is unstable: it distorts along a non-totally-symmetric coordinate to lift the degeneracy. In
the \((E \times e)\) problem a doubly degenerate electronic state \(E\) couples to a doubly
degenerate vibrational mode \((Q_x, Q_y)\), producing the "Mexican hat" surface with a
**conical intersection** at the symmetric point. This work uses the sym-triazine
(\(D_{3h}\)) parameter set throughout.

In the complex electronic basis \(|E_\pm\rangle = (|E_x\rangle \pm i|E_y\rangle)/\sqrt{2}\) the
JT Hamiltonian is

$$
\hat H_{\mathrm{JT}} = \sum_{r=\pm} \left[\hbar\omega\, \hat b_r^\dagger \hat b_r +
  \epsilon\,|E_r\rangle\langle E_r|\right] +
  \frac{\kappa}{\sqrt{2}}\Big\{\big(\hat b_+^\dagger + \hat b_-\big)|E_-\rangle\langle E_+| + \mathrm{H.c.}\Big\},
$$

which makes the key point explicit: the vibronic coupling **exchanges angular momentum**
between the electronic subspace and the vibrational pseudorotation. That is what lets JT
systems trade angular momentum with circularly polarised light.

### Conserved quantities

Coupling the \(|A\rangle \leftrightarrow |E_\pm\rangle\) transitions to the two circularly
polarised cavity modes within the rotating-wave approximation, the total Hamiltonian conserves
the excitation number \(\hat N_{\mathrm{ex}}\) and the total vibronic–photonic angular momentum

$$
\hat J = \sum_{k=1}^{N} \big(2\hat L_{z,k} + \hat S_{z,k}\big) + \hat P .
$$

Everything here is computed in the optically relevant single-excitation block
\((n_{\mathrm{ex}} = 1,\ j = -1)\).

### The collective vibronic cascade

For a **single** molecule, conservation of \(j\) forces the vibronic sector
\(v \in \{0, -1, -2\}\) — a bounded range, and hence modest spectral structure.

{{< figure src="single-molecule-spectrum.png" caption="Single-molecule cavity Jahn–Teller polariton spectrum (reproducing Nandipati & Vendrell). Grey: the bare (E×e) JT absorption spectrum of sym-triazine. Blue: the cavity polaritonic spectrum, with the stick spectrum underneath. Switching the cavity on redistributes the bare oscillator strength into well-separated LP and UP branches." >}}

For **two or more** molecules this changes qualitatively. The conserved quantity is the
*total* \(v = \sum_k v_k\), still restricted to \(\{0,-1,-2\}\), but the individual \(v_k\) are
now free: one molecule can be driven to large positive \(v_1\) if the other compensates with
large negative \(v_2\). The cavity photon, repeatedly absorbed and re-emitted by different
molecules, *mediates* this exchange — the **collective vibronic cascade**, an unbounded ladder.

The spread is measured by the **participation ratio** \(\mathrm{PR} = 1/\sum_v P^2(v)\).
\(N=1\) is bounded at \(\mathrm{PR} \le 3\); \(N=2\) reaches \(\mathrm{PR} \approx 20\).

{{< figure src="vibronic-sector-heatmap.png" caption="Clean (σ = 0) N = 2 vibronic-sector heatmap: for each bright polaritonic eigenstate (x, energy-ordered) the distribution P(v) over sectors (y). 42 bright eigenstates, PR_max = 19.9, sectors v ∈ [−14, 13]. This is the reference against which every disordered case is compared." >}}

## What I worked on

### Adding disorder

Each molecule's excited-state energy is drawn independently from a Gaussian,
\(\epsilon_i \sim \mathcal{N}(\epsilon, W^2)\) with \(\epsilon = 7.0\ \mathrm{eV}\), following
the disordered Holstein–Tavis–Cummings model of Wellnitz *et al.* and the random-arrowhead
analysis of Dubail *et al.* In the arrowhead picture the single-excitation Hamiltonian is an
\((N+1)\times(N+1)\) matrix with the random molecular energies on the diagonal and the photon
— the "arrow tip" — coupled to all of them. Two consequences matter: dark states collectively
steal a finite share of the photon and so **appear in absorption**, and the polaritons remain
well-defined outliers of the band only while the coupling beats the disorder.

I fixed the disorder width at \(W = 0.48\ \mathrm{eV}\), i.e. \(W/g \approx 2.0\),
\(W/\sqrt{N}g \approx 1.4\), \(W/\Omega \approx 0.70\) — deliberately just *below* the
\(W \sim 2g_c\) crossover, where individual realisations are physically distinct rather than
all reproducing the clean result.

### Numerics

- **Basis.** Product states \((e_1, n_{+1}, n_{-1}, e_2, n_{+2}, n_{-2}, p_+, p_-)\); at a
  vibrational cutoff \(N_v = 12\) the full space is 746 496 states.
- **Symmetry filtering.** Keeping only \(n_{\mathrm{ex}} = 1,\ j = -1\) cuts this to 6 900 — a
  factor of 108, which is what makes a converged calculation feasible.
- **Assembly.** The disorder-independent part is built once per \(N_v\); only the electronic
  diagonal is rebuilt per realisation.
- **Spectra.** Exact diagonalisation; the intensity of an eigenstate is its overlap with
  (both molecules in the vibronic ground state + one RCP photon), which by the arrowhead result
  *is* its photon weight. Lines are Lorentzian-broadened (\(\gamma = 0.025\ \mathrm{eV}\)) and
  averaged over \(M = 100\) realisations.
- **Validation.** Two regression tests (the representative-case analysis replays the same
  random stream as the average; the independent vibronic-basis route for the heatmaps
  reproduces the direct route to \(\sim 10^{-9}\) with \(\sum_v P(v) = 1\)), plus a
  near-zero-disorder draw as a physical control that must — and does — reproduce the clean
  result.

### Representative realisations

A disorder-*averaged* spectrum hides the mechanism: it superposes 100 very different individual
spectra. So instead I analysed the cloud of drawn pairs \((\epsilon_1, \epsilon_2)\) directly
and selected **eight physically meaningful realisations**, Cases A–H, each defined by a
criterion on the energies actually drawn. Two orthogonal coordinates organise the plane:

$$
s = \frac{\delta_1 + \delta_2}{2} \quad\text{(common-mode shift)}, \qquad
\Delta = \epsilon_1 - \epsilon_2 \quad\text{(inter-molecular mismatch)},
$$

where \(s\) moves both molecules together relative to the photon and is compared with the
collective coupling \(\sqrt{N}g\), while \(\Delta\) breaks permutation symmetry and is compared
with the per-molecule coupling \(g\).

| Case | Criterion | \(\Delta\) | \(s/g\) | #bright | \(\mathrm{PR_{max}}\) |
|---|---|---|---|---|---|
| A | resonant baseline | 0.02 | 0.0 | 39 | 20.6 |
| D | common blue detuning | 0.17 | +1.0 | 12 | 12.5 |
| E | common red detuning | 0.03 | −1.3 | 104 | 22.4 |
| F | single-molecule resonant | 0.26 (\(g\)) | −0.5 | 132 | 21.6 |
| H | A–C line, interior | 0.61 (2.5\(g\)) | 0.0 | 46 | 16.2 |
| C | opposite disorder (far) | 1.49 (6\(g\)) | 0.0 | 14 | 8.5 |
| B | large mismatch (same side) | 1.00 (4\(g\)) | +2.4 | 11 | 3.8 |
| G | bare-molecule limit | 0.10 | −3.3 | 8 | 4.5 |

*(Clean \(\sigma = 0\) reference: 42 bright states, \(\mathrm{PR_{max}} = 19.9\).)*

**What the cases show.** Case A is the internal control — drawn essentially on resonance and
matched, it reproduces the clean spectrum peak for peak. Cases D and E keep the molecules
matched but shift them together, and are *not* mirror images: E's red shift moves its
molecule-like branch into a dense stretch of bare JT structure where many sub-levels borrow
enough photon weight to light up (104 bright states), while D's blue shift moves it into a
sparser stretch (only 12). Case F brings one molecule back onto resonance while the other stays
detuned by \(-g\), sitting right at the crossover, and is the richest of all: 132 bright
states.

Push the mismatch further (H → C) and the cascade weakens monotonically,
\(\mathrm{PR_{max}}: 20.6 \to 16.2 \to 8.5\). Cases B and G are both "dead" at nearly the same
\(\mathrm{PR_{max}} \approx 4\), but — and this is one of the main results — they die by
*different* mechanisms. **B dies along the mismatch axis**: \(\Delta \gg g\) decouples the
molecules from each other, the excitation localises on the resonant one, and the spectrum
reverts to a single JT polariton with a clean Franck–Condon progression, overlaying an
independently computed one-molecule spectrum. **G dies along the common-mode axis**: the
molecules stay perfectly matched but \(|s| \gg \sqrt{N}g\) puts both outside the polariton
band, so the bright eigenstate reverts to the bare cavity photon and the cavity-mediated
exchange is switched off.

Ordering by \(\mathrm{PR_{max}}\) splits the cases into three groups rather than a smooth
trend — E, F, A at or above the clean value; H, D, C in a middle band; G, B an order of
magnitude lower. The grouping does **not** follow \(\Delta\) alone: Case G's mismatch
(\(0.10\)) is far smaller than Case H's (\(2.5g\)), yet G is dead and H only partly degraded.

### Caveats

Each case is a single extremal draw chosen to illustrate a mechanism, so quantitative claims
would need averaging over all realisations at fixed \(W\); the bright-state count depends on
the brightness threshold; and the bright/dark language is borrowed from the
\(N \to \infty\) arrowhead limit, proved for the disordered Tavis–Cummings model rather than a
JT vibronic cascade. Extending that proof to this model, and to \(N = 2\) specifically, remains
to be done.

The natural continuations are to map PR over the mismatch and common-mode shift at several
disorder widths, to separate convergence in \(N_v\) from the disorder effect, and to push to
\(N > 2\), where the dark manifold becomes a genuine band and the arrowhead predictions apply
quantitatively.

## Skills & methods

- Cavity QED, Tavis–Cummings and Holstein–Tavis–Cummings models
- Vibronic coupling, the \((E \times e)\) Jahn–Teller effect and conical intersections
- Symmetry analysis and conserved-quantum-number block diagonalisation
- Large-scale exact diagonalisation (NumPy/SciPy), disorder averaging, regression testing
- Spectral and participation-ratio analysis; scientific plotting with Matplotlib
