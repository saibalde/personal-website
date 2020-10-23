---
layout: page
title: "Research"
permalink: /research/
---

# Publications and Preprints

*   **Efficient MCMC Sampling for Bayesian Matrix Factorization by Breaking
    Posterior Symmetries** \\
    Saibal De, Hadi Salehi and Alex Gorodetsky \\
    *arXiv:2006.04295 (2020)* \\
    [(PDF)]({{ '/assets/pdf/de2020efficient.pdf' | prepend: site.baseurl }})

*   **Scalable Solvers for Cone Complementarity Problems in Frictional Multibody
    Dynamics** \\
    Saibal De, Eduardo Corona, Paramsothy Jayakumar and Shravan Veerapaneni \\
    *IEEE High Performance Extreme Computing (HPEC) Conference (2019)* \\
    [(PDF)]({{ '/assets/pdf/de2019scalable.pdf' | prepend: site.baseurl }})

# Current Projects

## Fast Solvers for Stokes Flow past Axisymmetric Geometries

At very small length scales (e.g. for describing motions of bacterias), the
motion of a fluid is approximated by Stokes equation. Using the Greens' function
for this elliptic partial differential equation, we can write the solution of a
boundary value problem as a boundary integral equation (BIE). It is well
established that using BIE formulation, we can construct a more accurate
solution faster compared to traditional finite difference, finite volume or
finite element schemes.

Nevertheless, due to the relatively poor quality of two-dimensional singular
quadratures, we require a high level of discretization to achieve high accuracy
for general surface boundaries. In this project, we assume that these surfaces
are axisymmetric, and leverage this rotational symmetry to decouple 2D BIE into
a series of 1D BIEs. Using good quality quadrature schemes available in 1D, we
can easily achieve high accuracy. In addition, the decoupling improves the
overall computational complexity of our solver.

## Scalable Solvers for Frictional Rigid Body Contact

Granular media is simply a collection of rigid particles. It is one of the most
common form of materials in several fields of applications (e.g. molecular
dynamics, terramechanics, robotics). However, unlike other states of matter,
there is no simple constitutive law governing granular flow. For this reason,
the discrete element method (DEM), which tracks each particle individually,
remains the most accurate way to simulate the these materials.

Naturally, since each particles needs to be tracked separately, the
computational cost of running DEM simulations for large-scale problems is very
high. In this project, we aim to

*   Use the complementarity model for contact, which allows for larger
    step-sizes in numerical time-stepping.
*   Develop a distributed memory framework to enable running simulations with a
    large number of particles (millions to billions).
*   Accelerate the collision resolution step using fast algorithms.

## Reduced-Order Model Generation with Tensor Factorizations

Learning tasks (e.g., optimization, control, uncertainty quantification) require
a large number of data points before they are able to produce reliable
predictions. In this setup, it is practically impossible to utilize the highly
accurate outputs from physics-based simulations for modeling the system under
consideration. We therefore seek reduced-order models (ROM) that can faithfully
approximate the full-fidelity model to used in these learning tasks.

High-fidelity models typically generate a huge amount of high-dimensional data
during the course of the simulation, so much so that even storing all of it
becomes challenging. We propose to utilize tensor decompositions (e.g.,
tensor-train decomposition) to compress the data for future use. We also propose
to use tensor factorizations to construct surrogate models out of the simulation
data.

## Bayesian Low-Rank Factorization of Matrices and Tensors

Low rank matrix and tensor completion has many different practical applications
in fields such as relational data analysis and image/video recovery. Over the
last few years, many optimization based approaches have been proposed to solve
this problem efficiently. Recently, Bayesian inference based approaches have
also gained popularity, since they allow for robust uncertainty quantification.

A key challenge in these Bayesian approaches for matrix and tensor
factorizations is that the factorizations are not unique, and this
non-identifiability issues often lead to symmetries in the posteriors. These
symmetries degrade the performances of Markov-chain Monte-Carlo (MCMC) sampling
algorithms. In this project, our goal is to develop theoretical results that
would break these symmetries, and lead to better performance in Bayesian
inference.

## Quantum Computing for Fast Optimizers

Quantum computing promises to be a revolutionary paradigm of scientific
computing. Quantum algorithms for certain classes of tasks have already been
designed that can outstrip their classical counterparts, at least
theoretically. One such class of problems is combinatorial optimization.

In this project, we propose to extend this approach for continuous optimization,
which is omnipresent in many computational tasks (e.g., in the complementarity
approach to frictional contact described above). A general framework for
quantum continuous optimization has the potential to accelerate many
simulations far beyond the capabilities of classical computing.
