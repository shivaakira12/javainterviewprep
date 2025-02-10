
---

# **Strings and StringBuffer in Java**

This document provides a detailed explanation of **Strings** and **StringBuffer** in Java, including their differences, use cases, and example programs.

---

## **Table of Contents**
1. [Introduction to Strings](#introduction-to-strings)
2. [Creating Strings](#creating-strings)
3. [Common String Methods](#common-string-methods)
4. [StringBuffer in Java](#stringbuffer-in-java)
5. [Common StringBuffer Methods](#common-stringbuffer-methods)
6. [Difference Between String and StringBuffer](#difference-between-string-and-stringbuffer)
7. [When to Use String vs StringBuffer](#when-to-use-string-vs-stringbuffer)
8. [Example Programs](#example-programs)
9. [StringBuilder (Bonus)](#stringbuilder-bonus)

---

## **1. Introduction to Strings**
- A **String** is a sequence of characters in Java.
- Strings are **immutable**, meaning their values cannot be changed after creation.
- Strings are stored in the **String Pool** for memory efficiency.

---

## **2. Creating Strings**
There are two ways to create a String:
1. **Using String Literal**:
   ```java
   String str1 = "Hello";
   ```
2. **Using `new` Keyword**:
   ```java
   String str2 = new String("Hello");
   ```

---

## **3. Common String Methods**
| Method                     | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| `length()`                 | Returns the length of the string.                                           |
| `charAt(int index)`        | Returns the character at the specified index.                               |
| `concat(String str)`       | Concatenates the specified string to the end of the current string.         |
| `equals(Object obj)`       | Compares the string with the specified object for equality.                 |
| `equalsIgnoreCase(String)` | Compares two strings, ignoring case differences.                            |
| `substring(int beginIndex)`| Returns a substring starting from the specified index.                      |
| `toLowerCase()`            | Converts the string to lowercase.                                           |
| `toUpperCase()`            | Converts the string to uppercase.                                           |
| `trim()`                   | Removes leading and trailing whitespace.                                    |
| `replace(char old, char new)` | Replaces all occurrences of a character with another character.          |
| `split(String regex)`      | Splits the string based on the given regular expression.                    |

---

## **4. StringBuffer in Java**
- **StringBuffer** is a **mutable** sequence of characters.
- It is **thread-safe** (synchronized), making it suitable for multi-threaded environments.
- Used when frequent modifications to the string are required.

---

## **5. Common StringBuffer Methods**
| Method                     | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| `append(String str)`       | Appends the specified string to the end of the current buffer.              |
| `insert(int offset, String str)` | Inserts the specified string at the given offset.                       |
| `delete(int start, int end)` | Removes the characters in the specified range.                            |
| `reverse()`                | Reverses the sequence of characters.                                        |
| `replace(int start, int end, String str)` | Replaces the characters in the specified range with the given string.  |
| `capacity()`               | Returns the current capacity of the buffer.                                 |
| `length()`                 | Returns the length of the buffer.                                           |

---

## **6. Difference Between String and StringBuffer**

| Feature                | String                                      | StringBuffer                                |
|------------------------|---------------------------------------------|---------------------------------------------|
| **Mutability**         | Immutable (cannot be changed after creation)| Mutable (can be changed after creation)     |
| **Thread Safety**      | Not thread-safe                            | Thread-safe (synchronized)                  |
| **Performance**        | Faster for immutable operations             | Slower due to synchronization overhead      |
| **Storage**            | Stored in String Pool                       | Stored in Heap memory                       |
| **Memory Efficiency**  | More memory-efficient for literals          | Less memory-efficient due to mutability     |
| **Use Case**           | Best for fixed strings                      | Best for frequently modified strings        |

---

## **7. When to Use String vs StringBuffer**
- Use **String** when:
  - The value of the string is fixed and won’t change.
  - You need to store a string literal.
  - You want to take advantage of the String Pool for memory efficiency.

- Use **StringBuffer** when:
  - You need to modify the string frequently (e.g., concatenation in loops).
  - You are working in a multi-threaded environment and need thread safety.

---

## **8. Example Programs**

### **String Example**
```java
public class StringExample {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = new String("World");

        System.out.println("Length of str1: " + str1.length()); // 5
        System.out.println("Concatenation: " + str1.concat(str2)); // HelloWorld
        System.out.println("Character at index 1: " + str1.charAt(1)); // e
        System.out.println("Substring: " + str1.substring(2)); // llo
        System.out.println("Uppercase: " + str1.toUpperCase()); // HELLO
    }
}
```

### **StringBuffer Example**
```java
public class StringBufferExample {
    public static void main(String[] args) {
        StringBuffer sb = new StringBuffer("Hello");

        sb.append(" World"); // Hello World
        sb.insert(5, " Java"); // Hello Java World
        sb.delete(5, 10); // Hello World
        sb.reverse(); // dlroW olleH

        System.out.println(sb.toString());
    }
}
```

---

## **9. StringBuilder (Bonus)**
- **StringBuilder** is similar to `StringBuffer` but is **not thread-safe**.
- It is faster than `StringBuffer` and is recommended for single-threaded environments.

### **Example**
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb.toString()); // Hello World
```

---

## **Conclusion**
- **String**: Immutable, thread-safe, stored in String Pool.
- **StringBuffer**: Mutable, thread-safe, stored in Heap memory.
- **StringBuilder**: Mutable, not thread-safe, faster than `StringBuffer`.

---
