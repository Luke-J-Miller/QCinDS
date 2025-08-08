$\huge{\textbf{Phase Estimation & Factoring}}$
# Slide 1: Session Overview
## Objective: 
Understand quantum phase estimation (QPE) and its role in Shor’s factoring algorithm
# Agenda:
- Recap of quantum noise
- Quantum Fourier Transform (QFT)
- Quantum phase estimation
- Shor’s factoring algorithm
- Period finding and modular arithmetic
- Qiskit implementation challenges
- Applications to AI and data science
- Q&A



# Recap from Session 6

## Key Points:
- Quantum noise: Decoherence (T1, T2), gate errors, measurement errors
- Noise models: Pauli, depolarizing, thermal relaxation
- Error mitigation: ZNE, readout correction, dynamical decoupling
- Transpilation: Optimizes circuits for hardware (gate count, depth)


## Connection to Today: 
Noise impacts deep circuits like QPE and Shor’s; understanding these is key for practical quantum algorithms
### Question: 
How might noise affect phase estimation accuracy in ML applications?

---

# Introduction to Quantum Phase Estimation (QPE)

## Purpose: 
Estimate the phase $θ$ of an eigenvalue $e^{i2πθ}$ for a unitary operator U and eigenvector $|ψ⟩$
## Input: 
Unitary $U$, eigenvector $|ψ⟩$ such that $U|ψ⟩ = e^{i2πθ}|ψ⟩$
## Output: 
Approximation of $θ$ to $n$-bit precision
## Applications: 
Core subroutine in Shor’s algorithm, quantum chemistry, and ML (e.g., eigenvalue problems)
## Significance: 
Enables solving problems intractable classically
## Relevance to AI: 
Estimating eigenvalues for data matrix analysis (e.g., PCA)

# Quantum Fourier Transform (QFT)

## Definition: 
Quantum analog of discrete Fourier transform, maps computational basis to Fourier basis
## Action: 
For $n$ qubits, $|x⟩ → (1/√2^n) ∑_{y=0}^{2^n-1} e^{\frac{i2πxy}{2^n}} |y⟩$
## Matrix Form: 
Unitary matrix with entries $[QFT]_{jk} = (1/√2^n) e^{i2πjk/2^n}$
## Circuit:
- Sequence of Hadamard and controlled phase gates ($R_k = diag(1, e^{i2π/2^k})$)
- Final swaps for bit order


## Complexity: 
$O(n^2)$ gates vs. classical FFT $O(n2^n)$
### Role: Extracts phase information in QPE; used in Shor’s for period finding

---

#: QFT Circuit and Intuition

## Circuit Structure (n=3):
- |0⟩ --[H]--•-----•-----swap--
-            |R_2  |R_3        |
- |0⟩ ------•-----[H]--•--swap--•--
-                  |R_2       |
- |0⟩ ------•-----------[H]-------•--


## Intuition: 
Encodes number $x$ as phase in superposition; like classical FFT but in quantum parallelism
## Inverse QFT (IQFT): 
Reverse circuit (swap H, $R_k$ → $R_{-k}$)
## AI Connection: 
QFT in quantum signal processing for time-series analysis

---

# Quantum Phase Estimation Algorithm

## Setup:
- Counting register: $n$ qubits for phase precision
- Eigenstate register: $m$ qubits for $|ψ⟩$


## Steps:
1. Initialize: $|0⟩^n |ψ⟩$
2. Apply $H^{\otimes n}$ to counting qubits: Superposition
3. Apply controlled-$U^{2^k}$ for $k=0$ to $n-1$: Encodes phase
4. Apply IQFT to counting qubits
5. Measure counting qubits: Yields $2^n θ$ (rounded)


## Accuracy: 
$n$ qubits give $\approx 1/2^n$ precision
## Circuit Depth: 
$O(n^2)$ for QFT + $O(n)$ controlled-U applications

---

# QPE Circuit and Analysis

## Circuit Diagram (simplified):
- |0⟩^n --[H]--[U^2^0]--[U^2^1]--...--[IQFT]-- Measure
- |ψ⟩   --[U]-------------------------------- |ψ⟩


## Output Probability: 
Peaks at state $|⌊2^n θ⌋⟩$
## Error Analysis: 
Noise in U or QFT reduces phase accuracy
## Complexity: 
Queries to U scale as $O(2^n)$ for high precision
## Challenge: 
Deep circuits require error correction or mitigation
## Qiskit Note:
Homework will simulate QPE for simple unitaries

---

# Shor’s Factoring Algorithm Overview

## Goal: 
Factorize integer $N$ into non-trivial factors (e.g., for RSA)
## Classical Difficulty: 
Best algorithms (e.g., GNFS) are sub-exponential
## Quantum Advantage: 
Polynomial time $O((log N)^3)$ with QPE
## Key Idea: 
Reduce factoring to period finding of $a^x mod N$
## Impact: 
Breaks RSA encryption; motivates quantum-safe cryptography
## Relevance to AI: 
Secure data processing in quantum ML systems

# Shor’s Algorithm: Period Finding

## Problem: 
Find period $r$ of $f(x) = a^x \text{ mod } N$, where $a$ is coprime to $N$
## Steps:
1. Choose random $a < N$, check gcd$(a,N)=1$
2. Use QPE on unitary $U: U|y⟩ = |ay$ mod $N⟩$
3. QPE outputs phase $φ ≈ s/r$ ($s$ random integer)
4. Use continued fractions to extract $r$
5. Check if $r$ is even and $a^{r/2} ≠ ±1$ mod $N$
6. Compute factors: gcd($a^{r/2} ± 1, N$)


## Probability: 
Success $> 1 - 1/\log N$ with few repetitions
## Oracle: 
U implements modular multiplication

---

# Shor’s Algorithm Circuit

## Components:
- Counting register for QPE
- Modular arithmetic register for $a^x$ mod $N$
- QFT for phase extraction


Simplified Circuit:
- |0⟩^n --[H]--[U_a^2^0]--[U_a^2^1]--...--[IQFT]-- Measure
- |0⟩^m ------------------------------------------- |ψ⟩


## $U_a$: 
Modular exponentiation (complex to implement)
## Depth Issue: 
Large n for precision → noise sensitivity
## AI Analogy: 
Period finding like pattern detection in time-series data

# Modular Arithmetic in Shor’s

## Challenge: 
Implementing $U: |x⟩|y⟩ → |x⟩|a^x y$ mod $N$⟩
## Classical Step: 
Precompute $a^x$ mod $N$ for efficiency
## Quantum Approach: 
- Reversible arithmetic circuits
- Addition, multiplication mod N using Toffoli gates
- Requires $O(log N)$ qubits, $O((log N)^2)$ gates


## Theoretical Insight: 
Modular exponentiation dominates circuit complexity
## Data Science Use: 
Modular operations in cryptographic ML tasks

---

# Qiskit Implementation Challenges

## QPE Issues:
- Deep circuits (QFT, controlled-U) sensitive to noise
- Large qubit count for realistic N


## Shor’s Issues:
- Modular exponentiation requires complex circuits
- Current NISQ devices limited to small N (e.g., 15, 21)


## Simulation Strategy: 
Use Aer simulator with small n; noise models for realism
## Mitigation: 
Apply techniques from Session 6 (ZNE, readout correction)
## Homework/Labs: 
Simulate QPE for simple unitaries, small factoring

---

# Applications in AI and Data Science

## Cryptography Impact:
- Shor’s threatens RSA, relevant for secure ML model distribution
- Drives quantum-safe algorithms for data privacy


## Period Finding Uses:
- Time-series analysis: Detect periodic patterns in data
## Signal processing: 
Quantum-enhanced Fourier methods


## QPE in ML: 
- Eigenvalue estimation for matrix-based algorithms (e.g., quantum PCA)
## Discussion: 
How might Shor’s inspire quantum algorithms for data analysis?

--- 

# Theoretical Insights

## QPE Accuracy: 
Error scales as 1/2^n; noise bounds via Kraus operators
## Shor’s Complexity: 
$O((log N)^3)$ quantum vs. $O(e^(log N)^(1/3))$ classical
## Optimality: 
Shor’s near-optimal for factoring
## Limitations: 
NISQ constraints; large-scale needs fault tolerance
## Connection to Course: 
QPE foundational for variational algorithms (VQE)

---
# Learning Objectives Review

## Objectives:
- Implement QPE and QFT circuits theoretically
- Understand Shor’s algorithm phases (period finding, factoring)
- Analyze challenges in Qiskit simulations
---

# Suggested Resources

## Qiskit Tutorials:
- Quantum Phase Estimation (IBM Quantum)
- Shor’s Algorithm in Qiskit
## Algorithm Guides:
- Coding with Qiskit: Shor’s Algorithm
## Further Reading: 
- Nielsen & Chuang Ch. 5; 
- Preskill Notes on Shor’s Algorithm

---

# Q&A and Looking Ahead

## Questions:
- How feasible is Shor’s on current quantum hardware?
- Role of QPE in other quantum ML algorithms?


## Discussion: 
- Quantum cryptography’s impact on secure AI
## Next Session: 
QAOA & Applications
## Homework Reminder: 
HW 2 includes QPE and Shor’s exercises
