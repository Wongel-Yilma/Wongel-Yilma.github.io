---
layout: default
title: Grain Growth Simulation in Metal Additive Manufacturing
---

## Grain Growth Simulation in Metal Additive Manufacturing

*Additive manufacturing course project, 2025*
<br>[Code](https://github.com/Wongel-Yilma/AM_microstructure_simulations) · [Report (PDF)](/pdf/AM_grain_growth_report.pdf)

**Summary:** Additive manufacturing (AM) produces complex microstructures that depend on processing conditions, and the link between process and microstructure is still hard to predict. This project uses SPPARKS, an open-source Monte Carlo simulator, to run mesoscale Potts kinetic Monte Carlo simulations of grain growth in 304L stainless steel built by directed energy deposition. The simulations are validated against experimental EBSD data and then used to study how processing parameters affect the grain structure.

---

### 1. Layer-by-layer build simulation

The melt pool geometry is described with Bézier curves, and the deposition is simulated pass by pass and layer by layer, with three passes per layer.

<img src="/images/projects/am-grain-growth/layer_by_layer.jpg" alt="Layer-by-layer Potts simulation"/>
*Layer-by-layer deposition simulated with the Monte Carlo Potts model: (a) first to (d) fourth layer.*

### 2. Validation against EBSD

Simulated grain structures are compared with experimental EBSD maps on three orthogonal cuts. The X-cut shows grains following the melt pool curvature, and the Z-cut shows grains growing along the scan direction, both reproduced by the simulation.

<img src="/images/projects/am-grain-growth/ebsd_vs_mc.jpg" alt="EBSD vs simulated microstructure"/>
*Simulated grain structures (bottom) compared with EBSD maps (top) for the X-, Y- and Z-cuts. EBSD images adapted from Trageser et al. (2023).*

Grain area and eccentricity are compared quantitatively. The X-cut agrees closely with EBSD on both metrics. The Y- and Z-cuts show more scatter but capture the main trends and stay within the same order of magnitude.

<img src="/images/projects/am-grain-growth/validation.jpg" alt="Grain area and eccentricity validation"/>
*Grain area (top) and eccentricity (bottom) distributions, simulation compared with EBSD.*

### 3. Effect of processing parameters

With the model validated, two processing parameters were changed. A 1.71× higher scan speed produced smaller, more equiaxed grains near the melt pool center. A 1.5× larger melt pool led to columnar grains spanning several layers.

<img src="/images/projects/am-grain-growth/perturbation.jpg" alt="Effect of scan speed and melt pool size"/>
*Grain structures with increased scan speed (top) and enlarged melt pool (bottom).*

*SPPARKS · Monte Carlo · Python*

[← Back to portfolio](/)
