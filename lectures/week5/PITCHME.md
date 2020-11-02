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


---


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
