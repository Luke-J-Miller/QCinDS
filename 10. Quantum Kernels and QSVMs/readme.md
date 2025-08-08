$\huge{\textbf{ Quantum Kernels and QSVMs}}$
# Session Overview

## Objective: 
Understand quantum kernels and their use in QSVMs for classification tasks
## Agenda:
- Recap of VQE
- Introduction to kernel methods
- Quantum feature maps
- Quantum kernel estimation
- QSVM classification
- Comparison with classical SVMs
- Qiskit implementation
- Applications in AI and data science
- Q&A

---

# Recap from Session 9

## Key Points:
- VQE: Finds ground state energies using variational ansatz
- Components: Ansatz (e.g., UCCSD), expectation values, classical optimizers (SPSA, COBYLA)
- Hybrid workflow: Quantum state prep, classical optimization
- SQD/SKQD: Emerging methods for noise-robust VQE


## Connection to Today: 
QSVMs use quantum circuits as feature maps, leveraging variational principles for ML
## Question: 
How might quantum feature maps improve classical ML?

---

# Introduction to Kernel Methods

## Kernel Methods in ML:
Transform data into high-dimensional space for linear separability
### Kernel function: 
- ( $K(x_i, x_j) = \langle \phi(x_i), \phi(x_j) \rangle$ ), where ($\phi$) is feature map
- Avoids explicit computation of (\phi(x))


## Support Vector Machines (SVMs):
Maximize margin between classes using kernel trick
### Optimize: 
( $\max \sum_i \alpha_i - \frac{1}{2} \sum_{i,j} \alpha_i \alpha_j y_i y_j K(x_i, x_j) $)


## Classical Kernels: 
Linear, polynomial, RBF (Gaussian)
## Quantum Potential: 
Quantum circuits as feature maps for complex data

---

# Quantum Feature Maps

## Definition: 
Quantum circuit ( $U_\phi(x)$ ) encoding data ( $x$ ) into quantum state ( $|\phi(x)\rangle = U_\phi(x)|0\rangle^n$ )
## Purpose: 
Maps classical data to high-dimensional Hilbert space ($2^n$ dimensions)
## Common Forms:
### ZZ Feature Map: 
- ( $U_\phi(x) = \prod_i e^{-i x_i Z_i} \prod_{i<j} e^{-i (x_i - x_j)^2 Z_i Z_j} $)
- Entangling gates for non-linear features


### Pauli Feature Map: 
Uses X, Y, Z rotations based on data


## Properties: 
Leverages entanglement, superposition for rich representations
## AI Relevance: 
Enhances separability for complex datasets (e.g., images)


---

# Quantum Kernel

## Definition: 
( $K(x_i, x_j) = |\langle \phi(x_i) | \phi(x_j) \rangle|^2 = | \langle 0 | U_\phi^\dagger(x_i) U_\phi(x_j) | 0 \rangle |^2 $)
## Interpretation: 
Measures similarity of quantum states
## Properties:
- Positive semi-definite (valid kernel)
- Captures non-linear patterns via quantum entanglement


## Computation: 
Run circuit for ( $U_\phi^\dagger(x_i) U_\phi(x_j)$ ), measure probability of $|0\rangle^n$
## Advantage: 
Accesses $2^n$-dimensional space with $n$ qubits
## ML Context: 
Replaces classical kernels in SVM training

---

# Quantum Kernel Estimation Circuit

Circuit for 
-$K(x_i, x_j):|0\rangle^n --[U_\phi(x_j)]--[U_\phi^\dagger(x_i)]-- Measure$


## Process:
- Prepare $|0\rangle^n$
- Apply ( $U_\phi(x_j)$ )
- Apply ( $U_\phi^\dagger(x_i)$ ) (inverse feature map)
- Measure: $P(|0\rangle^n) = | \langle \phi(x_i) | \phi(x_j) \rangle |^2$


## Challenge: 
Requires $O(N^2)$ circuits for $N$ data points
## NISQ Issue: 
Noise in feature map circuits affects kernel accuracy
## Qiskit Note: 
Implemented in Qiskit Machine Learning

--- 

# QSVM Classification

## Quantum SVM Workflow:
- Encode data into quantum feature map
- Compute kernel matrix K(x_i, x_j) using quantum circuits
- Train classical SVM with quantum kernel
- Predict using kernel evaluations


## Advantages:
- Quantum feature space may separate non-linear data better
- Potential quantum advantage for high-dimensional data


## Limitations: 
Noise, circuit depth, kernel computation cost
## AI Application: 
Classification of complex datasets (e.g., medical images)

---

# Comparison with Classical SVMs

## Classical SVMs:
### Kernels: 
Linear, RBF, polynomial
### Computation: 
- $O(N^2)$ for kernel matrix, efficient for small datasets
- Well-optimized libraries (e.g., scikit-learn)


## QSVMs:
### Quantum kernels: 
Exponential feature space with few qubits
### Computation: 
$O(N^2)$ circuits, noise-limited on NISQ
### Potential advantage: 
Complex data with quantum entanglement


### Performance: 
QSVM competitive on small datasets; scaling unclear
### Research Question: 
When does quantum kernel outperform RBF?

---

# Qiskit Implementation

## Qiskit Machine Learning Workflow:
- Define feature map (e.g., ZZFeatureMap)
- Create QuantumKernel with Aer simulator or hardware
- Use QuantumKernel in scikit-learn’s SVC
- Train and evaluate on dataset (e.g., iris, digits)


## Code Snippet (Conceptual):
```
from qiskit_machine_learning.kernels import QuantumKernel
from sklearn.svm import SVC
feature_map = ZZFeatureMap(num_qubits=2)
quantum_kernel = QuantumKernel(feature_map=feature_map, quantum_instance=Aer.get_backend('statevector_simulator'))
qsvm = SVC(kernel=quantum_kernel.evaluate)
qsvm.fit(X_train, y_train)
```

## Challenges: 
Noise, shot statistics, circuit depth
## Lab 3: 
Implement QSVM on iris dataset

---
# Applications in AI and Data Science

## Classification Tasks:
- Image classification (e.g., handwritten digits)
- Medical diagnostics (e.g., tumor detection)
- Anomaly detection in financial data


## Quantum Advantage Potential:
- High-dimensional, non-linearly separable data
- Small datasets with complex patterns


## Hybrid Pipelines: 
Quantum kernels + classical SVM for enhanced accuracy
## Discussion: 
How could QSVM improve feature engineering in ML?

---
# Theoretical Insights

## Kernel Theory: 
Quantum kernels are Mercer kernels, valid for SVM
## Feature Space: 
$2^n$ dimensions with $n$ qubits, but noise limits effective dimensionality
## Quantum Advantage: 
Hypothetical for specific data distributions
## Noise Impact: 
Errors in feature map reduce kernel fidelity
## Connection to Course: 
QSVM bridges to quantum neural networks, feature selection
## SQD/SKQD Note: 
Could enhance kernel estimation under noise (explored in labs)

# Learning Objectives Review

## Objectives:
- Construct quantum kernels using feature maps
- Train QSVM models on datasets
- Evaluate accuracy and potential quantum advantage


## Assessment: 
Homework on kernel theory; Lab 3 for QSVM implementation
## Connection to Course: 
Foundation for quantum deep learning algorithms

# Suggested Resources

## Qiskit Tutorials:
- Quantum Kernels and QSVM 
Introduction to Qiskit Machine Learning
## Further Reading:
- Havlíček et al., “Supervised Learning with Quantum-Enhanced Feature Spaces” (2019)
- Schuld & Petruccione, “Quantum Machine Learning” (book)
- Nielsen & Chuang Ch. 6 (kernel methods)


## Exploration: 
Compare QSVM vs. classical SVM on toy dataset

---

# Q&A and Looking Ahead

## Questions:
- When might quantum kernels outperform classical ones?
- Impact of noise on QSVM accuracy?


## Discussion: 
QSVM’s role in future quantum ML pipelines
## Next Session: 
Quantum Feature Selection
## Homework Reminder: 
HW 3 includes QSVM exercises
