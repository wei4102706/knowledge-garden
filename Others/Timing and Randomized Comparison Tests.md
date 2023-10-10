
## StopWatch
Demo:
```
Stopwatch sw = new Stopwatch();  
int fib41 = fib(41);  
double timeInSeconds = sw.elapsedTime();
```


### Randomized Comparison Test
随机对照试验
1. Initialize the objects you'll be testing, both your implementation and the correct implementation.
```
LinkedListDeque<Integer> studentDeque = new LinkedListDeque<>();
LinkedListDequeSolution<Integer> solutionDeque = new LinkedListDequeSolution<>();

```
2. Generate Random Operations
Use Java's `Random` class to generate random operations.
```
Random rand = new Random();
int operationNumber = rand.nextInt(4);  // Generate a number between 0 and 3

```
3. Perform Operations and Assertions
```
if (operationNumber == 0) {
    // Perform some operation e.g., addFirst
    int randomValue = rand.nextInt(100);
    studentDeque.addFirst(randomValue);
    solutionDeque.addFirst(randomValue);
} else if (operationNumber == 1) {
    // Perform some other operation e.g., addLast
    // ...
}

// Assert that both deques are the same
assertEquals(solutionDeque.size(), studentDeque.size());

```
4. Loop for Multiple Tests
```
for (int i = 0; i < 1000; i++) { // Step 2 and 3 }
```