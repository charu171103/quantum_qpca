# Quantum Principal Component Analysis (QPCA) Visualization

## Introduction

**Principal Component Analysis (PCA)** is a fundamental technique in classical data science and machine learning used for dimensionality reduction and feature extraction. PCA identifies directions (principal components) along which the variance of the data is maximized. This simplifies datasets while preserving their most important structures.

**Quantum Principal Component Analysis (QPCA)** is a quantum algorithm introduced by Lloyd, Mohseni, and Rebentrost (2014), designed to perform PCA on quantum-encoded data exponentially faster than classical algorithms under certain assumptions. QPCA leverages the principles of quantum computing — such as superposition, entanglement, and quantum phase estimation — to extract principal components from a density matrix representing data.

---

## Background: How QPCA Works

QPCA operates on a quantum density matrix \(\rho\) encoding the covariance matrix of classical data. The key idea is:

- Use **Quantum Phase Estimation (QPE)** on \(\rho\) to extract eigenvalues (principal components) and eigenvectors.
- Apply a **threshold operation** to filter out eigenvalues below a certain cutoff \(\tau\).
- Perform **controlled rotations** and **inverse QPE** to mark and isolate significant principal components.
- Finally, **measure** the ancilla qubits to collapse the system, revealing the desired principal components.

By doing so, QPCA can efficiently find dominant eigenvectors of large covariance matrices, which is useful for big data analysis, quantum machine learning, and quantum chemistry.

---

## About This Notebook 

This notebook contains two main parts that help illustrate PCA and QPCA concepts visually:

### 1. Quantum PCA Circuit Visualization

A detailed quantum circuit diagram is drawn showing the stages of the QPCA algorithm, including:

- **Initialization:** Preparation of quantum states representing input data.
- **Phase Estimation:** Using Phase Estimation qubits (PE) to extract eigenvalues.
- **Threshold Operation:** Applying a filter unitary \(U_{\lambda, \tau}\) to select eigenvalues above the threshold.
- **Controlled Rotation:** Rotations controlled by threshold qubits to mark significant components.
- **Inverse Phase Estimation:** Uncomputing the phase estimation to disentangle ancilla qubits.
- **Measurement:** Measuring the ancilla to retrieve classical results.

The visualization uses labeled qubit registers (`Ancilla`, `Threshold`, `PE[i]`, `State[i]`, `Output[i]`, `Classical`) and clear gate annotations (Hadamard, controlled-U, inverse QFT, etc.), making it easier to understand the quantum workflow of QPCA.

### 2. Classical PCA Concept Visualization

To ground the quantum concepts, a complementary visualization demonstrates classical PCA:

- Generates synthetic correlated multivariate data.
- Computes eigenvalues and eigenvectors of the covariance matrix.
- Projects data onto principal components.
- Plots histograms showing the distributions of original features versus PCA-transformed features.

This helps build intuition about PCA’s effect on data distribution and dimensionality reduction.

---

## How to Use

1. **Requirements:**

   - Python 3.6+
   - `numpy`
   - `matplotlib`

2. **Installation:**

   You can install dependencies via pip:

   ```bash
   pip install numpy matplotlib
