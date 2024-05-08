---
layout: default
title: General Topics
nav_order: 5
has_toc: true
has_children: false
---

# General Topics
{: .no_toc }

This section contains general topics that are not specific to any particular data structure or algorithm.

1. TOC 
{:toc}


## Communication

A significant aspect common to competitive programming and technical interviews is good communication. You need to be able to explain your thought process, your code, and your solutions to others. Here are some tips to help you communicate effectively:


### Explaining Your Thought Process

1. **Think out loud**: Explain your thought process as you work through a problem. This helps interviewers understand your approach and can lead to valuable feedback.

2. **Break down the problem**: Divide the problem into smaller subproblems and explain how you plan to solve each one.

3. **Use examples**: Provide examples to illustrate your points and make your explanations clearer.

4. **Ask questions**: If you're unsure about something, don't be afraid to ask questions. It's better to clarify things upfront than to make assumptions that could lead you down the wrong path.

5. **Be concise**: While it's important to explain your thought process, be mindful of the time and try to be concise in your explanations.

### Explaining Your Code

1. **Comment your code**: Use comments to explain your code and make it easier for others to understand.

2. **Use meaningful variable names**: Choose variable names that are descriptive and help convey the purpose of the variable.

3. **Follow a consistent style**: Stick to a consistent coding style to make your code more readable.

4. **Use whitespace**: Use whitespace to break up your code and make it easier to read.

5. **Practice explaining your code**: Practice explaining your code to others, either by talking through it out loud or writing explanations in comments.

### Explaining Your Solutions

1. **Summarize your solution**: Start by summarizing your solution in a few sentences to give the interviewer an overview of your approach.

2. **Explain the rationale**: Explain why you chose a particular approach and how it addresses the problem.

3. **Discuss trade-offs**: If there are trade-offs or limitations to your solution, be upfront about them and explain why you made the choices you did.

4. **Consider alternative approaches**: If time allows, discuss alternative approaches to the problem and compare them to your solution.

5. **Be open to feedback**: Be open to feedback and be willing to revise your solution based on the interviewer's input.


## Working under pressure

The other common aspect of competitive programming and technical interviews is working under pressure. You need to be able to think quickly and make decisions under tight time constraints. Here are some tips to help you work effectively under pressure:

### Practice, practice, practice

The more you practice solving problems under time constraints, the better you'll get at it. Set aside time each day to work on problems and challenge yourself to solve them quickly.

### Break down the problem

When faced with a complex problem, break it down into smaller subproblems that are easier to solve. Focus on solving one subproblem at a time and build up to the final solution.

### Manage your time

Keep an eye on the clock and allocate your time wisely. If you get stuck on a particular part of the problem, don't be afraid to move on and come back to it later.

### Stay calm

It's natural to feel nervous or stressed during a competition or interview, but try to stay calm and focused. Take deep breaths, remind yourself of your preparation, and trust in your abilities.

### Be adaptable

Be prepared to change your approach if you hit a roadblock or if your initial solution isn't working. Don't be afraid to try new strategies or techniques to solve the problem.

### Learn from your mistakes

After each competition or interview, take the time to reflect on what went well and what you could improve on. Use this feedback to inform your practice and make adjustments for next time.




## Big O Notation

Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. It is commonly used to describe the performance or complexity of an algorithm.

### Common Time Complexities

| Notation | Name | Example |
|----------|------|---------|
| O(1)     | Constant | Accessing an element in an array by index |
| O(log n) | Logarithmic | Binary search |
| O(n)     | Linear | Finding the maximum element in an array |
| O(n log n) | Linearithmic | Merge sort |
| O(n^2) | Quadratic | Bubble sort |
| O(n^3) | Cubic | Matrix multiplication |
| O(2^n) | Exponential | Recursive Fibonacci |
| O(n!) | Factorial | Permutations of a list |

### Common Space Complexities

| Notation | Name | Example |
|----------|------|---------|
| O(1)     | Constant | A fixed number of variables |
| O(log n) | Logarithmic | Recursive calls |
| O(n)     | Linear | An array of size n |
| O(n^2) | Quadratic | A 2D array of size n x n |
| O(2^n) | Exponential | Recursive calls |

### Rules of Thumb

- Ignore constants: O(2n) = O(n)
- Ignore lower order terms: O(n^2 + n) = O(n^2)
- Arithmetic operations are constant time: O(n + 1) = O(n)
- Nested loops multiply: O(n * m) = O(nm)
- Sequential statements add: O(n + m) = O(n + m)
- Different inputs are added: O(n + m)
- Drop non-dominant terms: O(n^2 + n) = O(n^2)

## Two Pointer Technique

The two pointer technique is a simple and effective algorithmic technique that is used to solve problems involving arrays or linked lists. It involves using two pointers that move through the data structure at different speeds or in different directions to solve the problem.

### Types of Two Pointer Technique

1. **Fast and Slow Pointers**: One pointer moves faster than the other, typically to find a cycle in a linked list or to find the middle of a linked list.

2. **Left and Right Pointers**: Two pointers move from opposite ends of the array towards the middle, typically to find a pair of elements that sum to a target value.

3. **Start and End Pointers**: Two pointers move from the start and end of the array towards the middle, typically to find a subarray that sums to a target value.

### Example Problems

1. **Two Sum**: Given an array of integers, return indices of the two numbers such that they add up to a specific target.

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

