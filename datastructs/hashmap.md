---
layout: default
title: Hashing & Sets
nav_order: 0
has_children: false
parent: Data Structures
---


# Hashing & Sets

Hashing is a technique used in data structures to store and retrieve data efficiently. It involves using a hash function to map data items to a fixed-size array which is called a hash table. Hash tables are used in a wide variety of applications, including databases, caching systems, and symbol tables. 

<center>

<iframe width="560" height="315" src="https://www.youtube.com/embed/9oKpRTBfNXo?si=s4hDmSyXX3mnnakP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

</center>

Hash sets are collections of distinct elements that are stored in a way that allows for quick access and retrieval. Sets are commonly used in computer science to store unique elements and perform set operations such as union, intersection, and difference.

Sets are collections of distinct elements that are stored in a way that allows for quick access and retrieval. Sets are commonly used in computer science to store unique elements and perform set operations such as union, intersection, and difference.



1. TOC
{:toc}


## Hash Table

<u><b>Hash Table</b></u> (also known as a hash map) is a fundamental data structure that efficiently stores and retrieves data in a way that allows for quick access. It involves mapping data to a specific index in a hash table using a <u><b>hash function</b></u> that enables fast retrieval of information based on its key. This method is commonly used in databases, caching systems, and various programming applications to optimize search and retrieval operations.

<img src="https://static.javatpoint.com/ds/images/types-of-hash-functions-in-c.png" style="filter:invert(100%);border-width:1px;">

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7d/Hash_table_3_1_1_0_1_0_0_SP.svg/1200px-Hash_table_3_1_1_0_1_0_0_SP.svg.png" style="filter:invert(100%);border-width:1px;">

### Hashing

Hashing is a technique used in data structures to store and retrieve data efficiently. It involves using a hash function to map data items to a fixed-size array which is called a hash table.

How it works:

1. Hash Function: You provide your data items into the hash function.
2. Hash Code: The hash function crunches the data and give a unique hash code.
3. Hash Table: The hash code then points you to a specific location within the hash table.

A hash table is also known as a hash map. It is a data structure that stores key-value pairs. It uses a hash function to map keys to a fixed-size array, called a hash table. This allows in faster search, insertion, and deletion operations.

### Hash Function

The hash function is a function that takes a key and returns an index into the hash table. The goal of a hash function is to distribute keys evenly across the hash table, minimizing collisions (when two keys map to the same index).

Common hash functions include:

* Division Method: Key % Hash Table Size
* Multiplication Method: (Key * Constant) % Hash Table Size
* Universal Hashing: A family of hash functions designed to minimize collisions

### Hash Collision

A hash collision occurs when two different keys map to the same index in a hash table. This can happen even with a good hash function, especially if the hash table is full or the keys are similar.

Causes of Hash Collisions:

* **Poor Hash Function**: A hash function that does not distribute keys evenly across the hash table can lead to more collisions.
* **High Load Factor**: A high load factor (ratio of keys to hash table size) increases the probability of collisions.
* **Similar Keys**: Keys that are similar in value or structure are more likely to collide.



### Collision Resolution Techniques
There are two types of collision resolution techniques:

1. Open Addressing:
	* Linear Probing: Search for an empty slot sequentially
	* Quadratic Probing: Search for an empty slot using a quadratic function

<center>
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5a/Hash_table_5_0_1_1_1_1_0_LL.svg" style="filter:invert(100%);border-width:1px;">
</center>

2. Closed Addressing:
	* Chaining: Store colliding keys in a linked list or binary search tree at each index
	* Cuckoo Hashing: Use multiple hash functions to distribute keys

<center>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Hash_table_5_0_1_1_1_1_1_LL.svg/1280px-Hash_table_5_0_1_1_1_1_1_LL.svg.png" style="filter:invert(100%);border-width:1px;" width="80%">
</center>

Hash tables are used in a wide variety of applications, including:

Databases: Storing and retrieving data based on unique keys
Caching: Storing frequently accessed data for faster retrieval
Symbol Tables: Mapping identifiers to their values in programming languages
Network Routing: Determining the best path for data packets

### Hash Table in Python

In Python, hash tables are implemented using the `dict` data structure, which is a built-in data type that stores key-value pairs. Hash tables in Python are optimized for fast search, insert, and delete operations.

```python
# Create a hash table
hash_table = {}

# Insert a key-value pair
hash_table["key1"] = "value1"

# Retrieve a value based on key
value = hash_table["key1"]

# Check if a key is in the hash table
if "key1" in hash_table:
	print("Key found in hash table")
```

### Hash Table Operations

Hash tables support a variety of operations, including:

* **Search**: Retrieve the value associated with a key.
* **Insert**: Add a new key-value pair to the hash table.
* **Delete**: Remove a key-value pair from the hash table.
* **Update**: Change the value associated with a key.
* **Size**: Get the number of key-value pairs in the hash table.

```python
# Create a hash table
hash_table = {}

# Insert key-value pairs
hash_table["key1"] = "value1"
hash_table["key2"] = "value2"
hash_table["key3"] = "value3"

# Search for a key
value = hash_table.get("key2")

# Delete a key
del hash_table["key3"]

# Update a value
hash_table["key1"] = "new_value"

# Get the size of the hash table
size = len(hash_table)
```

### Time and Space Complexity

The time complexity of hash table operations depends on the efficiency of the hash function and the collision resolution technique. In general, hash table operations have an average-case time complexity of O(1) for search, insert, and delete operations.

The space complexity of a hash table is O(n), where n is the number of key-value pairs stored in the table. The space complexity can vary based on the load factor and the collision resolution technique used.

## Sets

A set is a collection of distinct elements that are stored in a way that allows for quick access and retrieval. Sets are commonly used in computer science to store unique elements and perform set operations such as union, intersection, and difference.

Sets are implemented using hash tables in many programming languages, which allows for fast search and retrieval of elements. Sets are useful for removing duplicates from a list, checking for the presence of an element, and performing set operations.

### Sets in Python

In Python, sets are implemented using the `set` data structure, which is a built-in data type that stores unique elements. Sets are unordered collections of elements, and they do not allow duplicate values.

```python
# Create a set
s = set([1, 2, 3, 4, 5])

# Add an element to the set
s.add(6)

# Remove an element from the set
s.remove(3)

# Check if an element is in the set
if 4 in s:
	print("Element found in set")
```

### Set Operations

Sets support a variety of operations, including:

* **Union**: Combines two sets to create a new set containing all unique elements from both sets.

* **Intersection**: Finds the common elements between two sets and creates a new set with those elements.

* **Difference**: Finds the elements that are in one set but not the other and creates a new set with those elements.

* **Subset**: Checks if one set is a subset of another set.

* **Superset**: Checks if one set is a superset of another set.

```python

# Create two sets
s1 = set([1, 2, 3, 4, 5])
s2 = set([4, 5, 6, 7, 8])

# Union of two sets
union_set = s1.union(s2)

# Intersection of two sets
intersection_set = s1.intersection(s2)

# Difference of two sets
difference_set = s1.difference(s2)

# Check if s1 is a subset of s2
is_subset = s1.issubset(s2)

# Check if s1 is a superset of s2
is_superset = s1.issuperset(s2)

```


### Time and Space Complexity

The time complexity of set operations is similar to hash table operations, with an time complexity of O(1) for search, insert, and delete operations. The space complexity of a set is O(n), where n is the number of elements in the set.

Union and intersection operations have a time complexity of O(n) in the worst case, where n is the number of elements in the larger set. The space complexity of set operations depends on the size of the input sets and the implementation of the set data structure.

## Problems

Here are some common problems related to arrays and hashing:


<br/>

* ### [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)

	Given an integer array nums, return `true` if any value appears **at least twice** in the array, and return false if every element is distinct.

	Try to solve this problem without casting the array to a set.

	```python
	def containsDuplicate(nums):
		pass

	assert containsDuplicate([1,2,3,1]) == True, "Test case 1 failed"
	assert containsDuplicate([1,2,3,4]) == False, "Test case 2 failed"
	assert containsDuplicate([1,1,1,3,3,4,3,2,4,2]) == True, "Test case 3 failed"

	print("All test cases passed")
	```

<br/>

* ### [Valid Anagram](https://leetcode.com/problems/valid-anagram/)

	Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.

	An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

	* Example 1: _Input_: `s = "anagram", t = "nagaram"` _Output_: `true`
	
	* Example 2: _Input_: `s = "rat", t = "car"` _Output_: `false`

	<br/>

	```python
	def isAnagram(s, t):
		pass

	assert isAnagram("anagram", "nagaram") == True, "Test case 1 failed"
	assert isAnagram("rat", "car") == False, "Test case 2 failed"
	assert isAnagram("listen", "silent") == True, "Test case 3 failed"
	assert isAnagram("a", "a") == True, "Test case 4 failed"
	assert isAnagram("a", "ab") == False, "Test case 5 failed"

	print("All test cases passed")
	```

<br/>


* ### [Two Sum](https://leetcode.com/problems/two-sum/description/) 	

	Easy 
	{: .label .label-green }

	The **Two Sum Problem** is a classic algorithmic problem that asks the following question: given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

	```python
	def two_sum(nums, target):
		pass

	assert two_sum([2,7,11,15], 9) == [0, 1], "Test case 1 failed"
	assert two_sum([3,2,4], 6) == [1, 2], "Test case 2 failed"
	assert two_sum([3,3], 6) == [0, 1], "Test case 3 failed"
	assert two_sum([0, 2, 4, 5], 5) == [0, 3], "Test case 4 failed"

	print("All test cases passed")
	
	```

<br/>

* ### [Group Anagrams](https://leetcode.com/problems/group-anagrams/)
	Medium
	{: .label .label-yellow }	

	Given an array of strings `strs`, group the anagrams together. You can return the answer in any order.

	An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

	```python
	def groupAnagrams(strs):
		pass

	assert groupAnagrams(["eat","tea","tan","ate","nat","bat"]) == [['eat', 'tea', 'ate'], ['tan', 'nat'], ['bat']], "Test case 1 failed"
	assert groupAnagrams([""]) == [[""]], "Test case 2 failed"
	assert groupAnagrams(["a"]) == [["a"]], "Test case 3 failed"

	print("All test cases passed")
	```

* ### [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/description/)
	Medium
	{: .label .label-yellow }	

	Given an integer array `nums` and an integer `k`, return the `k` most frequent elements. You may return the answer in any order.

	```python
	def topKFrequent(nums, k):
		pass

	assert topKFrequent([1,1,1,2,2,3], 2) == [1,2], "Test case 1 failed"
	assert topKFrequent([1], 1) == [1], "Test case 2 failed"
	assert topKFrequent([1,2], 2) == [1,2], "Test case 3 failed"
	assert topKFrequent([1,2,2,3,3,3], 2) == [3,2], "Test case 4 failed"
	

	print("All test cases passed")
	``` 

* ### [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/description/)

	Medium
	{: .label .label-yellow }	

	Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

	You must write an algorithm that runs in O(n) time.

	```python
	def longestConsecutive(nums):
		pass

	assert longestConsecutive([100, 4, 200, 1, 3, 2]) == 4, "Test case 1 failed"
	assert longestConsecutive([0,3,7,2,5,8,4,6,0,1]) == 9, "Test case 2 failed"
	assert longestConsecutive([1,2,0,1]) == 3, "Test case 3 failed"
	assert longestConsecutive([5, 4, 3, 0, 7, 8, 9]) == 3, "Test case 4 failed"

	print("All test cases passed")
	```


<!--
	Find the Difference of Two Arrays
	Solution
	Easy

	Unique Number of Occurrences
	Solution
	Easy

	Determine if Two Strings Are Close
	Solution
	Medium

	Equal Row and Column Pairs
	Solution
	Medium
-->