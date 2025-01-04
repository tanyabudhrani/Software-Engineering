# system modeling

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

# structural models

- display the **organization of a system** in terms of the **components that make up that system and their relationships**
    - **static vs. dynamic | overall vs. focused**
- class diagrams are used when **developing an object-oriented system model** to show the **classes in a system and the relationships between these classes**
    - a **class** is a **general definition of one kind of system object**
- can be used at both the **analysis and the implementation phase** of software development

## classes

- a class encapsulates state (attributes) and behavior (operations)
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

### association multiplicity

- **multiplicity** denotes **how many objects of the class take part** in the relation

## special associations (has-a relation)

- **aggregation**: **“part-of” relation between objects**
    - **component can be part of multiple aggregates**
    - component can be created and **destroyed independently
    of the aggregate**

- **composition**: strong aggregation
    - **a component can only be part of a single aggregate**
    - **exists only together with the aggregate**

### navigability of association

- association can be **directed**
    - direction denotes **whether objects can be accessed through this association**

## generalization and specialization

- generalization relation expresses a kind-of (“Is-A”) relationship
- generalization is **implemented by inheritance**
    - the child classes **inherit the attributes and operations of the parent class**
- generalization simplifies the model by **eliminating redundancy**

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

## event-driven modeling

- event-driven modeling shows **how a system responds to external and internal events**
    - it assumes that **a system has a finite number of states** and that **events (stimuli) may cause transitions** between states
- UML state diagrams show **system states and events that cause transitions** from one state to another
    - **system states are modeled as nodes and events as arcs between the nodes**

## superstates

- the number of **possible states increases rapidly**
    - modelling states at different levels
    - a **superstate** looks like a single state in a high-level model but is **then expanded to show more detail in a separate diagram**
