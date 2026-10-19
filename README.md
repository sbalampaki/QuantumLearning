# QuantumLearning

QuantumLearning is a hands-on quantum computing project focused on building and benchmarking core quantum algorithms across Qiskit 2.x and PennyLane.

## Project Status

Component 3 (Jupyter Notebooks) currently includes four completed notebooks:

1. **Notebook 01 — Bell and GHZ States** (`notebooks/01_bell_ghz_states.ipynb`)
   - All four Bell states in Qiskit 2.x using V2 Primitives
   - Statevector analysis and entanglement entropy
   - PennyLane cross-framework verification

2. **Notebook 02 — Grover’s Search from Scratch** (`notebooks/02_grover_algorithm.ipynb`)
   - Custom phase oracle and diffusion operator
   - Optimal iteration analysis and multi-solution case
   - Classical linear-search baseline
   - Scaling comparison plots: **O(√N)** (quantum) vs **O(N)** (classical)

3. **Notebook 03 — VQE for H₂** (`notebooks/03_vqe.ipynb`)
   - Hardware-efficient ansatz with `StatevectorEstimator` (Qiskit 2.x V2)
   - No deprecated `qiskit_algorithms.VQE` usage
   - Optimizer comparison: COBYLA, L-BFGS-B, SPSA
   - Potential energy surface scan across 20 bond lengths
   - PennyLane gradient-descent implementation

4. **Notebook 04 — QAOA for MaxCut** (`notebooks/04_qaoa_maxcut.ipynb`)
   - Full cost layers (CNOT-Rz) and mixer layers (Rx)
   - Depth comparison for p = 1, 2, 3
   - Batched 30×30 parameter landscape scan
   - Solution sampling and PennyLane `qml.qaoa` layers

## Benchmarking

Each notebook appends structured benchmarking rows to a shared file:

- `results/benchmarks.csv`

This creates a consistent performance trail across all algorithm implementations.

## Compatibility Fixes Applied

Two key API compatibility issues were resolved during development:

- **Grover notebook fix:** `DataBin.meas` `AttributeError` resolved by using the correct classical register name (`c`, not `meas`).
- **PennyLane 0.45 fix:** Removed deprecated `expansion_strategy` argument from `qml.draw()`.

## Repository Structure

- `README.md`
- `notebooks/`
  - `01_bell_ghz_states.ipynb`
  - `02_grover_algorithm.ipynb`
  - `03_vqe.ipynb`
  - `04_qaoa_maxcut.ipynb`
