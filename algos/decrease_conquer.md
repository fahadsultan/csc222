---
layout: default
title: Decrease & Conquer
nav_order: 1
has_children: false
parent: Algorithms
---

# Decrease & Conquer

1. TOC 
{:toc}

Decrease and conquer algorithms take the following approach: 

1. Decrease or reduce the problem instance to smaller instance of the same problem.
2. Conquer the problem by solving smaller instance of the problem.
3. Extend solution of smaller instance to obtain solution to original problem . 

Basic intuition of the decrease-and-conquer technique is based on exploiting the relationship between a solution to a given instance of a problem and a solution to its smaller instance. This approach is also known as incremental or inductive approach.


<center>
<img src="https://fahadsultan.com/csc122/_images/decrease_conquer.png" width="70%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">
</center>

Decrease and Conquer algorithms contrasts with the Divide and Conquer approach in the scope of the problem reduction. 

<center>
<img src="https://fahadsultan.com/csc122/_images/divide_decrease.png" width="70%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">
</center>


| Decrease and Conquer | Divide and Conquer |
|:----------------------:|:--------------------:|
| Problem is reduced to a smaller instances in a **chain** like manner, piecing off one element at a time | Problem is reduced to two or more smaller instances in a **tree** like manner |
| Decrease by a constant amout <br/> Think subtraction<br> `n = n - constant` at each step | Decrease by a constant factor  <br/> Think division<br> `n = n / constant` at each step |
| Example: Insertion, Selection Sort | Example: Binary Search, Merge Sort |



<img src="https://upload.wikimedia.org/wikipedia/commons/3/3e/Sorting_selection_sort_anim.gif" align="right" width="25%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">

# Selection Sort

**Selection sort** is a simple decrease and conquer sorting algorithm that works by maintaining two sublists in a given array:

1. The sublist which is already sorted.
2. Remaining sublist which is unsorted.

<img width="23%" align="right" src="https://upload.wikimedia.org/wikipedia/commons/b/b0/Selection_sort_animation.gif" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">

The algorithm iteratively _"selects"_ the smallest (for ascending order) element from the unsorted sublist and appends it to the end of the sorted sublist. This process continues until the unsorted sublist is empty. 

Note that the algorithm does not require any extra space and is thus an in-place sorting algorithm. The two sublists are maintained by a single variables tracking the first element of the unsorted sublist. Everything before this variable is sorted and everything after it is unsorted.

<center>

<img src="https://miro.medium.com/v2/resize:fit:1102/1*H2bCd6eoIONJIUnG5Jm9sQ.gif" width="50%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">

</center>


Selection sort _"conquers"_ the sorting problem by _"decreasing"_ the size of the unsorted sublist by one in each iteration.


## Algorithm

The selection sort algorithm, conceptually in broad steps, works as follows:

1. Initialize a iterator $i$ to $0$.
2. Identify the smallest element in the unsorted sublist (from $i$ to $n-1$).
3. Swap the smallest element with the element at index $i$.
4. Increment $i$ by $1$.
5. Repeat steps 2-4 until $i$ is equal to $n-1$.

<center><img width="70%" src="https://miro.medium.com/v2/resize:fit:1144/1*5WXRN62ddiM_Gcf4GDdCZg.gif" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">
</center>

<!-- 
```{figure} 
---
width: 75%
name: selection-sort
---
Selection Sort
``` 
-->

## Implementation

```python

def find_min(data):
    min_index = 0
    for i in range(1, len(data)):
        if data[i] < data[min_index]:
            min_index = i
    return min_index

def selection_sort(data):
    n = len(data)
    for i in range(n):
        find_min(data[i:])
        data[i], data[min_index] = data[min_index], data[i]
    return data
```


## Analysis

Time Complexity of selection sort is `O(n^2)` in all cases.

In the worst case, the list is sorted in reverse order. In this case, the algorithm will perform $n$ comparisons and $n$ swaps. Thus, the time complexity is `O(n^2)`.

In the best case, the list is already sorted. In this case, the algorithm still performs `n^2` comparisons but does $0$ swaps. Thus, the time complexity is `O(n^2)`.

In the average case, the list is not sorted. In this case, the algorithm will perform $n$ comparisons and $n/2$ swaps. Thus, the time complexity is $O(n^2)$.

Space Complexity of selection sort is $O(1)$. This is because the algorithm sorts the list in-place.

<img src="https://upload.wikimedia.org/wikipedia/commons/2/24/Sorting_insertion_sort_anim.gif" align="right" width="25%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">

# Insertion Sort

**Insertion sort** is a sorting algorithm that works the way we sort playing cards in our hands. 

The algorithm works by maintaining two sublists in a given array:

1. The sublist which is already sorted.
2. Remaining sublist which is unsorted.

<img width="23%" align="right" src="https://upload.wikimedia.org/wikipedia/commons/2/25/Insertion_sort_animation.gif" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">

The algorithm iteratively _"inserts"_ the next element from the unsorted sublist into the correct position in the sorted sublist. This process continues until the unsorted sublist is empty.

Similar to selection sort, the algorithm does not require any extra space the two sublists are maintained by a single variables tracking the first element of the unsorted sublist. Everything before this variable is sorted and everything after it is unsorted.


<center><img src="https://miro.medium.com/v2/resize:fit:1102/1*qc-KD7DII1K097jnvOWqsg.gif" width="60%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black"></center>



## Steps 

The algorithm works as follows:

1. Initialize a iterator `i` to `1`.

2. Call the element at `ith` location `key` i.e. `key = L[i]`.

3. Iterate over sublist to the left of $i$ from right to left i.e. iterate over the list from `i-1` to `0` using an iterator called `j`. The sublist from `i-1` to `0` is the sorted sublist.

4. For all values `L[j] > key`, shift them one place to the right i.e. set `L[j+1]` to `L[j]` until `L[j] > key`.

5. Once you find a value `L[j] <= key`, you've found the correct location of `key`. Set `L[j+1]` to `key`.

6. Increment `i` by `1` and repeat steps 2-5 until `i` is equal to `n-1`.

<center>
<img src="https://miro.medium.com/v2/resize:fit:1280/1*jdXtqXw0EQVpqdZZoGnwsQ.gif" width="90%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black">
</center>


## Implementation

```python
def insertion_sort(data):
    n = len(data)
    for i in range(1, n):
        key = data[i]
        j = i - 1
        while j >= 0 and key < data[j]:
            data[j + 1] = data[j]
            j -= 1
        data[j + 1] = key
    return data
```

## Analysis

The time complexity of insertion sort depends on the initial order of the elements in the input array. 

In the worst case, the array is sorted in reverse order. In this case, the algorithm will perform $n$ comparisons and `n(n-1)/2` swaps. Thus, the time complexity is `O(n^2)`.

In the average case, the array is randomly ordered. In this case, the algorithm will perform $n$ comparisons and `n(n-1)/4` swaps. Thus, the time complexity is `O(n^2)`.

In the best case, the array is already sorted. In this case, the algorithm will perform `n` comparisons and `0` swaps. Thus, the time complexity is `O(n)`. Note that the best case of insertion sort is better than the best case of selection sort.

The space complexity of insertion sort is `O(1)` in all cases as the algorithm does not require any extra space.

## Comparison with Selection Sort

Selection and Insertion sort are similar algorithms with some subtle but key differences. 

### Similarities

They are similar in that they are

* Both decrease and conquer sorting algorithms
* Both maintain two sublists in a given array: 
    * The sublist which is already sorted.
    * Remaining sublist which is unsorted.
* Both have a time complexity of `O(n^2)`
* Both are in-place sorting algorithms 
* The space complexity of both is `O(1)`

### Differences 

They two key difference in that:

1. In selection sort, most of the work done is in "selecting" (finding) the smallest element in the unsorted sublist. 
    
    In insertion sort, most of the work is done in "inserting" the next element from the unsorted sublist into the correct position in the sorted sublist.

<center><img src="https://fahadsultan.com/csc122/_images/select_vs_insert.png" width="90%" style="filter:invert(100%);border-width:1px;border-style:solid;border-color:black"></center>

2. Depending on the implementation and the data, insertion sort can, in the best case, be faster than selection sort. 

