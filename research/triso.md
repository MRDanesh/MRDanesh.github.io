---
layout: project
title: Radionuclide Release from TRISO-Bearing Fuel Forms
permalink: /research/triso/
---

A TRISO fuel particle is a fuel kernel wrapped in a porous carbon buffer and three dense coatings: inner pyrolytic carbon, silicon carbide (SiC), and outer pyrolytic carbon. The SiC layer is the main barrier against metallic fission products. The particles sit inside a graphite or ceramic matrix, forming pebbles, compacts, or FCM fuel. When this fuel is stored or placed in a geological repository, the radioactivity that eventually escapes (the source term) does not come from one ideal particle. It comes from a large population of particles that differ in coating thickness, irradiation history, and degradation state, and that sit at different distances from cracks and from the outer surface of the fuel.

<figure class="fig-narrow">
  <video src="/images/TRISO/C5P400_flat_cut.mp4" width="500" autoplay loop muted playsinline></video>
  <figcaption>Palladium concentration on a flat cut through the 400-particle compact. The black line is the crack and the orange rings are the gaps around debonded particles. The matrix starts loaded with palladium, which diffuses out through the outer surface of the compact.</figcaption>
</figure>

Fuel-performance codes such as BISON and PARFUME describe in-reactor behaviour in detail, but access to them can be restricted, and they are not designed for transparent, long-time release calculations of degrading waste forms. In this project we are building an open, reduced-order model of radionuclide release that is cheap enough for uncertainty and sensitivity analysis and can later be coupled to repository-scale models. The work is split by scale. Mahyar Malekzade Kebria develops the particle model, where each particle is a set of concentric spherical layers and radionuclides move through them by diffusion, partitioning at layer boundaries, trapping, and decay. I develop the matrix model and the coupling between the two.

In the matrix model, the graphite is a three-dimensional continuum with the particles cut out as voids. Cracks, and the thin gaps that open around particles that have debonded from the matrix, are two-dimensional surfaces embedded in the 3D domain, and the circle where a gap meets a crack is a one-dimensional line. I built this mixed-dimensional model on **[PorePy](https://github.com/pmgbergen/porepy)**. The matrix and the cracks use a multi-point flux approximation, and an algebraic flux-correction limiter keeps the concentration from going negative on these meshes.

The two models are coupled in both directions. On every coupling interval the matrix passes each particle the concentration around it, the particle model returns the moles that crossed its outer surface, and those moles become sources in the matrix. Because the matrix concentration feeds back on the particle, a particle surrounded by matrix that already holds radionuclides releases more slowly. Both solvers book the same moles, and the balance between them is checked on every interval.

So far I have run the coupled model on single-particle cases that add one ingredient at a time (an intact matrix, a crack passing near the particle, and a debonded particle cut by the crack) and on a synthetic compact slice with 400 particles and a tilted crack, in which every particle the crack cuts is debonded. Next come decay chains, sorption in the matrix, and particle properties sampled from a statistical library so that each particle in the compact is different.
