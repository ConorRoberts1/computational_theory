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
6. [References / Research](#-references--research)

---

## 🌟 Overview

This project is part of the **Computational Theory** module, which explores fundamental concepts in computer science, such as binary operations, hashing, prime numbers, and computational models. Each task is implemented in Python and documented in a Jupyter Notebook (`Tasks.ipynb`).

---

## 🚀 How to Run the Project

Follow these steps to set up and run the project locally:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/ConorRoberts1/computational_theory
    ```

2. **Navigate to the repository**:
    ```bash
    cd computational_theory
    ```

3. **Open VSCode or Jupyter Notebook**:
    ```bash
    code . || jupyter notebook tasks.ipynb
    ```

---

## 📦 Dependencies

- Python 3.x
- Jupyter Notebook
- VSCode (optional)

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

This task involves implementing and analyzing a hash function from *The C Programming Language* by Kernighan and Ritchie. Hash functions are widely used in data structures, cryptography, and error detection.

#### Overview
The hash function computes a value for a string using:
1. A prime multiplier (`31`) to reduce collisions.
2. A prime modulus (`101`) to limit the output range (0–100).

#### Key Concepts
- **Efficient Data Retrieval**: Used in hash tables for fast lookups.
- **Data Integrity**: Checksums and cryptographic applications.
- **Collision Resistance**: Primes like 31 and 101 help distribute values evenly.

---

### 📍 Task 3: SHA256 Padding

This task implements a function that calculates and prints the **SHA-256 padding** for a file, following the official [FIPS 180-4 SHA specification](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf).

When performing a SHA-256 hash, padding is required to ensure that the message length (in bits) becomes a multiple of 512. This function simulates that padding and outputs it in hexadecimal format.

#### **What the Function Does**
1. **Reads the File**: Opens the file in binary mode and reads its content.
2. **Appends a `1` Bit**: Adds the byte `0x80` to represent a single `1` bit followed by seven `0` bits.
3. **Pads with Zeros**: Adds zero bytes (`0x00`) so that the message length is 64 bits (8 bytes) short of a multiple of 512 bits (i.e., `mod 64 == 56`).
4. **Appends Message Length**: Adds the original message length in **bits**, represented as a 64-bit **big-endian** unsigned integer.

The final padded message length is a multiple of 512 bits, which is the required input block size for the SHA-256 compression function. The output of the function is the padding portion only, printed in hexadecimal format.

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


## 🗂️ Repository Structure

```
computational_theory/
├── tasks.ipynb
├── README.md
└── 
```


---

## 📚 References / Research

1. **The C Programming Language (K&R)**: Original source of the hash function.
2. **Effective Java by Joshua Bloch**: Explains the use of 31 in hash functions.
3. **Prime Numbers in Hashing**: [GeeksforGeeks Article on Hashing](https://www.geeksforgeeks.org/hashing-set-1-introduction/).
4. **FIPS PUB 180-4** – [Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf)
5. **Python Official Docs**:
   - [`int.to_bytes`](https://docs.python.org/3/library/stdtypes.html#int.to_bytes)
   - [`bytes`](https://docs.python.org/3/library/functions.html#bytes)