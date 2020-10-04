---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 2 Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 2]
### Week 2

View the Week 2 Video Lectures via BlackBoard!

@ul[list-bullets-black](false)
- Classes & Objects
- Arrays
- Array lists
- Enhanced for loop
- ``toString()``   method
@ulend

---
@title[Content]
### Content

@ol[](false)
- Arrays
- Array lists
@olend

---
@title[Arrays & ArrayLists]
### Arrays & ArrayLists

@ul[list-bullets-black](false)
- We will need to handle collections of data
- We'll use the two types of data structures:
  - arrays
  - array lists
- We will be using _arraylists_ a lot in this module!
@ulend

---
@title[Content]
### Content

@ol[](false)
- **Arrays**
- Array lists
@olend

---
@title[Arrays]

### Arrays

@ul[list-bullets-black](false)
- Arrays store similar data types e.g. 
  - ``int``, 
  - ``float``, 
  - ``String``, etc.
- Each array item has a numbered position starting at ``0``
@ulend

---
@title[Arrays]
### Arrays
Declaring and creating an array:

```java
int[] grades = new int[5];
```
This is an ``int`` array variable called ``grades`` with 5 items

---
@title[Arrays]
### Arrays

Assigning values to an array:
```java
int[] grades = new int[5];

grades[0]=45;
grades[1]=35;
grades[2]=55;
grades[3]=65;
grades[4]=75;
```

Alternatively...

```java
int[] grades = {45,35,55,65,75};
```

---
@title[Arrays]
### Arrays

Accessing values in an array:
```java
int[] grades = new int[5];

grades[0]=45;
grades[1]=35;
grades[2]=55;
grades[3]=65;
grades[4]=75;

for(int i=0;i<grades.length;i++)
  System.out.println(grades[i]);
```
@[1]
@[3-7]
@[9-10]

---
@title[Arrays of Objects]
### Arrays of Objects

Arrays can store objects too, not just primitive data types

```java
String[] names = new String[3];

names[0]=new String("Alice");
names[1]=new String("Bob");
names[2]=new String("Charlie");
```

OR, your own objects...

---
@title[Array of Objects]
### Array of Objects
```java
public class Person
{
  String name;
  int age:

  Person(String name, int age)
  {
    this.name=name;
    this.age=age;
  }
}
Person[] pnames = new Person[3];
pnames[0]=new Person("Alice",20);
pnames[1]=new Person("Bob",21);
pnames[2]=new Person("Charlie",22);
```
@[1-11]
@[12]
@[13-15]
@[*]

---
@title[Content]
### Content

@ol[](false)
- Arrays
- **ArrayLists**
@olend

---
@title[ArrayLists]
### ArrayLists

Similar to arrays but -

@ul[list-bullets-black](true)
- arraylists can grow and shrink in size as needed
- arraylists have convenient methods for inserting and removing elements
- arraylists cannot store primitive data types, only objects
@ulend

---
@title[ArrayLists]
### ArrayLists

Declaring an arraylist:
```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<String>();
```

---
@title[ArrayLists]
### ArrayLists

Declare and initialise an arraylist:
```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<String>();
names.add("Alice");
names.add("Bob");
names.add(new String("Charlie"));
```
@[4-6](add() method)
@[*]

---
@title[ArrayLists]
### ArrayLists

Accessing an arraylist:
```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<String>();
names.add("Alice");
names.add("Bob");
names.add(new String("Charlie"));

for(int i=0;i<names.size();i++)
  System.out.println(names.get(i));
```
@[8](size() method)
@[9](get() method)
@[*]

---
Continue on Wednesday...


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 1 Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
