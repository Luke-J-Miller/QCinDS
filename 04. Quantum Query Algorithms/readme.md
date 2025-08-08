$\textbf{Quantum Query Algorithms}$
# Session Overview
## Objective: 
Introduce the query model, oracles, and algorithms that demonstrate quantum speedups
## Agenda:
- Recap of entanglement
- The query model in quantum computing
- Black-box oracles
- Deutsch-Jozsa algorithm
- Bernstein-Vazirani algorithm
- Query complexity analysis
- Applications to AI and data science
- Q&A

---

# Recap from Session 3

## Key Points:
### Entanglement: 
Non-separable states, correlations beyond classical
### EPR paradox: 
Challenges local realism
### Bell inequalities: 
Test non-locality, violated by QM
### Bell states: 
Maximally entangled pairs, creation via circuits
### Applications: 
Teleportation (state transfer), superdense coding (efficient comms)


## Connection to Today: 
Query algorithms use oracles that act like black-box functions, often leveraging superposition and interference (related to entanglement in multi-qubit settings)
## Question: 
How might non-local correlations aid in querying databases?

--- 

# Introduction to the Query Model

## Definition: 
In the query model, algorithms access input via oracle queries rather than direct reading; measures complexity by number of queries
### Classical Query Model: 
Deterministic or probabilistic queries to a black-box function
### Quantum Query Model: 
Superposition queries; oracle as unitary operator
### Why Important? 
Highlights quantum advantages in information access; basis for many algorithms
### Formal Setup: 
Oracle $O_f$ for function $f: {0,1}^n → {0,1}^m$; quantum: $O_f |x⟩|y⟩ = |x⟩|y ⊕ f(x)⟩$
### Relevance to Data Science: 
Models database searches or function evaluations in ML

---

# Black-Box Oracles

## Concept: 
Oracle as a "black box" computing $f(x)$ without revealing internals; assumed efficient
## In Quantum Computing: 
Implemented as reversible unitary gates; preserves superposition
## Examples:
### Bit flip oracle: 
$|x⟩|b⟩ → |x⟩|b ⊕ f(x)⟩$ (for single-bit output)
### Phase oracle: 
$|x⟩ → (-1)^{f(x)} |x⟩$ (for interference-based algorithms)


## Implementation Note: 
In theory, oracles are assumed; in practice, circuits simulate them
## Properties: 
Unitary, reversible; enables quantum parallelism (query all x simultaneously)
## Discussion: 
Why can't classical computers query in superposition?

---

# Deutsch-Jozsa Problem

##Problem Statement: 
Given oracle for $f: {0,1}^n → {0,1}$, promised constant (all 0 or all 1) or balanced (half 0, half 1); determine which
## Motivation: 
First algorithm showing quantum exponential speedup (deterministic)
## Classical Solution: 
Worst-case $2^{n-1} + 1$ queries (check half +1 inputs)
## Quantum Advantage: 
Single query suffices
## Relevance: 
Demonstrates power of quantum parallelism for decision problems in AI

---

# Deutsch-Jozsa Quantum Algorithm

## High-Level Steps:
1. Initialize n qubits in $|0⟩^n$ and auxiliary in $|1⟩$
2. Apply H to all: Superposition $|+⟩^n \mapsto$ (where $\mapsto = ( |0⟩ - |1⟩ )/√2$ )
3. Query oracle: $O_f$ applies $f$ in parallel
4. Apply H to first n qubits
5. Measure first n: All 0 → constant; else balanced


## Why It Works: 
For constant, no phase flips → back to $|0⟩^n$; for balanced, interference → non-zero
## Mathematical Insight: 
Output amplitude for $|0⟩^n: (1/2^n) ∑_x (-1)^{f(x)}$

---

# Deutsch-Jozsa Circuit and Analysis

## Circuit Diagram:

$|0⟩^n --[H]--[O_f]--[H]-- Measure$ \\
$|1⟩\;\; --[H]--[\quad\:]---------$


##Query Complexity: 
###Quantum: 
1 query; Classical: $O(2^n)$ worst-case
###Speedup: 
Exponential in deterministic setting
###Limitations: 
Artificial promise; but foundational for query-based algos
### In Qiskit: 
Theoretical circuit; implementation for homework using oracles

---
# Bernstein-Vazirani Problem

## Problem Statement: 
Given oracle for $f(x) = s · x (mod 2)$, where $s$ is hidden $n$-bit string; find $s$
## Classical Solution: 
$n$ queries (query basis vectors $e_i$ to get $s_i$)
## Quantum Advantage: 
Single query finds entire $s$
##Extension of Deutsch-Jozsa: 
Generalizes to linear functions
## Applications: 
Hidden pattern recognition in data analysis

---

# Bernstein-Vazirani Quantum Algorithm

## Steps (Similar to DJ):
1. Initialize $|0⟩^n |1⟩$
2. Apply $H$ to all: $|+⟩^n \mapsto $
3. Query $O_f$: Applies phase $(-1)^{s·x}$ to each $|x⟩$
4. Apply $H$ to first $n$
5. Measure: Yields $s$ directly


##Why? 
Fourier transform nature: $H^n$ is quantum Fourier over $Z_2^n$; extracts s
## Mathematical: 
Final state $|s⟩ \mapsto$ (up to normalization)

---

# Bernstein-Vazirani Circuit and Analysis

## Circuit: 
Identical to DJ, but oracle specific to linear $f$
## Query Complexity: 
Quantum: 1; Classical: n (linear)
# Speedup: 
Polynomial (factor $n$), but deterministic quantum vs. classical
# Generalization: 
Basis for more complex query algos like Simon's
# AI Context: 
Efficiently learns linear models or hidden shifts in features

# Query Complexity Analysis

## General Framework: 
Lower bounds via adversary method or polynomial method
### For DJ: 
Quantum $O(1)$, classical $Ω(2^n)$
## For BV: 
Quantum $O(1)$, classical $Ω(n)$
## Broader Implications: 
Query model separates quantum from classical (e.g., PARITY requires $Ω(n)$ classical, $O(1)$ quantum with phases)
## In NISQ Era: 
Query counts matter for error-prone hardware
## Theoretical Tools: 
Decision trees (classical) vs. quantum circuits

---

# Applications in Quantum AI

## Query Algorithms in ML:
Efficient oracles for feature extraction or similarity search
## Hybrid models: 
Quantum queries in classical pipelines for big data
## Speedups in optimization: 
Query-based subroutines in QAOA


## Data Science Use Cases: 
Database searching, pattern matching in graphs
## Challenges: 
Oracle implementation; noise in real queries
## Discussion: 
How could DJ/BV inspire quantum-enhanced classifiers?

---

# Learning Objectives Review

## Objectives:
- Understand query model and oracles
- Analyze DJ and BV algorithms (steps, circuits, speedups)
- Evaluate quantum advantages in query complexity


## Assessment: 
Homework on algorithm derivations; labs for Qiskit implementations
## Connection to Course: 
Builds toward Grover's (next) and quantum ML algos

## Suggested Resources

### Qiskit Tutorials:
Deutsch-Jozsa on IBM Quantum Learning
Bernstein-Vazirani with Qiskit (Q-munity)
Medium article on BV in Qiskit
### Guides to Quantum Algorithms:
Ultimate Guide to Quantum Algorithms (SpinQ)
Beginner's Guide to Understanding Quantum Algorithms
IBM Quantum Learning Platform
### Further Reading: 
Nielsen & Chuang Ch. 3; \\
Preskill Notes on Quantum Algorithms

# Q&A and Looking Ahead

## Questions:
- Why is the oracle model useful despite being abstract?
- Potential real-world oracles in AI?


## Discussion: 
- Limits of query speedups in practical quantum hardware
## Next Session: 
- Unstructured Search (Grover's Algorithm)
## Homework Reminder: 
HW 1 covers sessions 1-4, including query algos
