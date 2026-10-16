## Publications

---

### Learning the governing partial differential equation of solid diffusion from atomistic simulations

**W. Nadew**, H. Wang — *Proceedings of the Royal Society A*, 481(2322), 2025
<br>[Paper](https://royalsocietypublishing.org/rspa/article/481/2322/20250383/234348/Learning-the-governing-partial-differential) · [DOI: 10.1098/rspa.2025.0383](https://doi.org/10.1098/rspa.2025.0383)

Molecular dynamics (MD) captures atomistic physics in detail, but turning that into continuum-scale governing equations is hard. This work develops a data-driven framework that learns governing PDEs directly from noisy, limited MD data, combining numerical differentiation of the MD data with identification of constitutive relationships, with no prior knowledge of the final PDE. Applied to nickel–hydrogen alloys, it identifies a nonlinear PDE for solid-state diffusion whose diffusivity depends strongly on concentration, varying by over an order of magnitude.

---

## Projects

---

### Physics-Informed Neural Networks for PDE Discovery (PINN-SR)

[Code](https://github.com/Wongel-Yilma/PINN-SR) · [Project proposal (PDF)](/pdf/PINN_SR_proposal.pdf)

Sparse regression can discover PDEs from data, but it is sensitive to noise, which numerical differentiation amplifies. This project combines physics-informed neural networks (PINNs) with sparse regression to recover the diffusion equation from random-walk Monte Carlo simulation data, with no prior knowledge of the underlying equation. The framework was tested on three datasets with different boundary conditions (deposition, deletion and zero-flux), and the effect of hyperparameters on the identified PDE was analyzed.

*Python · PyTorch · Jupyter*

---

### Grain Growth Simulation in Metal Additive Manufacturing

[Code](https://github.com/Wongel-Yilma/AM_microstructure_simulations) · [Report (PDF)](/pdf/AM_grain_growth_report.pdf)

Mesoscale Potts kinetic Monte Carlo simulations of grain structure formation in metal additive manufacturing, run with the open-source SPPARKS simulator. The study relates melt pool geometry and temperature profiles to grain size and shape in 304L stainless steel built by directed energy deposition. Simulated microstructures are validated against experimental EBSD grain maps, and the influence of scan speed and melt pool size on grain growth is investigated.

*SPPARKS · Monte Carlo · Python*

---

### Entropic Regression in Python

[Code](https://github.com/Wongel-Yilma/Entropic-Regression)

A Python port of [Entropic Regression](https://github.com/almomaa/Entropic-Regression), an information-theoretic method for sparse model identification that is robust to noise and outliers. Originally implemented in MATLAB, it is applied here to benchmark dynamical systems such as the Lorenz system and to PDE discovery from Monte Carlo and molecular dynamics data, using a PDE-FIND candidate-term library.

*Python · NumPy*

---

### 2D Ising Model

Monte Carlo simulation of the two-dimensional Ising model of ferromagnetism using the Metropolis algorithm. It studies how magnetization, energy, specific heat and susceptibility vary with temperature, and shows the phase transition near the critical temperature.

*Python · Monte Carlo*

---
<p style="font-size:11px">Page template forked from <a href="https://github.com/evanca/quick-portfolio">evanca</a></p>
<!-- Remove above link if you don't want to attibute -->
