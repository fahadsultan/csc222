---
layout: default
title: Arrays / Strings
nav_order: 1
has_children: false
parent: Data Structures 
---

# Array / String

1. TOC 
{:toc}

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


<!-- ## Longest Substring Without Repeating Characters

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
``` -->

<!-- # Useful Techniques -->

A couple of _"techniques"_ that are neither _data structures_ nor _algorithms_ but are commonly used in solving all kinds of problems are "Two-Pointer" (TP) and "Sliding Window" (SW).

These are not _data structures_ because they don't store data, and they are not _algorithms_ because they don't solve a specific problem. They are more like _strategies_ that can be used to solve a wide variety of problems and are common enough to warrant its own LeetCode tags ([TP tag](https://leetcode.com/tag/two-pointers) and [SW tag](https://leetcode.com/tag/sliding-window/)) and articles ([TP article](https://leetcode.com/articles/two-pointer-technique/) and [SW article]()).



# Two Pointer Technique

The two pointer technique is a simple and effective algorithmic technique that is used to solve problems involving arrays or linked lists. It involves using two pointers that move through the data structure at different speeds or in different directions to solve the problem.

<br/>

<center>

<iframe width="560" height="315" src="https://www.youtube.com/embed/On03HWe2tZM?si=KVCDO0p-2C0bbAn9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

</center>

## Problems

* ### **Question 1**. [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)

	Easy
	{: .label .label-green }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }
	
   A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

   Given a string `s`, return `true` if it is a _**palindrome**_, or `false` otherwise.

	```python
	def is_palindrome(s: str) -> bool:
		pass

	assert is_palindrome("A man, a plan, a canal: Panama") == True, "Test case 1 failed"
	assert is_palindrome("race a car") == False, "Test case 2 failed"
	assert is_palindrome("0P") == False, "Test case 3 failed"
	assert is_palindrome("ab_a") == True, "Test case 4 failed"
	assert is_palindrome(" ") == True, "Test case 5 failed"
	```


* ### **Question 2**. [Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)

	Medium
	{: .label .label-yellow }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }

Given a **1-indexed** array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be `numbers[index1]` and `numbers[index2]` where `1 <= index1 < index2 <= numbers.length`.

_Return the indices of the two numbers, `index1` and `index2`, **added by one** as an integer array `[index1, index2]` of length 2_.

The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.

<u>Your solution must use only constant extra space</u>.

```python
def two_sum(numbers: List[int], target: int) -> List[int]:
	pass

assert two_sum([2,7,11,15], 9) == [1,2], "Test case 1 failed"
assert two_sum([2,3,4], 6) == [1,3], "Test case 2 failed"
assert two_sum([-1,0], -1) == [1,2], "Test case 3 failed"
```


* ### **Question 3.** [3Sum](https://leetcode.com/problems/3sum/description/)

	Easy
	{: .label .label-green }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }
		
	Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

	Notice that the solution set must not contain duplicate triplets.

	```python
	def three_sum(nums: List[int]) -> List[List[int]]:
		pass

	assert three_sum([-1,0,1,2,-1,-4]) == [[-1,-1,2],[-1,0,1]], "Test case 1 failed"
	assert three_sum([]) == [], "Test case 2 failed"
	assert three_sum([0]) == [], "Test case 3 failed"
	assert three_sum([0,1,1]) == [], "Test case 4 failed"
	assert three_sum([0,0,0]) == [[0,0,0]], "Test case 5 failed"

	```

* ### **Question 4.** [Container With Most Water](https://leetcode.com/problems/container-with-most-water/description/)

	Medium
	{: .label .label-yellow }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }

You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `ith` line are `(i, 0)` and `(i, height[i])`.

Find two lines that together with the x-axis form a container, such that the container contains the most water.

<center>
<img src="https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black;" width="70%">
</center>

_Return the maximum amount of water a container can store_.

**Notice** that you may not slant the container.

```python
def max_area(height: List[int]) -> int:
	pass

assert max_area([1,8,6,2,5,4,8,3,7]) == 49, "Test case 1 failed"
assert max_area([1,1]) == 1, "Test case 2 failed"
assert max_area([4,3,2,1,4]) == 16, "Test case 3 failed"
assert max_area([1,2,1]) == 2, "Test case 4 failed"
```

# Sliding Window Technique

The sliding window technique is a common algorithmic technique used to solve problems involving arrays or strings. It involves maintaining a window of elements in the array or string and sliding the window across the data structure to find a solution.	

<!-- ### Types of Sliding Window Technique -->

1. **Fixed Size Window**: The window size is fixed, and the window slides one element at a time.

2. **Variable Size Window**: The window size can vary, and the window slides one element at a time.

3. **Two Pointers**: Two pointers are used to maintain the window boundaries.

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/p-ss2JNynmw?si=jiwg-QzgBO06rtzv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</center>

## Problems


* ### **Question 1.** [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/) 

	Easy  
	{: .label .label-green }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }

	You are given an array prices where prices[i] is the price of a given stock on the ith day.

	You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

	Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

	```python
	def max_profit(prices: List[int]) -> int:
		pass

	assert max_profit([7,1,5,3,6,4]) == 5, "Test case 1 failed"
	assert max_profit([7,6,4,3,1]) == 0, "Test case 2 failed"
	assert max_profit([1,2]) == 1, "Test case 3 failed"
	assert max_profit([2,4,1]) == 2, "Test case 4 failed"
	```

* ### **Question 2.** [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

	Medium
	{: .label .label-yellow }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }

	Given a string `s`, find the length of the longest substring without repeating characters.

	For example,
	
	Input: `"abcabcbb"` \
	Output: `3` \
	Explanation: The answer is `"abc"`, with the length of `3`. 


	```python
	def length_of_longest_substring(s: str) -> int:
		pass

	assert length_of_longest_substring("abcabcbb") == 3, "Test case 1 failed"
	assert length_of_longest_substring("bbbbb") == 1, "Test case 2 failed"
	assert length_of_longest_substring("pwwkew") == 3, "Test case 3 failed"
	assert length_of_longest_substring("") == 0, "Test case 4 failed"
	```

* ### **Question 3.** [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/description/)

	Medium
	{: .label .label-yellow }

	[Solution](arrays(solutions).html)
	{: .label .label-purple }

	You are given a string `s` and an integer `k`. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most `k` times.

	Return _the length of the longest substring containing the same letter you can get after performing the above operations_.

	```python
	def character_replacement(s: str, k: int) -> int:
		pass

	assert character_replacement("ABAB", 2) == 4, "Test case 1 failed"
	assert character_replacement("AABABBA", 1) == 4, "Test case 2 failed"
	assert character_replacement("A", 0) == 1, "Test case 3 failed"
	assert character_replacement("ABBB", 2) == 4, "Test case 4 failed"

	print("All test cases passed!")
	```


