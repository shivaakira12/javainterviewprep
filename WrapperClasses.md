# Wrapper Classes in Java

## What are Wrapper Classes?
Wrapper classes in Java **convert primitive data types into objects**. They are useful when objects are required instead of primitive types, such as in **collections (ArrayList, HashMap)** or **generics**.

Each primitive data type has a corresponding **wrapper class** in the `java.lang` package:

| **Primitive Type** | **Wrapper Class** |
|--------------------|------------------|
| `byte`            | `Byte`           |
| `short`           | `Short`          |
| `int`             | `Integer`        |
| `long`            | `Long`           |
| `float`           | `Float`          |
| `double`          | `Double`         |
| `char`            | `Character`      |
| `boolean`         | `Boolean`        |

---

## Why Use Wrapper Classes?
### 1. Collection Framework Compatibility
Primitive types **cannot be stored** in collections like `ArrayList`, `HashSet`. Wrapper classes help to **store and manipulate** values as objects.
```java
import java.util.ArrayList;
public class WrapperExample {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10); // Autoboxing (int → Integer)
        list.add(20);
        System.out.println(list); // [10, 20]
    }
}
```

### 2. Utility Methods
Wrapper classes provide **utility methods** for parsing and conversion.
```java
int num = Integer.parseInt("123"); // Converts String to int
System.out.println(num + 10); // Output: 133
```

### 3. Synchronization in Multi-threading
Java supports **only object synchronization**. Wrapper classes help in **thread-safe** operations.

### 4. Serialization
Primitive data types **cannot be serialized**, but objects of wrapper classes can.

---

## Autoboxing and Unboxing
### Autoboxing (Primitive → Wrapper)
```java
public class AutoboxingExample {
    public static void main(String[] args) {
        int num = 10;
        Integer obj = num; // Autoboxing
        System.out.println("Integer object: " + obj);
    }
}
```

### Unboxing (Wrapper → Primitive)
```java
public class UnboxingExample {
    public static void main(String[] args) {
        Integer obj = 20;
        int num = obj; // Unboxing
        System.out.println("Primitive int: " + num);
    }
}
```

---

## Important Methods in Wrapper Classes
### Parsing Methods (String → Primitive)
```java
public class ParsingExample {
    public static void main(String[] args) {
        String str = "100";
        int num = Integer.parseInt(str); // Convert String to int
        System.out.println(num + 50); // Output: 150
    }
}
```

### Value Methods (Wrapper → Primitive)
```java
public class ValueMethodExample {
    public static void main(String[] args) {
        Double d = 99.99;
        double primitiveD = d.doubleValue(); // Wrapper to Primitive
        System.out.println(primitiveD); // Output: 99.99
    }
}
```

### Comparing Wrapper Objects
```java
public class CompareExample {
    public static void main(String[] args) {
        Integer a = 50, b = 50;
        System.out.println(a.equals(b)); // true
        System.out.println(Integer.compare(100, 50)); // 1 (100 > 50)
    }
}
```

---

## Converting Wrapper Class to String
### Using toString()
```java
Integer num = 200;
System.out.println(num.toString()); // "200"
```

### Using String.valueOf()
```java
Integer num = 300;
String str = String.valueOf(num);
System.out.println(str + 100); // Output: "300100"
```

---

## Performance Comparison (Primitive vs Wrapper)
```java
public class PerformanceTest {
    public static void main(String[] args) {
        long startTime = System.nanoTime();
        int sum = 0;
        for (int i = 0; i < 1000000; i++) {
            sum += i; // Using primitive
        }
        long endTime = System.nanoTime();
        System.out.println("Primitive Time: " + (endTime - startTime));

        startTime = System.nanoTime();
        Integer sumObj = 0;
        for (int i = 0; i < 1000000; i++) {
            sumObj += i; // Using Wrapper (Slower)
        }
        endTime = System.nanoTime();
        System.out.println("Wrapper Time: " + (endTime - startTime));
    }
}
```

---

## Practical Use Cases of Wrapper Classes
1. **Storing Primitive Data in Collections**
```java
ArrayList<Double> prices = new ArrayList<>();
prices.add(299.99);
```

2. **Parsing String Input from User**
```java
Scanner sc = new Scanner(System.in);
int age = Integer.parseInt(sc.nextLine()); // Convert String to int
```

3. **Switching Between Object and Primitive Types**
```java
Integer num = 100; // Autoboxing
int n = num; // Unboxing
```

---

## Summary
- Wrapper classes **convert primitive types into objects**.
- **Autoboxing** and **Unboxing** help in automatic conversion.
- Wrapper classes provide **utility methods** like `parseInt()`, `valueOf()`, and `compare()`.
- Primitive types are **faster** than wrapper classes.
- Wrapper classes are used in **collections, parsing, synchronization, and serialization**.

---

This is a **complete guide** on Wrapper Classes in Java. 🚀
