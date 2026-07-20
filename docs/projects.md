# Project Portfolio

## Systems, Quant Dev & Software Engineering

### C++ Limit Order Book & Matching Engine

Building a [C++20 limit order book and matching engine](https://github.com/3zik/limit-order-book-v1){:target="_blank"} with price-time priority, modeled on the matching logic used by real equities and futures exchanges.

Price ladders are stored as two `std::map`s (one per side), ordered so the inside market is always at `begin()`, with a FIFO `std::list` queue per price level for time priority. Order lookup, cancellation, and modification are O(1) via an `std::unordered_map` keyed on order ID, and a per-price aggregate cache lets Fill-or-Kill orders check fillability in O(1) before ever touching the book.

The engine supports five order types — GTC, IOC, FOK, Market, and Good-For-Day — with partial fills, atomic FOK rejection, per-trade attribution, and an aggregated L2 depth snapshot. A background thread prunes Good-For-Day orders at end of day using a condition-variable timed wait with atomic shutdown signaling.

Correctness is verified with a GoogleTest scenario suite, and concurrency is verified with a ThreadSanitizer stress harness. Micro-benchmarks (-O2, 200K operations, allocation excluded) show roughly 180ns p50 to add an order, 135ns p50 to cancel, 260ns p50 for a full match, and about 3.4M adds/sec of throughput.

This is v1.0 and still in progress — a latency-focused v2 is next.

Tools: C++20, STL, GoogleTest, ThreadSanitizer

### C++ Prime Generation & Sieves

Implementing and benchmarking a series of classic prime-generation algorithms in [C++](https://github.com/3zik/primes){:target="_blank"} — trial division, the Sieve of Eratosthenes, the Sieve of Sundaram, the Sieve of Atkin, and a linear Euler sieve — and comparing their theoretical complexity against measured performance. The next step is porting the fastest of these down to hand-written LLVM IR to see what further optimizations are possible.

Tools: C++, CMake

### Embedded Maze Game (C++/Arduino)

Built an [Arduino-based maze game](https://github.com/3zik/labyrinth-game){:target="_blank"} using an 8x8 LED matrix and an IMU accelerometer. At runtime, the game procedurally generates a random maze with a DFS carving algorithm and verifies it's solvable with a DFS pathfinding check before play starts. Navigation is tilt-based — accelerometer thresholds map to discrete movement commands — and the LED matrix renders walls, player, and exit in real time using differential blink rates.

Wrote this up as an academic paper.

<!-- TODO: confirm the semester -- believed Spring 2026 -->

Tools: C++, Arduino, IMU/Accelerometer, LED Matrix

## Computational & Quantitative Physics

### Phonon-Based Calculations of Graphene's Heat Capcity
[Developed analytical and numerical phonon models for graphene](documents/ethan_graphene.pdf){:target="_blank"} by constructing and diagonalizing the dynamical matrix of a honeycomb lattice. Computed full phonon dispersion relations including flexural (ZA) modes and implemented Bose–Einstein-based heat capacity calculations in Python. Validated results against experimental data and DFT literature, reproducing characteristic low-temperature T² scaling and analyzing anharmonic effects at high temperatures. Presented my findings in a ten-minute talk.

Tools: Python, Phonons, Lattice Modeling

Dates: Oct 2025 – Dec 2025 

### Toy NETS Simulation of Rare-Event Dynamics
Implemented a [Python simulation](https://github.com/3zik/nets_drift_sim){:target="_blank"} comparing standard Langevin dynamics with a drift-augmented “toy NETS” model in a 1D double-well potential (inspired by Albergo and Vanden-Eijnden, 2025). Explored connections between stochastic modeling and rare-event sampling theory.

Tools: Python, Stochastic Differential Equations

Dates: June 2025 – Sept 2025

### Energy Levels and Wavefunctions of Alkali Atoms Calculations
Built a [finite-difference eigenvalue solver in Python](https://github.com/3zik/PHYS-H214){:target="_blank"} to compute quantum energy spectra using large tridiagonal Hamiltonian matrices. Implemented adaptive convergence and grid-resolution control to ensure numerical stability and precision for large-scale scientific simulations.

Tools: Python, NumPy, SciPy, Numerical Linear Algebra, Quantum Mechanics

### Comparing ML Algorithm Detection for Development of an Artificially Intelligent Radiologist
Developed and compared multiple ML models (ResNets, DenseNets) for radiology image classification using Stanford’s MURA dataset of 40,561 MSK radiographs. Performed statistical evaluation (Cohen’s Kappa, ROC curves, AUROC, McNemar’s Test) to analyze model efficacy. Produced a [written research report](documents/APR.pdf){:target="_blank"} and presented findings in a ten-minute talk.

Tools: Python, TensorFlow, Keras, OpenCV, scikit-learn, Matplotlib

Dates: Sept 2022 – May 2023 

## Other Projects

### 4cast Prediction Market Platform

Built a [prediction market platform](https://prediction-market-v1-six.vercel.app/){:target="_blank"} using an LMSR automated market maker with bounded-loss guarantees, supporting multi-outcome markets. Verified the market maker's theoretical bounds with Monte Carlo simulations of randomized trading activity, with a Postgres-backed ledger and basic performance analytics layered on top.

Dates: Feb 2026 - Present

### Neural Variational Monte Carlo Solver (Ising Model)

Built a [Variational Monte Carlo solver](https://github.com/3zik/Ising_VMC){:target="_blank"} for the 1D transverse-field Ising model, using a Restricted Boltzmann Machine as a variational wavefunction ansatz. Trained the ansatz via Metropolis-Hastings sampling and gradient-based optimization, and validated the results against exact diagonalization.

### AI Beamline Copilot (NSLS-II)

Designed a documentation-grounded assistant for Bluesky/Ophyd/Queue Server beamline workflows, combining a retrieval pipeline over an internal documentation corpus with local LLM generation. Built a multi-page interface for chat, documentation search, code explanation, plan generation, and troubleshooting, along with an evaluation harness to assess response quality.
