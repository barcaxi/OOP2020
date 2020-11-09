---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP Week 6 
Lecture 1
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend


---
@title[Week 5 Notes]
### Week 5 Notes

Read [Java Inheritance](https://github.com/barcaxi/OOP2020/blob/master/notes/Inheritance.md) at GitHub

---
@title[Week 5 Videos]
### Week 5 Videos


Watch **Java Inheritance** videos at BB

---
@title[Week 6 Assingment #2]
### Assingment #2

@ul[list-bullets-black](false)
- There will be a class test this week
- Worth @size[1.5em](10%)
- Multiple choice questions on BB
@ulend

---
@title[Access Modifiers]
### Access Modifiers

@quote[Access Modifiers determine the visibility of things in Java.]


---
@title[Access Modifiers]
### Access Modifiers

The things that have their visibility determined are:

@ul[list-bullets-black](true)
- classes
- methods
- variables
@olend

---
@title[Access Modifiers]
### Access Modifiers

Visibility/access is determined by keywords:

@ul[list-bullets-black](true)
- ``private``
- ``protected``
- ``public``
- or the absence of these keywords!
@olend

---
@title[Access Modifiers]


Example:

```java
public class Animal {
  private int age;

  public Animal() {
    age = 0;
  }
  public void setAge(int age) {
    this.age=age;
  }
  public int getAge() {
    return age;
  }
}
```
@[1,13](Animal class is public)
@[2](age class variable is private to Animal class)
@[2,5,8,11](age class variable is private to Animal class)
@[4,7,10](class methods are public)

---
Example of valid/invalid access:

```java
//valid
Animal a = new Animal();
a.setAge(10);
println(a.getAge());

// invalid
a.age=10;

```
@[1-4](public class & methods)
@[6-7](age variable is private to Animal class)


---
@title[Animal Access Modifiers]

### Animal class access

![/images/AnimalAccess.png](/images/AnimalAccess.png)


---
@title[private Class Variables]
### private Class Variables

@ul[list-bullets-black](true)
- @size[1.5em](Always) declare class variables as ``private``
- It's good practice in OOP to do this
- It's to do with an OOP concept known as @size[1.5em](encapsulation)
- Encapsulation refers to the binding of data and methods
- more on encapsulation later
@ulend

---
@title[Setters & Getters]
### Setters & Getters

``private`` variables **may** need *setters* and *getters*

```java
public class Animal {
  private int age;

  public Animal() {
    age = 0;
  }
  public void setAge(int age) {
    this.age=age;
  }
  public int getAge() {
    return age;
  }
}
```
@[7-9](setter (mutator) setAge)
@[10-12](getter (accessor) getAge)
@[*](getter (accessor) getAge)


---
@title[Setters & Getters]
### Mutators & Accessors

@ul[list-bullets-black](true)
- *setter* methods are referred to as @size[1.5em](mutators)
- Any class method that changes a class variable is a mutator method
- *getter* methods are referred to as @size[1.5em](accessors)
- Any class method that gives the value of a class variable is a accessor method

@ulend

---
@title[private Class Methods]
### private Class Methods

@ul[list-bullets-black](true)
- You may have methods that need to be ``private``
- These methods don't need to be accessible to everyone
- For example, a ``BankAccount`` might need a ``private`` method... 
@ulend

---
@title[private Class Methods]

```java
public class BankAccount {
  private int balance;

  public BankAccount() {
    balance = 0;
  }
  public void setBalance(int balance) {
    this.balance=balance;
  }
  public int getBalance() {
    return age;
  }
  private void calculateInterest()
  {
    //
  }
}
```
@[13-16](private method)


---
@title[protected Access]
### protected Access



@ul[list-bullets-black](true)
- @size[1.5em](protected) access is available through @size[1.5em](inheritance)
- a ``protected`` variable or method is accessible to sub-classes only
- For example...
@ulend

---
```java
public class BankAccount {
  private int balance;

  public BankAccount() {
    balance = 0;
  }
  public void setBalance(int balance) {
    this.balance=balance;
  }
  public int getBalance() {
    return age;
  }
  protected void calculateInterest()
  {
    //
  }
}
```
@[13-16](protected method available to sub-classes)

---
```java
public class SavingsAccount extends BankAccount {
  
  public SavingsAccount() {
  }
  ...
}

SavingsAccount sa = new SavingsAccount();
sa.setBalance(10000);
sa.calculateInterest();
```
@[1,6](SavingsAccount is-a BankAccount)
@[1,6,8](Create a SavingsAccount object)
@[1,6,8,9](Call public setBalance() method)
@[1,6,8,9,10](Call protected calculateInterest() method)


---
@title[Default Access Modifiers]
### Default Access Modifiers

@ul[list-bullets-black](true)
- A fourth type of access modifier called *default* access
- It is the type of access provided in the absence of an explicit access modifier
- More later about this
@ulend

```java
public class BankAccount{
  int balance;
  public BankAccount() {
  }
  void setBalance(int balance){
    this.balance=balance;
  }
}
```
@[1,3,4,8](public access class & constructor)
@[2,5-7](default access method)
@[*]


---

@title[toString()]
### toString()

@ul[list-bullets-black](true)
- @size[1.5em](All classes) in Java should have a ``toString()`` method
- It prints a @size[1.5em](string representation) of an object state
- It is a method overridden from ``Object`` class...
@ulend

---
@title[Object class]
### Object class

```java
public class Object
{
  public boolean equals(Object obj);
  public String toString();
  protected Object clone();
  ...
}
```
@[4](toString())
@[3](equals() is here too)
@[*]

Every class has ``Object`` as a superclass


---
Every class inherits from ``Object`` class @size[1.15em](implicitly) or explicitly

```java
public class BankAccount {
  private int balance;

  public BankAccount(int balance) {
    this.balance = balance;
  }
  ...
  public int getBalance() {
    return balance;
  }
  @Override
  public String toString() {
    return "[BankAccount: balance="+getBalance()+"]";
  }
}
```


---
Every class inherits from ``Object`` class implicitly or @size[1.15em](explicitly)

```java
public class BankAccount extends Object {
  private int balance;

  public BankAccount(int balance) {
    this.balance = balance;
  }
  ...
  public int getBalance() {
    return balance;
  }
  @Override
  public String toString() {
    return "[BankAccount: balance="+getBalance()+"]";
  }
}
```

---

```java
public class BankAccount extends Object {
  private int balance;

  public BankAccount(int balance) {
    this.balance = balance;
  }
  ...
  public int getBalance() {
    return balance;
  }
  @Override
  public String toString() {
    return "[BankAccount: balance="+getBalance()+"]";
  }
}
```
@[11-14](toString())
@[*]

```java
BankAccount ba = new BankAccount(1000);
println(ba.toString());   // [BankAccount: balance=1000]
println(ba);              // [BankAccount: balance=1000]
```
@[1-15,16]
@[1-15,16,17]
@[1-15,16,17,18]


---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 6
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
