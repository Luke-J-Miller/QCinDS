# Introduction to Quantum Computing & Qiskit
Welcome to the Course

Course: CS490/5590 - Quantum Computing Applications in Data Science, AI, & Deep Learning
# Intro to Quantum Computing & Qiskit
## Instructor: 
Luke Miller
## Level: 
Graduate/Advanced Undergraduate
## Objective: 
Build a theoretical foundation in quantum computing principles, with an overview of Qiskit for implementation
## Agenda:
- Motivation and overview
- Classical vs. quantum computing 
- Qubits, superposition, and measurement 
- Quantum parallelism and basic concepts 
- Introduction to Qiskit and tools 
- Summary and preview 

# Course Context and Prerequisites

## Course Focus: 
Quantum foundations applied to data science, AI, and deep learning
## Prerequisites Review:
### Linear Algebra: 
Vectors, matrices, eigenvalues (essential for quantum states)
### Python: 
Basic programming; Qiskit uses Python
### Calculus: 
Derivatives, integrals (for optimization in variational algorithms)



# Motivation for Quantum Computing

## Challenges in Classical Computing:
- Exponential complexity in problems like factoring (RSA security), molecular simulation, optimization
- AI bottlenecks: Training large models, searching vast datasets


## Quantum Advantages:
- Exponential state space: ( n ) qubits represent ( 2^n ) states
- Speedups: Polynomial or quadratic for specific problems
- Applications in Data Science/AI: Quantum ML for high-dimensional data, optimization for logistics/neural nets


## Historical Context:
- Feynman (1982): Simulate quantum systems with quantum computers
- Shor (1994), Grover (1996): Key algorithms
- Current Era: NISQ (Noisy Intermediate-Scale Quantum) devices



# Current Landscape of Quantum Computing

## Hardware Providers: 
IBM (superconducting qubits), Google (Sycamore), IonQ (trapped ions), Rigetti
## Quantum Supremacy: 
Google's 2019 claim; debated, but highlights potential
## Software Ecosystems: 
Qiskit (IBM), Cirq (Google), PennyLane (Xanadu for ML)
## Challenges: 
Decoherence, error rates, scalability (current ~100-1000 qubits)
## Relevance to AI: 
Quantum kernels for SVMs, variational circuits for NNs
## Timeline: 
Practical quantum AI expected in 5-10 years (as of 2025)

# Classical Computing Fundamentals

## Bits and Gates:
- Bit: Binary state (0 or 1)
- Logic Gates: NOT, AND, OR; reversible/irreversible
- Computation: Deterministic, sequential/parallel


## Linear Algebra View:
- State as vector: Bit 0 = 
$$ \begin{pmatrix} 1 \ 0 \end{pmatrix} $$
- Gates as matrices: NOT = $ \begin{pmatrix} 0 & 1 \ 1 & 0 \end{pmatrix} $


Limitations:
No inherent parallelism beyond classical limits
Exponential time for certain problems (e.g., traveling salesman)



Slide 6: Transition to Quantum Computing

Key Principles from Quantum Mechanics:
Wave-particle duality, uncertainty principle
But focus on computational aspects: States as vectors in Hilbert space


Quantum vs. Classical:
Probabilistic vs. deterministic outcomes
Unitary (reversible) operations only
Measurement collapses state


Mathematical Framework:
Hilbert Space: Complex vector space with inner product
States: Normalized vectors ( |\psi\rangle ), ( \langle \psi | \psi \rangle = 1 )



Slide 7: Qubits: The Building Block

Definition:
Qubit: Unit vector in 2D complex Hilbert space
General State: ( |\psi\rangle = \alpha |0\rangle + \beta |1\rangle ), ( |\alpha|^2 + |\beta|^2 = 1 )


Basis States:
( |0\rangle = \begin{pmatrix} 1 \ 0 \end{pmatrix} ), ( |1\rangle = \begin{pmatrix} 0 \ 1 \end{pmatrix} )


Superposition:
Linear combination: Allows representing multiple states
Example: Equal superposition ( |\psi\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) )


Physical Realizations: Electron spin, photon polarization, superconducting loops

Slide 8: Superposition in Depth

Theoretical Insight:
Superposition arises from linearity of Schrödinger equation
Enables quantum parallelism: Operate on all basis states at once


Multi-Qubit Systems:
Tensor Product: 2 qubits ( |\psi\rangle \otimes |\phi\rangle )
State Space: Dimension ( 2^n ) for n qubits


Example:
3 qubits: 8 basis states, coefficients for each


Implications for Computing: Algorithms exploit interference to amplify desired outcomes

Slide 9: Quantum Measurement

Postulate:
Measurement in basis ( {|0\rangle, |1\rangle} ): Outcomes 0 or 1 with probabilities ( |\alpha|^2, |\beta|^2 )
Collapses wavefunction: Post-measurement state is the outcome eigenvector


Born Rule: Probability = squared amplitude
Ensemble Interpretation: Repeat experiments to estimate probabilities
Mathematical Representation:
Projectors: ( P_0 = |0\rangle\langle0| ), expectation ( \langle \psi | P_0 | \psi \rangle = |\alpha|^2 )


Challenge: Irreversibility; no cloning theorem prevents copying states

Slide 10: Quantum Parallelism

Concept:
Apply unitary operation U to superposition: U acts on all components simultaneously
Example: Compute f(x) for all x in superposition


Deutsch's Algorithm Insight:
Determine if function is constant or balanced with one query (vs. classical multiple)


Limits:
Measurement yields one result; need clever extraction (e.g., interference)


AI Tie-In: Parallel evaluation in feature spaces for ML kernels

Slide 11: Introduction to Quantum Gates

Unitary Operators:
Gates: 2x2 unitary matrices (preserve norms)
Example: Hadamard H = ( \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \ 1 & -1 \end{pmatrix} ) creates superposition


Reversibility: All quantum gates are invertible (U^\dagger U = I)
Preview of Session 2: Single-qubit (X, Y, Z, H) and multi-qubit gates (CNOT)

Slide 12: Overview of Qiskit

Role in the Course: Framework for implementing quantum circuits (hands-on in labs/HW)
Key Features:
Python API: Build circuits with QuantumCircuit class
Simulators: Aer for classical simulation (statevector, density matrix)
Backends: Access IBM quantum hardware via cloud


Basic Workflow:
Create circuit, apply gates, measure
Execute on simulator/hardware, analyze results


Setup Note: Detailed instructions in provided materials; install via pip

Slide 13: Theoretical Example: Simple Circuit

Conceptual Circuit:
1 qubit, apply H gate, measure
Initial: |0\rangle
After H: ( \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) )
Measurement: 50% |0\rangle, 50% |1\rangle


Matrix Form:
State evolution: H |0\rangle = superposition vector


Discussion: No code here; implement in HW 0

Slide 14: Quantum Computing in AI Context

Quantum Machine Learning (QML):
Use quantum states for data encoding
Algorithms like QSVM leverage kernel trick in quantum space


Hybrid Approaches: Combine quantum subroutines with classical ML
Potential Impact: Exponential speedup in training or inference for certain models

Slide 15: Challenges and Open Questions

Decoherence: Qubits lose coherence quickly (~ms)
Error Correction: Needs many physical qubits per logical qubit
Scalability: From NISQ to fault-tolerant quantum computers
Theoretical Limits: BQP complexity class; not all problems sped up

Slide 16: Summary of Key Concepts

Quantum computing exploits superposition and measurement for parallelism
Qubits as vectors in Hilbert space
Foundations for algorithms in later sessions (Grover, Shor)
Qiskit as tool for exploration (theory today, practice in labs)

Slide 17: Preview of Session 2

Quantum Circuits & Gates
Theoretical: Gate matrices, universality
Multi-qubit operations
Circuit decomposition


Homework 0 Reminder: Setup Qiskit, background survey; due before next session

Slide 18: Q&A and Discussion

Questions on Theory?
Superposition vs. classical probability
Measurement implications
Linear algebra connections


Discussion Prompts:
How might superposition aid AI optimization?
Ethical considerations in quantum-enhanced AI


