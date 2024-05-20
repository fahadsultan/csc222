---
parent: Dynamic Programming
title: 1-Dimensional Problems
layout: default
nav_order: 10
has_children: true
grand_parent: Algorithms
nav_exclude: false
---

# DP-1 Problems

1. TOC
{:toc}

### **Question 1**. [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/description/)

Easy
{: .label .label-green }

Solution
{: .label .label-purple }

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

**Example 1:** **Input**: `n = 2` **Output**: `2` \
**Explanation**: There are two ways to climb to the top. i. 1 step + 1 step ii. 2 steps

```python
def climb_stairs(n: int) -> int:
	pass

assert climb_stairs(2) == 2, "Test case 1 failed"
assert climb_stairs(3) == 3, "Test case 2 failed"
assert climb_stairs(4) == 5, "Test case 3 failed"
```

### **Question 2**. [House Robber](https://leetcode.com/problems/house-robber/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and **it will automatically contact the police if two adjacent houses were broken into on the same night**.

Given an integer array `nums` representing the amount of money of each house, return _the maximum amount of money you can rob tonight **without alerting the police**_.

**Example 1:** **Input**: `nums = [2,3,2]` **Output**: `3` \
**Explanation**: You cannot rob house 1 (money = 2) and then rob house 3 (money = 2), because they are adjacent houses.

**Example 2:** **Input**: `nums = [1,2,3,1]` **Output**: `4` \
**Explanation**: Rob house 1 (money = 1) and then rob house 3 (money = 3). \
Total amount you can rob = 1 + 3 = 4.

```python
def rob(nums) -> int:
	pass

assert rob([2,3,2]) == 3, "Test case 1 failed"
assert rob([1,2,3,1]) == 4, "Test case 2 failed"
assert rob([0]) == 0, "Test case 3 failed"
```

### **Question 3**. [House Robber II](https://leetcode.com/problems/house-robber-ii/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and **it will automatically contact the police if two adjacent houses were broken into on the same night**.

Given an integer array `nums` representing the amount of money of each house, return _the maximum amount of money you can rob tonight **without alerting the police**_.

**Example 1:** **Input**: `nums = [2,3,2]` **Output**: `3` \
**Explanation**: You cannot rob house 1 (money = 2) and then rob house 3 (money = 2), because they are adjacent houses.

**Example 2:** **Input**: `nums = [1,2,3,1]` **Output**: `4` \
**Explanation**: Rob house 1 (money = 1) and then rob house 3 (money = 3). \

```python
def rob(nums) -> int:
	pass

assert rob([2,3,2]) == 3, "Test case 1 failed"
assert rob([1,2,3,1]) == 4, "Test case 2 failed"
assert rob([0]) == 0, "Test case 3 failed"
```

### **Question 4**. [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given a string `s`, return the longest palindromic substring in `s`.

A string is palindromic if it reads the same forward and backward.

**Example 1:** **Input**: `s = "babad"` **Output**: `"bab"` \
**Explanation**: `"aba"` is also a valid answer.

**Example 2:** **Input**: `s = "cbbd"` **Output**: `"bb"`

```python
def longest_palindrome(s: str) -> str:
	pass

assert longest_palindrome("babad") == "bab", "Test case 1 failed"
assert longest_palindrome("cbbd") == "bb", "Test case 2 failed"
```

### **Question 5**. [Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given a string `s`, return _the number of **palindromic substrings** in `s`_.

A string is a palindrome when it reads the same backward as forward.

A **substring** is a contiguous sequence of characters within the string.

**Example 1:** **Input**: `s = "abc"` **Output**: `3` \
**Explanation**: The 3 palindromic strings are `"a"`, `"b"`, and `"c"`.

**Example 2:** **Input**: `s = "aaa"` **Output**: `6` \
**Explanation**: The 6 palindromic strings are `"a"`, `"a"`, `"a"`, `"aa"`, `"aa"`, and `"aaa"`.

```python
def count_substrings(s: str) -> int:
	pass

assert count_substrings("abc") == 3, "Test case 1 failed"
assert count_substrings("aaa") == 6, "Test case 2 failed"
```

### **Question 6**. [Decode Ways](https://leetcode.com/problems/decode-ways/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

A message containing letters from `A-Z` can be **encoded** into numbers using the following mapping:

```
'A' -> "1"
'B' -> "2"
...
'Z' -> "26"
```

To **decode** an encoded message, all the digits must be grouped then mapped back into letters using the reverse of the mapping above (there may be multiple ways). For example, `"11106"` can be mapped into:

* `"AAJF"` with the grouping `(1 1 10 6)`

* `"KJF"` with the grouping `(11 10 6)`

Note that the grouping `(1 11 06)` is invalid because `"06"` cannot be mapped into `'F'` since `"6"` is different from `"06"`.

Given a string `s` containing only digits, return the number of ways to **decode** it.

The test cases are generated so that the answer will fit in a **32-bit** integer.

**Example 1:** **Input**: `s = "12"` **Output**: `2` \
**Explanation**: It could be decoded as `"AB"` (1 2) or `"L"` (12).

**Example 2:** **Input**: `s = "226"` **Output**: `3` \
**Explanation**: It could be decoded as `"BZ"` (2 26), `"VF"` (22 6), or `"BBF"` (2 2 6).

```python
def num_decodings(s: str) -> int:
	pass

assert num_decodings("12") == 2, "Test case 1 failed"
assert num_decodings("226") == 3, "Test case 2 failed"
```

### **Question 7**. [Coin Change](https://leetcode.com/problems/coin-change/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

You are given an integer array `coins` representing coins of different denominations and an integer `amount` representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return `-1`.

You may assume that you have an infinite number of each kind of coin.

**Example 1:** **Input**: `coins = [1,2,5]`, `amount = 11` **Output**: `3` \
**Explanation**: 11 = 5 + 5 + 1

**Example 2:** **Input**: `coins = [2]`, `amount = 3` **Output**: `-1` 

**Example 3:** **Input**: `coins = [1]`, `amount = 0` **Output**: `0`

```python
def coin_change(coins, amount) -> int:
	pass

assert coin_change([1,2,5], 11) == 3, "Test case 1 failed"
assert coin_change([2], 3) == -1, "Test case 2 failed"
assert coin_change([1], 0) == 0, "Test case 3 failed"
```

### **Question 8**. [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given an integer array `nums`, find the contiguous subarray within an array (containing at least one number) that has the largest product. Return the product.

The test cases are generated so that the answer will fit in a **32-bit** integer.

**Example 1:** **Input**: `nums = [2,3,-2,4]` **Output**: `6` \
**Explanation**: `[2,3]` has the largest product `6`.

**Example 2:** **Input**: `nums = [-2,0,-1]` **Output**: `0` \
**Explanation**: The result cannot be `2`, because `[-2,-1]` is not a subarray.

```python
def max_product(nums) -> int:
	pass

assert max_product([2,3,-2,4]) == 6, "Test case 1 failed"
assert max_product([-2,0,-1]) == 0, "Test case 2 failed"
```

### **Question 9**. [Word Break](https://leetcode.com/problems/word-break/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given a string `s` and a dictionary of strings `wordDict`, return `true` if `s` can be segmented into a space-separated sequence of one or more dictionary words.

**Note** that the same word in the dictionary may be reused multiple times in the segmentation.

**Example 1:** **Input**: `s = "leetcode"`, `wordDict = ["leet","code"]` **Output**: `true` \
**Explanation**: Return `true` because `"leetcode"` can be segmented as `"leet code"`.

**Example 2:** **Input**: `s = "applepenapple"`, `wordDict = ["apple","pen"]` **Output**: `true` \
**Explanation**: Return `true` because `"applepenapple"` can be segmented as `"apple pen apple"`. \
Note that you are allowed to reuse a dictionary word.

**Example 3:** **Input**: `s = "catsandog"`, `wordDict = ["cats","dog","sand","and","cat"]` **Output**: `false`

```python
def word_break(s: str, wordDict) -> bool:
	pass

assert word_break("leetcode", ["leet","code"]) == True, "Test case 1 failed"
assert word_break("applepenapple", ["apple","pen"]) == True, "Test case 2 failed"
```

### **Question 10**. [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given an integer array `nums`, return the length of the longest strictly increasing subsequence.

A **subsequence** is a sequence that can be derived from an array by deleting some or no elements without changing the order of the remaining elements. For example, `[3,6,2,7]` is a subsequence of the array `[0,3,1,6,2,2,7]`.

**Example 1:** **Input**: `nums = [10,9,2,5,3,7,101,18]` **Output**: `4` \
**Explanation**: The longest increasing subsequence is `[2,3,7,101]`, therefore the length is `4`.

**Example 2:** **Input**: `nums = [0,1,0,3,2,3]` **Output**: `4` \
**Explanation**: The longest increasing subsequence is `[0,1,2,3]`, therefore the length is `4`.

```python
def length_of_lis(nums) -> int:
	pass

assert length_of_lis([10,9,2,5,3,7,101,18]) == 4, "Test case 1 failed"
assert length_of_lis([0,1,0,3,2,3]) == 4, "Test case 2 failed"
```
