---
layout: project
title: Sparse and Physics-Informed Reconstruction of Fluid Flows
permalink: /research/sparse-pinns/
---

This project compares two very different ways of reconstructing a full fluid flow field from sparse sensor measurements, using the classic dataset of a 2D incompressible cylinder wake. The goal is to recover the complete velocity and pressure fields from a limited number of spatial sensors. I implemented and compared a sparse snapshot-based method rooted in compressed sensing and a physics-informed neural network (PINN) that enforces the Navier–Stokes equations during training.

The sparse method assumes that any flow snapshot can be written as a sparse combination of previously observed snapshots. Solving a LASSO problem selects the few training snapshots that best match the sensor measurements. The method is fast, interpretable, and very accurate when the test flow lies within the span of the training data, but it is an interpolation and does not enforce any physical law.

The PINN instead learns a neural network that maps space and time coordinates to velocity and pressure, while minimizing both the mismatch with the data and the residuals of the Navier–Stokes equations. The physics constraint gives smooth, physically consistent reconstructions that can generalize beyond the training snapshots. Comparing the two shows the tradeoff between sparse, data-driven interpolation and physics-informed learning when reconstructing a dynamical system from limited observations.

<div class="fig-pair">
  <figure>
    <img src="/images/sparse.png" alt="Sparse reconstruction result">
    <figcaption>Sparse snapshot method (LASSO) result.</figcaption>
  </figure>
  <figure>
    <img src="/images/PINNs.png" alt="PINN reconstruction result">
    <figcaption>PINN (Navier–Stokes) result.</figcaption>
  </figure>
</div>

The code and the mathematical formulation are available on my **[GitHub](https://github.com/MRDanesh/Sparse_PINNs)**.
