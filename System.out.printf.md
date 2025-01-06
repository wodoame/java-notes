In Java, the `.printf()` function (from the `PrintStream` class) is used to format and print output to the console. It allows you to include variables in your output with precise control over formatting.

Here’s a quick guide:

---

### **Syntax**
```java
System.out.printf(format, arguments);
```

- **`format`**: A string containing text and format specifiers (placeholders) that define how the arguments are displayed.
- **`arguments`**: Values to be formatted and inserted into the placeholders in the format string.

---

### **Common Format Specifiers**
Here are the most commonly used format specifiers:

| **Specifier** | **Description**                 | **Example**        |
|---------------|---------------------------------|--------------------|
| `%d`          | Integer (decimal)              | `%d` → `42`        |
| `%f`          | Floating-point number          | `%.2f` → `3.14`    |
| `%s`          | String                         | `%s` → `Hello`     |
| `%c`          | Character                      | `%c` → `A`         |
| `%n`          | New line                       | (platform-specific)|
| `%t`          | Date/time                      | `%tY` → `2025`     |
| `%b`          | Boolean                        | `%b` → `true`      |

---

### **Examples**
#### **1. Basic Example**
```java
public class Main {
    public static void main(String[] args) {
        int age = 25;
        System.out.printf("I am %d years old.%n", age);
    }
}
```
**Output**:
```
I am 25 years old.
```

#### **2. Formatting Floating-Point Numbers**
```java
public class Main {
    public static void main(String[] args) {
        double pi = 3.14159;
        System.out.printf("Value of pi: %.2f%n", pi);
    }
}
```
**Output**:
```
Value of pi: 3.14
```
- `%.2f` ensures only two digits appear after the decimal point.

#### **3. Aligning and Padding Output**
```java
public class Main {
    public static void main(String[] args) {
        System.out.printf("%-10s %10s%n", "Left", "Right");
    }
}
```
**Output**:
```
Left              Right
```
- `%-10s`: Left-align the string in a 10-character width field.
- `%10s`: Right-align the string in a 10-character width field.

#### **4. Printing Multiple Values**
```java
public class Main {
    public static void main(String[] args) {
        String name = "Alice";
        int age = 30;
        double height = 5.4;

        System.out.printf("Name: %s, Age: %d, Height: %.1f ft%n", name, age, height);
    }
}
```
**Output**:
```
Name: Alice, Age: 30, Height: 5.4 ft
```

#### **5. Displaying Date and Time**
```java
import java.util.Date;

public class Main {
    public static void main(String[] args) {
        Date now = new Date();
        System.out.printf("Current year: %tY%n", now);  // Year
        System.out.printf("Current month: %tB%n", now); // Full month name
        System.out.printf("Current time: %tT%n", now);  // HH:MM:SS
    }
}
```
---

### **Notes**
- Always include `%n` for new lines instead of `\n` to ensure cross-platform compatibility.
- You can chain multiple placeholders in one format string and pass values in order.
