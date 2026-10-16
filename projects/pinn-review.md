---
layout: default
title: "Physics-Informed Neural Networks: A Brief Review and Examples"
---

## Physics-Informed Neural Networks: A Brief Review and Examples

*Term project, 2024*
<br>[Report (PDF)](/pdf/PINN_review.pdf)

**Summary:** A review of physics-informed neural networks (PINNs) for solving PDEs and discovering models from data, with worked examples that recover unknown physical parameters from simulated data.

---

### How PINNs work

A neural network approximates the solution u(x, t). Automatic differentiation gives its derivatives, which are used to evaluate the governing equation. The loss function combines how well the network fits the data with how well its output satisfies the physics. The unknown physical parameters are trained together with the network weights.

<img src="/images/projects/pinn-review/pinn_architecture.jpg" alt="PINN architecture"/>
*A typical PINN: the network, the physics component built with automatic differentiation, and the combined loss.*

### Example 1: Diffusion equation

Using only 5% of the available data (5,000 collocation points), the PINN recovered the diffusion coefficient as D = 5.98, against a true value of 6, an error of 0.33%.

<img src="/images/projects/pinn-review/diffusion.jpg" alt="Diffusion equation solution"/>
*Concentration profile over space and time used for training.*

### Example 2: Mass–spring–damper system

The PINN recovered the mass, damping coefficient and spring constant of a mass–spring–damper system, each within 1% of the true value.

<img src="/images/projects/pinn-review/mass_spring_damper.jpg" alt="Mass-spring-damper solution"/>
*Position and velocity of the mass–spring–damper system.*

The report also sets up linear elasticity (identifying Lamé parameters from FEniCS finite element data) and reviews PINNs for design optimization and for discovering parsimonious models.

[← Back to portfolio](/)
