# Math

## Power of 2 Table

Power of 2 | Full | Exact Value (X)   | Aprx Value    | X Bytes into MB, GB, etc
---        | ---  | ---               | ---           | ---
7  | $2^7$ | 128               |               | 128 B
8  | $2^8$ | 256               |               | 256 B
10 | $2^{10}$ | 1,024             | 1 thousand    | 1 KB
16 | $2^{16}$ | 65,536            | (64 thousand) | 64 KB
20 | $2^{20}$ | 1,048,576         | 1 million     | 1 MB
30 | $2^{30}$ | 1,073,741,824     | 1 billion     | 1 GB
32 | $2^{32}$ | 4,294,967,296     | (4 billion)   | 4 GB
40 | $2^{40}$ | 1,099,511,627,776 | 1 trillion    | 1 TB


## Bit Manipulation

### Quick Tips
```
x ^ 0s = x    x & 0s = 0    x | 0s = x
x ^ 1s = ~x   x & 1s = x    x | 1s = 1
x ^ x  = 0    x & x  = 1    x | x  = x
```

### Two's Compliment
```
y = ~x + 1
```

## Finding Square Root (Newton's method)

One of the best and widely used methods to compute sqrt is Newton's Method. Here we'll implement the version without the seed trimming to keep things simple. However, seed trimming is a bit of math and lot of fun, so here is a link if you'd like to dive in.

Let's keep the mathematical proofs outside of the article and just use the textbook fact that the set

$$
x_{k+1} = \frac{1}{2} \left[ x_{k} + \frac{x}{x_{k}} \right]
$$
converges to $\sqrt{x}$ if $x_{0} = x$. Then things are straightforward: define that error should be less than 1 and proceed iteratively.

```
class Solution {
  public int mySqrt(int x) {
    if (x < 2) return x;

    double x0 = x;
    double x1 = (x0 + x / x0) / 2.0;
    while (Math.abs(x0 - x1) >= 1) {
      x0 = x1;
      x1 = (x0 + x / x0) / 2.0;
    }

    return (int)x1;
  }
}
```

#### Complexity Analysis

Time complexity : $O(\log n)$ since the set converges quadratically.
Space complexity : $O(1)$

https://leetcode.com/problems/sqrtx/solutions/1867232/illustration-of-the-newtons-method-for-beginner-easy-detailed-explanation/

## Finding Prime Numbers (Sieve of Eratosthenes)

The sieve of Eratosthenes is an ancient algorithm for finding all prime numbers up to any given limit.

```
algorithm Sieve of Eratosthenes is
	input: an integer n > 1.
    output: all prime numbers from 2 through n.

    let A be an array of Boolean values, indexed by integers 2 to n,
    initially all set to true.
    
    for i = 2, 3, 4, ..., not exceeding √n do
        if A[i] is true
            for j = i2, i2+i, i2+2i, i2+3i, ..., not exceeding n do
                set A[j] := false

    return all i such that A[i] is true.
```

#### Complexity Analysis

Time Complexity: $O(\sqrt{n} \log \log n)$
Space complexity : $O(1)$

https://leetcode.com/problems/count-primes/solutions/1157321/count-primes/
https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes
