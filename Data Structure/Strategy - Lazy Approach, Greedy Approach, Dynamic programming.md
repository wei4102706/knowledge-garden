### **Lazy Approach**:
- minimizes the work done at each step, deferring operations until they are absolutely necessary. It aims to achieve the desired outcome with the least amount of work. This approach is typically used when operations are expensive or when the full set of operations is not required to achieve the goal.
- Example: The Quick Union algorithm, which avoids restructuring the data until a union operation is explicitly requested.

### Greedy Approach:
- A greedy approach builds up a solution piece by piece, always choosing the next piece that provides the most immediate benefit or value. It makes locally optimal choices at each stage with the hope of finding the global optimum.
- Example: Dijkstra's algorithm, which at each step expands the most promising node, is a classic example of a greedy algorithm.

### Dynamic Programming:
- breaks down a problem into simpler, overlapping subproblems, solves each subproblem just once, and stores their solutions - ideally using a memory-based solution for efficiency. It is used for optimization problems where the best solutions to subproblems are used to construct the best solution to the overall problem.
- Example: The Fibonacci sequence calculation can be optimized using dynamic programming to reduce the time complexity from exponential to linear.

### Divide and Conquer:
- breaks the problem into non-overlapping subproblems, solves the subproblems independently, and then combines their solutions to solve the original problem. Unlike Dynamic Programming, the subproblems do not overlap.
- Example: The Merge Sort algorithm divides the array into halves, sorts them independently, and then merges the sorted halves.

 ### Backtracking:
- systematic method to iterate through all the possible configurations of a problem. When it hits a dead end, it backtracks to the previous step, makes a different choice, and continues the search. It's often used for exhaustive search or constraint satisfaction problems.
- Example: The N-Queens puzzle, where the goal is to place N chess queens on an N×N chessboard so that no two queens threaten each other.

### Branch and Bound:
- an optimization technique used for computational problems. It partitions the problem into subproblems, solves them independently, and uses the solutions to prune the search space, thereby reducing the number of subproblems that need to be explored.
- Example: The Traveling Salesman Problem can be solved using Branch and Bound by systematically deciding which branches to prune and which to continue exploring based on the current best solution.