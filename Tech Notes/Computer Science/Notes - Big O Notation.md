# Big O Notation

Big O notation is the language we use for talking about how long an algorithm takes to run. It's how we compare the efficiency of different approaches to a problem.

**The two main measurements are:**
- Time Complexity
- Space Complexity

**The three versions of these measurements:**
- Best Case (**Ω**)
- Average Case (**Θ**) (Amortized?)
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

**Common Rules of Thumb**
* Sequential loops = addition
* Nested loops = multiplication

![[big-o-chart.png]]

# Common Data Structure Operations

## Average

![[big-o-data-average.png]]

## Worst

![[big-o-data-worst.png]]


![[big-o-sort-algorithms.png]]

#### References
https://www.bigocheatsheet.com/
https://www.interviewcake.com/article/java/big-o-notation-time-and-space-complexity