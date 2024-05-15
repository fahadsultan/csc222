---
layout: default
title: Arrays & Hashing (Solutions)
has_children: false
nav_exclude: true
---


# Arrays and Hashing (Solutions)

1. TOC 
{:toc}

## Problems

Here are some common problems related to arrays and hashing:

* ### **Question 1**. [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)

Given an integer array nums, return `true` if any value appears **at least twice** in the array, and return false if every element is distinct.

<hr/>

#### Solution 1: Brute Force

```python
def containsDuplicate(nums):
	for i in range(len(nums)):
		for j in range(i + 1, len(nums)):
			if nums[i] == nums[j]:
				return True
	return False

assert containsDuplicate([1,2,3,1]) == True, "Test case 1 failed"
assert containsDuplicate([1,2,3,4]) == False, "Test case 2 failed"
assert containsDuplicate([1,1,1,3,3,4,3,2,4,2]) == True, "Test case 3 failed"

print("All test cases passed")
```

The time complexity of the above algorithm is `O(n^2)` since we have to iterate over the array twice to find the duplicate elements. Space complexity is `O(1)`.

<hr/>

#### Solution 2: Sorting

```python
def containsDuplicate(nums):
	sorted_nums = sorted(nums)

	for i in range(len(sorted_nums) - 1):
		if sorted_nums[i] == sorted_nums[i + 1]:
			return True

assert containsDuplicate([1,2,3,1]) == True, "Test case 1 failed"
assert containsDuplicate([1,2,3,4]) == False, "Test case 2 failed"
assert containsDuplicate([1,1,1,3,3,4,3,2,4,2]) == True, "Test case 3 failed"

print("All test cases passed")
```

<hr/>

#### Solution 3: Hash Set

```python
def containsDuplicate(nums):
	seen = set()

	for num in nums:
		if num in seen:
			return True
		seen.add(num)

	return False

assert containsDuplicate([1,2,3,1]) == True, "Test case 1 failed"
assert containsDuplicate([1,2,3,4]) == False, "Test case 2 failed"
assert containsDuplicate([1,1,1,3,3,4,3,2,4,2]) == True, "Test case 3 failed"

print("All test cases passed")
```



* ### **Question 2**. [Valid Anagram](https://leetcode.com/problems/valid-anagram/)

```python
def isAnagram(s, t):

  if len(s) != len(t):
    return False

  count_s, count_t = {}, {}

  for i in range(len(s)):

    count_s[s[i]] = 1 + count_s.get(s[i], 0)
    count_t[t[i]] = 1 + count_t.get(t[i], 0)

  return count_s == count_t

assert isAnagram("anagram", "angram") == False, "Test case 1 failed"
assert isAnagram("anagram", "") == False, "Test case 0 failed"
assert isAnagram("anagram", "nagaram") == True, "Test case 1 failed"
assert isAnagram("rat", "car") == False, "Test case 2 failed"
assert isAnagram("listen", "silent") == True, "Test case 3 failed"
assert isAnagram("a", "a") == True, "Test case 4 failed"
assert isAnagram("a", "ab") == False, "Test case 5 failed"

print("All test cases passed")
```

* ### **Question 3**. [Two Sum](https://leetcode.com/problems/two-sum/description/) 	

```python
def two_sum(nums, target):

  prev = {}

  for i in range(len(nums)):

    n = nums[i]

    diff = target - nums[i]

    if diff in prev:

      return [prev[diff], i]

    prev[n] = i


assert two_sum([2,7,11,15], 9) == [0, 1], "Test case 1 failed"
assert two_sum([3,2,4], 6) == [1, 2], "Test case 2 failed"
assert two_sum([3,3], 6) == [0, 1], "Test case 3 failed"
assert two_sum([0, 2, 4, 5], 5) == [0, 3], "Test case 4 failed"

print("All test cases passed")
```

* ### **Question 4**. [Group Anagrams](https://leetcode.com/problems/group-anagrams/)

```python
def groupAnagrams(strs):
  dict = {}
  for st in strs:
    sort_st = sorted(st)
    if sort_st in dict:
      dict[sort_st] = dict[sort_st].append(st)
    else:
      dict[sort_st] = [st]
  res = []
  for x in dict:
    res.append(dict[x])
  return res

assert groupAnagrams(["eat","tea","tan","ate","nat","bat"]) == [['eat', 'tea', 'ate'], ['tan', 'nat'], ['bat']], "Test case 1 failed"
assert groupAnagrams([""]) == [[""]], "Test case 2 failed"
assert groupAnagrams(["a"]) == [["a"]], "Test case 3 failed"

print("All test cases passed")
```


* ### **Question 5**. [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/description/)

```python
def topKFrequent(nums, k):
  counts = {}
  for n in nums:
    counts[n] = counts.get(n,0)+1

  freqs = [[] for i in range(n+1)]

  for key, val in counts.items():
    freqs[val].append(key)

  result = []
  for i in range(len(freqs)-1, 0, -1):
    inner_list = freqs[i]
    for x in inner_list:
      result.append(x)
      if len(result) == k:
        return result


assert topKFrequent([1,1,2,2,3], 2) == [1,2], "Test case 1 failed"
assert topKFrequent([1], 1) == [1], "Test case 2 failed"
assert topKFrequent([1,2], 2) == [1,2], "Test case 3 failed"
assert topKFrequent([1,2,2,3,3,3], 2) == [3, 2], "Test case 4 failed"

print("All test cases passed")
```


* ### **Question 6**. [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/description/)

```python
def longestConsecutive(nums):
  uniques = set(nums)
  longest = 0
  for x in nums:
    if x-1 in uniques:
      continue

    length = 1
    y = x+1
    while y in uniques:
      y = y + 1
      length += 1
    longest = max(length, longest)

  return longest

assert longestConsecutive([100, 4, 200, 1, 3, 2]) == 4, "Test case 1 failed"
assert longestConsecutive([0,3,7,2,5,8,4,6,0,1]) == 9, "Test case 2 failed"
assert longestConsecutive([1,2,0,1]) == 3, "Test case 3 failed"
assert longestConsecutive([5, 4, 3, 0, 7, 8, 9]) == 3, "Test case 4 failed"
assert longestConsecutive([7, 6, 5, 100, 200]) == 3, "Test case 5 failed"

print("All test cases passed")
```