### Injection:

Injection is a programming technique where one object supplies the dependencies of another object. It's a form of the Inversion of Control (IoC) principle, which improves modularity and testability of software systems.

#### Types of Injection:

1. **Dependency Injection (DI):** In DI, dependencies are injected into objects through constructors, methods, or properties.
2. **SQL Injection:** A malicious technique where attackers can execute unauthorized SQL commands by manipulating the input.

```
interface Service {
    void serve();
}

class ServiceImpl implements Service {
    public void serve() {
        System.out.println("Service called");
    }
}

class Client {
    private Service service;

    Client(Service service) {
        this.service = service;
    }

    void doSomething() {
        service.serve();
    }
}

public class Main {
    public static void main(String[] args) {
        Service service = new ServiceImpl();
        Client client = new Client(service);
        client.doSomething();
    }
}

```

In the example above, `ServiceImpl` is injected into `Client` through the constructor.

### Reflection:

Reflection is a programming technique that allows a program to introspect and manipulate its own structure and behavior at runtime.

#### Key Features:

1. **Class Inspection:** Discover class properties, methods, and constructors at runtime.
2. **Dynamic Instantiation:** Create objects and call methods dynamically at runtime.
3. **Access Modifiers Bypass:** Ability to access private and protected members of a class.

```
public class ReflectionExample {
    public static void main(String[] args) throws Exception {
        Class<?> clazz = Class.forName("java.util.ArrayList");
        Object obj = clazz.newInstance();

        // Output: class java.util.ArrayList
        System.out.println(obj.getClass());
    }
}

```
In the example above, reflection is used to create a new instance of `java.util.ArrayList` dynamically at runtime.