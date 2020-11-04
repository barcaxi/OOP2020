---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 5  
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---
@title[Week 5 Notes]
### Week 5 Notes

Read [Java Inheritance](https://github.com/barcaxi/OOP2020/blob/master/notes/Inheritance.md) at GitHub

---
@title[Week 5 Videos]
### Week 5 Videos


Watch **Java Inheritance** on BB


---
@title[Java OOP Concepts]
### Java OOP Concepts


![OOP](/images/apieI.png)

---
@title[Java OOP Concepts]
### Java OOP Concepts

@ol[list-bullets-black](false)
- **Inheritance**
- Abstraction
- Encapsulation
- Polymorphism
@olend

Let's describe @size[1.5em](Inheritance)...

---?image=/images/inheritance1.png&size=auto 50%&position=right
@title[Inheritance]
### Inheritance


With @size[1.5em](classification) we achieve:

@ul[list-bullets-black](true)
- Structure
- Specialism
- @size[1.5em](Inheritance) of
  - characteristics
  - behaviour
@ulend


---
@title[Java Inheritance]
### Java Inheritance

See [All Java Classes](https://docs.oracle.com/javase/10/docs/api/allclasses-noframe.html) in API. All Classes in Java need:

@ul[list-bullets-black](true)
- Structure
- Specialism
- Inheritance occurs when sub-classes inherit variables and methods of parent classes
@ulend

---
@title[Integer class]
### Integer class

See [Integer](https://docs.oracle.com/javase/10/docs/api/java/lang/Integer.html) class.  Notice the:

@ul[list-bullets-black](true)
- Structure - ``Object> Number> Integer``
- Specialism - Integer is as specialism of ``Number``
- Inheritance - inherits methods from ``Object`` class
@ulend

---?image=/images/animal_cat_dog2.png&size=auto
@title[Inheritance Code Example]
### Inheritance Code Example

---
@title[Animal Class]

```java
public class Animal {
  private int age;

  public Animal() {
    age = 0;
  }
  public void eat() {
    println("munch munch munch!");
  }
  public void sleep() {
    println("zzzzzzzzzzzzzzzzz!")
  }
  public void setAge(int age) {
    this.age=age;
  }
  public int getAge() {
    return age;
  }
}
```
@[1](class name)
@[1,2](class variable)
@[1,2,4-6](class default constructor)
@[1,2,4-6,7-18](class methods)
@[*]

---
@title[Cat Class]
### Cat Class

```java
public class Cat extends Animal
{
  public Cat() {
  }
  public void meow() {
    println("meow!");
  }
}
```
@ul[list-bullets-black](true)
- @size[1.5em](extends) implements inheritance
- A ``Cat`` **is-a** ``Animal``
- ``Cat`` inherits variable age and methods ``eat()``, ``sleep()``, ``setAge()``, ``getAge()`` from ``Animal``
- ``Cat`` has its own specialist method ``meow()``
@ulend

---
@title[Dog Class]
### Dog Class

```java
public class Dog extends Animal
{
  public Dog() {
  }
  public void bark() {
    println("woof!");
  }
}
```
@ul[list-bullets-black](true)
- @size[1.5em](extends) implements inheritance
- A ``Dog`` **is-a** ``Animal``
- ``Dog`` inherits variable age and methods ``eat()``, ``sleep()``, ``setAge()``, ``getAge()`` from ``Animal``
- ``Dog`` has its own specialist method ``bark()``
@ulend

---
@title[Use the Classes]
### Use the Classes

```java
Dog dog = new Dog();
dog.setAge(12);
println("age="+dog.getAge());
dog.bark();
dog.eat();
```

prints:

```
age=12
woof!
munch munch munch!
```
@[1](create a dog object)
@[1,2](set dog age)
@[1,2,3,6](print dog age)
@[1,2,3,4,7](call Dog method bark())
@[1,2,3,4,5,8](call Animal method eat() - inherited from Animal)

---
@title[Java Inheritance]
### Java Inheritance

New concepts and keywords emerge like:

@ul[list-bullets-black](true)
- super class (parent class)
- sub-class
- ``extends`` keyword
- ``super()`` keyword
- method overriding
- ``@Override`` annotation
- method overloading
- ``Object`` class
- access modifiers
@ulend

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 5  
Lecture 2
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[super statement]
### super statement

@ul[list-bullets-black](true)
- The ``super`` statement is used when referring to @size[1.5em](parent class methods)
- It can be used by a sub-class to call a constructor in the parent class
- For example...
@ulend


---
@title[Animal Class]

```java
public class Animal {
  private int age;

  public Animal(int age) {
    this.age = age;
  }
  public int getAge() {
    return age;
  }
}
```
@[1,10](Animal class)
@[1,10,2](Animal has-a age class variable)
@[1,10,2,4-6](a constructor to intialise its variables)
@[1,10,2,4-6,7-9](a method to get age)

---
@title[Dog Class]

```java
public class Dog extends Animal {
  private String breed;

  public Dog(String breed, int age) {
    super(age);
    this.breed=breed;
  }
}

Dog dog = new Dog("Labrador",5);
```
@[1,8](Dog is-a subclass of Animal.)
@[1,2,8,4,6,7,10](Dog has a constructor to intialise its variables)
@[1,2,8,4,5,6,7,10](We can call Animal constructor and pass age value to it)

@ul[list-bullets-black](true)
- ``super`` must be @size[1.5em](first) statement in block 
- in this code we @size[1.5em](explicitly) called the parent constructor
- they can be @size[1.5em](implicitly) called too...
@ulend


---
```java
public class Animal {
  public Animal() {
    println("in Animal()");
  }
}
public class Dog extends Animal {
  public Dog() {
    println("in Dog()");
  }
}
Dog dog = new Dog();
```
@[1-5](Animal)
@[1-5,6-10](Dog)
@[1-5,6-10,11](Create a dog object)

@ul[list-bullets-black](true)
- Q. What does Java print here? 
@ulend

---
```java
public class Animal {
  public Animal() {
    println("in Animal()");
  }
}
public class Dog extends Animal {
  public Dog() {
    println("in Dog()");
  }
}
Dog dog = new Dog();
```

@ul[list-bullets-black](false)
- Q. What does Java print here? 
@ulend
```
in Animal()
in Dog()
```

---
```java
public class Animal {
  public Animal() {
    println("in Animal()");
  }
}
public class Dog extends Animal {
  public Dog() {
    super();   
    println("in Dog()");
  }
}
Dog dog = new Dog();
```
@[8](super() added implicitly by compiler if you don't)
@[*]

---
@title[Method Overriding]
### Method Overriding

@quote[When a method in a subclass has the exact same signature as a method in a superclass its called method overriding]

@ul[list-bullets-black](true)
- For example...
@ulend

---
@title[Method Overriding]
### Method Overriding

```java
public class Shape {
  private int x;
  private int y;

  public Shape(int x, int y) {
    this.x=x;
    this.y=y;
  }
  public void display() {
    point(x, y);
  }
  ...
}
```

We have a ``Shape`` class with ``display()`` method 

---
@title[Method Overriding]
### Method Overriding

```java
public class Circle extends Shape {
  int radius;

  public Circle(int x, int y, int radius) {
    super(x, y);
    this.radius=radius;
  }
  public void display() {
    ellipse(super.getX(), super.getY(), radius, radius);
  }
}
```
@[1,11](Circle is-a Shape)
@[1,11,2](has a radius variable)
@[1,11,2,4-7](has a constructor)
@[1,11,2,4-7,8-10](Overrides display() method)

@ul[list-bullets-black](true)
- ``display()`` is @size[1.5em](overridden) because to display a circle we need to use @size[1.5em](specific) code
@ulend

---
@title[Method Overriding]
### Method Overriding

@ul[list-bullets-black](true)
- ``toString()`` method is an overridden method
- Inherited from [Object](https://docs.oracle.com/javase/10/docs/api/java/lang/Object.html) class
- You should add it to ALL your classes
@ulend


---
@title[@Override annotation]
### @Override annotation

```java
public class Shape {
  ...
  @Override
  public void toString() {
  }
}
```

@ul[list-bullets-black](true)
- ``@Override`` is an annotation that is written above an overridden method
- It gets compiler to check super classes for a match
- It's optional
- It's useful to check for typos and good coding practice
@ulend

---

More next week...

to be continued...


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 5
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
