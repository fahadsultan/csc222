---
layout: default
title: Tree Solutions
nav_order: 5
has_children: true
parent: Trees
grand_parent: Data Structures
nav_exclude: true
---

# Trees


### **Question 1**. [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/description/)

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def invert_tree(root: TreeNode) -> TreeNode:
    if root == None: 
        return None
    left = invert_tree(root.left)
    right = invert_tree(root.right)
    root.left = right
    root.right = left
    return root
```

### **Question 2**. [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

```python
class Solution:
    def maxDepth(self, root):
        depth = 1 + self.maxDepthHelper(root)
        return depth 

    def maxDepthHelper(self, root, depth=0): 
        if root == None: 
            return depth-1
        left_depth = self.maxDepthHelper(root.left, depth+1)
        right_depth = self.maxDepthHelper(root.right, depth+1)

        return max(left_depth, right_depth)
```

### **Question 3**. [Same Tree](https://leetcode.com/problems/same-tree/description/)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        p_traverse = self.traverse(p)
        q_traverse = self.traverse(q)

        print(p_traverse)
        print(q_traverse)

        return p_traverse == q_traverse

    def traverse(self, root, traverse_str=""):
        if root == None: 
            return traverse_str+" null"
        
        root_result = traverse_str+" "+str(root.val)
        left_result = self.traverse(root.left, root_result)
        right_result = self.traverse(root.right, left_result)

        return right_result
```

### **Question 4**. [Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/description/)

```python
class Solution:
    def isSubtree(self, s: TreeNode, t: TreeNode) -> bool:
        if not t:
            return True
        if not s:
            return False

        if self.sameTree(s, t):
            return True
        return self.isSubtree(s.left, t) or self.isSubtree(s.right, t)

    def sameTree(self, s, t):
        if not s and not t:
            return True
        if s and t and s.val == t.val:
            return self.sameTree(s.left, t.left) and self.sameTree(s.right, t.right)
        return False
```

### **Question 5**. [Lowest Common Ancestor of a Binary Search Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/)

```python
class Solution:
    def lowestCommonAncestor(
        self, root: "TreeNode", p: "TreeNode", q: "TreeNode"
    ) -> "TreeNode":
        while True:
            if root.val < p.val and root.val < q.val:
                root = root.right
            elif root.val > p.val and root.val > q.val:
                root = root.left
            else:
                return root
```

### **Question 7**. [Count Good Nodes in Binary Tree](https://leetcode.com/problems/count-good-nodes-in-binary-tree/description/)


```python
class Solution:
    def goodNodes(self, root: TreeNode) -> int:
        def dfs(node, maxVal):
            if not node:
                return 0

            res = 1 if node.val >= maxVal else 0
            maxVal = max(maxVal, node.val)
            res += dfs(node.left, maxVal)
            res += dfs(node.right, maxVal)
            return res

        return dfs(root, root.val)
```


```python
class Solution:
    def isValidBST(self, root: TreeNode) -> bool:
        def valid(node, left, right):
            if not node:
                return True
            if not (left < node.val < right):
                return False

            return valid(node.left, left, node.val) and valid(
                node.right, node.val, right
            )

        return valid(root, float("-inf"), float("inf"))
```