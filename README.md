# Psuedospectral Methods for Heat Transfer and Fluid Dynamics

Psuedospectral methods are a class of numerical methods to solve partial differential equations that can be advantageous over finite difference or finite volume methods due to the use of fast algorithms such as the Fast-Fourier-Transform to compute derivative terms.
Rather than discretizing derivatives, the psuedospectral method starts by expanding the desired solution (fluid flow velocity, temperature, etc) into a linear combination of basis functions. For problems with periodic boundary conditions, these basis functions are plane waves and subsequent derivatives involve operations with the Fast-Fourier-Transform and Inverse-Fast-Fourier-Transform.
For problems with non-periodic boundary conditions, the basis functions are Chebyshev polynomials of the first kind and derivatives are calculated by taking the Discrete Cosine Transform and Inverse Discrete Cosine Transform. While other polynomial basis functions can be used such as Legendre or Hermite, the use of Chebyshev and plane-wave basis functions consist the Chebyshev Psuedospectral Method and Fourier Psuedospectral Method respectively.
In both methods, derivatives calculated via their respective transforms are inserted back into the PDE and are solved via the Method of Lines. 

A few problems are analyzed here such as the 1D Viscous Burgers equation, 2D Heat Equation, and 3D incompressible Navier Stokes and are solved via psuedospectral methods, yielding results that align with numerical solutions achieved via finite volume or finite difference methods. 
