### Basic Structures

Array

xxx | Read | Mutate | Search
--- | --- | --- | ---
Dynamic Array (Array List)| O(1) | O(n) | O(n)
Associative array (Map) | O(1) | O(1) | O(1)
Linked List | O(n) | O(n)
Queue | -- | O(1) | --

Hash Map

Linked List
Queue
Stack
Map | O(1)


Hash Map | O(1)


### Data Structures
xxx | xxx
--- | ---
Monotonic Stack | O(n)

Hash Table
Ordered Hash Map O(log n)

Priority Queue (Heap) | O(log n)

Tree
Graph

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


Structure   | Insert/Delete | Access Index | Search | Space Usage
---         | ---      | ---    | ---    | ---
Array       | O(n)     | O(1)   | O(n)   | O(n)
Stack	    | O(1)     | O(n)   | O(n)   | O(n)
Queue       | O(1)     | O(n)   | O(n)   | O(n)
Linked List | O(1)     | O(n)   | O(n)   | O(n)
Map         | O(1)     | O(1)   | O(1)   | O(n)
Hash Map    | O(1)     | O(1)   | O(1)   | O(n)
Heap        | O(log n) | --     | O(n)   | O(n)
Binary Search Tree | O(log n) | O(log n) | O(log n) | O(n)
Red-Black Tree | O(log n) | O(log n) | O(log n) | O(n)


Priority Queue
Monotonic Stack
Ordered Hash Map

https://www.bigocheatsheet.com/

### Common Data Structure Operations
Data Structure	Time Complexity	Space Complexity
Average	Worst	Worst
Data Structure | Access | Search | Insertion | Deletion
---       | ---    | ---    | ---       | ---
Array | Θ(1) | Θ(n)   | Θ(n)      | Θ(n)
Stack | Θ(n) | Θ(n)   | Θ(1)      | Θ(1)
Queue | Θ(n) | Θ(n) | Θ(1) | Θ(1)
Singly-Linked List | Θ(n) | Θ(n) | Θ(1) | Θ(1)
Doubly-Linked List | Θ(n) | Θ(n) | Θ(1) | Θ(1)
Skip List | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
Hash Table | N/A | Θ(1) | Θ(1) | Θ(1)
Binary Search Tree | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
Cartesian Tree | N/A | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
B-Tree | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
Red-Black Tree | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
Splay Tree | N/A | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
AVL Tree | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))
KD Tree | Θ(log(n)) | Θ(log(n)) | Θ(log(n)) | Θ(log(n))


Data Structure	Time Complexity	Space Complexity
Average	Worst	Worst
Access | Search | Insertion | Deletion | Access | Search | Insertion | Deletion
---    | ---    | ---       | ---      | ---    | ---    | ---       | ---
Array	| Θ(1)	| Θ(n)	Θ(n)	Θ(n)	O(1)	O(n)	O(n)	O(n)	O(n)
Stack	Θ(n)	Θ(n)	Θ(1)	Θ(1)	O(n)	O(n)	O(1)	O(1)	O(n)
Queue	Θ(n)	Θ(n)	Θ(1)	Θ(1)	O(n)	O(n)	O(1)	O(1)	O(n)
Singly-Linked List	Θ(n)	Θ(n)	Θ(1)	Θ(1)	O(n)	O(n)	O(1)	O(1)	O(n)
Doubly-Linked List	Θ(n)	Θ(n)	Θ(1)	Θ(1)	O(n)	O(n)	O(1)	O(1)	O(n)
Skip List	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(n)	O(n)	O(n)	O(n)	O(n log(n))
Hash Table	N/A	Θ(1)	Θ(1)	Θ(1)	N/A	O(n)	O(n)	O(n)	O(n)
Binary Search Tree	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(n)	O(n)	O(n)	O(n)	O(n)
Cartesian Tree	N/A	Θ(log(n))	Θ(log(n))	Θ(log(n))	N/A	O(n)	O(n)	O(n)	O(n)
B-Tree	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(log(n))	O(log(n))	O(log(n))	O(log(n))	O(n)
Red-Black Tree	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(log(n))	O(log(n))	O(log(n))	O(log(n))	O(n)
Splay Tree	N/A	Θ(log(n))	Θ(log(n))	Θ(log(n))	N/A	O(log(n))	O(log(n))	O(log(n))	O(n)
AVL Tree	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(log(n))	O(log(n))	O(log(n))	O(log(n))	O(n)
KD Tree	Θ(log(n))	Θ(log(n))	Θ(log(n))	Θ(log(n))	O(n)	O(n)	O(n)	O(n)	O(n)