---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 3
Lecture 1 
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 3 Notes]
### Week 3 Notes

View [Java Exceptions](https://github.com/barcaxi/OOP2020/blob/master/notes/Exceptions.md) at GitHub

---
@title[Week 3 Videos]
### Week 3 Videos

View Java Exceptions on BlackBoard

---
@title[Week 3 Assingment #1]
### Assingment #1

@ul[list-bullets-black](false)
- There will be a class test this week during Tuesday practical @ 4pm
- Worth 5%
- Multiple choice questions on BB
@ulend

---
@title[Contents]
### Contents

@ul[](false)
- **Java Exceptions**
- Throwing Exceptions
- Checked & Unchecked Exceptions
@ulend

---
@title[Java Exceptions]
### Java Exceptions

@ul[list-bullets-black](true)
- Exceptions are used in Java to deal with @size[1.5em](runtime) errors
- NOT @size[1.5em](compile time) errors
- Examples of runtime errors are:
  - @size[1.5em](array out of bounds) errors
  - @size[1.5em](division by zero) errors
  - @size[1.5em](null pointer) errors
- Let's see some runtime exceptions ...
@ulend


---?image=/images/exception3.png&size=auto 40%&position=right
@title[NullPointer Exception]
### NullPointer Exception

@ul[list-bullets-black](true)
- ``name`` object @size[1.5em](declared)
- ``name`` object @size[1.5em](NOT created)
- can't get ``length()`` of nothing/``null``
@ulend


---?image=/images/exception1.png&size=auto 70%&position=right
@title[ArrayIndexOutOfBounds Exception]
### ArrayIndexOutOfBounds Exception

``i=0,1,2,3``

@ul[list-bullets-black](true)
- there is no index 3
@ulend

---
@title[Java Exceptions]
### Java Exceptions

@ul[list-bullets-black](true)
- We need to @size[1.5em](handle) possible exceptions in our code
- We cannot have our programs end unexpectedly
- We do this using the ``try catch`` code block...
@ulend

---
@title[Java Exceptions]
### Java Exceptions

```java
try
{
   ...
   ...
}
catch(Exception e)
{
   ...
   ...
}
```
Let's handle that array out of bounds error...

---
@title[Java Exceptions]
### Java Exceptions

```java
int nums = {1,2,3};

try
{
   for(int i=0;i<4;i++)
     print(nums[i]);   
}
catch(ArrayIndexOutOfBoundsException e)
{
   println("There was an array out of bounds error");
   println(e.getMessage());
}
```
@[1](declare an array)
@[6](could throw an ArrayOutOfBounds exception)
@[3,4,6,7,8,9,12](catch the exception)
@[3,4,6,7,8,9,10,12](print a simple message)
@[3,4,6,7,8,9,10,11,12](print details)

@ul[](true)
- Catches error
- Program does not stop
@ulend

---
@title[Java Exceptions]
### Java Exceptions


@ul[](true)
- Java Exceptions are _Classes_
- See full list of Java exceptions at the Java Documentation [here](https://docs.oracle.com/javase/7/docs/api/java/lang/RuntimeException.html)
@ulend



---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 3
Lecture 2
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---
@title[Contents]
### Contents

@ul[](false)
- Java Exceptions
- **Throwing Exceptions**
- Checked & Unchecked Exceptions
@ulend

---
@title[Throwing Java Exceptions]
### Throwing Java Exceptions


@ul[](true)
- You can have your class methods @size[1.5em](throw) exceptions if something is wrong
- What could be wrong?
- Someone using your methods passes invalid values...
@ulend

---
@title[Spot class]
### Spot class

```java
public class Spot
{
  private float x, y, diameter;

  public Spot(float x, float y) {
    this.x=x;
    this.y=y;
    this.diameter=50;
  }
  public void move() {
    x++;
  }
  public void display() {
    ellipse(x, y, diameter, diameter);
  }
}
```
@[5-9](We should check for invalid x,y values...)
@[*]

---
@title[Use Spot class]
### Use Spot class
```java
Spot sp;

void setup()
{
  size(200, 200);
  sp = new Spot(-100, 100);
}

void draw()
{
  background(0, 0, 0);
  sp.move();
  sp.display();
}
```
@[6](-100 is outside window)
@[*]

@ul[](true)
- Let's have ``Spot()`` constructor throw an exception for invalid x,y values...
@ulend

---
@title[Throwing an Exception]
### Throwing an Exception

```java
public class Spot
{
  private float x, y, diameter;

  public Spot(float x, float y) {
    if(x<0 || x>width)
      throw new Exception("Invalid x coordinate: " + x);
    this.x=x;
    this.y=y;
    this.diameter=50;
  }
  ...
}
```
@[6-7](Check for invalid x values before intialising class vars & )
@[6-7](throw a generic Exception with message)
@[*]

@ul[](true)
- We also need to declare ``Spot()`` throws an Exception...
@ulend

---
@title[Throwing an Exception]
### Throwing an Exception

```java
public class Spot
{
  private float x, y, diameter;

  public Spot(float x, float y) throws Exception {
    if(x<0 || x>width)
      throw new Exception("Invalid x coordinate: " + x);
    this.x=x;
    this.y=y;
    this.diameter=50;
  }
  ...
}
```
@[5,11](Spot signature must be updated)
@[5-11](Spot constructor)
@[*]

@ul[](true)
- Next we must catch the exception...
@ulend

---
@title[Use Spot class]
### Catch the Exception
```java
Spot sp;

void setup()
{
  size(200, 200);
  sp = new Spot(-100, 100);
}

void draw()
{
  background(0, 0, 0);
  sp.move();
  sp.display();
}
```
@[6](We will get a compile time error here now)
@[6](e.g. Uncaught Exception)
@[*]

@ul[](true)
- Add a the ``try..catch`` statement... 
@ulend

---
@title[Use Spot class]
### Catch the Exception
```java
Spot sp;

void setup()
{
  size(200, 200);
  try {
    sp = new Spot(-100, 100);
  }
  catch(Exception e) {
    println(e.getMessage());
    exit();
  }
}

...
```
@[6-8](try)
@[6-12](try...catch)
@[10](Invalid x coordinate: -100)
@[*]

@ul[](true)
- Summary...
@ulend

---
@title[Throwing Your Own Exceptions]
### Throwing Your Own Exceptions

@ol[](true)
- ``throw`` an exception from within your method
- Update the method signature 
- Catch the exception where method is used
@olend


---
@title[Contents]
### Contents

@ul[](false)
- Java Exceptions
- Throwing Exceptions
- **Checked & Unchecked Exceptions**
@ulend


---
@title[Checked & Unchecked Exceptions]
### Checked & Unchecked Exceptions

We've seen two types of Java exceptions:

@ol[](true)
- Checked
- Unchecked
@olend

---
@title[Checked Exceptions]
### Checked Exceptions

@quote[Checked exceptions are **checked** at **compile time**]

Examples...

---?image=/images/exception4.png&size=auto 40%&position=right
@title[Checked Exceptions]
### Checked Exceptions

@ul[list-bullets-black](true)
- ``Spot()`` constructor is checked exception
- Java checks at compile time it has a ``try..catch``
- Another example...
@ulend

---?image=/images/exception5.png&size=auto 40%&position=right
@title[Checked Exceptions]
### Checked Exceptions

@ul[list-bullets-black](true)
- The ``Thread.sleep`` method is checked method
- Java checks at compile time it has a ``try..catch``
@ulend

---
@title[Unchecked Exceptions]
### Unchecked Exceptions

@quote[Unchecked exceptions are NOT checked at compile time]

@ul[](true)
- They happen at runtime
- All Java ``RuntimeException`` classes are unchecked exceptions, e.g.
  - ``NullPointerException``
  - ``ArrayIndexOutOfBoundsException``
  - ``ArithmeticException`` etc.
  - example...
@ulend

---?image=/images/exception3.png&size=auto 40%&position=right
@title[Unchecked Exceptions]
### Unchecked Exceptions

``NullPointerException`` is a unchecked exception

---
@title[To check or not to check?]
### To check or not to check?

@quote[If a client can reasonably be expected to recover from an exception, make it a checked exception]

@quote[If a client cannot do anything to recover from the exception, make it an unchecked exception]

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 3
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

