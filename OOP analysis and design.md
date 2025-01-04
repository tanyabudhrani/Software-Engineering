# OOP analysis and design

# object-oriented analysis

- the goal is to **understand the problem** and to begin to **develop a model of what you are trying to build**
    - independent of **implementation and technology concerns**
    - focuses on **translating the functional requirements into software concepts**
        - to get a rough cut at the objects that comprise our system, **then move very quickly into “design” and the other concerns**
    - **function-oriented analysis** – concentrating on the **decomposition of complex functions to simple ones**
    - **object-oriented analysis** – **identifying objects and the relationship between objects**

### analysis

- focus on **understanding the problem**
- **functional** requirements
- system structure
- **a small model**
- idealized design

### design

- focus on **understanding the solution**
- **non-functional** requirements
- operations and attributes
- **a large model**
- close to real code

## domain model

- a domain model is a **visual representation of conceptual classes in a domain of interest**
    - using UML notation, a domain model is illustrated with a **set of class diagrams in which no operations are defined**
    - it may show:
        1. **conceptual classes**
        2. **associations between the conceptual classes**
        3. **attributes of the conceptual classes**
- the following elements are not suitable in a domain model:

- **software artifacts**, such as a window or a database

- **responsibilities or methods**

## conceptual class identification

- a conceptual class is a **real-world concept or thing**, not an implementation class
    - it is better to over-specify a domain model with many fine-grained conceptual classes than to under-specify it
    - strategies to identify conceptual classes
        - **conceptual class category**
        - **noun phrase identification**

## domain modeling

- find the conceptual classes
    - discard a class if it is **outside the current requirements**
    - discard a class if it is **redundant**
    - discard a class if it **looks like an attribute more than a class**
    - discard a class if it is **not being considered in this iteration**
    - there is no correct set of conceptual classes
- draw them in a domain model, i.e., **a set of UML class diagrams in which no operations are defined**
- afterwards, add associations and attributes

### associations in domain modeling

- **a relationship between types** (or instances of those types) that indicates some **meaningful and interesting connection**
    - not a statement about data flows, instance variables, or object connections in a software solution
- guidelines for finding associations
    - **knowledge of the relationship needs to be preserved for some duration** ("need-to-know" associations)
    - it is more important to **identify conceptual classes than to identify associations**
    - **too many associations confuse a domain model** rather than illuminate it
        - **avoid showing redundant or derivable associations**

## attributes

- an attribute is a **logical data value of an object**
    - avoid representing something as an attribute **when it should have been a concept**
        - the attributes in a domain model should preferably be **simple attributes or data types**
    - **attributes should not be used to relate conceptual classes** in the domain model

# object-oriented design

- a process that uses the **analysis results** to produce a **specification for implementing a system**
    - the emphasis is on **defining software objects** and **how they collaborate to fulfill the requirements**
    - there are also other design activities like database design and interface design
    - the result is the **specification of a logical software solution** in terms of software objects, such as their classes, attributes, methods, and collaborations

## static models

- static models help design the **definition of packages, class names, attributes, and method signatures** (but not method bodies)
    - UML class diagram

## dynamic models

- dynamic models help **design the logic and the behavior of the code or the method bodies**
    - UML interaction diagram (e.g., sequence diagrams)

### doing and knowing responsibilities

- a responsibility is a doing or knowing service or a **group of services provided by an element**

- doing responsibilities of an object include:
    - doing something itself
    - initiating actions in other objects
    - controlling and coordinating activities in other objects

- knowing responsibilities of an object include:
    - knowing about private encapsulated data
    - knowing about related objects
    - knowing about things it can derive or calculate

## responsibility-driven design

- a general metaphor for thinking about OOD
    - software objects are like people with responsibilities who collaborate to get work done
    - RDD leads to viewing an OO design as a community of collaborating responsible objects
    - responsibilities are implemented by means of methods that either act alone or collaborate with other methods and objects
    - CRC cards are useful in detecting the responsibilities of objects

### class-responsibility-collaborator

- **one card per class**, **which shows its responsibilities** and with which other class(es) **it must collaborate to fulfill each responsibility**
    - then write a brief description of the class on the back of the card

# solid design principles

### single responsibility principle

```cpp
class Book {
	String getTitle(){ ... }
	String getAuthor(){ ... }
	void printPageAt(int index){
		// print page header
		// print page content
		// print page footer
	}
	int getTotalPageNumber() { ... }
	Page getPageAt(int index) { ... }
}

interface Printer{ void printPage(Page p); }
	class PlainTextPrinter implements Printer{
		void printPage(Page p) { ... }
	}
	class HtmlPrinter implements Printer {
		void printPage(Page p) { ... }
}
```

- **each responsibility is a reason for change**— a class should have only **one reason to change**


### open/closed principle

```cpp
class File{
	private int length, sent;
	...
}

class Progress{
	private File f;
	Progress(File f){ this.f = f; }
	int getAsPercent(){
		return f.getSent() * 100 / f.getLength();
	}
}

void test(){
	File f = new File();
	f.setLength (200); f.setSent (100);
	Progress p = new Progress(f);
	assert(p.getAsPercent() == 50);
}

interface Measurable {
	int getTotal();
	int getPartial();
}

class File implements Measurable {
	public int getTotal() { ... }
	public int getPartial() { ... }
	...
}

class Computation implements
	Measurable{
		public int getTotal() { ... }
		public int getPartial() { ... }
	...
}

class Progress{
	private Measurable m;
	Progress(Measurable m1){ m=m1;}
	int getAsPercent(){
	return (int)(f.getPartial() * 100 / f.getTotal());
	}
}

void test(){
	Measurable f = new File();
	// Set the total and
	// partial of f
	Progress p = new Progress(f);
	assert p.getAsPercent() == 50;
}
```

### liskov substitution principle

```cpp
class Rectangle {
	protected int w;
	protected int h;
	public void setH(int h){
		this.h = h;
	}
	public int getH() {
		return h;
	}
	public void setW(int w){
		this.w = w;
	}
	public int getW() {
		return w;
	}
}

class Square extends Rectangle{
	public void setH(int value){
		w = value; h = value;
	}
	public void setW(int value){
		w = value; h = value;
	}
}
class ShapeTest {
	@Test
	void testArea(){
		Rectangle r = getRectangle();
		r.setW(5); r.setH(4);
		assert r.area() == 20; // !!
	}
}
```

- objects in a program should be **replaceable with instances of their subtypes** without altering the correctness of that program

```cpp
class Rectangle {
	protected int w;
	protected int h;
	public void setH(int h){
		this.h = h;
	}
	public int getH() {
		return h;
	}
	public void setW(int w){
		this.w = w;
	}
	public int getW() {
		return w;
	}
}

class Square{
	private Rectangle rect;
	public Square(int len){
		rect = new Rectangle(len,len);
}
	public void setLen(int len){
		rect.setW(len); rect.setH(len);
}
	public int area(){
		return rect.area();
}
	...
}
```

### interface segregation principle

```cpp
interface Door{
	void lock();
	void unlock();
	boolean isOpen();
}

interface Timer{
	void register(int timeout,
		TimerClient client);
}
interface TimerClient{
	void timeOut();
}
```

- **clients apply a backwards force on interfaces**: fatter interfaces lead to **more reasons for change**
    - suppose a timer client may register multiple callbacks at each timer
    - **an ID will be added to each time-out registration**

```cpp
interface Timer{
void register(int timeout,
	int timeoutID,
	TimerClient client);
}
interface TimerClient{
	void timeOut(int timeoutID);
}

interface Door extends TimerClient{
	void lock();
	void unlock();
	boolean isOpen();
}
```

- clients should not be forced to **depend on methods that they do not need**
    - clients of an object can **access the object through delegation or through a base class of the object**

- many client-specific interfaces are better than **one general-purpose interface**

### dependency inversion principle

- in conventional application architecture, **higher-level components depend directly upon lower-level components to complete some tasks**
- limited reusability of the higher-level components
- inverted dependency

- **high-level modules should not depend on low-level modules**— both should depend on **abstractions**

- **abstractions should not depend on details—** details should depend on **abstractions**

```cpp
class PDFReader {
	private PDFBook pbook;
	PDFReader(PDFBook pbook){
		this.pbook = pbook;
	}
	String read() {
		return pbook.read();
	}
}
class PDFBook {
	String read() {
		return "reading";
	}
}

interface EBook{String read();}
class EBookReader {
	private EBook ebook;
	EBookReader(EBook ebook){
		this.ebook = ebook;
	}
	String read() {
		return ebook.read();
	}
}
class PDFBook implements EBook{
	String read() {
		return "reading";
	}
}
```

# solid

| single responsibility principle | a class should have only a **single responsibility** |
| --- | --- |
| open/closed principle | software entities should be **open for extension but closed for modification** |
| liskov substitution principle | **objects in a program should be replaceable with instances of their subtypes** without altering the correctness of that program |
| interface segregation principle | many **client-specific interfaces** are better than **one general-purpose interface** |
| dependency inversion principle | one should “**depend upon abstractions**— do not depend upon concretions” |
