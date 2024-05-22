---
layout: default
title: Graphs
nav_order: 7
has_children: false
parent: Data Structures
---

# Graphs 

1. TOC
{:toc}

## Depth First Search

<!-- Keys and Rooms
	Solution
	Medium

	Number of Provinces
	Solution
	Medium

	Reorder Routes to Make All Paths Lead to the City Zero
	Solution
	Medium

	Evaluate Division
	Solution
	Medium -->

## Breadth First Search

<!--
	Nearest Exit from Entrance in Maze
	Solution
	Medium

	Rotting Oranges
	Solution
	Medium
-->

## Problems

### **Question 1**. [Number of Islands](https://leetcode.com/problems/number-of-islands/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given an `m x n` 2D binary grid `grid` which represents a map of `'1'`s (land) and `'0'`s (water), return the _number of islands_.

An **island** is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Example 1:**

```
Input: grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]

Output: 1
```

**Example 2:**

```
Input: grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]

Output: 3
```

```python

def num_islands(grid):
	pass

assert num_islands([
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]) == 1, "Test case 1 failed"

assert num_islands([
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]) == 3, "Test case 2 failed"

assert num_islands([
  ["1","1","1"],
  ["0","1","0"],
  ["1","1","1"]
]) == 1, "Test case 3 failed"
```

### **Question 2**. [Clone Graph](https://leetcode.com/problems/clone-graph/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

Given a reference of a node in a [connected](https://en.wikipedia.org/wiki/Connectivity_(graph_theory)#Connected_graph) undirected graph.

Return a [deep copy](https://en.wikipedia.org/wiki/Object_copying#Deep_copy) (clone) of the graph.

Each node in the graph contains a value (`int`) and a list (`List[Node]`) of its neighbors.

**Test Case Format:**

For simplicity, each node's value is the same as the node's index (1-indexed). For example, the first node with `val == 1`, the second node with `val == 2`, and so on. The graph is represented in the test case using an adjacency list.

An adjacency list is a collection of unordered lists used to represent a finite graph. Each list describes the set of neighbors of a node in the graph.

The given node will always be the first node with `val = 1`. You must return the copy of the given node as a reference to the cloned graph.

**Example 1:**

<img src="https://assets.leetcode.com/uploads/2019/11/04/133_clone_graph_question.png" style="filter:invert(1);" width="65%">

**Input**: `adjList = [[2,4],[1,3],[2,4],[1,3]]` \
**Output**: `[[2,4],[1,3],[2,4],[1,3]]` \
**Explanation**: There are 4 nodes in the graph.<br/>
1st node (val = 1)'s neighbors are 2nd node (val = 2) and 4th node (val = 4).

2nd node (val = 2)'s neighbors are 1st node (val = 1) and 3rd node (val = 3).

3rd node (val = 3)'s neighbors are 2nd node (val = 2) and 4th node (val = 4).

4th node (val = 4)'s neighbors are 1st node (val = 1) and 3rd node (val = 3).

```python
class Node:
	def __init__(self, val = 0, neighbors = None):
		self.val = val
		self.neighbors = neighbors if neighbors is not None else []

def clone_graph(node):
	pass

assert clone_graph([[2,4],[1,3],[2,4],[1,3]]) == [[2,4],[1,3],[2,4],[1,3]], "Test case 1 failed"
assert clone_graph([[2,3],[1,3],[1,2]]) == [[2,3],[1,3],[1,2]], "Test case 2 failed"
assert clone_graph([[2],[1]]) == [[2],[1]], "Test case 3 failed"

print("Test cases passed :)")
```

### **Question 3**. [Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

There is an `m x n` rectangular island that borders both the Pacific Ocean and Atlantic Ocean. The Pacific Ocean touches the island's left and top edges, and the Atlantic Ocean touches the island's right and bottom edges.

The island is partitioned into a grid of square cells. You are given an `m x n` integer matrix `heights` where `heights[r][c]` represents the height above sea level of the cell at `(r, c)`.

The island receives a lot of rain, and the rain water can flow to neighboring cells directly north, south, east, and west if the neighboring cell's height is less than or equal to the current cell's height. Water can flow from any cell adjacent to an ocean into the ocean.

Return a list of grid coordinates `result` where `result[i] = [ri, ci]` denotes that rain water can flow from cell `(ri, ci)` to both the Pacific and Atlantic oceans.

**Example 1:**

**Input**: `heights = [[1,2,2,3,5],[3,2,3,4,4],[2,4,5,3,1],[6,7,1,4,5],[5,1,1,2,4]]` \
**Output**: `[[0,4],[1,3],[1,4],[2,2],[3,0],[3,1],[4,0]]` \
**Explanation**: The following cells can flow to the Pacific and Atlantic oceans, as shown below: 
```
[0,4]: [0,4] -> Pacific Ocean 
       [0,4] -> Atlantic Ocean
[1,3]: [1,3] -> [0,3] -> Pacific Ocean 
       [1,3] -> [1,4] -> Atlantic Ocean
[1,4]: [1,4] -> [1,3] -> [0,3] -> Pacific Ocean 
       [1,4] -> Atlantic Ocean
[2,2]: [2,2] -> [1,2] -> [0,2] -> Pacific Ocean 
       [2,2] -> [2,3] -> [2,4] -> Atlantic Ocean
[3,0]: [3,0] -> Pacific Ocean 
       [3,0] -> [4,0] -> Atlantic Ocean
[3,1]: [3,1] -> [3,0] -> Pacific Ocean 
       [3,1] -> [4,1] -> Atlantic Ocean
[4,0]: [4,0] -> Pacific Ocean 
       [4,0] -> Atlantic Ocean
```
Note that there are other possible paths for these cells to flow to the Pacific and Atlantic oceans.

<img src="https://assets.leetcode.com/uploads/2021/06/08/waterflow-grid.jpg" style="filter:invert(1);" width="50%">

```python
def pacific_atlantic(heights):
	pass

assert pacific_atlantic([
  [1,2,2,3,5],
  [3,2,3,4,4],
  [2,4,5,3,1],
  [6,7,1,4,5],
  [5,1,1,2,4]
]) == [[0,4],[1,3],[1,4],[2,2],[3,0],[3,1],[4,0]], "Test case 1 failed"

assert pacific_atlantic([
  [1,2,3],
  [8,9,4],
  [7,6,5]
]) == [[0,2],[1,0],[1,1],[1,2],[2,0],[2,1],[2,2]], "Test case 2 failed"

assert pacific_atlantic([
  [2,1],
  [1,2]
]) == [[0,0],[0,1],[1,0],[1,1]], "Test case 3 failed"

print("Test cases passed :)")
```


### **Question 4**. [Course Schedule](https://leetcode.com/problems/course-schedule/description/)

Medium
{: .label .label-yellow }

Solution
{: .label .label-purple }

There are a total of `numCourses` courses you have to take, labeled from `0` to `numCourses - 1`. You are given an array `prerequisites` where `prerequisites[i] = [ai, bi]` indicates that you must take course `bi` first if you want to take course `ai`.

For example, the pair `[0, 1]`, indicates that to take course `0` you have to first take course `1`.

Return `true` if you can finish all courses. Otherwise, return `false`.

**Example 1:**

**Input**: `numCourses = 2, prerequisites = [[1,0]]`  **Output**: `true` \
**Explanation**: There are a total of 2 courses to take. To take course 1 you should have finished course 0. So it is possible.

**Example 2:**

**Input**: `numCourses = 2, prerequisites = [[1,0],[0,1]]`  **Output**: `false` \
**Explanation**: There are a total of 2 courses to take. To take course 1 you should have finished course 0, and to take course 0 you should also have finished course 1. So it is impossible.

```python
def can_finish(numCourses, prerequisites):
	pass

assert can_finish(2, [[1,0]]) == True, "Test case 1 failed"
assert can_finish(2, [[1,0],[0,1]]) == False, "Test case 2 failed"
assert can_finish(4, [[1,0],[2,0],[3,1],[3,2]]) == True, "Test case 3 failed"

print("Test cases passed :)")
```
