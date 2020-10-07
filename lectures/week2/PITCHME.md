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

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 2 Lecture 2
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


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

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 2 Lecture 2
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---
@title[Content]
### Content

@ol[](false)
- **User-defined classes**

@olend


---
@title[User-defined Classes]
### User-defined Classes

@ul[list-bullets-black](false)You can easily create user-defined classes using Processing IDE
- You can easily create user-defined classes using Processing IDE
- e.g. ``Spot`` class...
@ulend


---?image=/images/Spot.png&size=auto 75%&position=right
@title[Processing Classes]
### Processing Classes

@ul[list-bullets-black](false)You can easily create user-defined classes using Processing IDE
- Create a _tab_ for your class(es)
@ulend

---?image=/images/Spot2.png&size=auto 75%&position=right
@title[Processing Classes]
### Processing Classes

@ul[list-bullets-black](false)You can easily create user-defined classes using Processing IDE
- Use from main project tab
@ulend

---
@title[Content]
### Content
@ol[](false)
- User-defined classes
- **ArrayList example**
@olend

---
@title[ArrayList Example]
### ArrayList Example

@size[1.5em](Correct) way to @size[1.5em](declare) and @size[1.5em](create) arraylist...

---

```java
import java.util.ArrayList;

ArrayList<Integer> data;
int largest=0;

void setup()
{
  size(500, 200);
  data = new ArrayList<Integer>();
  data.add(new Integer(10));
  data.add(new Integer(20));
  data.add(new Integer(30));
  data.add(new Integer(40));
  data.add(new Integer(50));
}

void draw()
{
  background(0, 0, 0);
  for (int i=0; i<data.size(); i++)
    ellipse(i*100, 100, data.get(i), data.get(i));
}
```
@[1,3](Declare data ArrayList)
@[1,3,6,7,15,9](Create data ArrayList)
@[1,3,6,7,15,9,10-14](Initialise data ArrayList)
@[17,18,20,21,22](Use data ArrayList)
@[*]

---
@title[ArrayList Example]
### ArrayList Example

@size[1.5em](What's wrong here?)

---

```java
import java.util.ArrayList;

ArrayList<Integer> data;
int largest=0;

void setup()
{
  size(500, 200);
  ArrayList<Integer> data = new ArrayList<Integer>();
  data.add(new Integer(10));
  data.add(new Integer(20));
  data.add(new Integer(30));
  data.add(new Integer(40));
  data.add(new Integer(50));
}

void draw()
{
  background(0, 0, 0);
  for (int i=0; i<data.size(); i++)
    ellipse(i*100, 100, data.get(i), data.get(i));
}
```
@[3,9](Now TWO data arraylists)
@[6,7,9-14,15](local to setup() method)
@[3](data=null - not created!)
@[17,18,20,21,22](NullPointer Exception)
@[*]

---
@title[Content]
### Content
@ol[](false)
- User-defined classes
- ArrayList example
- **Enhanced for loop**
@olend

---

```java
import java.util.ArrayList;

ArrayList<Spot> spots;                  // Declare arraylist of spot objects

void setup()
{
  size(300, 200);
  spots = new ArrayList<Spot>();        // Create arraylist of spot objects
  spots.add(new Spot(0, 100, 50));      // add spot objects to arraylist
  spots.add(new Spot(-100, 100, 50));
  spots.add(new Spot(-200, 100, 50));
}

void draw()
{
  background(0, 0, 0); 
  for (int i=0; i<spots.size(); i++)
  {
    spots.get(i).move();
    spots.get(i).display();
  }
}
```
@[3,8-11](Declare, Create & Initialise)
@[17-21](move & display using standard for loop)
@[*](There's another way using enhanced for loop...)

---

```java
import java.util.ArrayList;

ArrayList<Spot> spots;                  // Declare arraylist of spot objects

void setup()
{
  size(300, 200);
  spots = new ArrayList<Spot>();        // Create arraylist of spot objects
  spots.add(new Spot(0, 100, 50));      // add spot objects to arraylist
  spots.add(new Spot(-100, 100, 50));
  spots.add(new Spot(-200, 100, 50));
}

void draw()
{
  background(0, 0, 0); 
  for(Spot spot: spots)
  {
    spot.move();
    spot.display();
  }
}
```
@[17,18,21](for each spot in spots)
@[17-21](move & display)
@[*]


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 2 Lectures
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
