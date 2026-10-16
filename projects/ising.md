---
layout: default
title: Parallel 2D Ising Model on CPUs and GPUs
---

## Parallel 2D Ising Model on CPUs and GPUs

*With Connor Gould and Pavel Chowdhury · High-performance computing course project, 2026*

**Summary:** A Metropolis Monte Carlo simulation of the two-dimensional Ising model of ferromagnetism, written in C++. The project compares serial, shared-memory, distributed-memory and GPU implementations, and benchmarks how each scales on the University of Utah CHPC cluster. My part was the CUDA GPU version and the distributed multi-GPU (MPI + CUDA) versions.

---

### 1. The model

Each lattice site holds a spin of ±1. Neighboring spins prefer to align, so below a critical temperature the lattice magnetizes. Spins are updated with a checkerboard scheme. Because no two neighboring sites are updated at the same time, the update is reproducible and parallelizes cleanly.

<img src="/images/projects/ising/snapshots.jpg" alt="Ising lattice snapshots"/>
*A 1024 × 1024 lattice at t = 0, 5,000 and 25,000 steps, going from random spins to a fully magnetized domain.*

<img src="/images/projects/ising/phase_transition.jpg" alt="Magnetization vs temperature"/>
*Magnetization drops sharply near the critical temperature, T ≈ 2.2.*

### 2. Implementations

- **Serial:** the baseline.
- **OpenMP:** multithreaded checkerboard updates, with reductions for energy and magnetization.
- **CUDA:** one thread per lattice site, with shared-memory tiling and halo cells.
- **MPI:** row-wise domain decomposition, with ghost rows exchanged through `MPI_Sendrecv`.
- **MPI + CUDA:** one GPU per rank. A GPU-aware MPI version exchanges ghost rows directly between GPU buffers.

Every parallel version was checked against the serial output and produced identical results.

### 3. Performance

OpenMP and MPI both scale well, usually above 70% parallel efficiency. MPI efficiency drops once runs span several nodes, because communication between nodes is slower.

<img src="/images/projects/ising/omp_strong_scaling.jpg" alt="OpenMP strong scaling"/>
*OpenMP strong scaling on a 3072 × 3072 lattice: run time, speedup and efficiency.*

<img src="/images/projects/ising/mpi_strong_scaling.jpg" alt="MPI strong scaling"/>
*MPI strong scaling on up to 256 processes across 4 nodes.*

In the first multi-GPU version, ghost rows were copied between GPU and CPU twice per step, which cancelled out the benefit of adding GPUs. Exchanging ghost rows directly between GPU buffers with GPU-aware MPI removed those copies, and adding GPUs then cut the run time substantially.

<img src="/images/projects/ising/mpi_gpu.jpg" alt="Multi-GPU performance"/>
*Multi-GPU run time with and without GPU-aware MPI.*

*C++ · CUDA · MPI · OpenMP*

[← Back to portfolio](/)
