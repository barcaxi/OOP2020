---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 4  
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 4 Notes]
### Week 4 Notes

View [Java Composition](https://github.com/barcaxi/OOP2020/blob/master/notes/Composition.md) at GitHub

---
@title[Week 4 Videos]
### Week 4 Videos

View Java Composition on BB


---
@title[Java Composition]
### Java Composition

@ul[list-bullets-black](true)
- Many @size[1.5em](classes) that you create have an obvious @size[1.5em](relationship) to each other
- For example:
  - ``Book`` and ``Author`` classes
  - ``Planet`` and ``Moon`` classes
  - ``Course`` and ``Module`` classes
- Referencing one class from another is known as @size[1.5em](Composition)
- For example, ``Book`` and ``Author`` ...
@ulend

---?image=/images/BookAuthor_.png&size=auto
@title[Java Composition]
### Java Composition


---
@title[Book has-a Author]
### Book has-a Author

```java
class Author {
  private String name;

  public Author(String name) {
    this.name=name;
  }
  public String getName() {
    return name;
  }
}
```

---
@title[Book has-a Author]
### Book has-a Author

```java
class Book {
  String title;
  Author author;

  public Book(String title, Author author) {
    this.title=title;
    this.author=author;
  }
  public String getTitle() {
    return title;
  }
  public Author getAuthor() {
    return author;
  }
}
```
@[3](Book has-a Author. That's composition!)
@[*]


---
@title[Java Composition]
### Java Composition

@ul[list-bullets-black](true)
- Other @size[1.5em](Composition) examples:
  - a ``Planet`` has-a ``Moon``
  - a ``Course`` has-a ``Module``
  - a ``Team`` has-a ``Player``
- These are @size[1.5em](one-to-one) relationships
- There can be @size[1.5em](one-to-many) relationships too...
@ulend

---
@title[Java Composition]
### Java Composition

@ul[list-bullets-black](true)
- Possible one-to-many relationships:
  - a ``Planet`` can have 0 to many ``Moon``s
  - a ``Course`` can have 0 to many ``Module``s
  - a ``Team`` can have 0 to many ``Player``s
- How do we store many relationships?
- Use a @size[1.5em](data structure) (e.g. array, arraylist)
- For example..
@ulend


---?image=/images/BookAuthors.png&size=auto
@title[Java Composition]
### Java Composition


---
@title[Book has-a Author]
### Book has Authors

```java
class Author {
  private String name;

  public Author(String name) {
    this.name=name;
  }
  public String getName() {
    return name;
  }
}
```

---
@title[Book has-a Author]
### Book has Authors

```java
class Book {
  String title;
  Author[] authors = new Author[2];

  public Book(String title, Author[] authors) {
    this.title=title;
    this.authors=authors;
  }
  public String getTitle() {
    return title;
  }
  public Author[] getAuthors() {
    return authors;
  }
}
```
@[3](Book has 2 Authors. That's composition!)
@[12-14](return array.)
@[*]


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 4  
Lecture 2
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Week 3 Assignment #1]
### Assignment #1 Review

@ul[list-bullets-black](true)
- 54 attempts
- Average @size[1.5em](62%)
- Next Assignment - Class Test Week 6 @size[1.5em](10%)
- Let's look at @size[1.5em](top 5) incorrectly answered questions
- Don't make these mistakes *again...*

@ulend

---

### #5 - 30/54 Incorrect Answers

What type of exception will be thrown in the code below: 
```java
String name; 
println(name.length()); 
```
Choices:
```
(a) NullPointerException
(b) None of these
(c) ArithmeticException
(d) ArrayIndexOutOfBoundsException
```
@[1-2,3]


---
### #4 - 31/54 Incorrect Answers

What does the following code print? 
```java
ArrayList<String> al = new ArrayList<String>(); 
al.add("A"); 
al.add("B"); 
al.add("A"); 

al.remove("A"); 
println(al);
```
Choices:
```
(a) [B]
(b) [A,B,A]
(c) [B,A]
```
@[1-7,10]


---
### #3 - 35/54 Incorrect Answers

With an enhanced for loop we can retrieve array elements without having to specify the index. Provide the correct code at the missing code(...) so each value in the data array is printed.

```java
int data[] = {2,4,8,16,32};  
for(int value: data) 
  println(...);
```
Answer is:
@ul[list-bullets-black](true)
- ``value``
@ulend



---
### #2 - 37/54 Incorrect Answers

Provide the correct code at the missing code(...) so each value in the data array list is printed.
```java
import java.util.ArrayList;  
ArrayList<Integer>  data = new ArrayList<Integer>(); 
data.add(10); 
data.add(20); 
data.add(30);  
for(int i=0;i<data.size();i++) 
   println(...);
```
Answer is:
@ul[list-bullets-black](true)
- ``data.get(i)``
@ulend



---
### #1 - 46/54 Incorrect Answers

Which line number has an invalid array declaration and initialisation? 
```java
1: int[] nums = new int[2]; nums[0]=1;nums[1]=2; 
2: int nums[] = new int[2]; nums[0]=1;nums[1]=2; 
3: int[] nums = {1,2}; 
4: String[] strings = {"",""}; 
```
Choices:
```
(a) 1
(b) 2
(c) 3
(d) 4
(e) None of these are invalid
```
@[1-4,9]





---
Best answered question...

---
### #1 - 2/54 Incorrect Answers

What does the following code print? 
```java
ArrayList<String> al = new ArrayList<String>(); 
al.add("A"); 
al.add("B"); 
al.add("A"); 

println(al); 
```
Choices:
```
(a) [A,B]
(b) [A,B,A]
```
@[1-6,8]

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 4
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
