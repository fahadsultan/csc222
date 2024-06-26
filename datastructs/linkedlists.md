---
layout: default
title: Linked Lists
nav_order: 4
has_toc: true
has_children: false
parent: Data Structures
---

# Linked List

1. TOC
{:toc}

Linked lists are a fundamental data structure in computer science. They are linear data structures that consist of nodes, where each node contains a data value and a reference to the next node in the sequence. Linked lists are a dynamic data structure, meaning that they can grow or shrink in size during the execution of a program.

## Types of Linked Lists

<img src="https://i.ibb.co/pwpcPdf/0-0-XVK02-Guco9x-JMJL.png" style="filter:invert(1);">

1. **Singly Linked List**: Each node contains a data value and a reference to the next node in the sequence.

2. **Doubly Linked List**: Each node contains a data value and references to both the next and previous nodes in the sequence.

3. **Circular Linked List**: A linked list in which the last node points back to the first node.

## Operations on Linked Lists

1. **Insertion**: Adding a new node to the linked list.

<center>

<img src="https://cdn.devdojo.com/images/june2021/LinkedList_frontInsertion.gif" style="filter:invert(1);" width="65%">

<img src="https://cdn.devdojo.com/images/june2021/linkedlist-insertfromback1.gif" style="filter:invert(1);" width="65%">

<img src="https://cdn.devdojo.com/images/june2021/LinkedList_IndexInsertion.gif" style="filter:invert(1);" width="65%">

</center>

2. **Deletion**: Removing a node from the linked list.

<center>
<img src="https://cdn.devdojo.com/images/june2021/Delfront.gif" style="filter:invert(1);" width="65%">
<img src="https://cdn.devdojo.com/images/june2021/delBack.gif" style="filter:invert(1);" width="65%">
<img src="https://cdn.devdojo.com/images/june2021/delIndex.gif" style="filter:invert(1);" width="65%">
</center>

3. **Traversal**: Visiting each node in the linked list.

4. **Search**: Finding a specific node in the linked list.

5. **Update**: Changing the data value of a node in the linked list.

## Advantages of Linked Lists

1. **Dynamic Size**: Linked lists can grow or shrink in size during the execution of a program.

2. **Efficient Insertion and Deletion**: Inserting or deleting a node in a linked list is efficient compared to arrays.

3. **No Memory Wastage**: Linked lists can use memory efficiently by allocating memory only when needed.

## Disadvantages of Linked Lists

1. **Random Access**: Linked lists do not support random access to elements, meaning that you cannot directly access the `i`-th element in a linked list.

2. **Extra Memory**: Linked lists require extra memory to store references to the next node.

3. **Traversal Overhead**: Traversing a linked list requires visiting each node in sequence, which can be slower than accessing elements in an array.

# Problems

* ### **Question 1.** [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/)

Easy
{: .label .label-green }

[Solution](linkedlists_solutions.html#question-1-reverse-linked-list)
{: .label .label-purple }

Given the head of a singly linked list, reverse the list, and return the reversed list.

<center>
<img src="https://assets.leetcode.com/uploads/2021/02/19/rev1ex1.jpg" style="filter:invert(1);" width="50%">
</center>

```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

def reverse_list(head: ListNode) -> ListNode:
	pass

assert reverse_list([1,2,3,4,5]) == [5,4,3,2,1], "Test case 1 failed"
assert reverse_list([1,2]) == [2,1], "Test case 2 failed"
assert reverse_list([]) == [], "Test case 3 failed"

print("Test cases passed :)")
```

* ### **Question 2.** [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)

Easy
{: .label .label-green }

[Solution](linkedlists_solutions.html#question-2-merge-two-sorted-lists)
{: .label .label-purple }

<center>
<img src="https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg" style="filter:invert(1);" width="50%">
</center>

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

def merge_two_lists(l1: ListNode, l2: ListNode) -> ListNode:
	pass

assert merge_two_lists([1,2,4], [1,3,4]) == [1,1,2,3,4,4], "Test case 1 failed"
assert merge_two_lists([], []) == [], "Test case 2 failed"
assert merge_two_lists([], [0]) == [0], "Test case 3 failed"

print("Test cases passed :)")
```

### **Question 3.** [Reorder List](https://leetcode.com/problems/reorder-list/description/)

Medium
{: .label .label-yellow }

[Solution](linkedlists_solutions.html#question-3-reorder-list)
{: .label .label-purple }

You are given the head of a singly linked-list. The list can be represented as:

`L0 → L1 → … → (Ln - 1) → Ln`

Reorder the list to be on the following form:

`L0 → Ln → L1 → (Ln - 1) → L2 → (Ln - 2) → …`


You may not modify the values in the list's nodes. Only nodes themselves may be changed.

<img src="https://assets.leetcode.com/uploads/2021/03/04/reorder1linked-list.jpg" style="filter:invert(1);" width="50%">

```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

def reorder_list(head: ListNode) -> None:
	pass

assert reorder_list([1,2,3,4]) == [1,4,2,3], "Test case 1 failed"
assert reorder_list([1,2,3,4,5]) == [1,5,2,4,3], "Test case 2 failed"
assert reorder_list([1,2]) == [1,2], "Test case 3 failed"

print("Test cases passed :)")
```

### **Question 4.** [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/)

Easy
{: .label .label-green }

[Solution](linkedlists_solutions.html#question-4-linked-list-cycle)
{: .label .label-purple }

Given `head`, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the `next` pointer. Internally, `pos` is used to denote the index of the node that tail's `next` pointer is connected to. **Note that `pos` is not passed as a parameter**.

Return `true` if there is a cycle in the linked list. Otherwise, return `false`.

<center>
<img src="https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist.png" style="filter:invert(1);" width="50%">
</center>

```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

def has_cycle(head: ListNode) -> bool:
	pass

node1 = ListNode(3)
node2 = ListNode(2)
node3 = ListNode(0)
node4 = ListNode(-4)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node2

assert has_cycle(node1) == True, "Test case 1 failed"

node1 = ListNode(1)
node2 = ListNode(2)

node1.next = node2
node2.next = node1

assert has_cycle(node1) == True, "Test case 2 failed"

node1 = ListNode(1)

assert has_cycle(node1) == False, "Test case 3 failed"
```


### **Question 5.** [Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/)

Medium
{: .label .label-yellow }

[Solution](linkedlists_solutions.html#question-5-remove-nth-node-from-end-of-list)
{: .label .label-purple }

Given the `head` of a linked list, remove the `nth` node from the end of the list and return its head.

<center>
<img src="https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg" style="filter:invert(1);" width="50%">
</center>

Follow up: Could you do this in one pass?

```python	
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next

def remove_nth_from_end(head: ListNode, n: int) -> ListNode:
	pass

node1 = ListNode(1)
node2 = ListNode(2)
node3 = ListNode(3)
node4 = ListNode(4)
node5 = ListNode(5)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

assert remove_nth_from_end(node1, 2) == [1,2,3,5], "Test case 1 failed"

node1 = ListNode(1)

assert remove_nth_from_end(node1, 1) == [], "Test case 2 failed"

node1 = ListNode(1)
node2 = ListNode(2)

node1.next = node2

assert remove_nth_from_end(node1, 1) == [1], "Test case 3 failed"
```

