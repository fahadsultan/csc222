---
layout: default
title: Trees
nav_order: 5
has_children: true
parent: Data Structures
---

# Trees

1. TOC
{:toc}

Trees are a fundamental data structure in computer science. They are hierarchical data structures that consist of nodes, where each node contains a data value and references to its children nodes. Trees are used to represent hierarchical relationships between data elements, such as file systems, organization charts, and abstract syntax trees.

<center>

<iframe width="80%" height="315" src="https://www.youtube.com/embed/7tCNu4CnjVc?si=EsLQTGdHb1UqWDS1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<iframe width="80%" height="315" src="https://www.youtube.com/embed/oSWTXtMglKE?si=afb2v8kJXgX9enJj" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<img src="https://miro.medium.com/v2/resize:fit:975/1*PWJiwTxRdQy8A_Y0hAv5Eg.png" style="filter:invert(1);" width="80%">
</center>

## Types of Trees

<center>
<!-- <img src="https://datastructuresamy.wordpress.com/wp-content/uploads/2018/03/trees.png" style="filter:invert(1);" width="80%"> -->

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20200219144238/General-Tree-vs-Binary-Tree.png" style="filter:invert(1);" width="80%">

</center>

1. **Binary Tree**: A tree in which each node has at most two children nodes.

<center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240418110011/Binary-Search-Tree.webp" style="filter:invert(1);" width="90%">
</center>

2. **Binary Search Tree (BST)**: A binary tree in which the left subtree of a node contains only nodes with values less than the node's value, and the right subtree contains only nodes with values greater than the node's value.

<center>
<img src="https://miro.medium.com/v2/resize:fit:16000/1*CMGFtehu01ZEBgzHG71sMg.png" style="filter:invert(1);" width="100%">
</center>

3. **Balanced Binary Tree**: A binary tree in which the heights of the two subtrees of every node differ by at most one.

4. **Complete Binary Tree**: A binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible.

5. **Full Binary Tree**: A binary tree in which every node has either zero or two children.

6. **Perfect Binary Tree**: A binary tree in which all interior nodes have two children and all leaves have the same depth or same level.

## Properties of Trees

Trees have the following properties:


* A tree with `n` nodes has `n-1` edges.

* A tree with height `h` has at most `2^h - 1` nodes.

* A binary tree with height `h` has at most `2^(h+1) - 1` nodes.

* The height of a binary tree with `n` nodes is `log(n+1) - 1`.

* The height of a binary search tree with `n` nodes is `log(n)`.

* The time complexity of operations on a binary search tree is `O(log(n))` on average and `O(n)` in the worst case.

## Operations on Trees


### **Search**: Finding a specific node in the tree.

#### Depth First Search (DFS)

A traversal algorithm that explores as far as possible along each branch before backtracking.

```python
def dfs(root, target):
	if root is None:
		return False
	if root.val == target:
		return True
	return dfs(root.left, target) or dfs(root.right, target)
```

<img src="https://www.freelancinggig.com/blog/wp-content/uploads/2019/02/BFS-and-DFS-Algorithms.png" style="filter:invert(1);" width="80%">

#### Breadth First Search (BFS)

A traversal algorithm that explores all the nodes at the present depth before moving on to the nodes at the next depth.


```python
def bfs(root, target):
	if root is None:
		return False
	queue = [root]
	while queue:
		node = queue.pop(0)
		if node.val == target:
			return True
		if node.left:
			queue.append(node.left)
		if node.right:
			queue.append(node.right)
	return False
```


### **Traversal**

Traversal is the process of <u>visiting each node in the tree in a specific order</u>.

<hr/>

#### Preorder Traversal (DFS: Root-Left-Right)

<br/>

Visit the root node first, then recursively do a preorder traversal of the left subtree, followed by a preorder traversal of the right subtree.

```python
def preorder_traversal(root):
	if root is None:
		return
	print(root.val) 		# Visit the root node
	preorder_traversal(root.left) 	# Visit the left subtree
	preorder_traversal(root.right) 	# Visit the right subtree
```

<center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240429124832/Inorder-Traversal-of-Binary-Tree.webp" style="filter:invert(1);" width="60%">
</center>

<hr/>

#### In-order Traversal (DFS: Left-Root-Right)
<br/>
Visit the left subtree first, then visit the root node, followed by a recursive inorder traversal of the right subtree.

```python
def inorder_traversal(root):
	if root is None:
		return
	inorder_traversal(root.left) 	# Visit the left subtree
	print(root.val) 		# Visit the root node
	inorder_traversal(root.right) 	# Visit the right subtree
```

<center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240429124538/Preorder-Traversal-of-Binary-Tree.webp" style="filter:invert(1);" width="60%">
</center>

<hr/>

#### Post-order Traversal (DFS: Left-Right-Root)
<br/>
Recursively do a postorder traversal of the left subtree, followed by a postorder traversal of the right subtree, and then visit the root node.

<center>
<img  src="https://media.geeksforgeeks.org/wp-content/uploads/20240429125100/Postorder-Traversal-of-Binary-Tree.webp" style="filter:invert(1);" width="60%">
</center>
<br/>

```python
def postorder_traversal(root):
	if root is None:
		return

	postorder_traversal(root.left) # Visit the left subtree
	postorder_traversal(root.right) # Visit the right subtree
	print(root.val) # Visit the root node
```

<hr/>

#### Level-order Traversal (BFS)

<br/>

Level-order traversal is a breadth-first search (BFS) algorithm that visits all the nodes at the present depth before moving on to the nodes at the next depth.

<br/>

```python
def level_order_traversal(root):
	if root is None:
		return
	queue = [root]
	while queue:
		node = queue.pop(0)
		print(node.val)
		if node.left:
			queue.append(node.left)
		if node.right:
			queue.append(node.right)
```

<center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240429134701/Level-Order-Traversal-of-Binary-Tree.webp" style="filter:invert(1);" width="80%">
</center>

<hr/>


## Binary Search Tree Operations

### **Insertion**

Adding a new node to the tree.

```python
class TreeNode:
	def __init__(self, val=0, left=None, right=None):
		self.val = val
		self.left = left
		self.right = right


def insert(root, val): 
	"""
	Inserts a new node with value `val` into the binary search tree.
	"""
	if root is None:
		return TreeNode(val)
	if val < root.val:
		root.left = insert(root.left, val)
	else:
		root.right = insert(root.right, val)
	return root
```
### **Deletion**

Removing a node from the tree.

```python
def delete(root, val):
	"""
	Deletes a node with value `val` from the binary search tree.
	"""
	if root is None:
		return root
	if val < root.val:
		root.left = delete(root.left, val)
	elif val > root.val:
		root.right = delete(root.right, val)
	else:
		if root.left is None:
			return root.right
		elif root.right is None:
			return root.left
		root.val = find_min(root.right)
		root.right = delete(root.right, root.val)
	return root
```

### **Update**

Changing the data value of a node in the tree.

```python
def update(root, target, new_val):
	"""
	Updates the value of the node with value `target` to `new_val`.
	"""
	if root is None:
		return
	if root.val == target:
		root.val = new_val
	update(root.left, target, new_val)
	update(root.right, target, new_val)
```



<!-- ## Depth First Search -->

<!-- Maximum Depth of Binary Tree
	Solution
	Easy

	Leaf-Similar Trees
	Solution
	Easy

	Count Good Nodes in Binary Tree
	Solution
	Medium

	Path Sum III
	Solution
	Medium

	Longest ZigZag Path in a Binary Tree
	Solution
	Medium

	Lowest Common Ancestor of a Binary Tree
	Solution
	Medium -->

<!-- ## Breadth First Search -->

<!--
	Binary Tree Right Side View
	Solution
	Medium

	Maximum Level Sum of a Binary Tree
	Solution
	Medium
-->

<!-- # Binary Search Tree -->

<!--
	Search in a Binary Search Tree
	Solution
	Easy

	Delete Node in a BST
	Solution
	Medium
-->
