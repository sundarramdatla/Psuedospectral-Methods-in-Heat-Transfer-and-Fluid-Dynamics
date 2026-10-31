# Pseudospectral Methods for Heat Transfer and Fluid Dynamics

## Project Overview

Developed numerical algorithms in Python and MATLAB using Fourier and Chebyshev pseudospectral methods to solve complex partial differential equations governing fluid dynamics and heat transfer. Implemented solvers for the 1D viscous Burgers equation, 2D heat equation, and 3D incompressible Navier–Stokes equations, alongside Chebyshev polynomial interpolation, to investigate efficient numerical techniques for nonlinear and multidimensional systems.

## Theory

Pseudospectral methods approximate solutions to partial differential equations using global basis functions rather than local finite-difference approximations. Fourier methods represent periodic solutions as sums of complex exponentials, allowing spatial derivatives to be calculated through Fast Fourier Transforms (FFT):

$$\frac{\partial^n u}{\partial x^n}=\mathcal{F}^{-1}\left[(ik)^n\mathcal{F}(u)\right]$$

Chebyshev methods represent functions using Chebyshev polynomials, enabling accurate interpolation and spectral differentiation on nonuniform grids through polynomial expansions and Discrete Cosine Transforms (DCT).

The Method of Lines transforms the resulting spatially discretized PDEs into systems of ordinary differential equations for numerical time integration.

## How It Was Built

Developed MATLAB Fourier pseudospectral solvers for the **1D nonlinear viscous Burgers equation and 2D heat equation**, implementing FFT-based first- and second-order spatial derivatives in spectral space. Converted the governing PDEs into systems of coupled ODEs using the Method of Lines and integrated them using MATLAB's adaptive Runge–Kutta `ode45` solver. Implemented multidimensional Fourier differentiation along separate spatial axes to simulate time-dependent temperature distributions.

Built a **3D incompressible Navier–Stokes solver in Python** using NumPy's multidimensional FFT algorithms on a 64×64×64 periodic grid. Implemented spectral curl operators, nonlinear vorticity–velocity interactions, pressure projection to enforce incompressibility, and viscous diffusion. Applied the 2/3 de-aliasing rule to suppress spectral aliasing errors and explicit Euler time integration to evolve the velocity field. Structured FFT operations with MPI-aware functions and developed three-dimensional vector-field animations to visualize evolving fluid motion.

Implemented **Chebyshev polynomial interpolation algorithms in MATLAB** using Chebyshev–Gauss nodes, Vandermonde matrix construction, and discrete cosine transforms. Compared polynomial coefficients and reconstructed interpolants using both direct linear-system solutions and DCT-based spectral expansions, demonstrating two computational approaches to approximating the Runge function.

## Results

**1D Viscous Burgers Equation:** Developed a Fourier pseudospectral solver using 32 spatial grid points and adaptive Runge–Kutta integration to simulate nonlinear convection and viscous diffusion over 50 time units.

**2D Heat Equation:** Simulated transient heat diffusion on a 20×40 spatial grid using multidimensional spectral differentiation and adaptive time integration, generating time-dependent temperature-distribution visualizations.

**3D Navier–Stokes Equations:** Implemented a 64×64×64 spectral fluid solver with pressure projection, nonlinear term evaluation, and de-aliasing, producing animated three-dimensional velocity fields to investigate incompressible flow evolution.

**Chebyshev Interpolation:** Constructed a 30-node Chebyshev interpolation algorithm using both Vandermonde matrix inversion and DCT-based coefficient calculation, comparing reconstructed solutions against the analytical Runge function.

## Technologies

Python, MATLAB, NumPy, Matplotlib, SciPy, FFT, Inverse FFT, Discrete Cosine Transform, Fourier Pseudospectral Methods, Chebyshev Polynomials, Numerical Linear Algebra, Spectral Differentiation, Adaptive Runge–Kutta, Method of Lines, Navier–Stokes Equations, MPI, Numerical PDE Solvers.
