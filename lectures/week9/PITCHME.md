---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 9
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 9 Notes]
### Week 9 Notes

Read [Interfaces](https://github.com/barcaxi/OOP2020/blob/master/notes/Interfaces.md) at GitHub

---
@title[Week 9 Videos]
### Week 9 Videos

See BlackBoard

---
@title[Week 9 Notes]
### Week 9 Tutorial

Do [Tutorial #8](https://github.com/barcaxi/OOP2020/blob/master/tutorials/Tutorial8.md) at GitHub




---
@title[Interfaces]
### Interfaces

@ul[list-bullets-black](true)
- Interfaces are important to and widely used in Java
- You can use existing interfaces or write your own
- Let's see how to use an existing Java interface ...
@ulend



---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- **Comparable Interface**
- `Comparator` Interface

@olend

---
@title[Interfaces]


@size[1.5em](Comparable) interface


@ul[list-bullets-black](true)
- [Comparable](https://docs.oracle.com/javase/7/docs/api/java/lang/Comparable.html) allows you to @size[1.5em](order) objects into their @size[1.5em](natural order)
- For example:
  - strings ordered alphabetically
  - bank accounts ordered by balance
  - students ordered by grades
- The code for the ``Comparable`` interface looks something like this...
@ulend

---
### Interfaces

```java
public interface Comparable<T>
{
  public int compareTo(T obj);
}
```
That's it!

---
### Interfaces

```java
public interface Comparable<T>
{
  public int compareTo(T obj);
}
```

@ul[list-bullets-black](true)
- the ``interface`` keyword indicates that this is an interface
- ``Comparable`` is the name of this interface
- it has just one method - ``compareTo()``
- ``compareTo()`` gets an object (T) variable and returns an ``int``...

@ulend

---
### Interfaces

```java
public interface Comparable<T>
{
  public int compareTo(T obj);
}
```

@ul[list-bullets-black](true)
- the code for ``compareTo()`` is not implemented in the interface
- the code for ``compareTo()`` is written in a class that @size[1.5em](uses) the interface
- All interface methods are abstract like this
@ulend

@ul[list-bullets-black](true)
- Ok. Why is ``Comparable`` useful?
@ulend

---
### Interfaces

@ul[list-bullets-black](true)
- Earlier, we mentioned strings can be ordered alphabetically
- Here are some strings:
  - ``[Mary, Bob, Alice]``
- Order them alphabetically!
  - ``[Alice, Bob, Mary]``
- You ordered them by @size[1.5em](comparing) them to each other!
- That's what the interface ``Comaparable`` does for you
@ulend

---
### Interfaces

@quote[If you want to order any objects in Java make them implement the Comparable interface]

@ul[list-bullets-black](true)
- An example...
@ulend

---
### Interfaces

A simple ``Person`` class

```java
public class Person
{
  private String name;
  private int age;

  ...
}
```

and we want to order ``Person`` objects by age...

---
### Interfaces

```java
public class Person implements Comparable
{
  private String name;
  private int age;

  public int compareTo(Person obj)
  {
    // compare by age
  }
}
```
@[1](implement Comparable)
@[6-9](write compareTo() method)
@[*]

@ul[list-bullets-black](true)
- ``Person`` class @size[1.5](implements) the ``Comparable`` interface
- must add ``compareTo()`` method to class
- we'll see code soon
- another example...
@ulend


---
### Interfaces

A simple ``Circle`` class

```java
public class Circle
{
  private int radius;

  ...
}
```
and we want to order ``Circle`` objects by radius...

---
### Interfaces

```java
public class Circle implements Comparable
{
  private int radius;
  ...

  public int compareTo(Circle obj)
  {
    // compare by radius
  }
}
```
@[1](implement Comparable)
@[6-9](write compareTo() method)
@[*]

@ul[list-bullets-black](true)
- ``Circle`` class @size[1.5](implements) the ``Comparable`` interface
- must add ``compareTo()`` method to class
- we'll see code soon
@ulend


---
### Interfaces

Let's see how the [String](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html) class already @size[1.5em](implements) the ``Comparable`` interface...


---

```java
public class String implements Comparable
{
  ...
  public int compareTo(String obj)
  {
    if(this.value < obj.value)
      return -1;                // negative integer
    if(this.value > obj.value)
      return 1;                 // positive integer
    return 0;
  }
}
```
@[1](implement Comparable)
@[1,4-5,11](write compareTo() method)
@[1,4-5,11,6-7](if this string is less than other string)
@[1,4-5,11,6-7,8-9](if this string is greater than other string)
@[1,4-5,11,6-7,8-9,10](if strings are equal)
@[*]

@ul[list-bullets-black](true)
- ``compareTo()`` compares current string (``this``) to another string (``obj``)
- ``compareTo()`` returns either negative integer, zero, or a positive integer
- How is this useful?
@ulend


---
### Interfaces

We can do this:

```java
import java.util.*;

ArrayList<String> list = new ArrayList<String>();
list.add(new String("Mary"));
list.add(new String("Bob"));
list.add(new String("Alice"));

Collections.sort(list);  
```
@ul[list-bullets-black](true)
- ``list`` is sorted - ``[Alice, Bob, Mary]``
- The ``sort()`` method depends on the objects being sorted having implemented the ``Comparable`` interface
- You can do the same for your objects...
@ulend

---
### Interfaces

We can do this:

```java
import java.util.*;

ArrayList<Circle> list = new ArrayList<Circle>();
list.add(new Circle(10));
list.add(new Circle(50));
list.add(new Circle(30));

Collections.sort(list); 
```

@ul[list-bullets-black](false)
- ``list`` is sorted - ``[Circle r=10, Circle r=30, Circle r=50]``
- Because you implemented ``Comparable`` interface...
@ulend


---
### Interfaces

```java
public class Circle implements Comparable {
  private int radius;

  public int compareTo(Circle obj)
  {
    if(this.radius < obj.radius)
      return -1;
    if(this.radius > obj.radius)
      return 1;
    return 0;
  }
}
```
@[1](implement Comparable)
@[1,4-5,11](write compareTo() method)
@[1,4-5,11,6-7](if this circle radius is less than other circle radius)
@[1,4-5,11,6-7,8-9](if this circle radius is greater than other circle radius)
@[1,4-5,11,6-7,8-9,10](if circle radius are equal)
@[*]



---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- `Comparable` Interface
- **Comparator Interface**

@olend

---
@title[Interfaces]


@size[1.5em](Comparator) interface

@quote[Use Comparator interface to provide an ordering for objects that don't have a natural ordering]
 
---

@size[1.5em](Comparator) interface

@ul[list-bullets-black](true)
- [Comparator](https://docs.oracle.com/javase/7/docs/api/java/util/Comparator.html) allows you to @size[1.5em](order) objects using any one or more object variable(s)
- For example:
  - order circles by x coordinate
  - order bank accounts by sort code and customer name
- The code for the ``Comparator`` interface looks something like this...
@ulend

---
### Interfaces

```java
public interface Comparator<T>
{
  public int compare(T obj1, T obj2);
  public boolean equals(Object obj);
}
```
That's it!

---
### Interfaces

```java
public interface Comparator<T>
{
  public int compare(T obj1, T obj2);
  public boolean equals(Object obj);
}
```

@ul[list-bullets-black](true)
- ``Comparator`` is the name of this interface
- it has two methods - ``compare()`` and ``equals()``
- ``compare()`` gets 2 object variable and returns an ``int``
- We'll not need to implement ``equals()`` - the one we inherit from ``Object`` will suffice

- Let's see it used in ``Circle``...
@ulend

---
```java
public class Circle implements Comparable {
  private int radius;

  public int compareTo(Circle obj)
  {
    if(this.radius < obj.radius)
      return -1;
    if(this.radius > obj.radius)
      return 1;
    return 0;
  }
}
```
@ul[list-bullets-black](true)
- We already sort circles by radius - their *natural order*
- Use ``Comparator`` to order circles by something else... 
@ulend

---
### Interfaces

```java
public class Circle implements Comparable
{
  private int radius;
  private int x,y;
  ...
}
```
@[4](Assume circle has ``x`` and ``y`` variables too)
@[*]

@ul[list-bullets-black](true)
- Let's allow us to sort circles by ``x`` variable too...
@ulend

---
### Interfaces
Write a comparator class for comparing x values:

```java
public class XComparator 
             implements java.util.Comparator<Circle>
{
  public int compare(Circle c1, Circle c2)
  {
    return c1.getX() - c2.getX();
  }
}
```
@[1,2,3,8](comparator class XComparator implements Comparator interface)
@[*](compare method compares one circle x value with another)
@[*](we return a negative integer, zero, or a positive integer if the x value of c1 is less than, equal to, or greater than the x value of c2)

@ul[list-bullets-black](true)
- We can now sort by circle object by x value...
@ulend

---
### Interfaces
```java
ArrayList<Circle> circles = new ArrayList<Circle>();
circles.add(new Circle(300, 100, 50));
circles.add(new Circle(100, 300, 50));
circles.add(new Circle(200, 200, 50));

java.util.Collections.sort(circles, new XComparator());

println("Sorted by X:"+circles);
```
@[1-4](our circle collection)
@[1-4,6](sort collection using XComparator)
@[1-4,6,8](print sorted collection...)

---
### Interfaces
```java
ArrayList<Circle> circles = new ArrayList<Circle>();
circles.add(new Circle(300, 100, 50));
circles.add(new Circle(100, 300, 50));
circles.add(new Circle(200, 200, 50));

java.util.Collections.sort(circles, new XComparator());

println("Sorted by X:"+circles);
```
prints
```
Sorted by X:
Circle[x=100,y=300,radius=50], 
Circle[x=200,y=200,radius=50], 
Circle[x=300,y=100,radius=50]
```

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 10
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[equals]
### equals() method

@ul[list-bullets-black](true)
- Previously, we mentioned all Java classes inherit from the ``Object`` class
- See [Object](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html?is-external=true) in JavaDoc
- Two notable important methods in ``Object`` are:
  - ``toString()``
  - ``equals()``
- Example of ``equals()``...
@ulend


---
@title[equals]
### equals() method

```java
String name1 = new String("tom");
String name2 = new String("mary");

if(name1.equals(name2))
  println("name1 equals name2");
```
@[1-2](objects name1 & name2)
@[1-2,4,5](if they are equal print name1 equals name2)
@[*]

@ul[list-bullets-black](true)
- the [String](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html) class inherits from ``Object`` and overrides ``equals()``
- the ``String`` class determines for itself if two string objects are equal
@ulend

---
@title[equals]
### equals() method

@quote[We should implement the equals() method for ALL our own classes too]

@ul[list-bullets-black](true)
- Like:
  - ``Circle``
  - ``Square``
  - ``Person``
- An example for ``Person`` class...
@ulend

---
@title[equals]
### equals() method

```java
public class Person {
  private String name;
  private int age;

  public Person(String name, int age) {
    this.name = name;
    this.age = age;
  }
}
```
@ul[list-bullets-black](true)
- An ``equals()`` method should compare all the class variables
- Thus ``name`` and ``age`` for ``Person`` class...
@ulend

---

```java
public class Person {
  private String name;
  private int age;

  public Person(String name, int age) {
    this.name = name;
    this.age = age;
  }
  @Override
  public boolean equals(Object obj) {
    if((this.name.equals(obj.name)) && (this.age==obj.age))
      return true;
    else
      return false;
  }
}
```
@[9,10,15](Override Object class equals() method)
@[9,10,15,11](if name & age are equal...)
@[9,10,15,11,12](return true...)
@[9,10,15,11,12,13,14](else return false)
@[*]()

@ul[list-bullets-black](true)
- Always use ``equals()`` to compare ``String`` objects
- Use ``==`` to compare primitive types
@ulend


---
@title[equals]

Code Sample 1

```java
Person person1 = new Person("tom",20);
Person person2 = new Person("tom",20);
if(person1.equals(person2))
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _equal_
@ulend

---
@title[equals]

Code Sample 2

```java
Person person1 = new Person("tom",20);
Person person2 = new Person("mary",20);
if(person1.equals(person2))
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _NOT equal_
@ulend

---
@title[equals]

Code Sample 3

```java
String name1 = new String("tom");
String name2 = new String("tom");
if(name1==name2)
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _NOT equal_
- the object references have different memory addresses for both ``String`` objects
@ulend


---
@title[equals]

Code Sample 4

```java
Person person1 = new Person("tom",20);
Person person2 = new Person("tom",20);
if(person1==person2)
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _NOT equal_
- the object references have different memory addresses for both ``Person`` objects
@ulend


---
@title[equals]

Code Sample 5

```java
Person person1 = new Person("tom",20);
person2=person1;
if(person1==person2)
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _equal_
- the object references have same memory address for ``Person`` object
@ulend

---

Let's say we had a class ``Animal``...
```java
public class Animal {

  private String name;
  private int age;

  public Animal(String name, int age) {
    this.name = name;
    this.age = age;
  }
  @Override
  public boolean equals(Object obj) {
    if((this.name.equals(obj.name)) && (this.age==obj.age))
      return true;
    else
      return false;
  }
}
```


---
@title[equals]

Code Sample 6

```java
Person person = new Person("michael",20);
Animal animal = new Animal("michael",20);
if(person.equals(animal))
  System.out.println("equal");
else
  System.out.println("NOT equal");
```
@ul[list-bullets-black](true)
- Prints?
- _equal_
- because the ``name`` and ``age`` variables are the same in both objects
- But a Person is not an Animal!!
- In ``equals()`` check the @size[1.5em](object type) too...
@ulend

---

```java
public class Person {
 private String name;
 private int age;
...

 @Override
 public boolean equals(Object obj) {
  Person p;
  if(obj instanceof Person)
   p = (Person)obj;
  else
   return false;

  if((this.name.equals(p.name))&&(this.age==p.age))
   return true;
  else
   return false;
 }
}
```
@[7,18]()
@[7,18,8-12](check the object to compare is a Person)
@[7,18,8-12,14-17](then check are variables equal)
@[*]()

---
@title[equals]
### equals() method 

Summary

@ul[list-bullets-black](true)
- All classes should have an ``equals()`` method
- Compare the class variables
- Check both object types are the same before comparing
@ulend

---
@title[contains]
### contains() method 

@ul[list-bullets-black](true)
- The [ArrayList](https://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html?is-external=true) class has a method ``contains()``
- It checks if a collection _contains_ an object
- It is used like this...
@ulend

---
@title[contains]
### contains() method 

```java
ArrayList<String> strings = new ArrayList<String>();
strings.add(new String("tom"));
strings.add(new String("paddy"));
strings.add(new String("joe"));

if(strings.contains(new String("tom")))
  System.out.println("tom found in arraylist");
```
@[1-4](the array list)
@[1-4,6-7](check if array contains string "tom")

@ul[list-bullets-black](true)
- ``contains()`` can only work if the object in the array list has an ``equals()`` method
- ``String`` has an ``equals()`` method
- You can use ``contains()`` for @size[1.5em](your classes) too...
@ulend

---
@title[contains]
### contains() method 

```java
ArrayList<Person> persons = new ArrayList<Person>();
persons.add(new Person("tom",20));
persons.add(new Person("paddy",21));
persons.add(new Person("joe",22));

if(persons.contains(new Person("tom",20)))
  System.out.println("tom found in arraylist");
```

@ul[list-bullets-black](true)
- ``Person`` has a ``equals()`` method
- and ``contains()`` will work for ``Person`` objects too
@ulend




---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 9 & 10
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
