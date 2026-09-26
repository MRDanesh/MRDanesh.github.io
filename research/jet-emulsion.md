---
layout: project
title: "From Jet Collision to Emulsion Quality: Nozzle Dynamics and Recirculation"
permalink: /research/jet-emulsion/
---

Oil-based drilling fluids have to be conditioned during offshore drilling so that their rheology and dispersion stay stable. The **[Dual Shear Gun](https://jagtech.no/dual-shear-gun/)** has been proposed as a compact, high-throughput device for fast conditioning: the fluid is sheared hard in a nozzle and then mixed by jets downstream. Experiments look promising, but there is still no predictive framework that links the operating conditions to how much the emulsion is refined inside the device.

In collaboration with **[SINTEF](https://www.sintef.no/en/)**, we built two model problems. The first is a nozzle-resolved model of the hydrodynamics and droplet breakup in the converging nozzle of the Dual Shear Gun. The second is a model of the mixing chamber, used to see how two jets affect the recirculation of the injected fluids. The flow is turbulent, and the drilling fluid follows a Herschel–Bulkley law.

<figure>
  <img src="/images/SINTEFF.gif" alt="Droplet size distributions from the nozzle model and flow development in the mixing chamber">
</figure>

In the nozzle model, a higher pressure drop raises the near-wall shear rate, but the mean flow structure stays broadly the same across operating conditions. As a result, a single pass through the nozzle refines the droplets only slightly more at higher pressure drop. To capture the cumulative effect of conditioning, we introduce an iterative, flow-weighted model that tracks how the contribution of each droplet size evolves over successive passes through the nozzle. It predicts that repeated passes progressively remove the larger droplets, and that the mean characteristic droplet size drops by an order of magnitude after only a few circulations. In the mixing chamber model, two jets placed close together oscillate periodically, which increases recirculation in the chamber.

To model viscoplastic turbulent flows, I developed an eddy-viscosity turbulence solver in OpenFOAM based on the model derived by **[Lovato et al.](https://doi.org/10.1016/j.jnnfm.2021.104729)** The solver and a validation case are available on my **[GitHub](https://github.com/MRDanesh/non-Newtonian-RANS)**.

## Related publications

- **M.R. Daneshvar Garmroodi** and I. Karimfazli (2026). **A novel iterative method to enhance emulsion quality in non-Newtonian fluids**. *In preparation for the Journal of Non-Newtonian Fluid Mechanics*.
- **M.R. Daneshvar Garmroodi** and I. Karimfazli (2026). **From jet collision to emulsion quality: nozzle dynamics**. *45th International Conference on Ocean, Offshore and Arctic Engineering*.
- **M.R. Daneshvar Garmroodi** and I. Karimfazli (2026). **From jet collision to emulsion quality: fluid mixing**. *45th International Conference on Ocean, Offshore and Arctic Engineering*.
