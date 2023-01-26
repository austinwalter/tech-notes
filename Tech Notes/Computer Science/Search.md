# Search

## Heap Search
The idea is to init a heap "the smallest element first", and add all elements from the array into this heap one by one keeping the size of the heap always less or equal to `k`. That would results in a heap containing `k` largest elements of the array.

The head of this heap is the answer, i.e. the kth largest element of the array.

The time complexity of adding an element in a heap of size `k` is $O(\log k)$, and we do it `n` times that means $O(N \log k)$ time complexity for the algorithm.

This algorithm improves time complexity, but one pays with O(k)\mathcal{O}(k)O(k) space complexity.

```
int findKthLargest(vector<int>& nums, int k) {
	priority_queue<int, vector<int>, greater<int>> heap;
	
	for (int i = 0; i < nums.size(); i++) {
	    heap.push(nums[i]);
           
        if (heap.size() > k) {
	        heap.pop();
        }
    }
        
	return heap.top();
}
```

Complexity Analysis

Time complexity : $O(n \log k)$ where `n` is length of array and `k` is 
Space complexity : O(k)\mathcal{O}(k)O(k) to store the heap elements.

**Reference:**
https://leetcode.com/problems/kth-largest-element-in-an-array/solutions/214469/official-solution/




[-1,0,1,2,-1,-4]
[0,1,1]
[0,0,0]
[0,0,0,0]