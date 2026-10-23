---
title: "Marcus Theory and the Missing Inverted Region"
date: 2025-08-10
summary: "Why the Marcus inverted region refused to show up in solution-phase fluorescence quenching for decades, and how hydrogen-bonded complexes made both regimes visible in one sample."
tags: ["Photochemistry", "Electron Transfer", "Spectroscopy"]
---

{{< katex >}}

Marcus theory predicts that the electron transfer rate should *fall* once a reaction becomes
too exergonic. For about thirty years, solution-phase experiments refused to show it. The
resolution is a nice lesson in how an averaging artefact can hide real physics.

## The prediction

Marcus describes the rate through three parameters — the driving force \(\Delta G^\circ\), the
reorganisation energy \(\lambda\) and the electronic coupling \(H_{el}\) — with the rate
carrying the Gaussian factor

$$
k_{\mathrm{et}} \propto |H_{el}|^2 \exp\!\left[-\frac{(\Delta G^\circ + \lambda)^2}{4\lambda k_B T}\right].
$$

The rate is maximal at \(\Delta G^\circ = -\lambda\) and *decreases* beyond it. That is the
**inverted region**.

## The experiments that didn't see it

Rehm and Weller's 1970 study of fluorescence quenching established the opposite empirical
picture: the rate rises with exergonicity and then simply plateaus at the diffusion limit. No
turnover. The model worked so well at describing the data that diffusion became accepted as the
dominant factor masking the intrinsic kinetics in flexible donor–acceptor systems.

The disagreement persisted until it was recognised that Rehm–Weller behaviour is not a rival
theory but a **diffusion-limited special case** of Marcus theory. In a bimolecular encounter
the donor and acceptor meet at a distribution of separations; averaging the
distance-dependent rate over that distribution smears out the turnover. The inverted region is
real, but it is only observable once distance fluctuations are suppressed.

## Both regimes in one sample

Hydrogen-bonded donor–acceptor complexes resolve this directly. A fraction of the molecules sit
in associated complexes at a fixed separation; the rest diffuse freely in the same solution.
Prasad and Gopidas showed that carboxylic acid dimers with a 9.4 Å donor–acceptor separation
and \(H_{el} \approx 5\text{–}50\ \mathrm{cm^{-1}}\) give textbook Marcus behaviour, inverted
region included, while the unassociated molecules in the same sample follow Rehm–Weller
kinetics and never exceed the diffusion limit.

Observing both regimes simultaneously is about as direct a confirmation as one could ask for —
and it pins the cause of the discrepancy on molecular organisation rather than on the theory.

## Reading it off the decay

Because the two populations coexist, the fluorescence decay is biexponential:

$$
I(t) = A_1 e^{-t/\tau_1} + A_2 e^{-t/\tau_2}.
$$

The short component (\(\tau_1 \approx 1\text{–}10\ \mathrm{ns}\)) is the hydrogen-bonded
complexes, where the fixed distance allows fast charge separation; the long component is the
unassociated donors undergoing collisional quenching, following the time-dependent
Stern–Volmer form with its characteristic \(\sqrt{t}\) transient term. The rate inside the
complex comes straight out:

$$
k_{\mathrm{et}} = \frac{1}{\tau_1} - \frac{1}{\tau_0},
$$

and the amplitude ratio \(A_1/A_2\) tracks the association equilibrium. A monoexponential
decay means one homogeneous population; the second exponential *is* the signature that two
distinct environments coexist.

There is also a hierarchy of timescales worth remembering: femtosecond IR work by Zhong and
coworkers puts hydrogen-bond reorganisation at roughly 80 fs, well before the 1–10 ps electron
transfer itself. The hydrogen bond is both scaffold and participant.

This is the background to my
[IISc project]({{< ref "research/vibrational-spectroscopy-iisc" >}}), which asked whether
vibrational strong coupling can modify these transfer rates without changing the chemistry.
