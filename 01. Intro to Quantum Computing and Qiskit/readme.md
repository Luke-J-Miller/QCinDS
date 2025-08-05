Session 1: Introduction to Quantum Computing & Qiskit
Slide 1: Welcome to Quantum Computing!

Course: CS490/5590 - Quantum Computing Applications in Data Science, AI, & Deep Learning
Session 1: Intro to Quantum Computing & Qiskit
Instructor: [Your Name]
Objective: Provide a theoretical foundation in quantum computing principles and introduce Qiskit as a tool for implementation
Agenda (60 minutes):
Course overview and motivation (10 min)
Classical vs. quantum computing (10 min)
Key quantum concepts: Qubits, superposition, measurement (15 min)
Quantum parallelism and its implications (10 min)
Introduction to Qiskit framework (10 min)
Preview of hands-on via homework and resources (5 min)



Slide 2: Course Overview

Target Audience: Graduate or advanced undergraduate students with prerequisites in Linear Algebra, Python, and Calculus
Focus Areas:
Fundamental Quantum Computation
Quantum Optimization
Quantum Machine Learning (QML)
AI Applications


Structure:
Lectures: Theoretical concepts (this class)
Homework: Conceptual problems and basic implementations
Labs: Hands-on Qiskit experiments
Project: Quantum-enhanced AI/data science application


By End of Course: Ability to design quantum circuits, apply algorithms in AI, and integrate hybrid systems

Slide 3: Motivation for Quantum Computing

Challenges in Classical Computing:
Exponential complexity in problems like factoring (RSA security), optimization (NP-hard), and simulation (quantum systems)
Limits of Moore's Law: Scaling issues in transistors


Quantum Advantages:
Exponential state space: ( n ) qubits represent ( 2^n ) states
Speedups: Polynomial or quadratic in certain algorithms


Historical Context:
Feynman (1982): Simulating quantum systems requires quantum computers
Deutsch (1985): Quantum Turing machine
Shor (1994), Grover (1996): Landmark algorithms



Slide 4: Relevance to Data Science, AI, & Deep Learning

Applications:
Optimization: QAOA for portfolio optimization or logistics
Machine Learning: Quantum kernels for high-dimensional data classification
Deep Learning: Quantum neural networks for faster training on complex datasets
Data Processing: Quantum feature selection and clustering (e.g., quantum K-means)


Hybrid Approaches: Combine quantum for hard subproblems with classical ML pipelines
Current State: NISQ era (Noisy Intermediate-Scale Quantum) – Focus on variational algorithms
Future Impact: Potential disruption in drug discovery, finance, and AI model training

Slide 5: Classical Computing Fundamentals (Review)

Bits and Gates:
Binary states: 0 or 1
Logic gates: NOT, AND, OR – Irreversible operations


Computation Model:
Turing machine: Sequential processing
Parallelism: Limited by hardware (e.g., multi-core CPUs)


Limitations:
Time complexity: Exponential for certain problems (e.g., traveling salesman)
Space: Linear scaling



Slide 6: Transition to Quantum Computing

Quantum Mechanics Principles:
Wave-particle duality
Uncertainty principle
Probabilistic nature


Quantum vs. Classical:
Deterministic → Probabilistic
Bits → Qubits
Gates: Reversible unitary operations


Key Insight: Quantum computers harness physical phenomena for computation, not just simulate them

Slide 7: Qubits: The Building Block

Definition:
Quantum bit: Two-level quantum system (e.g., electron spin, photon polarization)
Mathematical representation: ( |\psi\rangle = \alpha |0\rangle + \beta |1\rangle ), where ( \alpha, \beta \in \mathbb{C} ), ( |\alpha|^2 + |\beta|^2 = 1 )


Basis States:
( |0\rangle = \begin{pmatrix} 1 \ 0 \end{pmatrix} ), ( |1\rangle = \begin{pmatrix} 0 \ 1 \end{pmatrix} )


Dirac Notation:
Bra: ( \langle \psi| ), Ket: ( |\psi\rangle )
Inner product: ( \langle \phi | \psi \rangle )



Slide 8: Superposition

Concept:
Qubit in linear combination of basis states
Allows representation of multiple states simultaneously


Example:
Balanced superposition: ( |\psi\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) )
General form: Amplitudes encode probabilities


Implications:
Enables parallel computation
Fragile: Decoherence collapses superposition


Mathematical View: Vector in Hilbert space

Slide 9: Measurement in Quantum Computing

Process:
Projects state onto basis vectors
Outcome probabilistic: ( P(0) = |\alpha|^2 ), ( P(1) = |\beta|^2 )


Collapse:
Irreversible: Post-measurement state is the observed basis state


Born Rule: Probability from amplitude squared
Example:
For ( |\psi\rangle = \frac{\sqrt{3}}{2} |0\rangle + \frac{1}{2} |1\rangle ), ( P(0) = 0.75 ), ( P(1) = 0.25 )


Challenge: Repeated measurements needed for statistics

Slide 10: Quantum Parallelism

Definition:
Ability to perform operations on all superposed states at once


Example (Single Qubit):
Apply function ( f(x) ) to superposed input: ( \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \rightarrow \frac{1}{\sqrt{2}} (|f(0)\rangle + |f(1)\rangle) )


Multi-Qubit:
( n ) qubits: Evaluate on ( 2^n ) inputs simultaneously


Limitation: Measurement yields one result; clever algorithms extract global information (e.g., period in Shor's)

Slide 11: Implications for Algorithms

Speedups:
Grover: ( O(\sqrt{N}) ) for search vs. ( O(N) ) classical
Shor: Polynomial for factoring vs. exponential classical


No General Speedup: Quantum not faster for all problems (e.g., no for NP-complete in general)
AI Relevance:
Parallel evaluation in feature spaces
Variational methods for optimization in ML training



Slide 12: Quantum Information Theory Basics

No-Cloning Theorem:
Cannot copy unknown quantum states perfectly
Implication: Quantum data is unique


Reversibility:
All quantum gates are unitary: ( U^\dagger U = I )


Density Matrices (Advanced):
For mixed states: ( \rho = \sum p_i |\psi_i\rangle \langle \psi_i| )
Useful in noisy systems and QML



Slide 13: Introduction to Qiskit

Overview:
IBM's open-source SDK for quantum programming
Python-based, modular design


Key Modules:
Terra: Circuit building, transpilation
Aer: Simulation backends
Ignis: Error mitigation
Nature/ML: Domain-specific libraries for chemistry and machine learning


Workflow:
Build circuit → Transpile → Execute (simulator/hardware) → Analyze results


Access: Local install or IBM Quantum cloud

Slide 14: Qiskit in Theory and Practice

Theoretical Role:
Implements quantum circuits as matrices and operators
Supports linear algebra operations (e.g., statevectors)


Example Concept (No Code in Class):
Hadamard gate: ( H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \ 1 & -1 \end{pmatrix} )
Creates superposition: ( H|0\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) )


Hands-On Deferred: Setup and first circuit in HW 0

Slide 15: Resources for Getting Started with Qiskit

Official Documentation: qiskit.org/documentation – Tutorials on basics
IBM Quantum Learning: learning.quantum.ibm.com – Free courses, videos
Textbooks:
"Quantum Computing for Computer Scientists" by Yanofsky & Mannucci
"Quantum Computation and Quantum Information" by Nielsen & Chuang (advanced)


Online Materials:
Qiskit Textbook (qiskit.org/textbook)
YouTube: Qiskit channel for conceptual overviews


Setup Guide: Provided in HW 0; install via pip

Slide 16: Preview of Session 2: Quantum Circuits & Gates

Topics:
Single-qubit gates (X, Y, Z, Hadamard)
Multi-qubit gates (CNOT, CZ)
Circuit composition and universality
Bloch sphere for visualization


Theory Focus: Matrix representations, unitarity, and effects on states

Slide 17: Homework and Labs Overview

HW 0 (Due Next Session):
Install Qiskit and verify setup
Run a simple superposition circuit (code provided)
Answer conceptual questions on qubits and measurement
Short survey on background


Lab 0 (Later): Quantum Hello World – Build and simulate basic circuit
Emphasis: Hands-on in homework/labs; class for theory

Slide 18: Q&A and Discussion

Questions to Ponder:
How does superposition enable parallelism, and what are its limits?
Why is measurement probabilistic, and how does it affect algorithm design?
Potential quantum advantages in your field of interest (AI/Data Science)?


Discussion (5 min): Share thoughts on quantum's role in future AI
Contact: [Your Email] for questions on concepts or setup
