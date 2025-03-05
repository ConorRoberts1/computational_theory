# Computational Theory - Module Tasks 🧮💻

This repository contains my solutions to the tasks for the **Computational Theory** module. The tasks cover a range of topics, including binary representations, hash functions, prime numbers, Turing machines, and computational complexity. Each task is designed to deepen my understanding of computational theory and its practical applications.

---

## 📌 Table of Contents

1. [Overview](#-overview)
2. [How to Run the Project](#-how-to-run-the-project)
3. [Dependencies](#-dependencies)
4. [Tasks](#-tasks)
   - [Task 1: Binary Representations](#-task-1-binary-representations)
   - [Task 2: Hash Functions](#-task-2-hash-functions)
   - [Task 3: SHA256 Padding](#-task-3-sha256-padding)
   - [Task 4: Prime Numbers](#-task-4-prime-numbers)
   - [Task 5: Roots](#-task-5-roots)
   - [Task 6: Proof of Work](#-task-6-proof-of-work)
   - [Task 7: Turing Machines](#-task-7-turing-machines)
   - [Task 8: Computational Complexity](#-task-8-computational-complexity)
5. [Repository Structure](#-repository-structure)
6. [Contributing](#-contributing)
7. [License](#-license)

---

## 🌟 Overview

This project is part of the **Computational Theory** module, which explores fundamental concepts in computer science, such as binary operations, hashing, prime numbers, and computational models. Each task is implemented in Python and documented in a Jupyter Notebook (`Tasks.ipynb`).

---

## 🚀 How to Run the Project

Follow these steps to set up and run the project locally:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/ConorRoberts1/computational_theory

2. **Navigate to the repository**:
    cd computational_theory

3. **Open VSCode or Jupyter Notebook**
    code . || jupyter notebook tasks.ipynb


---

## 🛠️ Tasks

### 📍 Task 1: Binary Representations

This task involves implementing and testing four functions that manipulate binary representations of 32-bit unsigned integers. These functions are fundamental to understanding bitwise operations, which are widely used in cryptography, hashing algorithms, and low-level programming.

#### Functions Implemented

| Function       | Description                                                                 | Example Usage                          |
|----------------|-----------------------------------------------------------------------------|----------------------------------------|
| `rotl(x, n=1)` | Rotates the bits of `x` to the left by `n` places.                          | `rotl(0b1100, 2)` → `0b0011`          |
| `rotr(x, n=1)` | Rotates the bits of `x` to the right by `n` places.                         | `rotr(0b1100, 2)` → `0b0011`          |
| `ch(x, y, z)`  | Chooses bits from `y` where `x` is `1`, and bits from `z` where `x` is `0`. | `ch(0b1100, 0b1010, 0b0101)` → `0b1001` |
| `maj(x, y, z)` | Takes a majority vote of the bits in `x`, `y`, and `z`.                     | `maj(0b1100, 0b1010, 0b0101)` → `0b1100` |

#### Implementation Details
- The functions are implemented using Python's bitwise operators (`<<`, `>>`, `&`, `|`, `~`).
- Each function is tested with example inputs, and the results are displayed in both binary and unsigned integer formats.

---

### 📍 Task 2: Hash Functions
*To be completed.*

---

### 📍 Task 3: SHA256 Padding
*To be completed.*

---

### 📍 Task 4: Prime Numbers
*To be completed.*

---

### 📍 Task 5: Roots
*To be completed.*

---

### 📍 Task 6: Proof of Work
*To be completed.*

---

### 📍 Task 7: Turing Machines
*To be completed.*

---

### 📍 Task 8: Computational Complexity
*To be completed.*

---

