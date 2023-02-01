# Intro to OOP Java - Weeks 1-3

## Professor Lord

### Intro to Java

* Java is universal - can be run on any OS as long as it has a java interpreter. 
* In C++, you need to compile the binary code using different compilers depending on OS/architecture.

* Java has a compiler for Windows/Mac/Other for each OS, producing Java ```bytecode``` which is interpreted by the Java Virtual Machine (JVM). This standardizes many concepts such as the size of an int, which caps at 2,147,483,647. (Max cash stack of Runescape)



### Primitive Data Types

```java
byte //8-bit signed two's complement integer
short //16-bit signed two's complement integer
int //32-bit signed two's complement integer
long //64-bit signed two's complement integer
float //32-bit single precision IEEE 754
double //64-bit single precision IEEE 754
boolean //true and false
char //16-bit Unicode Character
```



## Object Oriented Programming

**Class** - A blueprint or template that describe the properties and behaviors of an object.

**Object** - An instance of a class which has specific properties.



```java
public class animal {
    public static class Cat {
        static int numberOfCats = 0;
        static final int NUMBER_OF_LEGS = 4; // declares all cats have 4 legs, cannot be changed (final)
        String breed; // instance variables
        String gender;
        String color;
        boolean neutered;

        // Constructor
        public Cat() {
            numberOfCats++; // counts how many Cats have been initialized
        }
    }

    public static void main(String[] args) {
        Cat pet1, pet2, pet3;
        pet1 = new Cat(); // initializes pet1 as a Cat
        pet1.breed = "Tabby";
        pet1.color = "Orange";
        pet2 = new Cat();
        System.out.println(pet1.breed); // prints Tabby
        System.out.println(pet1.color); // prints Orange
        System.out.println(Cat.numberOfCats); // prints 2
    }
}

```



## Methods

A cat object could tell you its breed:

```java
public String getBreed() {
  return breed;
}
// run this as:
String b = pet1.getBreed();
```

You can have your cat neutered:

```java
public void setNeutered() {
  neutered = true;
}
//run as:
pet1.setNeutered(); //sets pet1's neutered status to true
```



### String methods

```java
int length(); //gives length of string
char charAt(int); //gives char at index int
boolean equals(String); //compares two strings, case sensitive
boolean equalsIgnoreCase(String); //compares two string, case insensitive
 
/* To find out how many 'o' chars in a string */
int o_count = 0;
for(int i = 0; i < s.length(); i++) {
  if(s.charAt(i)) 
    o_count++;
}
```
