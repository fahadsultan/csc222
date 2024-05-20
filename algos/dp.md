---
title: Dynamic Programming
layout: default
nav_order: 5
has_children: true
parent: Algorithms
---

# Dynamic Programming

1. TOC 
{:toc}

Dynamic programming is a method for solving complex problems by breaking them down into simpler subproblems. It is a powerful technique that can be used to solve a wide range of problems, from simple mathematical problems to complex optimization problems.

## Types of Dynamic Programming

1. **Top-Down Dynamic Programming**: In this approach, we start by solving the original problem and then break it down into smaller subproblems. We solve each subproblem recursively and store the results in a table to avoid redundant calculations.

2. **Bottom-Up Dynamic Programming**: In this approach, we start by solving the smallest subproblems and then build up to the original problem. We solve each subproblem iteratively and store the results in a table to avoid redundant calculations.

## Properties of Dynamic Programming

1. **Optimal Substructure**: The optimal solution to a problem can be constructed from the optimal solutions to its subproblems.

2. **Overlapping Subproblems**: The problem can be broken down into smaller subproblems that are reused multiple times.

## Applications of Dynamic Programming

1. **Fibonacci Sequence**: The Fibonacci sequence is a classic example of a problem that can be solved using dynamic programming.

2. **Shortest Path Problems**: Problems that involve finding the shortest path between two points in a graph can often be solved using dynamic programming.

3. **Knapsack Problem**: The knapsack problem is a classic optimization problem that can be solved using dynamic programming.

# Problems

## 1 Dimensional 


## Multidimensional

### **Question 1**. [Unique Paths](https://leetcode.com/problems/unique-paths/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

A robot is located at the top-left corner of a `m x n` grid. The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid.

How many possible unique paths are there?

**Example 1:**

```
Input: m = 3, n = 7
Output: 28
```

**Example 2:**

```
Input: m = 3, n = 2
Output: 3
```

```python
def unique_paths(m: int, n: int) -> int:
	pass

assert unique_paths(3, 7) == 28, "Test case 1 failed"
assert unique_paths(3, 2) == 3, "Test case 2 failed"
assert unique_paths(3, 3) == 6, "Test case 3 failed"
assert unique_paths(1, 1) == 1, "Test case 4 failed"
```

### **Question 2**. [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given two strings `text1` and `text2`, return the length of their longest common subsequence. If there is no **common subsequence**, return `0`.

A **subsequence** of a string is a new string generated from the original string with some characters(can be none) deleted without changing the relative order of the remaining characters. (eg, `"ace"` is a subsequence of `"abcde"` while `"aec"` is not). A **common subsequence** of two strings is a subsequence that is common to both strings.

```python
def longest_common_subsequence(text1: str, text2: str) -> int:
	pass

assert longest_common_subsequence("abcde", "ace") == 3, "Test case 1 failed"
assert longest_common_subsequence("abc", "def") == 0, "Test case 2 failed"
assert longest_common_subsequence("abc", "abc") == 3, "Test case 3 failed"
assert longest_common_subsequence("abc", "def") == 0, "Test case 4 failed"
```






<!-- 
### 1 dimensional
	N-th Tribonacci Number
	Solution
	Easy

	Min Cost Climbing Stairs
	Solution
	Easy

	House Robber
	Solution
	Medium

	Domino and Tromino Tiling
	Solution
	Medium

### Multidimensional

	Unique Paths
	Solution
	Medium

	Longest Common Subsequence
	Solution
	Medium

	Best Time to Buy and Sell Stock with Transaction Fee
	Solution
	Medium

	Edit Distance
	Solution
	Medium -->