## SLLists

## Sentinel Nodes
Create a sentinel node:
- serves as a marker 
- doesn't hold meaningful data but simplifies the code by eliminating the need for special cases

For example, consider the `addLast` method for a singly linked list (SLList):

Without Sentinel Node:
```
public void addLast(int x) {     
	size += 1; 
	     
	if (first == null) {         
		first = new IntNode(x, null); 
		return;     
	}      
	
	IntNode p = first;     
	while (p.next != null) {         
		p = p.next;     
	}      
	
	p.next = new IntNode(x, null); 
}
```

With Sentinel Node:
```
public void addLast(int x) {
	size += 1;     
	IntNode p = sentinel;     
	while (p.next != null) {         
		p = p.next;     
	}      
	
	p.next = new IntNode(x, null); 
}
```