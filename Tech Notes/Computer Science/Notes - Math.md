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

Newton's method