---
layout: project
title: "Interpretable Reduced-Order Model for Periodic Flows: POD Oscillators vs DMD"
permalink: /research/pod-dmd/
---

This project compares two classic reduced-order modelling approaches for predicting the 2D cylinder wake flow field from simulation snapshots.

For the POD-based model (4 modes), POD on the training window gives the dominant spatial modes. The corresponding temporal coefficients are modelled as oscillatory signals: two dominant frequencies are estimated from the phase dynamics of the coefficients, and each coefficient is fitted with a sinusoidal regression model. The predicted coefficients then reconstruct the flow field in the test window.

The DMD model (rank 4) is trained on the same window and identifies a low-rank linear model that advances the flow in time. Its modes and eigenvalues are used to roll out the dynamics and predict the test snapshots directly in field space.

The goal is a clean, interpretable baseline for periodic flows, and a comparison between modelling the POD coefficients and DMD's spectral prediction.

<figure>
  <img src="/images/POD.png" alt="POD prediction compared with ground truth and relative error">
  <figcaption>POD prediction.</figcaption>
</figure>

<figure>
  <img src="/images/DMD.png" alt="DMD prediction compared with ground truth and relative error">
  <figcaption>DMD prediction.</figcaption>
</figure>

The code and the mathematical formulation are available on my **[GitHub](https://github.com/MRDanesh/POD_DMD)**.
