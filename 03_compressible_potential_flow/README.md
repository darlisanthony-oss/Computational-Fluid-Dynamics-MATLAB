# Compressible Potential Flow around a Diamond Airfoil

## Overview

This project develops a numerical solver for the linearized compressible potential-flow equation around a symmetric diamond airfoil.

The solver is implemented from scratch in MATLAB using:

- finite-difference discretization
- a body-fitted structured grid
- transformed computational coordinates
- iterative SOR solution
- slip-wall boundary conditions

The influence of both the Mach number and airfoil thickness ratio on the pressure distribution is also investigated.

This work was completed individually as part of the undergraduate course **Computational Fluid Dynamics** at the University of Patras.

---

## Governing Equation

The linearized compressible potential-flow equation is:

\[
(1-M_\infty^2)
\frac{\partial^2\phi}{\partial x^2}
+
\frac{\partial^2\phi}{\partial y^2}
=0
\]

where:

- \(M_\infty\) is the free-stream Mach number
- \(\phi\) is the perturbation velocity potential

For subsonic conditions, \(M_\infty<1\), the equation is elliptic.

The velocity components are obtained from:

\[
u=
\frac{\partial\phi}{\partial x}
+
V_\infty
\]

\[
v=
\frac{\partial\phi}{\partial y}
\]

The pressure coefficient is evaluated from:

\[
C_p
=
-\frac{2}{V_\infty}
\frac{\partial\phi}{\partial x}
\]

---

## Body-Fitted Structured Grid

A structured non-Cartesian grid is generated around the diamond airfoil.

The computational domain is divided into:

- an upper block
- a lower block

The airfoil surface coincides with a grid line, allowing the wall boundary condition to be imposed directly.

The grid is generated through interpolation between the airfoil surface and the far-field boundary.

For the reported simulations, a grid of:

\[
181 \times 61
\]

nodes is used for each block.

---

## Numerical Solution

The potential equation is discretized using second-order central finite differences.

Three iterative methods are implemented:

- Jacobi
- Gauss–Seidel
- SOR

The final simulations use SOR to accelerate convergence.

A convergence criterion based on the maximum change of the solution between successive iterations is imposed.

---

## Boundary Conditions

At the far-field and lateral boundaries:

\[
\phi=0
\]

is imposed to approximate undisturbed free-stream conditions.

At the airfoil surface, a slip-wall condition is applied so that the velocity remains tangent to the body.

In transformed coordinates, the wall boundary condition is written in terms of the computational coordinate and the local wall slope.

---

## Post-Processing

After convergence, the solver computes:

- horizontal velocity
- vertical velocity
- velocity magnitude
- pressure coefficient \(C_p\)

The resulting flow fields are visualized using contour plots.

For the symmetric airfoil, the upper and lower solutions show the expected symmetry.

---

## Parametric Studies

### Effect of Airfoil Thickness

Two thickness ratios are compared:

\[
t/c = 5\%
\]

and

\[
t/c = 10\%
\]

Increasing the thickness produces a stronger local acceleration and more negative minimum pressure coefficient.

### Effect of Mach Number

The surface pressure distribution is compared for:

\[
M_\infty=0.4
\]

and

\[
M_\infty=0.6
\]

Increasing Mach number leads to stronger pressure variations while maintaining the overall shape of the distribution.

---

## MATLAB Structure

Main routines include:

- `GenerateDiamondGrid`
- `DiamondSurface`
- `BuildBlock`
- `SolvePotentialIterative`
- `ApplyPotentialBCs`
- `RunThicknessCase`

---

## Key Concepts

- Compressible potential flow
- Finite-difference methods
- Body-fitted structured grids
- Coordinate transformation
- Slip-wall boundary conditions
- SOR iterative solver
- Pressure coefficient
- Parametric CFD studies

---

## Selected Results

Recommended figures for the repository:

1. Full body-fitted computational grid
2. Grid close-up around the diamond airfoil
3. Velocity-magnitude contours
4. Pressure-coefficient contours
5. Surface \(C_p\) comparison for different thickness ratios
6. Surface \(C_p\) comparison for different Mach numbers

---

## Academic Context

**Course:** Computational Fluid Dynamics  
**Institution:** University of Patras  
**Department:** Mechanical Engineering and Aeronautics  
**Implementation:** MATLAB  
**Project type:** Individual coursework project

All numerical implementation, analysis and report preparation were completed individually.
