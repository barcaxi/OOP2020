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
OOP
Week 3
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
