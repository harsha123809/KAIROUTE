# KAIROUTE Engine

## Quantum-Inspired Intelligent Traffic Route Optimization

### Status

Proof-of-concept / architecture implementation scaffold.

No benchmark results are claimed at this stage.

## Purpose

The KAIROUTE engine is designed around a two-tier routing architecture:

1. Time-dependent exact path computation
2. Memetic Quantum Particle Swarm Optimization (QPSO)

## System Pipeline

Road Network + Stops
→
Time-Dependent Cost Field
→
Tier 1: Time-Dependent Dijkstra
→
Tier 2: Memetic QPSO
→
Fleet-Limited Split Decoder
→
Local Search
→
Dispatch

## Tier 1: Exact Path Computation

Time-dependent Dijkstra is used to calculate fastest paths between stop pairs under changing traffic conditions.

The planned model uses:

- 15-minute time slots
- FIFO travel-time behaviour
- interpolated lookups across slot boundaries

## Tier 2: Route Optimization

The route optimization layer uses Memetic QPSO with:

- random-key encoding
- fleet-limited Split decoding
- Relocate
- Swap
- Or-opt
- Lamarckian local-search write-back

The Split decoder enforces the fleet constraint.

## Closure Re-planning

When a road closure occurs:

- served stops remain locked
- parcels remain on their assigned van
- only unserved stops are re-planned
- the previous swarm provides the warm start
- re-planning re-enters at the Matrix/Field stage

## Scenario

The current proof-of-concept scenario uses:

- Seethammadara, Visakhapatnam
- 1 depot
- 30 synthetic stops
- demand of 1–3 per stop
- 5 vans

This is a synthetic/illustrative scenario and is not presented as a real-world deployment.

## Objective

The optimization objective is:

min F = w_T · Time + w_CE · Congestion + w_L · Lateness

subject to:

- each stop served once
- maximum of 5 vans
- vehicle load constraints
- FIFO travel time
- soft time windows

## Current Status

This repository represents the KAIROUTE proof-of-concept architecture.

It does not claim completed production deployment or benchmark results.
