# Tower of Hanoi – Java Implementation

## Overview

This project implements the classic **Tower of Hanoi problem** using Java. It demonstrates the concept of recursion, method declaration, conditional statements, parameter passing, and output operations.

The objective is to move a stack of disks from a source rod to a destination rod using an auxiliary rod while following specific rules.

## 1. Problem Rules

The Tower of Hanoi has three rods:

- **Source (A):** The rod where all disks initially start.
- **Auxiliary (B):** The temporary rod used during the movements.
- **Destination (C):** The rod where all disks must end up.

The rules are:

1. Only one disk can be moved at a time.
2. Only the top disk of a rod can be moved.
3. A larger disk cannot be placed on top of a smaller disk.

## 2. Java Syntax Explained

### A. Class Declaration

```java
public class TowerOfHanoi {
```

- `public`: Makes the class accessible from other classes.
- `class`: Declares a Java class.
- `TowerOfHanoi`: The name of the class.

### B. Method Declaration

```java
static void towerOfHanoi(int n, char source, char auxiliary, char destination)
```

This declares the recursive method.

| Syntax | Purpose |
|---|---|
| `static` | Allows the method to be called without creating an object. |
| `void` | Indicates that the method does not return a value. |
| `towerOfHanoi` | Method name. |
| `int n` | Number of disks. |
| `char source` | Starting rod. |
| `char auxiliary` | Temporary rod. |
| `char destination` | Final rod. |

### C. Conditional Statements

```java
if (n == 1) {
    System.out.println("Move disk 1 from " + source + " to " + destination);
    return;
}
```

- `if`: Executes a block of code when a condition is true.
- `==`: Compares two values for equality.
- `return`: Terminates the current method execution.

This is the **base case**. It stops recursion when only one disk remains.

### D. Output Statement

```java
System.out.println("Move disk " + n + " from " + source + " to " + destination);
```

- `System`: A built-in Java class.
- `out`: The standard output stream.
- `println()`: Prints information and moves to a new line.
- `+`: Joins strings and variables through string concatenation.

### E. Recursive Method Calls

First recursive call:

```java
towerOfHanoi(n - 1, source, destination, auxiliary);
```

Purpose:
Moves the smaller `n-1` disks from the source rod to the auxiliary rod.

Second recursive call:

```java
towerOfHanoi(n - 1, auxiliary, source, destination);
```

Purpose:
Moves the smaller disks from the auxiliary rod to the destination rod.

Both calls use the same method but with different parameters.

### F. Main Method

```java
public static void main(String[] args) {
    int n = 3;
    towerOfHanoi(n, 'A', 'B', 'C');
}
```

- `public`: Makes the method accessible.
- `static`: Allows the Java runtime to call the method without creating an object.
- `void`: Indicates no return value.
- `main`: The entry point of the Java application.
- `String[] args`: Receives command-line arguments.
- `int n = 3`: Declares and initializes the number of disks.

## 3. Complete Java Code

```java
public class TowerOfHanoi {

    static void towerOfHanoi(int n, char source, char auxiliary, char destination) {

        // Base case
        if (n == 1) {
            System.out.println("Move disk 1 from " + source + " to " + destination);
            return;
        }

        // Move n-1 disks from source to auxiliary
        towerOfHanoi(n - 1, source, destination, auxiliary);

        // Move the largest disk to destination
        System.out.println("Move disk " + n + " from " + source + " to " + destination);

        // Move n-1 disks from auxiliary to destination
        towerOfHanoi(n - 1, auxiliary, source, destination);
    }

    public static void main(String[] args) {

        int n = 3;

        towerOfHanoi(n, 'A', 'B', 'C');
    }
}
```

## 4. Understanding the Recursion Logic

The algorithm follows three main steps:

1. Move `n-1` disks from the source to the auxiliary rod.
2. Move the largest disk from the source to the destination.
3. Move `n-1` disks from the auxiliary rod to the destination.

This is an example of **recursion**, where a method calls itself to solve smaller versions of the original problem.

### Mathematical Formula

The minimum number of movements is:

\[
T(n)=2^n-1
\]

Where `n` represents the number of disks.

| Disks | Minimum Movements |
|---:|---:|
| 1 | 1 |
| 2 | 3 |
| 3 | 7 |
| 4 | 15 |
| 5 | 31 |

## 5. Sample Output

For three disks:

```text
Move disk 1 from A to C
Move disk 2 from A to B
Move disk 1 from C to B
Move disk 3 from A to C
Move disk 1 from B to A
Move disk 2 from B to C
Move disk 1 from A to C
```

## 6. Key Concepts Learned

Through this project, the following Java concepts are demonstrated:

- Classes and methods.
- Primitive data types (`int` and `char`).
- Method parameters and arguments.
- Conditional statements (`if`).
- Comparison operators (`==`).
- Output operations (`System.out.println()`).
- Recursion and base cases.
- Method calls and parameter passing.

## 7. Possible Improvements

Future improvements could include:

- Using `Scanner` to allow users to enter the number of disks.
- Validating user input.
- Displaying the total number of moves.
- Implementing an interactive visualization of the disk movements.

---

**Language:** Java  
**Topic:** Data Structures and Algorithms / Recursion  
**Project:** Tower of Hanoi
