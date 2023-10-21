Used to solve dynamic connectivity problem, determining whether there is a path connecting certain points in a network. 
### Union-Find / Merge-Find:
A data structure to track disjoint sets, 
Provides operations to 
1. create sets, MakeSet: O(1)
2. merge sets, Union: O(α(n)) (amortized with path compression and union by rank)
3. find the set an element belongs to, Find: O(α(n)) (amortized with path compression)
### ListOfSet-DS:

### Quick-Find:
**uses an array of integers to track which set each element belongs to.**
Union: O(n)
Find:O(1)
### Quick-Union:
**stores the parent of each node rather than the set to which it belongs and merges sets by setting the parent of one root to the other.**
may lead to unbalanced trees, causing a slower find operation over time.
1. Union: O(logN), but O(n) in the worst case
2. Find: O(log N), but O(n) in the worst case
### Weighted Quick-Union DS:
an optimization over Quick-Union, the smaller set is always attached to the larger set
ensure the height of the trees grows slowly
1. Union: O(log n) in the worst case
2.  Find: O(log n) in the worst case
### Weighted Quick-Union with Path Compression DS
**sets the parent of each node to the set’s root whenever find() is called on it.**
- Union: O(α(N)) (where α is the inverse Ackermann function)
- Find: O(α(N))
Implementation:
```
public int find(int x) { 
	if (parent[x] != x) { 
		parent[x] = find(parent[x]); // Recursively update parent pointers 
	} 
	return parent[x]; 
}
```
![[截圖 2023-10-20 下午8.22.30.png]]almost linear time! ![[截圖 2023-10-20 下午8.24.02.png]]