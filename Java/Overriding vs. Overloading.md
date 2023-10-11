### Method Overriding
If a “subclass” has a method with the exact same signature as in the        “superclass”, we say the subclass overrides the method.

In Java, methods in a class can have the same name, but different parameters. For example, a `Math` class can have an `add(int a, int b)` method and an `add(float a, float b)` method as well. The Java compiler is smart enough to choose the correct method depending on the parameters that you pass in. Methods with the same name but different parameters are said to be overloaded.

**Overriding** For each method in `AList` that we also defined in `List`, we will add an @Override right above the method signature. As an example:

```
@Override
public Item get(int i) { ... }
```

This is not technically necessary, but is good style and thus we will require it. Also, it allows us to check against typos. If we mistype our method name, the compiler will prevent our compilation if we have the @Override tag.
### Overloading
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


**Static vs. Dynamic Type** Every variable in Java has a static type. This is the type specified when the variable is declared, and is checked at compile time. Every variable also has a dynamic type; this type is specified when the variable is instantiated, and is checked at runtime. As an example:

```
Thing a;
a = new Fox();
```

Here, `Thing` is the static type, and `Fox` is the dynamic type. This is fine because all foxes are things. We can also do:

```
Animal b = (Animal) a;
```

This is fine, because all foxes are animals too. We can do:

```
Fox c = (Fox) b;
```

This is fine, because `b` points to a `Fox`. Finally, we can do:

```
a = new Squid()
```

This is fine, because the static type of `a` is a `Thing`, and `Squid` is a thing.

**Dynamic Method Selection** The rule is, if we have a static type `X`, and a dynamic type `Y`, then if `Y` overrides the method from `X`, then on runtime, we use the method in `Y` instead. Student often confuse overloading and overriding.

**Overloading and Dynamic Method Selection** Dynamic method selection plays no role when it comes to overloaded methods. Consider the following piece of code, where `Fox extends Animal`.

```
1  Fox f = new Fox();
2  Animal a = f;
3  define(f);
4  define(a);
```

Let’s assume we have the following overloaded methods in the same class:

```
public static void define(Fox f) { ... }
public static void define(Animal a) { ... }
```

Line 3 will execute `define(Fox f)`, while line 4 will execute `define(Animal a)`. Dynamic method selection only applies when we have overridden methods. There is no overriding here, and therefore dynamic method selection does not apply.