### **`Comparable` Interface**:

- When a class implements the `Comparable` interface, it provides a natural ordering for its objects.
- By implementing the `Comparable` interface and overriding its `compareTo` method, you are defining a default way to compare instances of that class.
- This is useful when there is a single, natural ordering that makes sense for the class.
- Example: If you have a `Person` class, a natural ordering might be by last name, so you would implement `Comparable` to compare `Person` objects by their last names.
```
public class Person implements Comparable<Person> {
    private String lastName;
    // other fields...

    @Override
    public int compareTo(Person other) {
        return this.lastName.compareTo(other.lastName);
    }
}

```

### **`Comparator` Interface**:

- The `Comparator` interface is used when you want to define multiple different possible orderings for a class.
- A class does not implement `Comparator`; instead, you create separate `Comparator` classes to define each ordering.
- This is useful when a class has several attributes by which it can be ordered.
- Example: Continuing with the `Person` class example, you might have separate `Comparator` classes to order `Person` objects by first name, age, or city.
```
import java.util.Comparator; 
public class PersonFirstNameComparator implements Comparator<Person> { 
	@Override public int compare(Person person1, Person person2) { 
		return person1.getFirstName().compareTo(person2.getFirstName()); 
	} 
}
```

In summary:
- Use `Comparable` when there is a single logical ordering for your class.
- Use `Comparator` when you need to support multiple orderings, or when you want to sort instances of a class that you do not have control over, or that does not have a natural ordering.