# stepik: https://stepik.org/a/249447

# Cholesky Decomposition Solver — Course & Implementation

[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![Website](https://img.shields.io/badge/website-live-blue.svg)](https://senatorovai.github.io/singular-value-decomposition-svd-solver-course/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18818738.svg)](https://doi.org/10.5281/zenodo.18820364)

> 🚀 Professional course project for understanding and implementing **Cholesky Decomposition** from scratch in Python.

---

## 🔥 Project Overview

This repository provides a complete implementation and mathematical explanation of **Cholesky Decomposition** for symmetric positive definite matrices.

It includes:

- Mathematical derivation
- Algorithm explanation
- Python implementation from scratch
- Numerical stability discussion
- Practical applications in linear systems

---

## Keywords

```

cholesky decomposition
cholesky factorization
cholesky solver python
matrix decomposition
numerical linear algebra
positive definite matrix
linear system solver
linalg cholesky from scratch
least squares optimization
python cholesky implementation

```

---

## 📚 Mathematical Definition

For a symmetric positive definite matrix:

$$
A \in \mathbb{R}^{n \times n}
$$

Cholesky decomposition states:

$$
A = LL^T
$$

Where:

- $$L$$ — lower triangular matrix
- $$L^T$$ — transpose of $$L$$

Condition:

$$
A = A^T
$$

and

$$
x^T A x > 0 \quad \forall x \neq 0
$$

---

## 🧠 Elementwise Formula

The elements of matrix $$L$$ are computed as:

For diagonal:

$$
L_{ii} = \sqrt{A_{ii} - \sum_{k=1}^{i-1} L_{ik}^2}
$$

For off-diagonal:

$$
L_{ij} = \frac{1}{L_{jj}} \left( A_{ij} - \sum_{k=1}^{j-1} L_{ik} L_{jk} \right)
$$

---

## ⚡ Applications

Cholesky decomposition is used in:

- Solving linear systems
- Gaussian processes
- Bayesian statistics
- Optimization
- Covariance matrix factorization
- Machine learning models

It is computationally cheaper than LU for SPD matrices.

---

## 🏗 Project Structure

```

cholesky-decomposition-solver/
│
├── README.md
├── LICENSE
├── requirements.txt
│
├── src/
│   ├── cholesky.py
│   ├── solver.py
│
├── examples/
│   └── demo.py
│
├── docs/
│   └── theory.md
│
├── images/
│   └── factorization.png
│
└── index.html

````

Clean structure improves:

✔ Professional appearance  
✔ Search visibility  
✔ Educational clarity  

---

## 🐍 Example Implementation

### Basic Cholesky Algorithm

```python
import numpy as np

def cholesky_decomposition(A):
    A = A.astype(float)
    n = A.shape[0]
    L = np.zeros_like(A)

    for i in range(n):
        for j in range(i + 1):
            s = sum(L[i, k] * L[j, k] for k in range(j))

            if i == j:
                L[i, j] = np.sqrt(A[i, i] - s)
            else:
                L[i, j] = (A[i, j] - s) / L[j, j]

    return L
````

---

## 🚀 Installation

```bash
pip install -r requirements.txt
```

Run example:

```bash
python examples/demo.py
```

