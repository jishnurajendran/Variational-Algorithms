---
title: Variational Quantum Algorithms
subject: Quantum Computing
subtitle: Variational Quantum Algorithms for Quantum Computing
short_title: VQAs
authors:
  - name: Jishnu Rajendran
    orcid: 0000-0003-2598-1266
    email: jishnu.rajendran@dfa.unict.it
license: CC-BY-4.0
keywords: quantum computing, variational algorithms, quantum chemistry, optimization
tags: [VQAs, quantum computing, quantum algorithms, quantum chemistry, optimization]

abstract: Variational quantum algorithms (VQAs) are a class of hybrid quantum-classical algorithms that leverage the power of quantum computing to solve complex optimization and simulation problems. They are particularly useful for near-term quantum devices, which may not have the capability to run full-scale quantum algorithms. In this repository, we explore the principles and applications of VQAs, including their mathematical foundations, implementation details, and practical use cases. I am particulary interseted in real-world applications of VQAs, such as quantum chemistry, and optimization problems. The goal is to provide a comprehensive understanding of VQAs and their potential impact on various fields.
---
 ## Introduction

 As the development of quantum devices continues to advance, researchers are increasingly turning their attention to the design and implementation of quantum algorithms that can be executed on near-term quantum hardware. The current noisy intermediate-scale quantum (NISQ) devices are not yet capable of running full-scale quantum algorithms, but they can still be used to solve complex problems through the use of hybrid quantum-classical algorithms. One such class of algorithms is known as variational quantum algorithms (VQAs). VQAs are designed to combine the strength of quantum computing with classical optimization techniques, enabling the solutions of computationally challenging problems in areas such as  quantum chemistry, material science, combinatorial optimization, and machine learning.

## Variational Approach

At the core of VQAs is the variational principle, which states that the expectation value of the energy for any trial quantum state will always be greater than or equal to the true ground state energy. This principle allows us to use a parameterized quantum circuit to prepare a trial state and optimize its parameters to minimize the energy expectation value. 

In quantum mechanics, the physical quantities are represented by observable operators, which are Hermitian operators. The *Hamiltonian* operator $(H)$ is a key observable that describes the total energy of a quantum system. The ground state of the system corresponds to the lowest eigenvalue of the Hamiltonian, and the goal of VQAs is to find this ground state energy.

The **Variational Theorem** (or the Variational Principle) states that for any normalized trial quantum state with wavefunction \(|\psi(\theta)\rangle\), the expectation value of the Hamiltonian \(H\) provides an upper bound to the true ground state energy \(E_0\) of the system.
```{math}
:label: variational_theorem
    \langle \psi(\theta) | H | \psi(\theta) \rangle \geq E_0
```

In Eq [](#variational_theorem), the equality holds if and only if $|\psi(\theta)\rangle$ is the true ground state of the system. This means that by optimizing the parameters $\theta$ of the trial state, we can approach the true ground state energy.

This theorem is the foundation of variational algorithms. The variational approach consists of several modualr components, which can be combined  and optimized based on algorithm, problem and hardware. In these components we encode our problem, the state space and the optimization strategy to optimize and solve the problem. The main components of the variational approach are:

1. **Cost function**: The cost function is a measure of how well the trial state approximates the true ground state. It is typically defined as the expectation value of the Hamiltonian with respect to the trial state. The goal of the optimization process is to minimize this cost function. This cost function describes the specific problem we want to solve. For example, in quantum chemistry, the cost function could be the energy of a molecule, while in optimization problems, it could be a cost function that we want to minimize.
2. **Ansatz:**  The ansatz expresses the search space of the trial state with the parameters $\theta$. An ansatz is a combination of initial fixed state and collection of parameterized states. 
3. **Optimization strategy** The optimization strategy is the method used to update the parameters of the trial state in order to minimize the cost function. We iteratively explore the parameter space and adjust the parameters based on the feedback from the cost function until we converge to a solution. The optimization strategy is typically based on classical optimization algorithms like gradient descent or  simulated annealing.

