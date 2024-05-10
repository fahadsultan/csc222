---
layout: default
title: Arrays / Strings
nav_order: 1
has_children: false
parent: Data Structures 
---

# Array / String

<!-- 
	* Merge Strings Alternately, Solution, Easy

    * Greatest Common Divisor of Strings, Solution, Easy

    * Kids With the Greatest Number of Candies, Solution, Easy

    * Can Place Flowers, Solution, Easy

    * Reverse Vowels of a String, Solution, Easy

    * Reverse Words in a String
	Solution
	Medium

	Product of Array Except Self
	Solution
	Medium

	Increasing Triplet Subsequence
	Solution
	Medium

	String Compression
	Solution
	Medium 
	-->


## Longest Substring Without Repeating Characters

Given a string, find the length of the longest substring without repeating characters.

**Example 1:**

```
Input: "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

Solution:

```python
def lengthOfLongestSubstring(s: str) -> int:
	n = len(s)
	if n <= 1:
		return n

	i, j, max_len = 0, 0, 0
	while j < n:
		if s[j] in s[i:j]:
			i = i + 1
		else:
			j = j + 1
			max_len = max(max_len, j - i)
	return max_len
```

# Useful Techniques

A couple of _"techniques"_ that are neither _data structures_ nor _algorithms_ but are commonly used in solving all kinds of problems are "Two-Pointer" (TP) and "Sliding Window" (SW).

These are not _data structures_ because they don't store data, and they are not _algorithms_ because they don't solve a specific problem. They are more like _strategies_ that can be used to solve a wide variety of problems and are common enough to warrant its own LeetCode tags ([TP tag](https://leetcode.com/tag/two-pointers) and [SW tag](https://leetcode.com/tag/sliding-window/)) and articles ([TP article](https://leetcode.com/articles/two-pointer-technique/) and [SW article]()).



## Two Pointer Technique

The two pointer technique is a simple and effective algorithmic technique that is used to solve problems involving arrays or linked lists. It involves using two pointers that move through the data structure at different speeds or in different directions to solve the problem.

<br/>

<center>

<iframe width="560" height="315" src="https://www.youtube.com/embed/On03HWe2tZM?si=KVCDO0p-2C0bbAn9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

</center>

<br/>

### Types of Two Pointer Technique

<br/>

1. **Left and Right Pointers**: Two pointers move from opposite ends of the array towards the middle.

An example of this is the **Palindrome** problem, where you use two pointers to check if the string is a palindrome in O(1) space and O(n) time.

```python
def is_palindrome(s):
    i, j = 0, len(s) - 1
    while i < j:
        if s[i] != s[j]:
            return False
        i += 1
        j -= 1
    return True
```

2. **Start and End Pointers**: Two pointers move from the start and end of the array towards the middle, typically to find a subarray that sums to a target value.

3. **Fast and Slow Pointers**: One pointer moves faster than the other, typically to find a cycle in a linked list or to find the middle of a linked list.

### Example Problems

1. **Two Sum**: Given an array of integers, return indices of the two numbers such that they add up to a specific target.

    ```python
    def two_sum(nums, target):
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
    ```

2. 

3. **Median of Two Sorted Arrays**: Find the median of two sorted arrays.   

2. **Reverse Linked List**: Reverse a singly linked list.

## Sliding Window Technique

The sliding window technique is a common algorithmic technique used to solve problems involving arrays or strings. It involves maintaining a window of elements in the array or string and sliding the window across the data structure to find a solution.	

### Types of Sliding Window Technique

1. **Fixed Size Window**: The window size is fixed, and the window slides one element at a time.

2. **Variable Size Window**: The window size can vary, and the window slides one element at a time.

3. **Two Pointers**: Two pointers are used to maintain the window boundaries.

### Example Problems

1. **Maximum Subarray Sum**: Find the maximum sum of a subarray of size k.

2. **Longest Substring Without Repeating Characters**: Find the length of the longest substring without repeating characters.

