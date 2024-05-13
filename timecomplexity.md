---
layout: default
title: Time and Space Complexity
nav_order: 6
has_toc: true
has_children: false
math: mathjax
---

# Time and Space Complexity

1. TOC 
{:toc}

{: .notice }
Try **[Quiz 1](https://forms.gle/EJj8JnTe7WzX7X6R9)** and **[Quiz 2](https://forms.gle/KXqsksBdz6ckz2un7)** for practice


Asymptotic analysis is a method of describing limiting behavior. 

<center>
<img width="80%" style="filter:invert(100%)" src="https://www.openbookproject.net/books/pythonds/_images/newplot.png">
</center>

For example, the function `f(n) = 3n^2 + 5n + 7` is asymptotically equivalent to `g(n) = n^2`. This is because the term `5n + 7` becomes insignificant as `n` becomes infinitely large i.e. `n → ∞`. 

In other words, the term `n^2` _'dominates'_ the behavior of the function. 

This is often written symbolically as `f (n) ≈ n^2`, which is read as "`f(n)` is asymptotic to `n^2`".

Alternatively,  if `g(n) = n^2` and `f(n) = 3n^2 + 5n + 7`, we can write `f(n) \sim g(n)`.

Formally, given functions `f(x)` and `g(x)`, we define a binary relation

`f(x) \sim g(x)` as `x → ∞`, if and only if

lim `x → ∞` `f(x) / g(x) = 1`


We say that a faster-growing function dominates a slower-growing one. When `f` and `g` belong to different classes and `g` dominates `f`, it is sometimes written as `g ≫ f`.


`n! ≫ d^n ≫ n^3 ≫ n^2 ≫ nlogn ≫ n ≫ logn ≫ 1`

We say that `f(n)` and `g(n)` have the same asymptotic behavior, and write `f(n) = Θ(g(n))`.


# Time Complexity

Time Complexity of an algorithm is the amount of 'time' it takes to run in terms of the size of the input, that is independent of machine and programming language. 

In essence, it gives us a way to compare the efficiency and scalability of algorithms.

We can measure this by counting the number of operations that are performed under the assumptions of the RAM model of computation.

## Counting Operations

Consider the following function that takes in a list of numbers and returns the sum of the numbers.

```python
def sum_list(data):
    total = 0
    for num in data:
        total += num
    return total
```

We can count the number of operations that are performed in this function to get a sense of how long it will take to run. Under the assumptions of RAM model of computation, we assume that each operation that is not a function call or a loop takes 1 unit of time. Using this assumption, we can count the number of operations in the function above as follows:

```python
def sum_list(data):
    total = 0          # 1 operation: assigment 
    for num in data:   # n operation where n = len(data)
        total += num   # 2 operations: assignment + addition
    return total       # 1 operation: return
```

In this case, 2 operations that are performed for each element in the list, so the total number of operations is 2n + 2. 

As a general rule, the number of operations in a function is the number of operations in a block of code is: 

`Count(Code) =  Operations outside loop(s) + (Operations inside loop * Iterations of the loop)`

Please note that this is a rough estimate of the number of operations. The heuristic above assumes a single loop. 

In case of multiple loops, we can use the following heuristic for counting the number of operations, for a given pair of loops: 

`Total Operations for 2 loops = Count(Loop_1) * Count(Loop_2) if Loop_1 and Loop_2 are nested` 

`Total Operations for 2 loops = Count(Loop_1) + Count(Loop_2) if Loop_1 and Loop_2 are NOT nested`

Consider the block of code that follows and answer the Search questions below.

**Question:** Given **two inputs**: 1. list of n numbers `data` and 2. a number called `query`, return **output** last location of query in list, if it exists, otherwise return -1

**Solution:**
    
```python
def search(data, query):         # 1
   for i in range(len(data)):    # 2
      if data[i] == query:       # 3
         return i                # 4
   return -1                     # 5
```

## Best, Average and Worst Case

Using the RAM model of computation, we can count how many steps our algorithm takes on any given input instance by executing it. 

However, to understand **how good or bad** an algorithm is in general, we must know how it works **over ALL instances** (inputs).

To understand the notions of the best, worst, and average-case complexity, think about running an algorithm over all possible instances of data that can be fed to it. For the problem of searching, the set of possible input instances consists of all possible integers as `query` and all possible lists of $n$ elements as `data`.

We can represent each input instance as a point on a graph where the x-axis represents the size of the input problem (size/length of data), and the y-axis denotes the number of steps taken by the algorithm in this instance.

<center>
<img width="80%" style="filter:invert(100%)" src="https://miro.medium.com/v2/resize:fit:4800/format:webp/1*1WlWN-d_vqf-_o48bWMjNA.png">
</center>

These points naturally align themselves into columns, because only integers represent possible input size (e.g., it makes no sense to sort 10.57 items). We can define three interesting functions over the plot of these points:

* The **Worst-case complexity** of the algorithm is the function defined by the **maximum number of steps** taken in any instance of size _n_. This represents the curve passing through the highest point in each column. This is the blue curve in the figure above. 

    <br/>

    In case of the search algorithm, the worst case is when the `query` is either not in `data` or is the last element in `data`, and the algorithm has to go through all the elements in the list to determine that.

    The worst-case complexity proves to be **most useful** of these three measures **in practice**. The reasons for this is that the worst-case complexity is the highest stakes scenario, and therefore the most important to understand. A lack of understanding and subsequently preparedness for the worst-case scenario can often lead to high cost catastrophic consequences such as downtime, data loss, and even loss of life.

    <br/>

* The **Best-case complexity** of the algorithm is the function defined by the **minimum number of steps** taken in any instance of size _n_. This represents the curve passing through the lowest point of each column.

    <br/>

    In case of the search algorithm, the best case is when the `query` is the first element in `data`, and the algorithm only has to go through one element in the list to determine that. 

    In other words, in the best case, the amount of time it takes to run the algorithm is independent of the size of the input.

    The best case is rarely used in practice, because it is not a good indicator of how the algorithm will perform in general. In fact, probabilistically speaking, the best case is the least likely to happen.

    <br/>
* The **Average-case complexity** of the algorithm, which is the function defined by the **average number of steps** over all instances of size _n_.

    <br/>

    In case of the search algorithm, the average case is when the `query` is in the middle of `data`, and the algorithm has to go through half the elements in the list to determine that. This is assuming that the `query` is equally likely to be in any position in the list i.e. incoming queries are uniformly distributed.

The important thing to realize is that each of these time complexities define a numerical function, representing time versus problem size. These functions are as well defined as any other numerical function, be it $y = x^2 − 2x + 1$ or the price of Google stock as a function of time. But time complexities are such complicated functions that we must simplify them to work with them. For this, we need the “Big Oh” notation and the concept of asymptotic behavior.

## `O`, `Ω`, and `Θ` 
Assessing algorithmic performance makes use of the “big Oh” notation that, proves essential to compare algorithms and design more efficient ones. 

While the hopelessly _"practical"_ person may blanch at the notion of theoretical analysis, we present the material because it really is useful in thinking about algorithms.

This method of keeping score will be the most mathematically demanding part of this book. But once you understand the intuition behind these ideas, the formalism becomes a lot easier to deal with.

<center>
<img width="80%" style="filter:invert(100%)" src="https://fahadsultan.com/csc122/_images/bigoh2.png">
</center>

The best, worst, and average-case time complexities for any given algorithm are numerical functions over the size of possible problem instances. However, it is very difficult to work precisely with these functions, because they tend to:

* _Have too many bumps_ – The _exact_ time complexity function for any algorithm is liable to be very complicated with many little up and down bumps as shown in black curve in Figure 7.7. below. This is because the exact number of steps taken by an algorithm depends upon the exact input instance and the space of input instances is wide and varied. 

* _Require too much detail to specify precisely_ – Counting the exact number of RAM instructions executed in the worst case requires the algorithm be specified to the detail of a complete computer program. Further, the precise answer depends upon uninteresting coding details (e.g., did he use a case statement or nested ifs?). Performing a precise worst-case analysis like

$$T(n)=12754n^2 +4353n+834lg_2n+13546$$

would clearly be very difficult work, but provides us little extra information than the observation that “the time grows quadratically with n.”

It proves to be much easier to talk in terms of simple upper and lower bounds of time-complexity functions using asymptotics. Asymptotic analysis simplifies our analysis by ignoring levels of detail that do not impact our comparison of algorithms.

For example, asymptotic analysis ignores the difference between multiplicative constants. The functions $f(n) = 2n$ and $g(n) = n$ are identical in terms of asymptotics. This makes sense given our application. Suppose a given algorithm in (say) C language ran twice as fast as one with the same algorithm written in Java. This multiplicative factor of two tells us nothing about the algorithm itself, since both programs implement exactly the same algorithm. We ignore such constant factors when comparing two algorithms.

#### Formal Definitions

The formal definitions associated with the Big Oh notation are as follows:

* **Big Oh `O(.)`**  
    
    <br/>

    `f (n) = O(g(n))` means `c · g(n)` is an _upper bound_ on `f(n)`. 

    Thus there exists some constant c such that f (n) is always $\leq c · g(n)$, for large enough $n$ (i.e. , $n \geq n_0$ for some constant $n_0$).

    $O$ is the function that gives the **upper bound** on the running time of an algorithm. 

    For example, our current implementation of `search`, we can say that it is $\O(n)$, since the worst case is when the `query` is either not in `data` or is the last element in `data`, and the algorithm has to go through all the elements in the list to determine that, which is dependent on the size of the input.

<br/>

<center>
<img style="filter:invert(100%)" src="https://fahadsultan.com/csc122/_images/bigoh3.png">
</center>

* **Big Omega `Ω(.)`**  
    
    <br/>

    `f(n) = Ω(g(n))` means `c · g(n)` is a _lower bound_ on f(n). 

    Thus there exists some constant `c` such that `f(n)` is always $\geq c · g(n)$, for all $n \geq n_0$.

    $\Omega$ is the function that gives the **lower bound** on the running time of an algorithm.

    For example, our current implementation of `search`, we can say that it is $\Omega(1)$, since the best case is when the `query` is the first element in `data`, and the algorithm only has to go through one element in the list to determine that, which is independent of the size of the input.

    

<br/>

* **Big Theta Θ(.)** 
    
    <br/>

    `f(n) = Θ(g(n))` means `c_1 · g(n)` is an _upper bound_ on f(n) and `c_2 · g(n)` is a lower bound on `f(n)`, for all `n \geq n_0`. 

    Thus there exist constants $c_1$ and $c_2$ such that $f(n) ≤ c_1 · g(n)$ and $f(n) ≥ $c_2$ · g(n)$. This means that $g(n)$ provides a nice, tight bound on f(n).

    $\Theta$ is the function that gives the **tight bound** on the running time of an algorithm. 

    For example, our current implementation of `find_max`, where the best case is the same as the worst case, we can say that it is $\Omega(n)$.

<br/>

These definitions are illustrated in the figure above. Each of these definitions assumes a constant $n_0$ beyond which they are always satisfied. We are not concerned about small values of $n$ (i.e. , anything to the left of $n_0$). After all, we don’t really care whether one sorting algorithm sorts six items faster than another, but seek which algorithm proves faster when sorting 10,000 or 1,000,000 items. The Big Oh notation enables us to ignore details and focus on the big picture.

#### Informal Usage 

Informally, we can think of `O(.)` as the worst-case running time of an algorithm, `\Omega(\cdot)$ as the best-case running time of an algorithm, and $\Theta((\cdot))$ as the average-case running time of an algorithm.

That does not mean that we cannot refer to the worst case in terms of Big O. In fact, in practice, we often refer to the best, worst and average case all in terms of Big O.

For instance, we say linear search has worst case time complexity of $O(n)$, best case time complexity of $O(1)$, and average case time complexity of $O(n)$.

## Common Time Complexities


The good news is that only a few function classes tend to occur in the course of basic algorithm analysis. These suffice to cover almost all the algorithms we will discuss in this text, and are listed in order of increasing dominance:

<center>
<img style="filter:invert(100%)" src="https://fahadsultan.com/csc122/_images/bigoh4.png">
</center>


* **Constant functions**, `f(n) = 1`

    Such functions might measure the cost of adding two numbers, printing out "Hello, World!” or the growth realized by functions such as $f(n) = min(n, 100)$. In the big picture, there is <u>no dependence on the input $n$</u>.

* **Logarithmic** functions, `f (n) = log n`

    Logarithmic time-complexity shows up in algorithms such as binary search. Such functions grow quite slowly as n gets big, but faster than the constant function (which is standing still, after all). 

    <u>Logarithmic algorithms do not loop over all their input, but rather cut the problem size in half at each step.</u> More on logarithms below. 

* **Linear** functions, `f(n) = n`

    Such functions measure the cost of looking at each item once (or twice, or ten times) in an n-element array, say to identify the biggest item, the smallest item, or compute the average value. <u>If your code has a single loop over the input, it is probably linear. Even if your code has more than one loop, it may still be linear as long as no loop is nested inside another</u>.

* **Superlinear** functions, `f(n) = n log n`

    This important class of functions arises in such common in-place sorting algorithms. They grow just a little faster than linear, just enough to be a different dominance class. Time complexities of the form $n lg n$ often result from <u>algorithms that both a) have a loop and b) divide problems in half at each step</u>.

* **Quadratic** functions, `f(n) = n^2`

    Such functions measure the cost of looking at most or all pairs of items in an n-element universe. This arises in slow sorting algorithms. <u>If your code has two nested loops over the input, it is probably quadratic</u>.

* **Cubic** functions, `f(n) = n^3`

    Such functions enumerate through all triples of items in an $n$-element universe. 
    
    These also arise in certain dynamic programming algorithms developed. <u>If your code has three nested loops over the input, it is probably cubic</u>.

* **Polynomial** functions, `f(n) = n^k` for a given constant `k > 1`

    Note that linear, quadratic and cubic functions are all special cases of polynomial functions. Polynomial functions are relevant in Computational Theory and the long unsolved [P vs NP problem](https://en.wikipedia.org/wiki/P_versus_NP_problem) question.

    Polynomial functions arise in algorithms that make multiple passes over the input, such as matrix multiplication. <u>If your code has $k$ nested loops over the input, it is probably polynomial</u>.

* **Exponential** functions, `f(n) = c^n` for a given constant `c > 1`

    Functions like $2^n$ arise when enumerating all subsets of n items. Exponential algorithms are uselessly fast. 

    <u>If your code has $n$ nested loops over the input, it is probably exponential</u>.

* **Factorial** functions, $f(n) = n!$

    Functions like $n!$ arise when <u>generating all permutations or orderings of $n$ items</u>.

<hr/>

The table below lists the amount of time in seconds for each of the most common time complexities for a given input size $n$. 

<center>
<img style="filter:invert(100%)" src="https://fahadsultan.com/csc122/_images/skiena_bigo.png">
</center>

Note that if it takes **1 second** for an **O(n) algorithm** to process 1 billion elements (last row), it takes **31.7 years** for an **O($n^2$) algorithm** to process the same number of elements.

In other words, algorithms with a time complexity worse than $O(n logn)$ are not at all scalable for any modern day data set.


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