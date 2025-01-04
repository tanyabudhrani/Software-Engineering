# requirements engineering

Created: September 15, 2024 7:46 PM
Tags: LEC

# requirements and requirements engineering

- the **requirements** are the **descriptions of the services that a system should provide** and the **constraints on its operation**
    - the process of finding out, analyzing, documenting, and **checking these services and constraints** is called **requirements engineering (RE)**
    - different kinds of requirements are **needed to communicate information** **about a system** to different types of stakeholders
        - **stakeholder**: any person or organization who is **affected by the system in some way**
- types of requirements

- **user requirements**: statements in **natural language plus diagrams**

- **system requirements**: a detailed, **structured document**

![Screenshot 2024-09-15 at 7.48.16 PM.png](requirements%20engineering%20102b756f8122802aba46d7a5d10a1926/Screenshot_2024-09-15_at_7.48.16_PM.png)

## agile methods and requirements

- requirements in agile processes
    - producing detailed system requirements is a waste of time
    - use **incremental requirements engineering** and often express **requirements as “user stories”**
    - **practical for business systems** but problematic for many others
- this lecture presents a “traditional” view of requirements
    - for most large systems, there is a **clearly identifiable requirements engineering phase** **before system implementation begins**
- the outcome is a **requirements document**

# functional requirements

- functional requirements are **statements of services the system should provide**
    - may **state what the system should not do**

# non-functional requirements

- non-functional requirements are **constraints on the system’s services or functions**
    - **often apply to the system as a whole**, rather than individual features or services
- the line between them is not always clear **since requirements are not independent**
- the system requirements **should include both types of requirements**

## functional requirements

- statements of services the system should provide
    - may be in **different forms** and at **different levels of detail**
    - functional **user requirements** may be **high-level statements of what the system should do**
    - functional **system requirements** **should describe the system services in detail**
    - ideally, a **system's functional requirements** **specification** should be **complete and consistent**
    

### mentcare system: functional system requirement

1. a user shall be able to search the appointments lists for all clinics
2. the system shall generate each day, for each clinic, a list of patients who are expected to attend appointments that day
3. each staff member using the system shall be uniquely identified by his or her 8-digit employee number

# non-functional requirements

- **constraints on the system’s services or functions**
- may be **more critical than functional requirements**
- it is often more **difficult to identify** **which system components implement specific non-functional requirements**
    - non-functional requirements **may affect the overall architecture of a system** rather than the individual components
    - a non-functional requirement **may generate other related functional and/or non-functional requirements**

## verifiable non-functional requirements

- non-functional requirements may be **difficult to state precisely**, and imprecise requirements may be **difficult to verify**
- **verifiable non-functional requirement**: a statement using **some measure that can be objectively tested**

| property | measure |
| --- | --- |
| speed | processed transactions/second
user/event response time
screen refresh time |
| size | mbytes
number of ROM chips |
| ease of use | training time
number of help frames |
| reliability | mean time to failure
probability of unavailability
rate of failure occurrence
availability |
| robustness | time to restart after failure
percentage of events causing failure
probability of data corruption on failure |
| portability | percentage of target dependent statements
number of target systems |

### challenges in specifying non-functional requirements

- customers for a system may find it **difficult to translate their goals into measurable requirements**
    - **no simple metrics for some goals** (e.g., maintainability)
    - unclear connection **between metrics and everyday experience**
    - too **high costs** for verification
- non-functional requirements often **conflict and interact with other functional or non-functional requirements**
- it is **difficult to separate functional and non-functional requirements** in the requirements document

# requirements engineering process

- the processes used for RE vary widely
- however, there are a number of generic activities common to all processes
    - **requirements elicitation**;
    - **requirements specification**;
    - **requirements validation**;
- in practice, RE is an **iterative activity in which these processes are interleaved**

# requirements elicitation

- involves **technical staff working with stakeholders** to find out about the **application domain, work activities, services, system features that stakeholders want, etc**

![Screenshot 2024-09-15 at 8.00.16 PM.png](requirements%20engineering%20102b756f8122802aba46d7a5d10a1926/Screenshot_2024-09-15_at_8.00.16_PM.png)

## techniques

|  | problems | benefits |
| --- | --- | --- |
| interviewing | application specialists **may use language that isn’t easy for the requirements engineer to understand** to describe their work

interviews are **not good for understanding domain requirements** | be open-minded, avoid pre-conceived ideas about the requirements, and **be willing to listen to stakeholders**

**prompt the interviewee to talk about the system by suggesting requirements** rather than simply asking them what they want |
| observation | participants might get disturbed

participants **might change their way of working during observation** and the observer might not get a clear picture

**knowledge-based activities (e.g., debugging) are hard to observe** | **people do not have to explain or articulate their work**

it is relatively inexpensive

the observer will get a **practical insight into the work**— social and organizational factors of importance may be observed |

### problems of requirements elicitation

- **stakeholders don’t know what they really want**
- stakeholders **express requirements in their own terms** and with implicit knowledge of their work
- different stakeholders, with diverse requirements, **may express their requirements in different ways**
- organizational and political factors **may influence the system requirements**
- the requirements change **during the analysis process**
- **new stakeholders may emerge, and the business environment may change**

# requirements specification

- the process of **writing down the user and system requirements in a requirements document**
    - user requirements must be **understandable by end-users and customers who do not have a technical background**
    - system requirements are **more detailed requirements and may include more technical information**
- common notations for writing system requirements
    - natural language sentences
    - structured natural language
    - graphical notations
    - mathematical specifications

## natural language specification

- natural languages are
    - **expressive, intuitive, and universal**
    - potentially vague and ambiguous
- guidelines on writing natural language requirements
    - invent a **standard format and use it for all requirements**
    - use language in a consistent way
        - use “shall” for mandatory requirements; use “should” for desirable requirements
    - use **text highlighting** to identify key parts of the requirement
    - **avoid the use of computer jargon**
    - include an **explanation (rationale) of why a requirement is necessary**

### structured natural language specifications

- an approach to writing requirements where the **requirements are written in a standard way rather than as free-form text**
    - maintains most **expressiveness and understandability of NL**
    - removes some of the problems of NL specification
    - it is still sometimes **difficult to write requirements in a clear and unambiguous way**

## use cases

- describe interactions between users and a system using a **graphical model and structured text**
    - identify the **actors involved in an interaction and name the type of the interaction**
    - additional information can be added to describe the interaction
- use case diagram
    - each **use case (a named ellipse) represents a class of interaction**
    - an **actor (a stick figure) is a person or a system**
    - lines link actors with the interaction
    - documented with a textual description

## requirements and design

- in principle, **requirements should state what the system should do and the design should describe how it does this**
- in practice, **requirements and design are inseparable**
    - you may have to **design an initial architecture of the system to help structure the requirements specification**
    - in most cases, **systems must interoperate with existing systems**, which **constrain the design and impose requirements on the new system**
    - the use of a specific architecture to satisfy non-functional requirements, such as N-version programming to achieve reliability, may be necessary

### software requirements specification

- the official statement of **what the system developers should implement**
    - the information in the SRS **depends on the type of system and the development process used**
    - should include **both user and system requirements**
    - requirements specification standards have been designed (e.g., IEEE standard)
- it is NOT a design document— as far as possible, **it should set out WHAT the system should do rather than HOW it should do it**

| preface |
| --- |
| introduction |
| glossary |
| user requirements definition |
| system requirements specification |
| system models |
| system evolution |
| appendices |
| index |

# requirements validation

- the process of checking that **requirements define the system that the customer really wants**
    - overlaps with **elicitation and analysis**

| validity checks | do the requirements reflect the real needs of system users? |
| --- | --- |
| consistency checks | are there any requirements conflicts? |
| completeness checks | are all functions required by the customer included? |
| realism checks | can the requirements be implemented, given the available budget and technology? |
| verifiability checks | can the requirements be verified? |

## requirements validation techniques

- various techniques that can be used **individually or together**

- **requirements reviews**: systematically and manually **analyze the requirements to check for errors and inconsistencies**
    - should be held regularly
    - should involve both client and contractor staff
    - may be formal (with completed documents) or informal

- **prototyping**: using an **executable model of the system to check requirements**

- **test-case generation**: developing **tests for requirements** to check verifiability

# changing requirements

- software systems are often **developed to address “wicked” problems—problems that cannot be completely defined**
- once a system is installed and regularly used, **new requirements inevitably emerge**
- the original requirements may have errors and omissions
- the **business and technical environment of the system always changes** after installation
- the stakeholders as well as their **priorities and requirements may change**

## requirements traceability matrix

- a grid that helps to link requirements to business and project objectives, track requirements throughout the software life cycle, and manage changes