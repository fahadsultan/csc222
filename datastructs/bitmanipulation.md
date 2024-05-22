---
layout: default
title: Bit Manipulation
nav_order: 10
has_children: false
parent: Data Structures
---

# Bit Manipulation

1. TOC
{:toc}

Bit manipulation is the act of algorithmically manipulating bits or binary digits. It is a fast and efficient way to perform operations such as addition, subtraction, multiplication, and division on binary numbers. Bit manipulation is commonly used in computer science and programming to optimize algorithms and data structures.

## Bitwise Operators

Bitwise operators are used to perform operations on individual bits of binary numbers. The following are the bitwise operators available in most programming languages:

1. **AND (`&`)**: The AND operator performs a bitwise AND operation on two binary numbers. It returns 1 if both bits are 1; otherwise, it returns 0.

    ```python
    0 & 0 = 0
    0 & 1 = 0
    1 & 0 = 0
    1 & 1 = 1
    5 & 3 = 1 # 101 & 011 = 001
    ```

2. **OR (`|`)**: The OR operator performs a bitwise OR operation on two binary numbers. It returns 1 if at least one of the bits is 1; otherwise, it returns 0.

    ```python
    0 | 0 = 0
    0 | 1 = 1
    1 | 0 = 1
    1 | 1 = 1
    5 | 3 = 7 # 101 | 011 = 111
    ```

3. **XOR (`^`)**: The XOR operator performs a bitwise XOR (exclusive OR) operation on two binary numbers. It returns 1 if the bits are different; otherwise, it returns 0.

    ```python
    0 ^ 0 = 0
    0 ^ 1 = 1
    1 ^ 0 = 1
    1 ^ 1 = 0
    5 ^ 3 = 6 # 101 ^ 011 = 110
    ```

4. **NOT (`~`)**: The NOT operator performs a bitwise NOT operation on a binary number. It flips the bits, changing 1s to 0s and 0s to 1s.

    ```python
    ~0 = 1
    ~1 = 0
    ~5 = -6 # ~0101 = 1010
    ```

5. **Left Shift (`<<`)**: The left shift operator shifts the bits of a binary number to the left by a specified number of positions. It appends zeros to the right.

    ```python
    5 << 1 = 10 # 101 << 1 = 1010
    5 << 2 = 20 # 101 << 2 = 10100
    ```

6. **Right Shift (`>>`)**: The right shift operator shifts the bits of a binary number to the right by a specified number of positions. It appends zeros to the left.

    ```python
    5 >> 1 = 2 # 101 >> 1 = 10
    5 >> 2 = 1 # 101 >> 2 = 1
    ```

## Common Bit Manipulation Techniques

### 1. Check if a Number is Even or Odd

To check if a number is even or odd, you can use the bitwise AND operator. An even number has its least significant bit (LSB) set to 0, while an odd number has its LSB set to 1.

```python
def is_even(n):
    return n & 1 == 0

def is_odd(n):
    return n & 1 == 1
```

### 2. Swap Two Numbers

To swap two numbers without using a temporary variable, you can use the XOR operator. The XOR operator has the property that `a ^ b ^ b = a`, which allows you to swap two numbers without using additional memory.

```python
def swap(a, b):
    a = a ^ b
    b = a ^ b
    a = a ^ b
    return a, b
```

### 3. Set a Bit

To set a specific bit in a binary number, you can use the OR operator. To set the `i`-th bit of a number `n`, you can use the expression `n | (1 << i)`.

```python

def set_bit(n, i):
    return n | (1 << i)
```

### 4. Clear a Bit

To clear a specific bit in a binary number, you can use the AND operator. To clear the `i`-th bit of a number `n`, you can use the expression `n & ~(1 << i)`.

```python
def clear_bit(n, i):
    return n & ~(1 << i)
```

### 5. Toggle a Bit

To toggle a specific bit in a binary number, you can use the XOR operator. To toggle the `i`-th bit of a number `n`, you can use the expression `n ^ (1 << i)`.

```python
def toggle_bit(n, i):
    return n ^ (1 << i)
```

### 6. Check if a Bit is Set

To check if a specific bit in a binary number is set, you can use the AND operator. To check if the `i`-th bit of a number `n` is set, you can use the expression `(n & (1 << i)) != 0`.

```python

def is_bit_set(n, i):
    return (n & (1 << i)) != 0
```

### 7. Count the Number of Set Bits

To count the number of set bits (1s) in a binary number, you can use the following algorithm, known as the Brian Kernighan's Algorithm. The algorithm works by repeatedly flipping the least significant 1 bit to 0.

```python

def count_set_bits(n):
    count = 0
    while n:
        n = n & (n - 1)
        count += 1
    return count
```

### 8. Find the Missing Number

To find the missing number in an array of integers from 0 to `n`, you can use the XOR operator. The XOR operator has the property that `a ^ a = 0` and `a ^ 0 = a`. By XORing all the numbers in the array with the numbers from 0 to `n`, the missing number will be left.

```python
def find_missing_number(nums):
    n = len(nums)
    missing = n
    for i in range(n):
        missing ^= i ^ nums[i]
    return missing
```

### 9. Find the Single Number

To find the single number in an array of integers where every element appears twice except for one, you can use the XOR operator. The XOR operator has the property that `a ^ a = 0` and `a ^ 0 = a`. By XORing all the numbers in the array, the single number will be left.

```python

def find_single_number(nums):
    single = 0
    for num in nums:
        single ^= num
    return single
```

### 10. Find the Two Single Numbers

To find the two single numbers in an array of integers where every element appears twice except for two, you can use the XOR operator. The XOR operator has the property that `a ^ a = 0` and `a ^ 0 = a`. By XORing all the numbers in the array, you will be left with the XOR of the two single numbers. You can then find the rightmost set bit in the XOR result and partition the numbers based on that bit.

```python

def find_two_single_numbers(nums):
    xor = 0
    for num in nums:
        xor ^= num

    rightmost_set_bit = xor & -xor

    single1, single2 = 0, 0
    for num in nums:
        if num & rightmost_set_bit:
            single1 ^= num
        else:
            single2 ^= num

    return single1, single2
```

# Problems

* ### **Question 1.** [Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/description/)

Easy
{: .label .label-green }

Given an integer `n`, return the number of `1` bits in its binary representation.

**Example 1:**

```
Input: n = 00000000000000000000000000001011
Output: 3
```

**Example 2:**

```
Input: n = 00000000000000000000000010000000
Output: 1
```

```python
def hamming_weight(n):
    pass

assert hamming_weight(11) == 3, "Test case 1 failed"
assert hamming_weight(128) == 1, "Test case 2 failed"
assert hamming_weight(4294967293) == 31, "Test case 3 failed"
```

* ### **Question 2.** [Counting Bits](https://leetcode.com/problems/counting-bits/description/)

Easy
{: .label .label-green }

Given a non-negative integer `n`, for every number `i` in the range `0 ≤ i ≤ n`, calculate the number of `1` bits in its binary representation and return them as an array.

**Example 1:**

```
Input: n = 2
Output: [0,1,1]
```

**Example 2:**

```
Input: n = 5
Output: [0,1,1,2,1,2]
```

```python
def count_bits(n):
    pass

assert count_bits(2) == [0,1,1], "Test case 1 failed"
assert count_bits(5) == [0,1,1,2,1,2], "Test case 2 failed"
assert count_bits(0) == [0], "Test case 3 failed"
```

* ### **Question 3.** [Reverse Bits](https://leetcode.com/problems/reverse-bits/description/)

Easy
{: .label .label-green }

Reverse the bits of a given 32-bit unsigned integer.

**Example 1:**

```
Input: x = 123
Output: 321
```

**Example 2:**

```
Input: x = -123
Output: -321
```

**Example 3:**

```
Input: x = 120
Output: 21
```

```python
def reverse_bits(x):
    pass

assert reverse_bits(123) == 321, "Test case 1 failed"
assert reverse_bits(-123) == -321, "Test case 2 failed"
assert reverse_bits(120) == 21, "Test case 3 failed"
```

* ### **Question 4.** [Missing Number](https://leetcode.com/problems/missing-number/description/)

Easy
{: .label .label-green }

Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

**Example 1:**

```
Input: nums = [3,0,1]
Output: 2
```

**Example 2:**

```
Input: nums = [0,1]
Output: 2
```

**Example 3:**

```
Input: nums = [9,6,4,2,3,5,7,0,1]
Output: 8
```

```python
def missing_number(nums):
    pass

assert missing_number([3,0,1]) == 2, "Test case 1 failed"
assert missing_number([0,1]) == 2, "Test case 2 failed"
assert missing_number([9,6,4,2,3,5,7,0,1]) == 8, "Test case 3 failed"
```







