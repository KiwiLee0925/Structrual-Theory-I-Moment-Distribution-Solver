# Moment Distribution Solver

A generalized Python solver for structural analysis using the **Moment Distribution Method**.  
This project can be used to analyze both **continuous beams** and **rigid frame structures** by defining member connectivity, stiffness, fixed-end moments, carry-over factors, and balanced joints.

The solver was developed as part of a structural analysis project, including a simplified rigid-frame model inspired by **UCLA Royce Hall**.

---

## Features

- Generalized moment distribution solver
- Supports continuous beam problems
- Supports rigid frame problems
- Allows different member lengths and moments of inertia
- Computes distribution factors automatically
- Performs iterative joint balancing
- Applies carry-over moments automatically
- Outputs moment distribution tables
- Gives final member-end moments

---

## Method

The Moment Distribution Method is an iterative structural analysis method for statically indeterminate beams and frames.

The program follows these steps:

1. Define all members and joints
2. Compute member stiffness

\[
K = \frac{4EI}{L}
\]

3. Compute distribution factors at each balanced joint
4. Apply fixed-end moments
5. Balance unbalanced joint moments
6. Carry over half of the distributed moment to the far end
7. Repeat until convergence
8. Output final member-end moments

---

## Sign Convention

The program uses the following sign convention:

> Member-end clockwise moment is positive.

This convention is used internally for the moment distribution table.

When drawing the bending moment diagram, the sign may need to be converted depending on the diagram convention used, such as sagging moment positive.

---

## Example 1: Continuous Beam

The first example is a continuous beam:


A ───── B ───── C

##  Example 2: UCLA Royce Hall Simplified Frame

The second example is a simplified rigid-frame model inspired by UCLA Royce Hall:

        P          P          P
        ↓          ↓          ↓
A'──────B'────────C'────────D'
│       │         │         │
│       │         │         │
A       B         C         D
fixed   fixed     fixed     fixed
