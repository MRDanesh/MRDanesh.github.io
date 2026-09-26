---
layout: project
title: Buoyancy-Driven Melting in Phase-Change Materials With Embedded Heat Spreaders
permalink: /research/pcm-melting/
---

Phase-change materials (PCMs) are used for thermal management in photovoltaic panels and electronic cooling devices, but they are often used inefficiently. The problem comes from the lack of natural convection in the melted PCM. In this work, done in collaboration with Université de Lorraine, we built a simplified benchmark model to study how embedded high-conductivity inserts can improve heat transport in PCMs.

<figure>
  <img src="/images/PCM.gif" alt="Melting of a phase-change material with and without embedded conductors">
</figure>

The system is heated from the top at a fixed temperature and insulated at the bottom. This mimics a sink-limited scenario, where heat has to be redistributed inside the material because it cannot be rejected externally. We tested several conductor topologies and measured their effect on latent heat utilization and on the onset of buoyancy-driven flow in the melted PCM. The outcome is a set of design insights for using conductor networks to lower the hot-side temperature and make melting more uniform.

To simulate the melting process, I developed an enthalpy-based solver in OpenFOAM. The code is available on my **[GitHub](https://github.com/MRDanesh/conjugateMeltingFOAM)**.

## Related publications

- **M.R. Daneshvar Garmroodi** and I. Karimfazli. **Enhancement of buoyancy-driven melting**. *In preparation for the International Journal of Heat and Mass Transfer*.
