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

This task implements multiple methods for primality testing and compares their efficiency through visualization. Prime numbers are fundamental to number theory and cryptography, with widespread applications in encryption algorithms.

#### Methods Implemented
1. **Trial Division**: Tests primality by dividing by all integers from 2 up to the square root of the candidate number. This approach is mathematically elegant and efficient for smaller numbers.
   
2. **Divisor Counting**: Determines primality by counting all divisors of a number. A prime number has exactly two divisors: 1 and itself. While conceptually simple, this method becomes increasingly inefficient as numbers grow.

#### Performance Analysis
- The task includes a performance comparison showing how the execution time of both methods scales with increasing input size.
- A visualization clearly demonstrates the O(n) complexity of divisor counting versus the more efficient O(√n) complexity of trial division.

---

### 📍 Task 5: Roots

This task implements the calculation of the first 32 bits of the fractional parts of the square roots of the first 100 prime numbers. This technique demonstrates how mathematical constants can be derived through deterministic methods to create values that appear random but are verifiable.

According to [Methods of Computing Square Roots](https://en.wikipedia.org/wiki/Methods_of_computing_square_roots), extracting binary digits of irrational square roots has been a classical computational problem dating back centuries, with methods ranging from Babylonian approximations to modern digital algorithms. Our implementation uses the digit-by-digit calculation method (also known as the shift-and-subtract algorithm) to extract the binary representation of these fractional parts.

#### Visualization Features
- A bar chart showing the frequency distribution of 1's at each bit position
- A heatmap displaying binary patterns across the first 50 prime square roots

---

### 📍 Task 6: Proof of Work

This task explores a simplified version of the "proof of work" concept used in cryptocurrencies like Bitcoin, by finding English words whose SHA-256 hashes begin with the most zero bits.

#### What is Proof of Work?
Proof of Work is a consensus mechanism that requires computational effort to solve a difficult problem, making it resource-intensive to manipulate a system. In cryptocurrencies, miners compete to find a hash value with a specific pattern (usually leading zeros).

#### Implementation Details
- The task processes a dictionary file of English words
- For each word, it:
  1. Calculates the SHA-256 hash
  2. Counts leading zero bits in the hash
  3. Identifies words with the highest number of leading zeros
- The results demonstrate the probabilistic nature of finding hash patterns, showing why mining becomes exponentially harder as difficulty increases

> **Note:** The `words.txt` file containing English words is required to run this task but is not included in the repository. You'll need to provide your own dictionary file with one word per line.

---

### 📍 Task 7: Turing Machines

This task implements a basic Turing machine that adds 1 to a binary number. Turing machines are fundamental theoretical models of computation that underpin our understanding of algorithms and computability.

#### Components Implemented
- **Tape**: An infinite storage medium divided into cells
- **Head**: Reads and writes symbols, moving left or right
- **State Transitions**: Rules that determine the machine's behavior

#### Binary Increment Machine
The implemented machine follows these steps:
1. Moves to the end of the input binary number
2. Performs addition with carry logic from right to left
3. Handles the carry bit appropriately, including prepending a 1 when necessary

The task includes test cases demonstrating the machine's ability to correctly increment various binary values, showcasing the fundamental concept that even simple state machines can perform meaningful computation.

---

### 📍 Task 8: Computational Complexity

This task looks at how bubble sort actually performs when sorting different arrangements of the same list. By counting comparisons for every possible arrangement (permutation) of a small list, we can see real patterns in algorithm efficiency.

#### What is Computational Complexity?

Computational complexity is basically how we measure how much work (time or memory) an algorithm needs based on its input size. While theory gives us big-O notation, actually counting operations shows us what happens in practice.

#### Bubble Sort Analysis

Bubble sort has these complexity characteristics:
- **Best-case**: O(n) when already sorted
- **Average-case**: O(n²)
- **Worst-case**: O(n²)

What my code does:
1. Generates all 120 possible arrangements of [1,2,3,4,5]
2. Runs bubble sort on each one, counting exactly how many comparisons happen
3. Shows which arrangements are easiest and hardest to sort
4. Calculates average comparison count across all permutations
5. Visualizes the distribution with matplotlib

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
6. **Methods of Computing Square Roots** – [Wikipedia](https://en.wikipedia.org/wiki/Methods_of_computing_square_roots): Historical context and implementation approaches for extracting binary digits of square roots.
7. **Proof of Work Concept** – [Investopedia](https://www.investopedia.com/terms/p/proof-work.asp): Explanation of the consensus mechanism used in blockchain technology.
8. **Turing Machines: A Modern Approach** – [Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/turing-machine/): Theoretical foundations of Turing machines and their significance in computability theory.
9. **Python's `itertools.permutations`** – [Python Documentation](https://docs.python.org/3/library/itertools.html#itertools.permutations): Used to generate all possible arrangements of a list for bubble sort analysis.
10. **Bubble Sort Algorithm** – [GeeksforGeeks](https://www.geeksforgeeks.org/bubble-sort/): Explanation of bubble sort algorithm and its performance characteristics.

