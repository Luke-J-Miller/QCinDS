# Special Topics CS490/5590 - Quantum Computing Applications in Data Science, AI, & Deep Learning
This course is designed to provide students with a strong foundation in quantum computing, with a specific emphasis on applications in data science and artificial intelligence. Throughout the course, students will develop an understanding of quantum mechanics principles, quantum algorithms, and the implementation of quantum models using Qiskit.  
  
By the end of the term, students will be able to:

- Construct and manipulate quantum circuits for computation and data processing.
- Understand key quantum algorithms, including Grover's search and Shor’s factoring algorithm.
- Explore variational quantum optimization techniques such as QAOA and VQE.
- Apply quantum machine learning methods, including quantum support vector machines, quantum convolutional neural networks, and quantum feature selection.
- Integrate quantum computing with classical machine learning pipelines for hybrid AI applications.
- Develop and present a final project demonstrating a quantum-enhanced approach to an AI or data science problem.

The course balances theoretical insights with practical implementation, enabling students to engage with the latest advancements in quantum computing for data-driven applications.
** Prerequisites:** Linear Algebra, Python, Calculus

** Focus: ** Fundamental Quantum Computation, Quantum Optimization, Quantum Machine Learning (QML), and AI Applications
## Course Outline
### Quantum Foundations

#### 1. Intro to Quantum Computing & Qiskit

##### Description: 
This session introduces the fundamental differences between classical and quantum computing, including concepts like qubits, superposition, and quantum measurement. Students will set up Qiskit and run their first quantum circuit on a simulator.
##### Key Concepts/Subtopics: 
Classical bits vs. qubits; basic quantum states (Dirac notation); quantum parallelism; installing Qiskit and using IBM Quantum Experience; creating a simple quantum circuit with measurement.
##### Learning Objectives: 
Understand the motivation for quantum computing; install and configure Qiskit; execute a basic quantum program.
##### Suggested Resources: 
IBM Quantum Learning platform for introductory courses; Qiskit YouTube tutorial on introduction and hands-on setup.


#### 2. Quantum Circuits & Gates

##### Description: 
Exploration of quantum circuits as sequences of operations on qubits, focusing on single- and multi-qubit gates. Students will build and visualize circuits in Qiskit.
##### Key Concepts/Subtopics: 
Single-qubit gates (X, Y, Z, Hadamard, S, T); controlled gates (CNOT, CZ); circuit composition and decomposition; Bloch sphere representation; quantum circuit diagrams.
##### Learning Objectives: 
Identify and apply basic quantum gates; construct multi-qubit circuits; visualize gate effects using Qiskit tools.
##### Suggested Resources: 
Qiskit documentation tutorials on quantum circuits; Hands-on guide to quantum programming with Qiskit.


#### 3. Entanglement & Bell States

##### Description: 
Discussion of quantum entanglement as a key resource in quantum computing, with hands-on creation of Bell states and exploration of their properties.
##### Key Concepts/Subtopics: 
EPR paradox; Bell inequalities; creating entangled states (e.g., Bell pairs); measuring correlations; applications in quantum teleportation and superdense coding.
##### Learning Objectives:
Explain entanglement and its non-classical nature; generate and manipulate entangled states in Qiskit; demonstrate Bell state measurements.
##### Suggested Resources: 
IBM Quantum tutorials on advanced quantum information; Introductory Qiskit notebook examples from community tutorials.



### Basic Quantum Algorithms

#### 4. Quantum Query Algorithms

##### Description: 
Introduction to the query model in quantum computing, covering oracles and how quantum algorithms can outperform classical ones in query complexity.
##### Key Concepts/Subtopics: 
Black-box oracles; Deutsch-Jozsa algorithm for balanced vs. constant functions; Bernstein-Vazirani for hidden strings; query complexity analysis.
##### Learning Objectives: 
Understand the query model; implement simple query algorithms in Qiskit; analyze quantum speedups.
##### Suggested Resources: 
Qiskit tutorials on quantum algorithms; Guide to learning quantum algorithms.


#### 5. Unstructured Search

##### Description: 
Detailed study of Grover's algorithm for searching unstructured databases, including circuit implementation and amplitude amplification.
##### Key Concepts/Subtopics: 
Grover's oracle; diffusion operator; quadratic speedup over classical search; multiple solutions and iterations; Qiskit implementation on simulators.
##### Learning Objectives: 
Derive Grover's algorithm steps; build and optimize Grover circuits; apply to data search problems.
##### Suggested Resources: 
Qiskit community tutorials on Grover's algorithm; Coding with Qiskit video series on algorithms.


#### 6. Quantum Noise & Transpilation

##### Description: 
Examination of real-world quantum hardware challenges, including noise models and circuit optimization via transpilation.
##### Key Concepts/Subtopics: 
Types of quantum noise (decoherence, gate errors); error mitigation techniques; transpiler passes in Qiskit (optimization levels); simulating noisy backends.
##### Learning Objectives: 
Model quantum noise in simulations; use Qiskit transpiler to optimize circuits; evaluate circuit performance under noise.
##### Suggested Resources: 
IBM Quantum documentation on noise and performance enhancement.


#### 7. Phase Estimation & Factoring

##### Description: 
Coverage of quantum phase estimation (QPE) and its application in Shor's factoring algorithm for breaking RSA encryption.
##### Key Concepts/Subtopics: 
Quantum Fourier Transform (QFT); eigenvalue estimation; period finding in Shor's algorithm; modular arithmetic; Qiskit implementation challenges.
##### Learning Objectives: 
Implement QPE and QFT circuits; understand Shor's algorithm phases; simulate factoring small numbers.
##### Suggested Resources: 
Qiskit tutorials on phase estimation and Shor's algorithm; Coding with Qiskit on Shor's.



### Quantum AI

#### 8. QAOA & Applications

##### Description: 
Introduction to the Quantum Approximate Optimization Algorithm (QAOA) for solving combinatorial optimization problems.
##### Key Concepts/Subtopics: 
MaxCut and other NP-hard problems; variational parameters; mixer and cost Hamiltonians; optimization loops in Qiskit; applications in data science (e.g., graph partitioning).
##### Learning Objectives: 
Formulate problems for QAOA; implement and tune QAOA circuits; evaluate performance against classical solvers.
##### Suggested Resources: 
Qiskit optimization tutorials; Qiskit Machine Learning building blocks.


#### 9. Variational Quantum Eigensolver (VQE)

##### Description: 
Study of VQE for finding ground states of molecular Hamiltonians, with ties to quantum chemistry and optimization.
##### Key Concepts/Subtopics: 
Ansatz circuits (e.g., UCCSD); expectation value computation; classical optimizers (SPSA, COBYLA); hybrid quantum-classical workflow; Qiskit Nature integration.
##### Learning Objectives: 
Build VQE circuits; integrate with classical optimization; apply to simple molecules or Ising models.
##### Suggested Resources: 
Qiskit Machine Learning tutorial on VQE; Variational algorithms in IBM docs.


#### 10. Quantum Kernels/QSVMs


##### Description: 
Exploration of quantum kernels for enhancing support vector machines in high-dimensional feature spaces.
##### Key Concepts/Subtopics: 
Kernel theory; quantum feature maps; QSVM classification; kernel estimation circuits; comparison with classical SVMs; Qiskit implementation.
##### Learning Objectives: 
Construct quantum kernels; train QSVM models on datasets; evaluate accuracy and quantum advantage.
##### Suggested Resources: 
Qiskit Machine Learning tutorials on quantum kernels and QSVM; Introduction to Qiskit ML.


#### 11. Quantum Feature Selection


##### Description: 
Techniques for selecting relevant features using quantum algorithms, improving machine learning efficiency.
##### Key Concepts/Subtopics: 
Quantum mutual information; feature maps for selection; hybrid approaches with classical ML; applications in data preprocessing; Qiskit-based experiments.
##### Learning Objectives: 
Implement quantum feature selection methods; integrate into ML pipelines; assess impact on model performance.
##### Suggested Resources: 
Advanced Qiskit ML tutorials on kernels and data processing; Quantum machine learning resources.

### Midterm

#### 12. Midterm Review


##### Description: 
Comprehensive review of sessions 1-11, including key algorithms, circuits, and Qiskit implementations. Group discussions and practice problems.
##### Key Concepts/Subtopics: 
Recap of foundations, algorithms, and quantum AI basics; common pitfalls in circuit design; sample exam questions.
##### Learning Objectives: 
Consolidate knowledge; identify weak areas; prepare for exam.
##### Suggested Resources: 
Review materials from Qiskit community tutorials.


#### 13. Midterm Exam


##### Description: 
In-class exam covering theoretical and practical aspects from sessions 1-11.
##### Format: 
Mix of multiple-choice, short answers, circuit design, and Qiskit coding problems (20% of grade).

### Quantum Deep Learning

#### 14. Quantum Neural Networks


##### Description: 
Introduction to parameterized quantum circuits as neural networks for machine learning tasks.
##### Key Concepts/Subtopics: 
Quantum circuit learning; variational quantum classifiers/regressors; training with gradient descent; Qiskit ML integration.
##### Learning Objectives: 
Build and train QNNs; compare with classical NNs; apply to classification datasets.
##### Suggested Resources: 
Qiskit Machine Learning tutorial on quantum neural networks; Neural network classifier tutorial.


#### 16. Hybrid Methods


##### Description: 
Strategies for combining quantum and classical components in AI pipelines.
##### Key Concepts/Subtopics: 
Quantum-classical interfaces; data encoding/decoding; hybrid optimization loops; use cases in deep learning; Qiskit with PyTorch or TensorFlow.
##### Learning Objectives: 
Design hybrid architectures; implement data flow between quantum and classical systems; optimize hybrid models.
##### Suggested Resources: 
Training quantum models on real datasets tutorial; Qiskit for machine learning guide.


#### 17. Quantum-CNNs


##### Description: 
Quantum analogs of convolutional neural networks for image and sequence data processing.
##### Key Concepts/Subtopics: 
Quanvolutional layers; parameter sharing in quantum circuits; applications in computer vision; Qiskit implementations.
##### Learning Objectives: 
Construct QCNN architectures; train on image datasets; evaluate quantum enhancements.
##### Suggested Resources: 
Qiskit ML tutorials on advanced neural networks; Quantum machine learning with Qiskit.


#### 18. Quantum-GNNs


##### Description: 
Quantum graph neural networks for processing graph-structured data in AI.
##### Key Concepts/Subtopics: 
Graph encoding in quantum states; quantum message passing; applications in social networks or molecular graphs; hybrid QGNN models.
##### Learning Objectives: 
Implement QGNN layers; apply to graph classification tasks; analyze scalability.
##### Suggested Resources:
Qiskit ML building blocks for networks; Resources on quantum machine learning algorithms.


#### 18. Final Project Description/Rubric


##### Description: 
Detailed overview of the final project requirements, including proposal guidelines and evaluation criteria.
##### Key Concepts/Subtopics: 
Project ideas (e.g., quantum-enhanced ML model); milestones (proposal, progress report, presentation); rubric focusing on innovation, implementation, and analysis.
##### Learning Objectives: 
Plan a quantum AI project; align with course topics; prepare for development.
##### Suggested Resources: 
Example projects from Qiskit community.


#### 19. Quantum-Bayes


##### Description: 
Quantum extensions of Bayesian inference and networks for probabilistic modeling.
##### Key Concepts/Subtopics: 
Quantum Bayesian networks; phase estimation for probabilities; applications in uncertainty quantification; Qiskit simulations.
##### Learning Objectives: 
Model Bayesian problems quantumly; implement inference circuits; compare with classical Bayes.
##### Suggested Resources:
Advanced quantum ML tutorials; Quantum machine learning resources.


#### 20. Quantum K-Means


##### Description: 
Quantum versions of K-means clustering for unsupervised learning on large datasets.
##### Key Concepts/Subtopics: 
Distance estimation via quantum circuits; quantum amplitude encoding; hybrid clustering algorithms; performance analysis.
##### Learning Objectives: 
Implement quantum K-means; cluster data using Qiskit; evaluate clustering quality.
##### Suggested Resources: 
Qiskit ML on kernel methods and clustering; Qiskit for quantum ML.


#### 21. Quantum GAN


##### Description:
Quantum generative adversarial networks for generating data distributions.
##### Key Concepts/Subtopics: 
Quantum generators and discriminators; variational training; applications in synthetic data generation; challenges with barren plateaus.
##### Learning Objectives: 
Build QGAN architectures; train on simple datasets; assess generated samples.
##### Suggested Resources: 
Qiskit ML tutorials on quantum neural networks (extendable to GANs); Quantum machine learning with Qiskit.


#### 22. Quantum Autoencoder


##### Description: 
Quantum autoencoders for dimensionality reduction and anomaly detection.
##### Key Concepts/Subtopics: 
Encoding/decoding circuits; loss functions for reconstruction; applications in data compression; hybrid integrations.
##### Learning Objectives: 
Design quantum autoencoders; train and evaluate on datasets; apply to AI tasks.
##### Suggested Resources: 
Qiskit ML on variational models; Tutorials on quantum neural networks.

### Final Exam

#### 23. Final Review Session


##### Description: 
Cumulative review of all course material, with emphasis on quantum deep learning and project insights. Practice problems and Q&A.
##### Key Concepts/Subtopics: 
Integration of topics; advanced applications; exam preparation strategies.
##### Learning Objectives: 
Synthesize course knowledge; resolve doubts; gear up for final assessment.
##### Suggested Resources: 
Comprehensive Qiskit learning paths.


#### 24. Final Exam


##### Description: 
Comprehensive exam covering all sessions, with focus on practical implementations and theoretical understanding (25% of grade).
##### Format: 
Theoretical questions, circuit designs, coding exercises, and essay on quantum AI applications.

## Deliverables
### Homework (15%)
Each homework assignment includes theoretical questions, circuit design exercises, and Qiskit coding tasks. Submissions via Jupyter notebooks.

##### HW 0: How to submit/More about you (Session 1)

Setup Qiskit environment; short survey on background and interests.


##### HW 1: Sessions 1-4

Problems on quantum basics, circuits, gates, and entanglement; simple Qiskit scripts.


##### HW 2: Sessions 5-8

Implement Grover's and QAOA; analyze query algorithms and optimization.


##### HW 3: Sessions 9-11

VQE simulations; QSVM on toy datasets; feature selection exercises.


##### HW 4: Sessions 14-17 (Note: Original outline skips HW 5; assuming renumbering or addition here for coverage)

Quantum NNs and hybrid methods; QCNN and QGNN implementations.


##### HW 5: Sessions 19-22 (Adjusted for consistency)

Quantum Bayes, K-means, GAN, and autoencoder problems.



### Labs (15%)
Hands-on labs using Qiskit, graded on completion, correctness, and analysis. Run on simulators or IBM Quantum hardware.

##### Lab 0: Quantum Hello World (Session 2)

Build and execute a basic circuit with gates and measurements.


##### Lab 1: Grover's Algorithm (Session 5)

Implement Grover for a small search space; visualize iterations.


##### Lab 2: Variational Quantum Eigensolver (Session 9)

Solve a simple Hamiltonian; tune parameters.


##### Lab 3: QSVM (Session 14) (Adjusted to match outline; original has Session 14 for QNN, but aligns with QSVM)

Classify iris dataset using quantum kernels.


##### Lab 4: QCNN (Session 16)

Build and train a quantum convolutional network on images.



## Tests (45%)

##### Midterm - Sessions 1-11 (20%)

As described in session 13.


##### Final - Cumulative (25%)

As described in session 24.



## Final Project (25%)
Students will propose, develop, and present a quantum-enhanced AI or data science application (e.g., quantum-boosted recommender system or anomaly detection). Milestones: Proposal (week 10), Progress Report (week 15), Final Presentation and Report (week 24). Rubric: Innovation (30%), Technical Implementation (40%), Analysis/Results (20%), Presentation (10%). Use Qiskit for core quantum components; integrate with scikit-learn or PyTorch for hybrids. Suggested resources: Qiskit ML examples.
