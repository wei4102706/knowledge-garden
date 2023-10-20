Used to solve dynamic connectivity problem, determining whether there is a path connecting certain points in a network. 
### Union-Find(or Merge-Find):
A data structure to track disjoint sets, 
Provides operations to 
1. create sets, MakeSet: O(1)
2. merge sets, Union: O(α(n)) (amortized with path compression and union by rank)
3. find the set an element belongs to, Find: O(α(n)) (amortized with path compression)
### Quick-Union:
a variant of Union-Find, where union operations are optimized to quickly merge sets by changing root pointers.
may lead to unbalanced trees, causing a slower find operation over time.
1. Union: O(n) in the worst case without optimizations
2. Find: O(n) in the worst case without optimizations
### Weighted Quick Union:
an optimization over Quick-Union, the smaller set is always attached to the larger set
ensure the height of the trees grows slowly
1. Union: O(log n) in the worst case (or O(α(n)) amortized with path compression)
2.  Find: O(log n) in the worst case (or O(α(n)) amortized with path compression)

### Path Compression
an optimization technique used in the disjoint-set data structure to speed up the Find operation, and the Union operation as well.
works by flattening the structure of the tree whenever the Find operation is performed. 
When Find is called on a particular element, path compression updates the parent pointers of all the nodes along the path from that element to the root, making them point directly to the root. As a result, the height of the tree is reduced, and future Find and Union operations become faster.
Implementation:
```
public int find(int x) { 
	if (parent[x] != x) { 
		parent[x] = find(parent[x]); // Recursively update parent pointers 
	} 
	return parent[x]; 
}
```