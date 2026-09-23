# Computational-Fluid-Dynamics-Matlab
Computational Fluid Dynamics &amp; PDE Solvers in MATLAB

A collection of three progressively more complex numerical projects developed during the undergraduate course **Computational Fluid Dynamics** at the University of Patras, Department of Mechanical Engineering and Aeronautics.

The projects focus on the numerical solution of partial differential equations relevant to fluid dynamics, with emphasis on finite-difference methods, stability, convergence, iterative solvers, grid generation and aerodynamic flow modelling.

## Projects

### 1. Advection and Burgers Equations
Implementation and comparison of explicit finite-difference schemes for the 1D linear advection equation and nonlinear Burgers equation.

Main topics:
- FTBS, Lax and Lax–Wendroff schemes
- CFL-based time stepping
- numerical dissipation and dispersion
- comparison with analytical solutions
- nonlinear wave steepening
- inviscid and viscous Burgers equations
- adaptive stability constraints

### 2. 2D Laplace Equation and Iterative Solvers
Numerical solution of the 2D Laplace equation using classical iterative methods.

Main topics:
- Jacobi method
- Gauss–Seidel method
- Successive Over-Relaxation (SOR)
- grid refinement
- convergence histories
- influence of the initial condition
- analytical estimation and numerical verification of the optimal SOR relaxation parameter

### 3. Compressible Potential Flow around a Diamond Airfoil
Development of a numerical solver for the linearized compressible potential-flow equation around a symmetric diamond airfoil.

Main topics:
- body-fitted structured grid generation
- finite-difference discretization
- transformed computational coordinates
- slip-wall boundary conditions
- SOR solution of the potential equation
- velocity and pressure-coefficient fields
- effect of Mach number
- effect of airfoil thickness ratio

## Tools
- MATLAB
- Finite Difference Methods
- Iterative Linear Solvers
- Numerical Stability and Convergence Analysis
- CFD Post-processing

## Repository Structure

```text
01_advection_burgers/
02_laplace_iterative_solvers/
03_compressible_potential_flow/
reports/
