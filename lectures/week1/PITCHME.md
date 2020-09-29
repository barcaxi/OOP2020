---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 1 
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Contents]

### Contents

@ol[](false)
- Processing
- Processing Specific Methods
- Processing Reference
- Program Flow
- ``rect()`` and ``ellipse()`` functions
@olend

---

@title[Processing]

### Processing

@ul[list-bullets-black](true)
- Processing is @size[1.25em](NOT a programming language)
- You are not writing Processing code
- It's @size[1.25em](Java) code
- Processing is an alternative development tool to jGrasp
- It does have some handy built-in methods though...
@ulend

---

@title[Processing Specific Methods]

### Processing Specific Methods

@ul[list-bullets-black](true)
- Built-in methods
    - ``size()``
    - ``line()``
    - ``rect()``
    - ``ellipse()``
    - ``point()``
- They are like Java methods
- They allow you to quickly draw things
- That's a good thing_
@ulend

---

@title[Processing Reference]

### Processing Reference

Use the [Processing Reference](https://processing.org/reference/)

---

@title[Program Flow]

### Program Flow

@ul[list-bullets-black](true)
- Last year your programs executed code in sequence
- Processing uses 2 blocks of code to control the flow of its programs
- The methods:
    - ``setup()``
    - ``draw()``
@ulend

@ul[list-bullets-black](true)
- ``setup()`` statements execute at the start of the program only once
- ``draw()`` statements execute continuously
- For example...
@ulend


---?color=black

```java
float x;

void setup() // runs once
{
  size(200, 200);
  x=0;
}

void draw() // runs continuously
{
  background(0, 0, 0);
  fill(255, 255, 255);
  ellipse(0, 100, 50, 50);
}
```

+++?color=black

```java
float x;

void setup() // runs once
{
  size(200, 200);
  x=0;
}

void draw() // runs continuously
{
  background(0, 0, 0);
  fill(255, 255, 255);
  ellipse(0, 100, 50, 50);
}
```
@[3-7](Setup runs ONCE)
@[9-14](draw runs CONTINUOUSLY)
@[3-7]
@[5](initialise window size)
@[6](initialise variable x)
@[9-1]
@[11](draw black background)
@[12-13](draw white ellipse)


---?color=black

```java
float x;

void setup() // runs once
{
  size(200, 200);
  x=0;
}

while(true)
{
  background(0, 0, 0);
  fill(255, 255, 255);
  ellipse(0, 100, 50, 50);
}
```
@[9,10,14](Think of draw() like this!)

---

@title[Program Flow]

### Program Flow

Why have a method that runs continuously?

@ul[list-bullets-black](true)
- draw new content
- move content
- get user input
- check location of things
- update scores
- change variable values
- example...
@ulend

---?color=black
```java
float x;

void setup() // runs once
{
  size(200, 200);
  x=0;
}

void draw() // runs continuously
{
  background(0, 0, 0);
  fill(255, 255, 255);
  ellipse(x, 100, 50, 50);
  x++;
}

```

---?color=black
@title[rect() function]

### rect() function

```java
void setup()
{
  size(200, 200);
}

void draw()
{
  rect(100, 100, 100, 100);  // origin is top-left
}
```

![alt](images/rect1.png)

---?color=black
@title[ellipse() function]

### ellipse() function

```java
void setup()
{
  size(200, 200);
}

void draw()
{
  rect(100, 100, 100, 100);
  ellipse(100, 100, 100, 100);  // origin is center
}
```

![alt](images/ellipse1.png)

---
@title[Change Origin]

### Change Origin

@ul[list-bullets-black](false)
- You can change the origin of a rectangle using ``rectMode()``
- You can change the origin of an ellipse using ``ellipseMode()``
@ulend

For example...

---?color=black

```java
void setup()
{
  size(200, 200);
}

void draw()
{
  rectMode(CENTER);  // origin is center
  rect(100, 100, 100, 100);
  ellipse(100, 100, 100, 100);
}
```
@[8](change origin to center)
@[*]

![alt](images/rect2.png)

---
@title[Video Lectures]

### Video Lectures

Watch the video lectures on BlackBoard

---?color=black
@title[Title]

@snap[west headline text-white span-70]
OOP
Week 1 
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
