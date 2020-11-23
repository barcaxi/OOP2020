---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 8
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 8 Notes]
### Week 8 Notes

Read [Abstract Classes](https://github.com/barcaxi/OOP2020/blob/master/notes/AbstractClasses.md) at GitHub

---
@title[Week 8 Videos]
### Week 8 Videos

Watch **Abstract Class** Videos at BB

---
@title[Week 8 Notes]
### Week 8 Tutorial

Do [Tutorial #7](https://github.com/barcaxi/OOP2020/blob/master/tutorials/Tutorial7.md) at GitHub


---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- **Abstract Classes**
- Review of Assignment #2
@olend

---
@title[Abstract Classes]
### Abstract Classes

@ul[list-bullets-black](true)
- An abstract class is an @size[1.5em](incomplete class)
- It will declare methods that have @size[1.5em](no code)
- It @size[1.5em](forces) it's @size[1.5em](subclasses) to implement these methods...
@ulend

---
@title[Abstract Classes]
### Abstract Classes

@ul[list-bullets-black](true)
- An abstract class cannot be @size[1.5em](instantiated)
- A subclass that extends an abstract class can be instantiated
- The keyword ``abstract`` is used to declare abstract classes and methods
- An example...
@ulend


---

```java
public abstract class Shape {
  private int x;
  private int y;

  public Shape (int x, int y) {
    this.x=x;
    this.y=y;
  }
  public int getX() { return x; }
  public int getY() { return y; }
  public abstract double getArea();
  public abstract void display();
  public abstract boolean intersect(int x, int y);
}
```
@[1,14](Shape is an abstract class.)
@[1,14](Shape is an abstract class. Why?)
@[1,14,11-13](Because it has abstract methods.)
@[1,14,5-10](It has normal methods too.)
@[*]()

@ul[list-bullets-black](true)
- To understand abstract classes let's look at an example...
@ulend

---?image=/images/ShapeCircleSquare3.png&size=auto 65%&position=bottom&color=#FFFFFF
@title[Abstract Classes]
### Abstract Classes

We've seen the superclass ``Shape`` and subclasses ``Circle`` and ``Square``

---?image=/images/ShapeCircleSquare3.png&size=auto 65%&position=bottom&color=#FFFFFF
@title[Abstract Classes]
### Abstract Classes
All of these classes have certain variables and methods in common:
@ul[list-bullets-black](true)
- ``x`` and ``y``
- ``getX()`` & ``getY()``
- ``setX()`` & ``setY()``
- ``display()``
- ``getArea()``
- ``intersect()``
@ulend

---?image=/images/ShapeCircleSquare3.png&size=auto 65%&position=bottom&color=#FFFFFF
@title[Abstract Classes]
### Abstract Classes
Some of these methods are implemented in the superclass ``Shape``:
@ul[list-bullets-black](true)
- ``getX()`` & ``getY()``
- ``setX()`` & ``setY()``
- For example...
@ulend


---

```java
public abstract class Shape {
  private int x;
  private int y;
  ...
  public int getX(){
    return x;
  }
  public void setX(int x){
    this.x=x;
  }
  public int getY(){
    return y;
  }
  public void setY(int y){
    this.x=x;
  }
}
```
@[1,18](Shape is an abstract class.)
@[1,18,5-16](normal methods)
@[*]()

---?image=/images/ShapeCircleSquare3.png&size=auto 65%&position=bottom&color=#FFFFFF
@title[Abstract Classes]
### Abstract Classes
Others methods are specific and need implementing in the subclasses:
@ul[list-bullets-black](true)
- ``display()``
- ``getArea()``
- ``intersect()``
- e.g. ``display()``...
@ulend

---
```java
public class Circle extends Shape {
  ...
  @Override
  public void display(){
    ellipse(getX(), getY(), 100, 100);
  }
  ...
}
public class Square extends Shape {
  ...
  @Override
  public void display(){
    rect(getX(), getY(), 100, 100);
  }
  ...
}
```
@[1,8](Circle class)
@[1,8,3-6](implements abstract method display)
@[9,16](Square class)
@[9,16,11-14](implements abstract method display)
@[*]()

@ul[list-bullets-black](true)
- ``display()`` has a specific implementation that was overriden for each subclass
@ulend

---
@title[Abstract Classes]
### Abstract Classes

```java
public class Shape {
  ...
  public void display() {
    // We cannot display a generic shape
    // The subclass will implements this (hopefully)
  }
  ...
}
```
@ul[list-bullets-black](true)
- Previously, in ``Shape``, the method ``display()`` was implemented like above
- It doesn't do anything
- It doesn't know what shape it is!
@ulend


---
@title[Abstract Classes]
### Abstract Classes

```java
public class Shape {
  ...
  public void display() {
    // We cannot display a generic shape
    // The subclass will implements this (hopefully)
  }
  ...
}
```

You should not allow someone to create a ``Shape`` object and use it like this:
```java
Shape shape = new Shape();
shape.display();  // displays nothing!!!!!
```

@ul[list-bullets-black](true)
- Solution...
@ulend

---
@title[Abstract Classes]
### Abstract Classes

Make the class and method @size[1.5em](abstract)

```java
public abstract class Shape {
  ...
  public abstract void display();
  ...
}
```
@[1,5](class is now abstract)
@[1,5,3](method display is now abstract)
@[*]()

@ul[list-bullets-black](true)
- A ``Shape`` class cannot be instantiated now
<!-- - Only a subclass that implements ``display()`` method -->
- We are @size[1.5em](forcing) a subclass to override and implement ``display()``...
@ulend

---
@title[Abstract Classes]
### Abstract Classes

Latest version of ``Shape``

```java
public abstract class Shape {
  private int x;
  private int y;

  public Shape (int x, int y) {
    this.x=x;
    this.y=y;
  }
  public int getX() { return x; }
  public int getY() { return y; }
  public abstract double getArea();
  public abstract void display();
  public abstract boolean intersect(int x, int y);
}
```


---
@title[Abstract Classes]
### Abstract Classes

Features of abstract classes:

@ul[list-bullets-black](true)
- The keyword abstract tells the compiler this class/method is incomplete
- It needs to be extended to be useful
- An abstract method has no body
- An abstract method forces a subclass to override it and implement it
@ulend


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 8
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
