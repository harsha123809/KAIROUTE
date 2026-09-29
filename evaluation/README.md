# KAIROUTE Evaluation Harness

## Purpose

The KAIROUTE evaluation harness is intended to provide a controlled framework for evaluating the route optimization approach.

The planned comparison is:

QPSO vs PSO vs GA

## Fair-Fight Design

All methods use the same:

- random-key encoding
- fleet-limited Split decoder
- local search
- fitness-call budget

Local-search moves are counted within the fitness budget.

The optimization update rule is the principal difference being evaluated.

## Repeated Evaluation

The planned experiment uses:

30 random seeds.

## Validation References

The evaluation framework uses:

### PuLP/CBC

Exact MILP validation for small instances of up to 12 stops.

### CVRPLIB

Reference against published best-known solutions.

### OR-Tools

Used as a heuristic reference.

OR-Tools is not presented as an exact solver.

## Statistical Analysis

Planned statistical analysis:

- Wilcoxon test
- Holm correction

## Current Status

This repository contains the initial evaluation-harness structure.

No benchmark results are currently claimed.

No accuracy, speedup, convergence, or solution-quality percentage should be inferred from this repository.
