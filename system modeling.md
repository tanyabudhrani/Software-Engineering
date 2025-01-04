# system modeling

Created: September 26, 2024 7:00 PM
Tags: LEC

# system modeling

- system modeling is the process of **developing abstract models of a system**
    - a **model** is an **abstraction of the system being studied** rather than an alternative representation of that system
    - each model presents a **different view/perspective of the system**
        - external, structural, and behavioral
- models can be
    - from **different perspectives**
    - in **different forms** (e.g., graphical vs. formal/mathematical)
    - for systems at **different stages** (e.g., existing vs. to be developed)

## graphical system models

- **to stimulate and focus discussion about a system**
    - incomplete and informal (normal in agile modeling)

- **to document an existing system**
    - correct but incomplete

- **to generate a system implementation**
    - complete and correct

## unified modeling language

- a standardized language for **specifying, visualizing, constructing, and documenting (software) systems**
    - general purpose modeling language (for [OO software] systems)
    - today’s de-facto standard in the industry

### UML diagram types

![Screenshot 2024-09-26 at 7.04.46 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.04.46_PM.png)

# context models

- context models **illustrate a system's operational context**— they show **other systems used by or depend on the system being developed** but not how the systems interact with each other
- **system boundaries define what is inside and outside the system**
    - social and organizational concerns may affect where to position the system boundaries

## process perspective

- business process models defined using UML activity diagrams may help **reveal how the system being developed is used in broader business processes**

# interaction models

- all systems involve **interactions of some kind**
    - modeling **user interaction** helps to **identify user requirements**
    - modeling **component interaction** helps us understand **if a proposed system structure will deliver the required performance and dependability**
    - modeling **system-to-system interaction** highlights the **communication problems** that may arise
- two related approaches to interaction modelling

- **use case diagrams** model interactions between **systems and
external agents** (human users or other systems)

- **sequence diagrams** model interactions between **system
components (and external agents)**

## use case modeling

- each use case (an ellipse) represents a **discrete task that involves external interaction with a system**
- an actor (a stick figure) in a use case may be a **person or a system**

### sequence diagrams

- to model the interactions between **the** **actors and the objects** within a system and **those between the objects themselves**
- a sequence diagram shows the **sequence of interactions during a particular process** or process instance
- sequence diagram elements
    
    
    | entities | objects/actors |
    | --- | --- |
    | relations | message passing |
    | syntactic sugar | lifelines
    activations
    frames |

### frame for looping

![Screenshot 2024-09-26 at 7.24.16 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.24.16_PM.png)

### frame for conditioning

![Screenshot 2024-09-26 at 7.24.49 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.24.49_PM.png)

# structural models

- display the **organization of a system** in terms of the **components that make up that system and their relationships**
    - **static vs. dynamic | overall vs. focused**
- class diagrams are used when **developing an object-oriented system model** to show the **classes in a system and the relationships between these classes**
    - a **class** is a **general definition of one kind of system object**
- can be used at both the **analysis and the implementation phase** of software development

## classes

- a class encapsulates state (attributes) and behavior (operations)

![Screenshot 2024-09-26 at 7.26.52 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.26.52_PM.png)

- each attribute has a type

- each operation has a signature
- the class name is the only mandatory information

### relationships

- **general relationship**: dependency

- **instance-level** (objects are also called instances)
    - association
    - aggregation
    - composition

- **class-level**
    - generalization
    - realization/implementation

## dependency

- a semantic connection between **dependent and independent classes** (modules)
- if **changes to the definition of one class** (module) (the server or target) **may cause changes to the other** (the client or source)

## associations

- an association is a **type of relation between class instances**
- objects of the classes can communicate using the association
    - class A has an attribute of type B
    - class A creates instances of B
    - class A received a message with argument of type B

![Screenshot 2024-09-26 at 7.32.34 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.32.34_PM.png)

### association multiplicity

- **multiplicity** denotes **how many objects of the class take part** in the relation

![Screenshot 2024-09-26 at 7.33.13 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.33.13_PM.png)

## special associations (has-a relation)

- **aggregation**: **“part-of” relation between objects**
    - **component can be part of multiple aggregates**
    - component can be created and **destroyed independently
    of the aggregate**

![Screenshot 2024-09-26 at 7.33.59 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.33.59_PM.png)

- **composition**: strong aggregation
    - **a component can only be part of a single aggregate**
    - **exists only together with the aggregate**

![Screenshot 2024-09-26 at 7.34.37 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.34.37_PM.png)

### navigability of association

- association can be **directed**
    - direction denotes **whether objects can be accessed through this association**

![Screenshot 2024-09-26 at 7.35.41 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.35.41_PM.png)

## generalization and specialization

- generalization relation expresses a kind-of (“Is-A”) relationship
- generalization is **implemented by inheritance**
    - the child classes **inherit the attributes and operations of the parent class**
- generalization simplifies the model by **eliminating redundancy**

![Screenshot 2024-09-26 at 7.36.28 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.36.28_PM.png)

### example

![Screenshot 2024-09-26 at 7.36.51 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.36.51_PM.png)

# behavioral models

- behavioral models **model a system's dynamic behavior as it executes**
    - they show what happens or what is supposed to happen **when a system responds to a stimulus from its environment**

- **data**: some data arrives and must be processed by the
system— **the availability of the data triggers the processing**

- **events**: some event happens that triggers system processing— **events may have associated data, although this is not always
the case**

## data-driven modeling

- data-driven models show the **sequence of actions involved in processing input data** and **generating an associated output**
    - many business systems are data-processing systems that are primarily driven by data

### activity diagrams

![Screenshot 2024-09-26 at 7.38.25 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.38.25_PM.png)

### sequence diagrams

![Screenshot 2024-09-26 at 7.38.31 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.38.31_PM.png)

## event-driven modeling

- event-driven modeling shows **how a system responds to external and internal events**
    - it assumes that **a system has a finite number of states** and that **events (stimuli) may cause transitions** between states
- UML state diagrams show **system states and events that cause transitions** from one state to another
    - **system states are modeled as nodes and events as arcs between the nodes**

## superstates

- the number of **possible states increases rapidly**
    - modelling states at different levels
    - a **superstate** looks like a single state in a high-level model but is **then expanded to show more detail in a separate diagram**

![Screenshot 2024-09-26 at 7.40.26 PM.png](system%20modeling%2010db756f81228094a560c928cde23edd/Screenshot_2024-09-26_at_7.40.26_PM.png)