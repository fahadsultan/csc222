---
layout: default
title: Matrices
nav_order: 2
has_toc: true
has_children: false
parent: Data Structures
---

# Matrices

1. TOC
{:toc}

Matrices are a fundamental data structure in computer science. They are two-dimensional arrays that consist of rows and columns. Matrices are used to represent data in a tabular format, such as images, graphs, and tables. Matrices are widely used in various fields, including mathematics, computer science, and engineering.

## Matrices in Python

In Python, matrices can be represented using nested lists. Each element in the matrix is accessed using the row and column indices. The following code snippet shows how to create and access elements in a matrix in Python:

```python

# Create a 3x3 matrix
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Access the element at row 1, column 2
element = matrix[1][2]

print(element)  # Output: 6

```

# Problems

## **Question 1**. [Rotate Image](https://leetcode.com/problems/rotate-image/description/)

Given an `n x n` 2D matrix representing an image, rotate the image by 90 degrees (clockwise).

You have to rotate the image **in-place**, which means you have to modify the input 2D matrix directly. **DO NOT** allocate another 2D matrix and do the rotation.

**Example 1:**

```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[7,4,1],[8,5,2],[9,6,3]]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/08/28/mat1.jpg" style="filter:invert(1);" width="40%">
</center>

**Example 2:**

```
Input: matrix = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]
Output: [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/08/28/mat2.jpg" style="filter:invert(1);" width="40%">
</center>

```python
def rotate(matrix):
    pass

assert rotate([[1,2,3],[4,5,6],[7,8,9]]) == [[7,4,1],[8,5,2],[9,6,3]], "Test case 1 failed"
assert rotate([[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]) == [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]], "Test case 2 failed"

print("Test cases passed :)")
```

## **Question 2**. [Spiral Matrix](https://leetcode.com/problems/spiral-matrix/description/)

Given an `m x n` matrix, return all elements of the matrix in spiral order.

**Example 1:**

```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,6,9,8,7,4,5]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/11/13/spiral1.jpg" style="filter:invert(1);" width="25%">
</center>

**Example 2:**

```
Input: matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
Output: [1,2,3,4,8,12,11,10,9,5,6,7]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/11/13/spiral.jpg" style="filter:invert(1);" width="30%">
</center>

```python
def spiral_order(matrix):
    pass

assert spiral_order([[1,2,3],[4,5,6],[7,8,9]]) == [1,2,3,6,9,8,7,4,5], "Test case 1 failed"
assert spiral_order([[1,2,3,4],[5,6,7,8],[9,10,11,12]]) == [1,2,3,4,8,12,11,10,9,5,6,7], "Test case 2 failed"

print("Test cases passed :)")
```

## **Question 3**. [Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/description/)

Given an `m x n` matrix, if an element is `0`, set its entire row and column to `0`. Do it **in-place**.

**Example 1:**

```
Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]
Output: [[1,0,1],[0,0,0],[1,0,1]]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/08/17/mat1.jpg" style="filter:invert(1);" width="50%">
</center>

**Example 2:**

```
Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
```

<center>
<img src="https://assets.leetcode.com/uploads/2020/08/17/mat2.jpg" style="filter:invert(1);" width="50%">
</center>

```python
def set_zeroes(matrix):
    pass

assert set_zeroes([[1,1,1],[1,0,1],[1,1,1]]) == [[1,0,1],[0,0,0],[1,0,1]], "Test case 1 failed"
assert set_zeroes([[0,1,2,0],[3,4,5,2],[1,3,1,5]]) == [[0,0,0,0],[0,4,5,0],[0,3,1,0]], "Test case 2 failed"

print("Test cases passed :)")
```