# Simulation of Barrier Options Using Variance Reduction in Merton’s Jump-Diffusion

## Executive Summary
This project prices down-and-out call options under Merton’s jump-diffusion model via Monte Carlo methods. We compare crude MC to variance-reduced methods (Metwally–Atiya, Joshi–Leung, Ross–Ghamami) in accuracy, variance, and runtime across jump intensities.

## Key Sections

### 1. Introduction
Motivates Merton's jump-diffusion vs. Black–Scholes by highlighting fat tails and jumps in returns. States the goal: efficient and accurate barrier option pricing with variance reduction.

### 2. Merton’s Jump-Diffusion Model
Defines the SDE under the risk-neutral measure with Poisson jumps and lognormal jump multipliers.

### 3. Simulation Algorithms
Overview of down-and-out barrier pricing and barrier monitoring. Each algorithm below targets lower variance and/or faster simulation while preserving unbiasedness.

#### 3.1 Crude Monte Carlo
Discrete-time “short-step” simulation with Poisson jump counts per step. Simple baseline but suffers from discretization bias and higher variance.

#### 3.2 Metwally & Atiya (Brownian-Bridge Between Jumps)
Simulates jump times explicitly and applies Brownian-bridge crossing tests between jumps. Much faster than short-step and reduces missed barrier crossings.

#### 3.3 Joshi & Leung (Importance Sampling + Conditioning)
Uses truncated normals to avoid immediate knockouts and corrects with likelihood ratios; also conditions on at least one jump occurring.

#### 3.4 Ross & Ghamami (Stratification on Jump Count)
Applies conditional expectation within strata; uses closed-form for the zero-jump case.

### 4. Numerical Results
Benchmarks each method across different jump intensity values with fixed parameters. Reports mean price, standard deviation, and time over trials.



## Project Files
- **Paper:** [`mcPaper.pdf`](mcPaper.pdf) — full methods, proofs/lemmas, and experiments.
- **Code:** [`mcCode.pdf`](mcCode.pdf) — Implementation of all methods. 


