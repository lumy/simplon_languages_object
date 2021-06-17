# java (yuk)

https://www.w3schools.com/java/java_getstarted.asp

## entrypoint

Unlike Python and like a lot of language, the entrypoint is fixed, which mean your programme will
ALWAYS start with the same function:

```java
public class Main {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
```

Java will always be looking for a `public class` named `Main` with a `public static` method named
`main`.

## Type

Java is strongly typed. Which mean we have to tell which type is every variable.

```java
String str = "This is a string";
int number = 1234;
float fl = 123.321;
char myLetter = 'D';
boolean myBool = true;
```

Most of typed language let you dynamically change the type of a variable !*It is dangerous to do
that if you don't know what you're doing*!

```java
double myDouble = 9.78;
int myInt = (int) myDouble; // Manual casting: double to int

System.out.println(myDouble);   // Outputs 9.78
System.out.println(myInt);      // Outputs 9
```


## Operator

like Python you can do `i += 1` but you can do `i++` or `i = i + 1` (same for `-=` and `--`)

## Switch

Unlike python, Java implement the switch operator:

```java
string y = "toto";
switch(expression) {
  case "my-sentences":
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

`break` is really important !

# Methods

In java, everything is an object, so you won't find any functions, only methods:

```java
public class Main {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
  }
}

// Outputs "I just got executed!"
```

# Methods overloading

Java is strongly typed, which enable the language to look for you the right methods to use (by
looking at the parameters given).

```java
static int plusMethod(int x, int y) {
  return x + y;
}

static double plusMethod(double x, double y) {
  return x + y;
}

public static void main(String[] args) {
  int myNum1 = plusMethod(8, 5);
  double myNum2 = plusMethod(4.3, 6.26);
  System.out.println("int: " + myNum1);
  System.out.println("double: " + myNum2);
}
```


## POO in java

You should read this and all section about the OOP in java.
Teacher will be available to answer all your question ONCE you have read these.
https://www.w3schools.com/java/java_oop.asp

### Class and instances

```java

public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```

You declare a new class with the keyword `class` and a new instances with the keyword `new`.

### Constructor

Look at constructor by yourself it is not very complicated.


### Modifier and Encapsulation

```java
public class Person {
  private String name; // private = restricted access

  private String toLowerString(String newName) {
    return newName.toLowerCase()
  }
  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = this.toLowerString(newName);
  }
}

public class Main {
  public static void main() {
    Person p = new Person();
    p.setName("Toto");
    p.getName(); // return "toto"
    p.toLowerString(); // error can not access this methods !
  }
}
```

The methods `toLowerString` is a private methods which can only be called inside the class context.
the methods `getName` and `setName` are public and can be called from outside the class.

## Inheritance

Unlike python, were everything is public, it is not the case here, So inheritance is more developped
with new concept. (you should discover `protected` and the `polymorphism`)


## Abstraction and interface.

Like python you can declare abstract class (Way more easily) and interfaces (new concept !)

An Abstract class could be easily implemented like this:

``` java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}
```

When an interface is implemented like this:
```java
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}


// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}
```

The difference can seems obselete and you might wanna use Abstract everytime but you should not.
Abstract are to declare common trait to object.

An example of interface and abstract together.


```java
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

abstract class Mammal implements Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

abstract class Insect implements Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}


// Pig "implements" the Animal interface
class Pig extends Mammal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}
```

Here that you manipulate an insect, a Mammal or a Pig they can all be manipulated as an Animal
object (the interfaces).

In a video game, everything that should be printed would answer to an GraphicRessources Interface,
behind it can be the player, an png, an object. You just know that it will be printed with a methods `printToScreen`.

## And now

It is mostly new design pattern that you will learn and discover.
Java offer some nice design and poor design. As all languages it has his pros and cons.
Good Luck !
