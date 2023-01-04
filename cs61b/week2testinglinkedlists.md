# Week 2 - Testing && Linked Lists

## Lecture 3 - Testing 

### Introduction  



junit - a testing framework for Java. for example, to test if two string arrays are equal:

```java
org.junit.Assert.assertArrayEquals(expected, actual);
```
**Note**: You can use: 

```java
import org.junit.Assert.* 
```

to use all the methods in the Assert class as demonstrated below:

```java
import org.junit.Assert.*;
//code goes here
assertArrayEquals(expected, actual);
```

Just like in CS50P - Unit tests are important. Use junit to test your code. Make small tests for each function you would like to confirm is working correctly.

### Testing in Java

Steps to develop with Test Driven Development (TDD):

1. Identify a new feature.
2. Write a unit test for that feature.
3. Run the test and see it fail.
4. Write the minimum amount of code to make the test pass.
5. Refactor the code to make it clean and readable.

___

## Lecture 4 - Reference Types, Recursion && Lists

There are 8 primitive types in Java:

* boolean, byte, short, **int**, long, float, **double**, char

Everything else, including arrays, is a **reference type**. Reference types are objects that are stored in the heap.

### Parameter Passing

When you pass in variables to a method, you **pass by value**, where the original variable is not changed. However, when you pass in objects, you **pass by reference**, where the original object is changed.

### Example of Pass by Reference

```java
public static void main(String[] args) {
    int[] a = {1, 2, 3};
    int[] b = a;
    b[0] = 5; //a is also modified, as b and a point to the same object (array)
    System.out.println(a[0]); // prints 5
}
```

The golden rule:

* b = a **copies the bits** from a into b.

* Passing parameters **copies the bits**.

To create an Linked List *IntList*, you can use the following code:

```java
public class IntList {
    public int first;
    public IntList rest;

    //sets up the IntList object
    public IntList(int f, IntList r) {
        first = f;
        rest = r;
    }
    /** Returns the size of the list using... recursion! */
    public int size() {
        if (rest == null) {
            return 1;
        }
        return 1 + this.rest.size();

    }
    public static void main(String[] args) {
        //instantiates an IntList object
        IntList L = new IntList(15, null);
        //sets L pointer to a new IntList object of size 10, pointing to the prior IntList object.

        L = new IntList(10, L);

        //sets L pointer to IntList of size 5

        L = new IntList(5, L);

        //Now, L points to 5 which points to 10 which points to 15.

        //We worked backwards, the first IntList object is the last one in the list.
    }
}
```

The previous code, without comments can be read here - 
```java
public class IntList {
    public int first;
    public IntList rest;

    //sets up the IntList object
    public IntList(int f, IntList r) {
        first = f;
        rest = r;
    }

    /** Returns the size of the list using... recursion! */
    public int size() {
        if (rest == null) {
            return 1;
        }
        return 1 + this.rest.size();
    }

    //Creates an IntList object with the following values: 5, 10, 15
    public static void main(String[] args) {

        IntList L = new IntList(15, null);

        L = new IntList(10, L);

        L = new IntList(5, L);
    }
}
```

Another method to iteratively return the size of the linked list using iteration is:

```java
public int iterativeSize() {
    IntList p = this;
    int totalSize = 0;
    while (p != null) {
        totalSize += 1;
        p = p.rest;
    }
    return totalSize;
}
```

To get the value of the ith item in the list, you can use the following code:

```java
public int get(int i) {
    if (i == 0) {
        return first;
    }
    return rest.get(i - 1);
}
```

