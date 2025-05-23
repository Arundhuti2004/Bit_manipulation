Here’s a comprehensive **theory explanation about Bit Manipulation**, suitable for notes, interviews, or a README file:

---

# 🧠 Bit Manipulation: Theory Guide

## 📌 What is Bit Manipulation?

**Bit Manipulation** refers to the process of performing operations directly on the binary representation of integers using bitwise operators. This is a powerful and low-level technique used in algorithms to optimize performance, reduce memory usage, and handle complex logic with simple expressions.

Each integer is stored as a sequence of bits (0s and 1s). Bit manipulation takes advantage of this representation to perform operations like shifting, masking, toggling, or checking the state of individual bits.

---

## 🧮 Why Use Bit Manipulation?

* **Efficiency**: Bitwise operations are extremely fast — much faster than arithmetic operations.
* **Memory Optimization**: Bitwise techniques can store multiple boolean states in a single integer.
* **Mathematical Tricks**: Many mathematical tricks (like checking powers of 2) can be elegantly done using bitwise logic.
* **Useful in**:

  * Competitive programming
  * Cryptography
  * Embedded systems
  * Graphics programming
  * Algorithm optimization

---

## ⚙️ Common Bitwise Operators

| Operator    | Symbol | Description             | Example (a = 5, b = 3)        |     |              |            |
| ----------- | ------ | ----------------------- | ----------------------------- | --- | ------------ | ---------- |
| AND         | `&`    | 1 if both bits are 1    | `5 & 3 = 1` (101 & 011 = 001) |     |              |            |
| OR          | \`     | \`                      | 1 if at least one bit is 1    | \`5 | 3 = 7\` (101 | 011 = 111) |
| XOR         | `^`    | 1 if bits are different | `5 ^ 3 = 6` (101 ^ 011 = 110) |     |              |            |
| NOT         | `~`    | Flip all bits           | `~5 = -6` (in 2’s complement) |     |              |            |
| Left Shift  | `<<`   | Multiply by 2 (n times) | `5 << 1 = 10` (101 → 1010)    |     |              |            |
| Right Shift | `>>`   | Divide by 2 (n times)   | `5 >> 1 = 2` (101 → 10)       |     |              |            |

---

## 🧰 Useful Bit Manipulation Techniques

### 1. Check if a number is even or odd:

```cpp
if (n & 1) // odd
else      // even
```

### 2. Multiply or divide by 2:

```cpp
n << 1  // n * 2
n >> 1  // n / 2
```

### 3. Check if the i-th bit is set:

```cpp
bool isSet = (n & (1 << i)) != 0;
```

### 4. Set the i-th bit:

```cpp
n = n | (1 << i);
```

### 5. Clear the i-th bit:

```cpp
n = n & ~(1 << i);
```

### 6. Toggle the i-th bit:

```cpp
n = n ^ (1 << i);
```

### 7. Count number of set bits (Brian Kernighan’s Algorithm):

```cpp
int count = 0;
while (n) {
    n = n & (n - 1);
    count++;
}
```

---

## 🎯 Bit Manipulation Applications

1. **Checking Power of 2**:

```cpp
bool isPowerOfTwo(int n) {
    return n > 0 && (n & (n - 1)) == 0;
}
```

2. **Finding a unique number where every other number appears twice**:

```cpp
int unique = 0;
for (int num : arr) {
    unique ^= num;
}
```

3. **Subset generation using bitmasking**:

```cpp
for (int mask = 0; mask < (1 << n); ++mask) {
    for (int i = 0; i < n; ++i) {
        if (mask & (1 << i)) {
            // i-th element is included in this subset
        }
    }
}
```

---

## 🛠️ Advantages

* Constant time performance
* Efficient state representation (bitmasks)
* Often simplifies complex problems

---

## ⚠️ Pitfalls

* Can be error-prone due to binary-level reasoning
* Not always readable without comments
* Signed vs unsigned issues (especially with right shifts)

---


