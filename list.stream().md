In Java, `list.stream()` is a method that converts a `List` (or any `Collection`) into a **Stream**. A **Stream** is a sequence of elements that supports various methods to perform operations like filtering, mapping, and reducing, typically in a functional style.

### Key Features of `list.stream()`:
1. **Functional Operations**: Enables operations like `filter()`, `map()`, `reduce()`, `collect()`, and more.
2. **Non-Mutating**: It doesn’t change the original list; it produces a new stream for processing.
3. **Lazy Evaluation**: Operations on a stream are evaluated lazily, meaning computation happens only when necessary.
4. **Single Use**: A stream can be consumed only once. After a terminal operation (e.g., `collect()`, `forEach()`), it cannot be reused.

### Example:
```java
import java.util.Arrays;
import java.util.List;

public class StreamExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6);

        // Using stream to filter even numbers and print them
        numbers.stream()
               .filter(n -> n % 2 == 0)
               .forEach(System.out::println);
    }
}
```

**Output:**
```
2
4
6
```

### Related Method:
- **`list.parallelStream()`**: Similar to `stream()`, but it processes elements in parallel, utilizing multiple CPU cores for performance.  
