---
layout: default
title: Learning the governing PDE of solid diffusion from atomistic simulations
---

## Learning the governing PDE of solid diffusion from atomistic simulations

**W. Nadew**, H. Wang — *Proceedings of the Royal Society A*, 481(2322), 2025
<br>[Paper](https://royalsocietypublishing.org/rspa/article/481/2322/20250383/234348/Learning-the-governing-partial-differential) · [DOI: 10.1098/rspa.2025.0383](https://doi.org/10.1098/rspa.2025.0383)

**Summary:** Molecular dynamics (MD) simulations capture atomistic behavior in detail, but translating those insights into continuum-scale governing equations remains a challenge. This work develops a data-driven framework that learns governing PDEs directly from noisy, limited MD data, with no prior knowledge of the final equation. Applied to hydrogen diffusion in nickel, it identifies a nonlinear PDE whose diffusivity depends strongly on concentration.

---

### 1. Generating data with MD simulations

Hydrogen diffusion in crystalline nickel is simulated under three different initial and boundary conditions: depositing H atoms into pristine Ni, a closed system with a linear initial H profile, and deleting H atoms from a uniform Ni–H alloy.

<img src="/images/projects/md-diffusion/md_setup.jpg" alt="MD simulation setup for H diffusion in Ni"/>
*MD simulation setup: (a) H deposition, (b) closed diffusive system, (c) H deletion.*

<img src="/images/projects/md-diffusion/md_results.jpg" alt="MD concentration, flux and gradient data"/>
*Concentration, flux and concentration gradient from MD for the deposition (top), zero-flux (middle) and deletion (bottom) cases.*

### 2. Identifying the PDE

MD data is noisy, and numerical differentiation amplifies that noise. The framework computes derivatives with total-variation regularized (TVR) differentiation, builds a library of candidate terms, and selects the active terms with sparse regression. Differential evolution tunes the hyperparameters (the TVR parameter η and the sparsity parameter λ) to minimize the data loss between the PDE's solutions and the MD data. The best candidate PDEs are then tested against new MD simulations with different initial and boundary conditions to select the final equation.

<img src="/images/projects/md-diffusion/workflow.jpg" alt="PDE identification workflow"/>
*Workflow for identifying a PDE from MD simulation data.*

### 3. Result: concentration-dependent diffusivity

The selected PDE for H diffusion in Ni at 800 K is

<p align="center"><i>∂c/∂t = ∂/∂z [ (75.674 − 119.326 c + 1019.499 c³) ∂c/∂z ]</i></p>

Its diffusivity varies by more than an order of magnitude across the concentration range, from 59.96 to 975.85 ns⁻¹. On unseen validation cases it predicts the MD concentration profiles more accurately than the classical constant-diffusivity equation.

<img src="/images/projects/md-diffusion/pde_validation.jpg" alt="Validation of identified PDEs against MD"/>
*(a, b) Concentration profiles predicted by the identified PDEs (lines) compared with MD (circles) for two validation cases. (c) Concentration-dependent diffusivity of the selected PDE (PDE-IV) compared with the constant diffusivity of the classical equation (PDE-I).*

---
Figures from Nadew & Wang, *Proc. R. Soc. A* 481: 20250383 (2025).

[← Back to portfolio](/)
