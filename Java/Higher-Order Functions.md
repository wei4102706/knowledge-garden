1. **Functional Interface**:

- For a function to be passed as an argument in Java, it must be represented as an object. This is typically done using a functional interface, which is an interface with just one abstract method.
- Example:
```
@FunctionalInterface
public interface FunctionInterface {
    int apply(int x);
}

```

2. **Lambda Expressions**:

- Lambda expressions provide a concise way to create anonymous function instances. They are often used when passing functions as arguments to higher-order functions.
- Example:
```
FunctionInterface multiplyByTwo = (int x) -> x * 2;

```

3. **Method References**:

- If you have a method that performs the operation you want, you can use a method reference instead of a lambda.
- Example:
```
public class Utils {
    public static int multiplyByThree(int x) {
        return x * 3;
    }
}
FunctionInterface multiplyByThree = Utils::multiplyByThree;

```

4. **Predefined Functional Interfaces**:

- Java provides several predefined functional interfaces in the `java.util.function` package, such as `Function<T,R>`, `Predicate<T>`, `Consumer<T>`, and `Supplier<T>`.

5. **Creating Higher-Order Functions**:

- A higher-order function can be created by defining a method that accepts and/or returns a functional interface type.
- Example:
``` 
public class HigherOrderFunction {
    public static void applyTwice(FunctionInterface func, int x) {
        System.out.println(func.apply(func.apply(x)));
    }

    public static void main(String[] args) {
        FunctionInterface multiplyByTwo = (int x) -> x * 2;
        applyTwice(multiplyByTwo, 5);  // Output: 20
    }
}

```

6. **Combining Functions**:

- Higher-order functions can also return functions, enabling function composition or other ways of combining functions.
- Example:
```
public static FunctionInterface compose(FunctionInterface f1, FunctionInterface f2) {
    return (int x) -> f1.apply(f2.apply(x));
}

```