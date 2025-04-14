# Java 17

## Introduction to Java

<!-- ### Java Language origin and use cases. -->
<!-- ### Java portability and provider neutrality -->
<!-- ### OOPS concept -->
<!-- ### Java syntax and coding conventions -->
<!-- ### Java class with main method -->
<!-- ### Compile and execute java applications -->

### Java Editions

- Java Card: Smart Card Edition
- Java ME: Micro Edition
- Java SE: Standard Edition
- Java MP: Micro Profile
- Jakarta EE: (Java EE) Enterprise Edition
- Java SE is the base edition on which other editions are based.

### Object Oriented Principles

- Abstraction:
  The software objects represents a subset of behaviors
  and information of the real-world objects.

- Encapsulation:
  The software objects hides its implementation details and internal state.

- Inheritance:
  A specialized type (child) inherits code from the more general type (parent).

- Polymorphism:
  Objects of different types responds differently to the same message.

### Introduction to Classes and Objects

Class and object are two key object-oriented concepts.

- Java code is structured with classes.
- Class represents a type of thing or a concept, such as: Dog, Cat, Ball, Person.
- Class is an abstraction of real-world thing or concept.
- An object is a specific instance (example of) a class.

```java
class Person {
  void play() {
    Dog dog = new Dog();
    dog.name = "Rex";
    Ball ball = new Ball();
    dog.fetch(ball);
  }
}
```

```java
class Dog {
  String name;
  fetch(Ball ball) {
    ball.find();
    ball.chew();
  }
}
```

#### Classes

- Each class defines what kind of information (attributes) it can store:

  - A Dog could have a name, color, size.
  - A Ball would have type, material, and so on.

- Each class defines what kind of behaviors(operations) it is capable of.
- Operations implement program logic(algorithms):
  - A Dog could bark and fetch a Ball.
  - A Cat could meow but is not likely to play fetch.

#### Objects

- Each object would be capable of having specific values for each attribute
  defined by a class that represents its type.
- Examples
  - A dog could be called Fido, and be brown and small.
  - Another could be called Rex, and be orange and big.
- To operate on an object,
  you can reference it by using a variable of a relevant type.
- Each object would be capable of behaviors defined by a class
  that represents its type:
  - At runtime, objects invoke operations upon each other to execute program logic.

#### Inheritance

You can reuse (inherit) at attributes and behaviors across class hierarchy.

- Classes an form hierarchical relationships.
- Superclass represents a more generic parent type (living organism).
- Superclass define common attributes and behaviors (eat, propagate).
- A subclass represents a more specific child type (animal, plant, and so on).
- There could be any number of levels in the hierarchy,
  from very generic to very specific child types.
- Subclasses inherit all attributes and behaviors from their parent.
- Subclasses can define more specific attributes and behaviors (swim, fly).

```java
class Animal extends LivingOrganism {
  // generic attributes and behaviors
}
```

```java
class Dog extends Animal {
  // specific attributes and behaviors
}
```

#### Java APIs

Java Development Kit (JDK) provides hundreds of classes for various programming purposes:

- To represent basic data types,
  for example, `String`, `LocalDateTime`, `BigDecimal` and so on.
- To manipulate collections,
  for example, `Enumeration`, `ArrayList`, `HashMap` and so on.
- To handle generic behaviors and perform system actions,
  for example, `System`, `Object`, `Class` and so on.
- To perform input/output (I/O) operations,
  for example `FileInputStream`, `FileOutputStream`, and so on.

Many other API classes are used to access databases, manage concurrency,
enable network communications, execute scripts, manage transactions,
security and logging, build graphical user interfaces, and so on.

> Application Programming Interface (API) is a term that describes a collection of classes that are designed to serve a common purpose.
> All Java APIs are thoroughly documented for each version of the language.
> Java SE documentation can be found [here](https://docs.oracle.com/en/java/javase/index.html)

[Java Documentation](https://docs.oracle.com/en/java/javase/index.html)

### Java Keywords, Reserved Words, and Special Identifiers

#### Since 1.0

- `if`
- `else`
- `continue`
- `break`
- `for`
- `do`
- `while`
- `switch`
- `case`
- `default`
- `private`
- `protected`
- `public`
- `import`
- `package`
- `abstract`
- `implements`
- `extends`
- `interface`
- `class`
- `static`
- `final`
- `return`
- `transient`
- `void`
- `byte`
- `short`
- `int`
- `long`
- `char`
- `float`
- `double`
- `boolean`
- `try`
- `catch`
- `finally`
- `throw`
- `throws`
- `new`
- `this`
- `super`
- `instanceof`
- `native`
- `synchronized`
- `volatile`
- `true`
- `false`
- `null`

#### Added later

- `enum`
- `module`
- `requires`
- `transitive`
- `exports to`
- `uses`
- `provides with`
- `open to`
- `open`
- `var`
- `permits`
- `records`
- `sealed`
- `non-sealed`
- `yield`
- `assert`

#### Reserved or not in use

- `goto`
- `const`
- `strictfp`

#### Notes

- Keywords and literal cannot be used as identifiers (names of classes, variables, methods, and so on).

### Java Naming Conventions

- Java is case-sensitive; `Dog` is not the same as `dog`.
- Package name is a reverse of your company domain name, plus the naming system adopted within your company.
- Class name should be a noun, in mixed case with the first letter of each word capitalized.
- Variable name should be in mixed case starting with a lowercase letter; further words start with capital letters.
- Names should not start with numeric characters (0-9), underscore (\_) or dollar ($) symbols.
- Constant name is typically written in uppercase with underscore symbols between words.
- Method name should be a verb, in mixed case starting with a lowercase letter; further words start with capital letters.

- correct way

```yaml
package: com.oracle.demos.animals
class: ShepherdDog
variable: shepherdDog
constant: MIN_SIZE
method: giveMePaw
```

- incorrect way

```yaml
package: animals
class: Shepherd Dog
variable: _price
constant: minSize
method: xyz
```

> The use of the \_ symbol as a first or only character in a variable name produces a compiler warning in Java 8 and an error in Java 9 onwards.

### Java Basic Syntax Rules

- All Java statements must be terminated with the ";" symbol.
- Code blocks must be enclosed with "{" and "}" symbols.
- Indentations and spaces help readability, but are syntactically irrelevant.

```java
package com.oracle.demos.animals;
class Dog {
  void fetch(){
    while (ball == null) {
      keepLooking();
    }
  }
  void makeNoise() {
    if (ball != null){
      dropBall();
    } else {
      bark();
    }
  }
}
```

### Defining a Java Class

- Class name is typically represented by one or more nouns; `Dog`, `GreatCat`.
- Class must be saved into a file with the same name and the `.java` extension.
- Classes are grouped into packages, represented as folders where class files are saved.
- Package name is typically a reverse of your company domain name, plus a naming system adopted within your company: `com.oracle.demos`, `org.acme.something`.
- Package and class name must form a unique combination.

> If package definition is missing, class would belong to a "default" package and would not be placed into any package folder. However, this is not a recommended practice.

### Accessing Classes Across Packages

To access a class in another package, do one of the followig:

- Prefix the class name with the package name.
- Use the import statement to import specific classes or the entire package content.
  - The import of al classes from the `java.lang.*` package is implicitly assumed.

> Imports are not present in a complied code. An import statement has no effect on the runtime efficiency of the class. It is a simple convenience to avoid prefixing class name with package name throughout your source code.

### Implementing Encapsulation with Access Modifiers

Access modifiers describe the visibility of classes, variables, and methods.

- `public`: Visible to any other class.
- `protected`: Visible to classes that are in the same package or to subclasses.
- no access modifier (`default`): Visible only to classes in the same package
- `private`: Visible only within same class

> Any non private parts of your class should be kept as stable as possible, because changes to such code may adversely affect several other classes that may be using your code.

### Creating a Main Application Class

The main method is the entry point into your application.

- It is the starting point of program execution
- the method must be called `main`.
- It must be `public`. You intend to invoke this method from outside this class.
- It must be `static`. Such methods can be invoked without creating an instance of this class.
- It must be `void`. It does not return a value.
- It must accept array of String objects as the only parameter.
  (The name of this parameter "`args`" is irrelevant.)

```java
package demos;
public class Whatever {
  public static void main(String[] args) {
    // program execution starts here
  }
}
```

### Compiling a Java Program

Compile classes with the `javac` Java compiler.

- the `-classpath` or `-cp` parameter points to location of other classes that my be required to compile your code.
- The `-d` parameter points to a path to store the compilation result.
  (The compiler creates package subfolder with compiled class files in this path.)
- Provide path to source code.

```bash
javac -cp "/project/classes" -d "/project/classes" "/project/sources/demos/Whatever.java"
# will create "/project/classes/demos/Whatever.class"
```

### Executing a Java Program

Execute a program using the `java` executable Java Virtual Machine (JVM).

- Specify `-classpath` or `-cp` to point to folders where your classes are located.
- Specify fully qualified class name. Use a package prefix; do nt use the `.class` extension.
- Provide a space-separated list of parameters after the class name.

Access command-line parameters:

- Use an array object to access parameters.
- Array index starts at 0 (first parameter).

```java
package demos;
public class Whatever {
  public static void main(String[] args) {
    String param1 = args[1];
    System.out.println("Hello " + param1);
  }
}
```

```bash
java -cp /project/classes demos.Whatever Jo John "A Name" Jane
# Hello John
```

> Since Java 11, it is also possible to run signle-file source code as if it is a compiled class. JVM will interpret you code, but no compiled class file would be created.
>
> ```bash
> java /project/sources/demos/Whatever.java
> ```

### Comments and Documentation

- Code Comments can be placed anywhere in your source code.
- Documentation Comments:
  - May contain HTML markups
  - May contain descriptive tags prefixed with the @ sign
  - Are used by the Javadoc tool to generate documentation

```java
// single-line comment
/*
Multi line comment
*/
/**
* the {@code Whatever} class represents and example of documentation comment
* @version 1.0
* @author oracle
*/
```

```bash
javadoc -d <documentation path> -sourcepath <source code path> -subpackages <name of the root package>
```

> All APIs in the JDK are documented using the Javadoc utility.

## Primitive types, Operator, and Flow Control Statement o

### Java Primitive Types

Java provides eight primitive types to represent simple numeric, character, and Boolean values.

#### Whole Numbers

| type  | Bits | min                  | max                 |
| ----- | ---- | -------------------- | ------------------- |
| byte  | 8    | -128                 | 127                 |
| short | 16   | -32768               | 32767               |
| int   | 32   | -2147483648          | 2147483647          |
| long  | 64   | -9223372036854780000 | 9223372036854780000 |

- default value 0 or 0L
- binary 0b1001
- octal O72
- decimal 1234
- Hex 0x4f
- Upper of Lowercase L at the end indicates long value.

#### Floating Point Numbers

| type   | Bits | min      | max                      |
| ------ | ---- | -------- | ------------------------ |
| float  | 32   | 1.4E-45  | 3.4028235E+38            |
| double | 64   | 4.9E-324 | 1.79769311348623157E+308 |

- default value 0.0F or 0.0
- Normal 123.4 or exponential notations 1.234E2
- Upper or lower case F at the end indicates float value

#### Boolean

| type    | value      |
| ------- | ---------- |
| boolean | true/false |

- default value false

#### Character (represents a single character value)

| type | bits    | min | max    |
| ---- | ------- | --- | ------ |
| char | 16 bits | 0   | 65,535 |

- default value `\u0000`
- Character 'A' ASCII code '\101' Unicode '\u0041' Excase sequences: tab '\t' backspace '\b' new line '\n' carriage return '\r' form feed '\f' single quote '\'' double quote '\"' backslash '\\'

## Text, Date, Time, and Numeric Objects

## Classes and Objects

## Improved Class Design

## Implement Inheritance and Use Records

## Interfaces and Generics

## Arrays and Loops

## Collections

## Nested Classes and Lambda Expressions

## Java Streams API

## Exception Handling, Logging, and Debugging

## Java I/O API

## Java Concurrency and Multithreading

## Modules and Deployment

## Appendix A: Annotations

## Appendix B: Java Database Connectivity

## Appendix C: Java Security

## Appendix D: Advanced Generics

## Appendix E: Java Applications on Oracle Cloud

## Appendix F: Miscellaneous Java Topic
