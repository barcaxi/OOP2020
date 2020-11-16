---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 7
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 7 Notes]
### Week 7 Notes

Read [Polymorphism](https://github.com/barcaxi/OOP2020/blob/master/notes/Polymorphism.md) at GitHub

---
@title[Week 7 Videos]
### Week 7 Videos


Watch **Polymorphism** Videos at BB


---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- **Polymorphism**
- instanceof operator
- Casting
@olend

---
@title[Java OOP Concepts]
### Java OOP Concepts


![OOP](/images/apieP.png)

@ul[list-bullets-black](true)
- Polymorphism is  a key concept of OO Programming
- What is it?  
- Let's see using an example...
@ulend


---
@title[Polymorphism]
<!-- ### Polymorphism -->

![OOP](/images/ShapeCircleSquare2.png)

@ul[list-bullets-black](false)
-	``Circle`` and ``Square`` override ``display()`` ...
@ulend

---
@title[Polymorphism]




```java
public class Circle extends Shape
{
  public Circle(int x, int y, int radius)
  {
    super(x,y,radius); 
  }

  public void display()  // uses ellipse() to draw circles
  {
    ellipse(getX(), getY(), getRadius(), getRadius()); 
  }

}
```
@[8-11](display() specific to Circle)
@[*]()




---
@title[Polymorphism]


```java
public class Square extends Shape
{
  public Square(int x, int y, int length)
  {
    super(x,y,length);
  }

  public void display()  // uses rect() to draw circles
  {    
    rect(getX(), getY(), getLength(), getLength());
  }

}
```
@[8-11](display() specific to Square)
@[*]()

@ul[list-bullets-black](true)
- Let's display some shapes...
@ulend

---
@title[Polymorphism]
### Polymorphism

```java
ArrayList<Shape> shapes = new ArrayList<Shape>();

shapes.add(new Circle(100, 100, 10));
shapes.add(new Circle(200, 100, 10));
shapes.add(new Circle(300, 100, 10));

shapes.add(new Square(100, 200, 20));
shapes.add(new Square(100, 300, 20));

```
@[1](Create an arraylist for the shapes)
@[1-8](Add shapes to the arraylist)

---
@title[Polymorphism]
### Polymorphism

![OOP](/images/shapesArraylist.png)




---
@title[Polymorphism]

```java
ArrayList<Shape> shapes = new ArrayList<Shape>();

shapes.add(new Circle(100, 100, 10));
shapes.add(new Circle(200, 100, 10));
shapes.add(new Circle(300, 100, 10));
shapes.add(new Square(100, 200, 20));
shapes.add(new Square(100, 300, 20));

for(Shape shape : shapes)
{
  shape.display();
}

```
@[9-12](Display the shapes)
@[11](This is Polymorphism here!)


@ul[list-bullets-black](true)
- Explanation...
@ulend

---
@title[Polymorphism]
<!-- ### Polymorphism -->

![OOP](/images/shapesArraylist.png)

```java
for(Shape shape : shapes)
{
  shape.display();
}

```

@ul[list-bullets-black](true)
- We fetch each shape one-by-one
- Use the correct version of ``display()`` depending on shape's *type*
- That's **polymorphism**

@ulend




---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- Polymorphism
- **instanceof operator**
- Casting
@olend


---
@title[instanceof operator]
### instanceof operator

@ul[list-bullets-black](true)
- ``instanceof`` is a Java operator
- It compares an object to a specified type
- For example...
@ulend

---
@title[instanceof operator]
### instanceof operator


```java  
String name = new String("Mary");
if(name instanceof String)
  System.out.println("name is a String object");

Integer number = new Integer(100);
if(number instanceof Integer)
  System.out.println("num is a Integer object");
```
@[1-3](is name a String?)
@[5-7](is number a Integer?)


---
@title[Contents]
### Contents

@ol[list-bullets-black](false)
- Polymorphism
- instanceof operator
- **Casting**
@olend


---
@title[Casting]
### casting

@quote[Casting means taking a variable of one particular type and turning it into another type]

For example...

---
@title[Casting]
### casting

```java
float pi=3.14;
int i;

i=pi;     // Type mismatch, float does not match with int
```
@[4](Type mismatch)


@ul[list-bullets-black](true)
- Solution is to **cast**...
@ulend

---
@title[Casting]
### casting

```java
float pi=3.14;
int i;

i=(int)pi;  
```
@[4](Cast pi to a int)
@[*]

@ul[list-bullets-black](true)
- ``i`` is now 3
- Another example...
@ulend

---
@title[Casting]
### casting

```java
int diceValue = random(1,6); // Type mismatch
```
@[1](Type mismatch)

@ul[list-bullets-black](true)
- ``random(``) returns a ``float`` number
- Solution is to **cast**...
@ulend

---
@title[Casting]
### casting

```java
int diceValue = (int)random(1,6); 
```

@ul[list-bullets-black](true)
- Cast ``float`` value to an ``int``
- ``diceValue`` is now 1..6
@ulend

---?image=/images/ShapeCircleSquare2.png&size=auto 80%&position=bottom&color=#FFFFFF

@ul[list-bullets-black](true)
We've already seen how a super class can be assigned sub classes...
@ulend

---
@title[Casting]


```java
ArrayList<Shape> shapes = new ArrayList<Shape>();
shapes.add(new Circle(100, 100, 10));
shapes.add(new Circle(200, 100, 10));
shapes.add(new Circle(300, 100, 10));
shapes.add(new Square(100, 200, 20));
shapes.add(new Square(100, 300, 20));
```
@[1](shapes arraylist type is super class Shape)
@[2-6](we can add sub class types to shapes)
@[*]

![](/images/shapesArraylist.png)


---
@title[Casting]

This is also valid:
```java
Shape shape;

shape = new Circle();
shape.display();

shape = new Square();
shape.display();
```
@[3,6](a sub class can be assigned to a super class)

---
@title[Casting]
### Casting Rule

@quote[a sub class object can be assigned to a super class object]

For example:
```java
Shape shape = new Circle();
```

---
@title[Casting]
### Casting Rule

@quote[a super class object can NEVER be assigned to a sub class object]

For example:
```java
Circle circle = new Shape();
Square square = new Shape();
```


---?image=/images/animal_cat_dog.png&size=auto 60%&position=bottom&color=#FFFFFF
@title[Casting]
### Casting

The need for casting sometimes arises due to the existence of super and subclasses

---
@title[Casting]
### Casting

Let's assign some objects to an arraylist...

```java
ArrayList<Animal> animals new ArrayList<Animal>();

animals.add(new Cat());
animals.add(new Cat());
animals.add(new Cat());
animals.add(new Dog());
```
@[1](array list of animals)
@[1,2-6](add cats & dog)

@ul[list-bullets-black](true)
- Let's invoke the ``meow()`` method for the cats...
@ulend


---
@title[Casting]
### Casting

Invoking ``meow()`` for Cats

```java
for (Animal animal : animals)
  animal.meow();

```

See anything wrong??

---
@title[Casting]
### Casting

Invoking ``meow()`` for Cats

```java
for (Animal animal : animals)
  animal.meow();

```

We get this error:

![](/images/castingError1.png)

@ul[list-bullets-black](true)
- ``meow()`` is a ``Cat`` class method
- NOT a ``Animal`` class method
- Solution...
@ulend

---
@title[Casting]
### Casting

```java
for(Animal animal: animals)
{
  if(animal instanceof Cat)
  {
    Cat cat = (Cat)animal;
    cat.meow();
  }
}
```
@[1,8](for each animal...)
@[1,8,3,4,7](is animal object a Cat)
@[1,8,3,4,7,5](cast it to a Cat object)
@[1,8,3,4,7,5,6](invoke the meow() method)


---

We'll look at class test results next week...


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 7
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 7
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
