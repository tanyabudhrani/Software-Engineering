# architectural design

Created: October 2, 2024 1:01 PM
Tags: LEC

# architectural design

- concerned with the understanding **how a software system should be organized** and **designing the overall structure of the system**
    - the output is an **architectural model** that describes **how the system is organized as a set of communicating components**
    - a critical link between **design and requirements engineering**
    - an overall system architecture should be **design at the early stage of an agile development process**

## architectural abstraction

- architecture in the small is concerned with the **architecture of individual** program
- architecture in the large is concerned with the **architecture of complex enterprise systems** that include other systems, programs, and program components

### advantages of explicit architecture

| stakeholder communication | the architecture is a **high-level presentation of the system** that may be used as a **focus for discussion by various stakeholder** |
| --- | --- |
| system analysis | architectural design decisions profoundly affect **whether or not the system can meet critical requirements** |
| large-scale reuse | the architecture may be **reusable across a range of systems**

product-line architectures may be developed |

## architectural representations

- **software architectures** are often **modeled informally using simple block diagrams**
    - **box**: components
    - **boxes in boxes**: component decomposition
    - **arrows**: data and control flow

- they do not show the **type of relationships or the components’ externally visible properties**

- they are **useful for communication with stakeholders** for project planning

## design decisions

- architectural design essentially **involves a series of decisions to make**
    - is there a generic application architecture that can act as a template for the system being designed
    - how will the system be distributed across hardware cores or processors?
    - what architectural patterns or styles might be used?
    - what architectural organization is best for delivering the system’s non-functional requirements
    - how would the architecture of the system be documented?

### architecture and non-functional requirements

| performance | **localize critical operations and minimize communications**— use large rather than fine-grain components |
| --- | --- |
| security | use a **layered architecture** with **critical assets** in the inner layers |
| safety | **localize safety critical features** in a **small number of sub-systems** to reduce the costs and problems of safety validation |
| availability | include **redundant components and mechanisms** for fault tolerance |
| maintainability | use **fine-grain, self-contained components** that may be easily changed |

## architectural views

- what views are useful when designing and documenting a system architecture
    - each architectural model **only shows one view or perspective of system**
    - for both design and documentation, you usually **need to present multiple views**

# architectural patterns

- an architectural pattern is a **stylized description of good design practice**
    - they should include information about **when they are and when they are not appropriate to use**
    - they may be described using a **mixed of narrative descriptions and diagrams**

## MVC pattern

- **separates presentation and interaction from system data**
- the system is structured into three logical components that interacts with each other
    - the **model component** manages the **system data and operations**
    - the **view component** defines and manages **how the data is presented to the user**
    - the **controller component** manages **user interaction** and passes these interactions to the view and the model

![Screenshot 2024-10-02 at 1.37.23 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.37.23_PM.png)

- **advantage**: allows the data to **change independently of its representation**

- **disadvantage**: can involve **code complexity**

## layered architecture

- the system functionality is **organized into separate layers**, and each layer only relies on the **facilities and services offered by the layer immediately beneath it**
    - supports the **incremental development of sub-systems** in different layers
    - when a layer interface changes, **only the adjacent layer is affected**
    - however, it is often artificial to structure systems in this way
    - a generic layered architecture

![Screenshot 2024-10-02 at 1.39.00 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.39.00_PM.png)

- **organizes the system into layers** with **related functionality associated with each layer**— a layer provides services to the layer above it so the **lowest-level layers represent core services** that are likely to be used throughout the system

- **advantages**: allows **replacement of entire layers** so long as the interface is maintained

- **disadvantages**: providing a **clean separation between layers** is often difficult

## repository architecture

- exchange of data among subsystem may be done in two ways

- **centralized storage**: shared data is held in a **central database or repository** and may be accessed by all sub-systems

- **distributed storage**: each sub-system **maintains its own database** and **passes data explicitly** to other subsystems
- **organizing tools around a repository** is an efficient way of **sharing large amounts of data**
    - **a repository architecture for an IDE with tools to support model driven development**

![Screenshot 2024-10-02 at 1.42.10 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.42.10_PM.png)

- all data in a system is managed in a **central repository that is accessible to all system components**
    - **components do not interact directly, only through the repository**

- **advantages**: components can be **independent**

- **disadvantages**: repository is a **single point of failure**

### repository model:

- a repository is **passive**, and its **the responsibility of the components using the repository to control the access to it**

### blackboard model:

- a blackboard **notifies components when particular data becomes available**

## client-server architecture

- a **distributed system model** which shows **how data and processing is distributed across a range of components**
    - set of **stand-alone servers** which provide specific services such as printing, data management
    - set of **clients** which call on these services
    - **network** which allows **clients to access servers**
    - can be **implemented on a single computer**

![Screenshot 2024-10-02 at 1.46.45 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.46.45_PM.png)

- the functionality of the system is **organized into services**, with **each service delivered from a separate server** — clients are **users of these services and access servers** to make use of them

- **advantages**: servers can be **distributed across a network**

- **disadvantages**: each service is a **single point of failure**

## pipe and filter architecture

- a model of the **runtime organization of a system** where functional transformations **process inputs and produce outputs**
    - **pipe** is used because a **transformation filters out the data it can process from its input data stream**
    - best suited to batch processing systems and embedded systems with **limited user interactions**

![Screenshot 2024-10-02 at 1.50.02 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.50.02_PM.png)

- the processing of the data in a system is organized so that **each processing component is discrete and carries out one type of data transformation**

- **advantages**: easy to understand and **supports transformation reuse**

- **disadvantages**: the format of data transfer **has to be agreed upon between communicating transformations**

# application architecture

- architecture that **encapsulates the principal characteristics of a class of systems**
    - similar businesses have common requirements, and therefore **their applications systems tend to have common architectures** that reflect the application requirements

## transaction processing applications

- database-centered applications that process user requests for information and update the information in a system database
- from a user perspective, a transaction is any coherent sequence of operations that satisfies a goal

![Screenshot 2024-10-02 at 1.54.07 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.54.07_PM.png)

## language processing systems

- applications where the users’ intentions are specified in a formal language that is processed and interpreted by the system
- translate one language into an alternative representation of that language

![Screenshot 2024-10-02 at 1.56.15 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.56.15_PM.png)

## information systems

- all systems involving interactions with a shared database can be considered transaction-based information systems— an information system allows controlled access to a large base of information
    - information systems have a generic architecture that can be organized as a layered architecture

![Screenshot 2024-10-02 at 1.55.40 PM.png](architectural%20design%20113b756f81228008adb7ed2b7d34a04b/Screenshot_2024-10-02_at_1.55.40_PM.png)

### other architectures of LPSs

- programming language compilers that are part of a more general programming environment have a generic architecture
- programming language compilers can be implemented using a composite of a repository and a pipe and filter model