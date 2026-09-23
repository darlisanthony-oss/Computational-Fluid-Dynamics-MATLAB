# 2D Laplace Equation and Iterative Solvers

## Overview

This project investigates the numerical solution of the two-dimensional Laplace equation using classical iterative methods.

The main focus is the comparison of convergence behaviour between:

- Jacobi
- Gauss–Seidel
- Successive Over-Relaxation (SOR)

The influence of grid resolution, initial conditions and the SOR relaxation parameter is also examined.

This work was completed individually as part of the undergraduate course **Computational Fluid Dynamics** at the University of Patras.

---

## Governing Equation

The problem considered is the steady two-dimensional Laplace equation:

\[
\frac{\partial^2T}{\partial x^2}
+
\frac{\partial^2T}{\partial y^2}
=0
\]

applied to a square plate with prescribed boundary temperatures.

---

## Numerical Methods

The equation is discretized using finite differences and solved iteratively with:

### Jacobi Method

Each new value is computed only from values of the previous iteration.

### Gauss–Seidel Method

The newest available values are used immediately during the iteration.

### Successive Over-Relaxation

SOR extends Gauss–Seidel by introducing a relaxation parameter:

\[
T^{k+1}
=
(1-\omega)T^k
+
\omega T^{GS}
\]

allowing faster convergence when the relaxation parameter is chosen appropriately.

---

## Numerical Experiments

Four main cases are considered using combinations of:

- coarse and fine grids
- zero and parabolic initial conditions

The implementation stores:

- final numerical field
- number of iterations
- convergence history
- final residual
- convergence status

---

## Convergence Comparison

The results show clear differences in computational efficiency.

For the studied cases:

- Jacobi requires the highest number of iterations
- Gauss–Seidel converges significantly faster
- SOR provides the fastest convergence

Grid refinement increases the number of iterations required by all methods.

The influence of the initial condition is also investigated by comparing convergence histories for zero and parabolic initial fields.

---

## Optimal SOR Relaxation Parameter

A theoretical optimal relaxation parameter is estimated from the spectral radius of the Jacobi iteration matrix.

The theoretical value is then tested numerically for both grids.

For the cases studied, the estimated optimal parameter gives the lowest iteration count.

Values closer to the stability limit may still converge rapidly, but with more oscillatory behaviour.

---

## MATLAB Structure

Main routines include:

- `PlateCase`
- `ApplyBCs`
- `SolveLaplaceIterative`
- `OmegaOpt`
- `RunSORStudy`
- `PrintCaseTable`
- `PrintSORTable`

---

## Key Concepts

- Laplace equation
- Finite differences
- Jacobi iteration
- Gauss–Seidel iteration
- Successive Over-Relaxation
- Grid refinement
- Residual convergence
- Spectral radius
- Relaxation-parameter optimization

---

## Selected Results

Recommended figures for the repository:

1. Temperature contours for coarse and fine grids
2. Jacobi / Gauss–Seidel / SOR convergence histories
3. Effect of initial conditions on convergence
4. SOR convergence for different relaxation parameters
5. Iteration-count table comparing all methods

---

## Academic Context

**Course:** Computational Fluid Dynamics  
**Institution:** University of Patras  
**Department:** Mechanical Engineering and Aeronautics  
**Implementation:** MATLAB  
**Project type:** Individual coursework project
