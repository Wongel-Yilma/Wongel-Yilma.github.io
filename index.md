## Publications

---

### [Learning the governing partial differential equation of solid diffusion from atomistic simulations](/projects/md-diffusion)

**W. Nadew**, H. Wang — *Proceedings of the Royal Society A*, 481(2322), 2025
<br>[Project page](/projects/md-diffusion) · [Paper](https://royalsocietypublishing.org/rspa/article/481/2322/20250383/234348/Learning-the-governing-partial-differential) · [DOI: 10.1098/rspa.2025.0383](https://doi.org/10.1098/rspa.2025.0383)

<a href="/projects/md-diffusion"><img src="/images/projects/md-diffusion/workflow.jpg" alt="PDE identification workflow"/></a>

A data-driven framework that learns governing PDEs directly from noisy, limited molecular dynamics data, with no prior knowledge of the final equation. Applied to hydrogen in nickel, it finds a nonlinear diffusion PDE whose diffusivity varies by more than an order of magnitude with concentration.

---

## Projects

---

### [Physics-Informed Neural Networks for PDE Discovery (PINN-SR)](/projects/pinn-sr)

[Project page](/projects/pinn-sr) · [Code](https://github.com/Wongel-Yilma/PINN-SR) · [Report (PDF)](/pdf/PINN_SR_proposal.pdf)

<a href="/projects/pinn-sr"><img src="/images/projects/pinn-sr/architecture.jpg" alt="PINN-SR architecture"/></a>

A physics-informed neural network combined with sparse regression recovers the diffusion equation from noisy Monte Carlo random-walk data, with the diffusion coefficient within 3% of the analytical value.

*Python · PyTorch*

---

### [Grain Growth Simulation in Metal Additive Manufacturing](/projects/am-grain-growth)

[Project page](/projects/am-grain-growth) · [Code](https://github.com/Wongel-Yilma/AM_microstructure_simulations) · [Report (PDF)](/pdf/AM_grain_growth_report.pdf)

<a href="/projects/am-grain-growth"><img src="/images/projects/am-grain-growth/ebsd_vs_mc.jpg" alt="Simulated vs EBSD grain structures"/></a>

Potts kinetic Monte Carlo simulations in SPPARKS of grain growth in 304L stainless steel built by directed energy deposition. The simulations are validated against EBSD maps and used to study the effects of scan speed and melt pool size.

*SPPARKS · Monte Carlo · Python*

---

### [Parallel 2D Ising Model on CPUs and GPUs](/projects/ising)

[Project page](/projects/ising)

<a href="/projects/ising"><img src="/images/projects/ising/snapshots.jpg" alt="Ising lattice snapshots"/></a>

A Metropolis Monte Carlo Ising model in C++, implemented in serial, OpenMP, MPI, CUDA and multi-GPU (MPI + CUDA) versions and benchmarked on up to 256 cores. Team project; I built the GPU and multi-GPU versions.

*C++ · CUDA · MPI · OpenMP*

---

### [Physics-Informed Neural Networks: A Brief Review and Examples](/projects/pinn-review)

[Project page](/projects/pinn-review) · [Report (PDF)](/pdf/PINN_review.pdf)

<a href="/projects/pinn-review"><img src="/images/projects/pinn-review/pinn_architecture.jpg" alt="PINN architecture"/></a>

A review of PINNs for solving PDEs and discovering models, with examples that recover a diffusion coefficient and mass–spring–damper parameters to within 1%.

---

### Entropic Regression in Python

[Code](https://github.com/Wongel-Yilma/Entropic-Regression)

A Python port of [Entropic Regression](https://github.com/almomaa/Entropic-Regression), an information-theoretic method for sparse model identification that is robust to noise and outliers. It is applied to the Lorenz system and to PDE discovery from Monte Carlo and molecular dynamics data, using a PDE-FIND candidate-term library.

*Python · NumPy*

---
<p style="font-size:11px">Page template forked from <a href="https://github.com/evanca/quick-portfolio">evanca</a></p>
<!-- Remove above link if you don't want to attibute -->
