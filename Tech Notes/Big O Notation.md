# Big O Notation

Big O notation is used to compare the efficiency of different algorithms, which is done by calculating how much memory is needed, and how much time it takes to complete.

**The two main measurements are:**
- Time Complexity
- Space Complexity

**The three versions of these measurements:**
- Best Case (**Ω**)
- Average Case (**Θ**)
- Worst Case (**O**)

**Some common types for output given an input `n` are:**
- $O(1)$ - constant (same amount of time/space regardless of `n` size)
- $O(\log n)$ - logarithmic (time/space grows at slower diminishing rate)
- $O(n)$ - linear (time/space grows proportional to `n` size)
- $O(n \log n)$ - quasi-linear (becomes more linear over time) equal to $O(\log n!)$
- $O(n^2)$ - exponential (time/space grows exponentially to `n` size)
- $O(2^n)$ - exponential to `n` (even more exponential)
- $O(n!)$ - factorial (time/space grows crazy big to `n` size)
- $O(m+n)$ - additive linear (time/space grows proportional to `n` and `m`)
- $O(mn)$ - multiplied

![[big-o-chart.png]]

# Common Data Structure Operations

## Average

![[big-o-data-average.png]]

## Worst

![[big-o-data-worst.png]]


![[big-o-sort-algorithms.png]]

Source: https://www.bigocheatsheet.com/

# Less Common Data Structures

- Priority Queue
- Monotonic Stack
- Ordered Hash Map

### Algorithms
Binary Search
Kadane's Algorithm
KMP Algorithm
RK Algorithm
BM Algorithm
Sieve of Eratosthenes
Newton's method
Hoare's selection algorithm (quickselect)
Divide and Conquer
Dijkstra's algorithm

### Techniques
Sliding Window
Two Pointers
Three Pointers