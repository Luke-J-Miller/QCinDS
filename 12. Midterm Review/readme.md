$\huge{\textbf{Session 12: Midterm Review}}$
# Session Overview

## Objective: 
Consolidate knowledge from sessions 1-8, address gaps, and prepare for the midterm exam
## Agenda:
- Overview of sessions 1-8
- Recap of quantum foundations
- Recap of quantum algorithms
- Recap of quantum AI (QAOA)
- Common pitfalls in circuit design
- Practice problems and group discussion
- Exam format and preparation tips
- Q&A

---

# Course Progress and Midterm Scope

## Sessions Covered:
1. Intro to Quantum Computing & Qiskit
2. Quantum Circuits & Gates
3. Entanglement & Bell States
4. Quantum Query Algorithms
5. Unstructured Search
6. Quantum Noise & Transpilation
7. Phase Estimation & Factoring
8. QAOA & Applications


## Midterm Focus: 
Theoretical understanding, circuit design principles, algorithm derivations
## Connection to Course: 
Builds foundation for quantum AI and deep learning
## Question: 
Which topic feels most challenging so far?

---
# Recap: Quantum Foundations (Sessions 1-3)

## Session 1: Intro to Quantum Computing & Qiskit
- Qubits: ( $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ ), superposition, measurement
- Quantum parallelism: Process all states simultaneously
- Qiskit: Framework for circuits, simulation (Aer), hardware access


## Session 2: Quantum Circuits & Gates
- Single-qubit gates: X, Y, Z, H, S, T; matrices and Bloch sphere
- Multi-qubit: CNOT, CZ; circuit composition


## Session 3: Entanglement & Bell States
- Entanglement: Non-separable states, e.g., ( $|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$ )
- EPR paradox, Bell inequalities: Non-locality
- Applications: Teleportation, superdense coding


Key Insight: Foundations enable quantum advantage in AI

---

# Recap: Quantum Query Algorithms (Session 4)

Query Model: Oracle access to function $f(x)$
- Deutsch-Jozsa:
-- Problem: Constant vs. balanced function
-- Quantum: 1 query vs. classical $O(2^n)$
- Circuit: $H^{\otimes n}$, oracle, $H^{\otimes n}$, measure


- Bernstein-Vazirani:Find hidden string $s$ in $f(x) = s · x$
-- Quantum: 1 query vs. classical O(n)


- Significance: Demonstrates quantum speedups
- AI Relevance: Efficient pattern recognition in data

---

# Recap: Unstructured Search (Session 5)

## Grover’s Algorithm:
- Search for $x$ where $f(x) = 1$ in $N = 2^n$ items
- Steps: Initialize superposition, iterate oracle + diffusion, measure
- Oracle: Phase flip for solutions
- Diffusion: Amplify target amplitudes


- Complexity: $O(√N)$ vs. classical $O(N)$ → quadratic speedup
- Multiple Solutions: $~π√(N/M)/4$ iterations for $M$ solutions
- AI Use: Search for optimal parameters, anomalies
- Pitfall: Over-iteration reduces success probability

---

# Recap: Quantum Noise & Transpilation (Session 6)

- Noise Types: Decoherence (T1, T2), gate errors, measurement errors
- Models: Pauli, depolarizing, thermal relaxation


- Error Mitigation: ZNE, readout correction, dynamical decoupling
## Transpilation:
- Optimize circuits for hardware (layout, routing, gate decomposition)
- Qiskit levels 0-3: Trade-off optimization vs. compilation time


## Impact on AI: 
Noise distorts QML circuits; mitigation critical
## Pitfall: 
Over-optimization may increase transpilation time

---

# Recap: Phase Estimation & Factoring (Session 7)

## Quantum Phase Estimation (QPE):
- Estimate phase $θ$ of $U|ψ⟩ = e^{i2πθ}|ψ⟩$
- Components: QFT, controlled-U, inverse QFT
- Complexity: $O(n^2)$ for $n$-bit precision


## Shor’s Algorithm:
- Factor $N$ by finding period of $a^x$ mod $N$
- Uses QPE, continued fractions
- Polynomial time vs. classical sub-exponential


- Challenges: Deep circuits, noise sensitivity
- AI Connection: Secure ML, period finding in data

---

# Recap: QAOA & Applications (Session 8)

- Quantum Approximate Optimization Algorithm:
-- Hybrid algorithm for combinatorial problems (e.g., MaxCut)
-- Cost Hamiltonian: Encodes problem (e.g., H_C = ∑ w_{ij} Z_i Z_j)
-- Mixer Hamiltonian: Exploration (e.g., H_B = ∑ X_i)
-- Variational Loop: Optimize parameters γ, β classically
-- Performance: Improves with depth p, but noise-limited
-- AI Applications: Clustering, graph partitioning
-- Pitfall: Barren plateaus in parameter optimization

---

# Common Pitfalls in Circuit Design

- Initialization Errors:
-- Incorrect qubit state (e.g., missing H for superposition)
-- Example: Grover requires uniform superposition
- Gate Misapplication:
-- Wrong gate order or matrix (e.g., H vs. X confusion)
-- Controlled gates: Misplaced control/target
- Measurement Issues:
-- Measuring too early, wrong basis
-- Ignoring shot noise in Qiskit simulations
- Noise Sensitivity:
-- Deep circuits (e.g., QPE) accumulate errors
-- Ignoring hardware constraints in transpilation
- Optimization Traps: 
-- Over-iterating in Grover, 
-- poor parameter initialization in QAOA

---

# Quantum Circuits

## Problem: 
Derive the final state of a 2-qubit circuit:
```
|0⟩ --[H]--•--
           |CNOT
|0⟩ ------⊕--
```

### Steps:
- Initialize: $|00⟩$
- Apply $H$ to $q0$: $(1/√2)(|00⟩ + |10⟩)$
- Apply $CNOT$: $(1/√2)(|00⟩ + |11⟩) = |Φ^+⟩$


### Question: 
What’s measured in computational basis? (50% |00⟩, 50% |11⟩)
### Discussion: 
How does this relate to entanglement in AI feature maps?

---

# Practice Problem 2: Deutsch-Jozsa

## Problem: 
For a 2-qubit oracle (constant $f(x)=1$), sketch the circuit and predict output
Circuit:
```
|0⟩ --[H]--[O_f]--[H]-- Measure
|0⟩ --[H]--[O_f]--[H]-- Measure
|1⟩ --[H]---------[H]--
```

## Solution:
- Constant f → all |0⟩ output
- Balanced f → non-zero output


## Task: 
Compute final state before measurement for f=1
## AI Relevance: 
Pattern detection in datasets

---

# Practice Problem 3: Grover’s Algorithm

## Problem: 
For $N=4$, one solution $x^*=11$, calculate iterations and success probability
### Steps:
- N=4, M=1 → iterations ≈ π√4/4 ≈ 1
- Each iteration rotates by $θ ≈ arcsin(1/√4) = π/6$
- After 1 iteration: $P(success) ≈ sin^2(3π/6) = 1 (ideal)$


## Question: 
What happens with 2 iterations? (Over-rotation)
## AI Use: 
Optimize feature search in high-dimensional data

---

# Practice Problem 4: Noise and QAOA

## Problem: 
For a 3-node MaxCut graph, define cost Hamiltonian and estimate noise impact
### Solution:
- $H_C = ∑_{ij∈E} Z_i Z_j / 2 (e.g., Z_1 Z_2 + Z_2 Z_3 + Z_3 Z_1)$
- Noise: Depolarizing error reduces ⟨H_C⟩ accuracy


# Task: 
Sketch 1-layer QAOA circuit
## Pitfall: 
- Noise in ZZ gates distorts cost evaluation
## AI Context: 
Noise affects clustering accuracy

---

# Midterm Exam Format

## Details:
- Covers Sessions 1-8
- Duration: Normal class time (75 minutes)
- Format: Mix of multiple-choice, short answers, circuit design, derivations


## Sample Questions:
- Derive final state of a given circuit
- Explain Grover’s speedup vs. classical search
- Design Qiskit circuit for Deutsch-Jozsa (theoretical)
- Analyze noise impact on QPE


## Grading: 
20% of final grade
## Tips: 
Review homework feedback, practice circuit derivations

---

# Group Discussion: Key Concepts

## Activity: 
### Break into groups, discuss:
- How does entanglement enable quantum algorithms?
- Why are variational algorithms (QAOA) suitable for NISQ?
- Common errors in circuit design and how to avoid them


### Share Insights: 
- Each group presents one key takeaway
- Goal: Reinforce understanding, clarify doubts
- AI Focus: How do these concepts apply to quantum ML?

---
# Preparation Tips

## Review Strategies:
- Revisit material for sessions 1-8
- Focus on key algorithms: Deutsch-Jozsa, Grover, QPE, QAOA
- Practice deriving circuit states (pen-and-paper)
- Understand noise and mitigation conceptually


## Resources:
- Qiskit Community Tutorials
- IBM Quantum Learning Platform
- Homework solutions, lab feedback
- Practice: Solve sample problems from slides, textbooks
- Office Hours for extra help

---

# Q&A and Looking Ahead

## Questions:
- Which algorithm is hardest to grasp?
- Clarifications on circuit design or noise?


## Discussion: 
How will quantum foundations impact QML in later sessions?
## Next Session: 
Midterm Exam
## Reminder: 
Review HW 1-2, Lab 0-1 feedback
