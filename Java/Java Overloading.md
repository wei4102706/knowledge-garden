allows you to define multiple methods with the same name but different parameter lists. Overloaded methods can differ in the number of parameters, types of parameters, or both.

#### Rules for Overloading
1. **Method Name**: Must be the same.
2. **Parameter List**: Must differ in type, order, or number of parameters.
3. **Return Type**: Does not matter; it cannot be used to distinguish overloaded methods.

```
// Overloaded methods for adding numbers
public int add(int a, int b) {
    return a + b;
}

public double add(double a, double b) {
    return a + b;
}

public int add(int a, int b, int c) {
    return a + b + c;
}

```

#### Points to Remember
1. **Compile-Time Polymorphism**: Overloading is resolved at compile-time.
2. **Not Based on Return Type**: Two methods with different return types but the same name and parameter list are not considered overloaded methods.
3. **Varargs**: You can also overload methods using variable arguments (varargs), but use cautiously to avoid ambiguity.