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
