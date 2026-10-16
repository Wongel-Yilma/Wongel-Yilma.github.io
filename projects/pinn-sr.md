---
layout: default
title: Physics-Informed Neural Networks for PDE Discovery (PINN-SR)
---

## Physics-Informed Neural Networks for PDE Discovery (PINN-SR)

*With Frank Katjipaha · Course project, 2025*
<br>[Code](https://github.com/Wongel-Yilma/PINN-SR) · [Project report (PDF)](/pdf/PINN_SR_proposal.pdf)

**Summary:** Sparse regression can discover PDEs from data, but it is sensitive to noise, which numerical differentiation amplifies. This project combines a physics-informed neural network (PINN) with sparse regression to recover the diffusion equation from random-walk Monte Carlo data, without assuming the form of the equation. The recovered diffusion coefficient is within 3% of the analytical value.

---

### 1. Data

Concentration time-series come from a Metropolis Monte Carlo random-walk simulation. The simulation knows nothing about any PDE, which makes the data resemble real experiments. The ground truth, the classical diffusion equation, is still known, so results can be checked. Three datasets with different boundary conditions were used.

<img src="/images/projects/pinn-sr/mc_data.jpg" alt="Monte Carlo concentration data"/>
*Monte Carlo concentration data: (a) deposition (positive boundary flux), (b) deletion (negative boundary flux), (c) zero boundary flux.*

### 2. Method

A feed-forward network learns a smooth representation of the concentration c(z, t). Automatic differentiation then provides the derivatives needed to build a library of 16 candidate terms (polynomials of c up to third order, multiplied by spatial derivatives up to third order). The PDE coefficients Λ are trained together with the network weights using a combined loss:

<p align="center"><i>L<sub>total</sub> = L<sub>data</sub> + α L<sub>physics</sub> + β L<sub>regularization</sub></i></p>

Sequential threshold ridge regression (STRidge) then selects the active terms, and the PINN is retrained on them.

<img src="/images/projects/pinn-sr/architecture.jpg" alt="PINN-SR architecture"/>
*PINN-SR architecture.*

### 3. Results

After 150 epochs with Adam, sparse regression keeps a single term:

<p align="center"><i>c<sub>t</sub> = 0.214 c<sub>zz</sub></i></p>

The Einstein–Smoluchowski relation gives an analytical diffusivity of 0.2083, so the coefficient error is about 2.9%. A larger regularization weight β gave sparser PDEs. Applying the physics constraint gradually, after the network had learned the data, improved training.

<img src="/images/projects/pinn-sr/losses.jpg" alt="Training losses"/>
*Data, physics and total loss during training.*

<img src="/images/projects/pinn-sr/coefficients.jpg" alt="Coefficient evolution"/>
*Evolution of the candidate-term coefficients before the sparse regression step.*

*Python · PyTorch · Jupyter*

[← Back to portfolio](/)
