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
@title[Week 3 Notes]
### Week 3 Notes

View [Java Composition](https://github.com/barcaxi/OOP2020/blob/master/notes/Composition.md) at GitHub

---
@title[Week 3 Videos]
### Week 3 Videos

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


---
to be continued...

Assignment #1 Review on Wednesday!


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 4
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
