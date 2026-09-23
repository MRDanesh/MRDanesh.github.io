---
layout: project
title: Mixing Localization in Yield-Stress Fluids
permalink: /research/yield-stress-mixing/
---

The goal of this study is to identify the mechanisms behind the different mixing regimes, and the localization of mixing, in yield-stress fluids. We studied the stirring of an infinite, two-dimensional domain filled with a Bingham fluid. A cylindrical stirrer moves along a circular path at constant speed. The domain starts at rest, and a passive dye marks its lower half, so we can follow how the dye interface evolves and how mixing develops.

<figure>
  <img src="/images/regimes.gif" alt="Regime map of mixing in yield-stress fluids with vorticity fields for each regime">
</figure>

We first look at mixing in Newtonian fluids and identify three mechanisms: stretching and folding of the interface around the stirrer's path, diffusion across streamlines, and advection and stretching of the dye by shed vortices. Adding a yield stress localizes mixing in three ways. Shed vortices are advected only a finite distance from the stirrer, vortices can be trapped near the stirrer, and at high yield stress vortex shedding stops altogether. From these mechanisms we classify three mixing regimes in yield-stress fluids: (i) Regime SE, where shed vortices escape the central region, (ii) Regime ST, where shed vortices stay trapped near the stirrer, and (iii) Regime NS, where no vortex shedding occurs.

A spectral analysis of energy oscillations separates the regimes quantitatively and gives the transitions and the critical Bingham and Reynolds numbers. Effective Reynolds numbers capture these transitions, which supports the hypothesis that regime transitions in yield-stress mixing share their basic features with flow past a bluff body. The results give a mechanistic framework for understanding and predicting mixing in yield-stress fluids, and we expect the localization mechanisms and regimes found here to be representative of stirred-tank applications.

As part of my PhD thesis, I extended the OpenFOAM solver twoLiquidMixingFoam with a dynamic mesh to simulate these flows. The solver is available on my **[GitHub](https://github.com/MRDanesh/twoLiquidMixingDyMFoamVol)**.

## Related publications

- **M.R. Daneshvar Garmroodi** and I. Karimfazli (2025). **[Yield-stress fluid mixing: localisation mechanisms and regime transitions](https://doi.org/10.1017/jfm.2025.10729)**. *Journal of Fluid Mechanics*, 1021, A42.
- **M.R. Daneshvar Garmroodi** and I. Karimfazli. **Mixing dynamics and vortex shedding in laminar stirring flows**. *Submitted to Physics of Fluids*.
