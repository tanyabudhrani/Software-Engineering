# software testing

Created: October 20, 2024 6:32 PM
Tags: LEC

# program testing

- testing is intended to show that **a program does what it is intended to do** and **discover program defects before it is used**
    - testing a software system involves **executing the program using input data and checking the results of the test run for errors**, anomalies, or information about the program’s **non-functional attributes**
- goals
    1. to demonstrate to the developer and the customer that **the software meets its requirements**
    2. to discover situations in which the **behavior of the software is incorrect, undesirable or does not conform to its specification**

## validation and defect testing

1. the first goal leads to **validation testing**
    - you expect the system to **perform correctly using a given set of test cases that reflect the system’s expected use**
    - a successful test shows that the system operates as intended
2. the second goal leads to **defect testing**
    - the test cases are designed to **expose defects**
        - the test cases in defect testing can be **deliberately obscure and need not reflect how the system is normally used**
    - a successful test is a test that **makes the system perform incorrectly and exposes a defect in the system**
    - can reveal **the presence of errors but NOT their absence**

## V&V

- testing is part of a more general V&V process

- **verification**: the software should **conform to its specification**
    - "are we building the product right”.

- **validation**: the software should **do what the user really requires**
    - "are we building the right product.”
- the aim of V&V is to establish confidence that **the system is ‘fit for purpose’**
    
    
    | software purpose | the level of confidence depends on **how critical the software is to an organization** |
    | --- | --- |
    | user expectations | users may have **low expectations of certain software** |
    | marketing environment | getting a product to market early **may be more important than finding defects** in the program |

## software inspections

- these involve people **examining the source representation** with the aim of **discovering anomalies and defects**
    - applicable to **any representation of the system**
        - requirements, design, configuration data, test data, etc
    - because inspection is a static process, **you don’t have to be concerned with interactions between errors**
        - during testing, **errors can mask (hide) other errors**
    - as well as searching for program defects, **an inspection can also consider broader quality attributes** of a program
        - compliance with standards, portability, maintainability, etc
- they have been shown to be an **effective technique for discovering program errors**

## stages of testing

1. **development testing**: the system is **tested during development to discover bugs and defects**
2. **release testing**: a separate testing team **tests a complete version of the system before it is released** to users
3. **user testing**: users or potential users of a system are **involved in testing the system**

# development testing

- including all testing activities carried out by the development team
    
    
    | unit testing | **individual program units or object classes are tested** | focus on testing the **functionality of objects or methods** |
    | --- | --- | --- |
    | component testing | individual units are **integrated to create composite components** | focus on testing **component interfaces** |
    | system testing | some or all of the components in a system are integrated, and **the system is tested as a whole** | focus on testing **component interactions** |
- **white box testing vs. black box testing**
    - with vs. without **knowledge about the internal structure, design, or implementation of the software**

# unit testing

- the process of testing **individual code units in isolation**, where units may be:
    - **individual functions or methods** within an object
    - **object classes** with several attributes and methods
- **object class testing**: coverage of **all the features of an object**
    1. **getting and setting** all object attributes
    2. testing **all operations** associated with an object
    3. exercising the object in **all possible states**
    4. simulating **all events that cause a state change**
- **inheritance** makes it more difficult to design object class tests as **the information to be tested is not localized**

## automated testing

- whenever possible, **unit test execution should be automated**

- automated test components
    - **a setup part**, where you **initialize the system with the test case**, namely the **inputs and expected outputs**
    - **a call part**, where you **call the object or method** to be tested
    - an automated mechanism to **compare the result of the call with the expected result**

- test automation framework
    - in automated unit testing, **you use a test automation framework** (such as JUnit) to write and run your program tests
    - unit testing frameworks **provide generic test classes that you extend to create specific test cases** and can **run all the tests** you have implemented and report the results

### partition testing

- identify groups of inputs that have **common characteristics and should be processed in the same way**
- choose tests from within each of these groups

### guideline-based testing

- **use testing guidelines to choose test cases**
- these guidelines reflect the **previous experience of the kinds of errors that programmers often make** when developing code units

## partition testing

- input data and output results often fall into **different classes where all members of a class are related**
    - each of these classes is an **equivalence partition or domain** where the program behaves in an **equivalent way for each class member**
    - **test cases should be chosen from each partition**
    - partition boundary

![Screenshot 2024-10-20 at 6.43.59 PM.png](software%20testing%20125b756f812280518c71d181d6557f16/Screenshot_2024-10-20_at_6.43.59_PM.png)

## testing guidelines

- **software with sequences**
    - test software with **sequences that have only a single value**
    - use sequences of **different sizes in different tests**
    - derive tests so that **the sequence's first, middle, and last elements are accessed**
    - test with sequences of **zero length**

- **general software**
    - choose inputs that **force the system to generate all error messages**
    - design inputs that **cause input buffers to overflow**
    - repeat the same input or series of inputs **numerous times**
    - force computation results to be **too large or too small**

# component testing

- software components are often **composite units comprising several interacting objects**
- the functionality of these components is **accessed through their defined interface**
    - testing components should focus on showing that the component interface **behaves according to its specification**
    - you can assume that unit tests on the individual objects within the component have been completed

## interface testing

- objectives are to **detect faults due to interface errors or invalid interface assumptions**

- interface types
    - parameter interfaces
    - shared memory interfaces
    - procedural interfaces
    - message passing interfaces

- interface errors
    - interface misuse
    - interface misunderstanding
    - timing errors

### interface testing guidelines

1. design tests so that parameters to a called procedure are at the **extreme ends of their ranges**
2. always test pointer parameters with **null pointers**
3. design tests that **cause the component to fail**
4. use **stress testing** in message-passing systems
5. in shared memory systems, **vary the order in which components are activated**

# system testing

- involves integrating components to create a version of the system and **then testing the integrated system**
    - tests can be derived from the **use cases**
    - essentially, it checks that **components are compatible, interact correctly, and transfer the right data at the right time**
- system testing overlaps with component testing, but there are two important differences:
    - **the complete system is tested**
    - **system testing is a collective rather than an individual process**
        - sometimes, system testing may involve a **separate testing team with no involvement from designers and programmers**

### system testing policies

- exhaustive system testing is impossible so testing policies which define the required system test coverage may be developed
    - examples of testing policies:
        - **all system functions that are accessed through menus should be tested**
        - **combinations of functions** (e.g., text formatting) that are accessed through the same menu must be tested
        - where user input is provided, **all functions must be tested with both correct and incorrect input**

## regression testing

- regression testing is testing the system to check that **changes have not ‘broken’ previously working code**
- in a manual testing process, regression testing is expensive— but, with automated testing, it is simple and straightforward
    - **all tests are rerun every time a change is made to the program**
- **tests must run ‘successfully’ before the change is committed**

# release testing

- the process of testing a **particular release of a system** that is intended for use outside of the development team
- the primary goal of the release testing process is to **convince the supplier of the system that it is good enough for use**
    - release testing has to show that the system delivers its specified functionality, performance, and dependability and that it does not produce unexpected behaviors or results
- release testing is usually a **black-box testing process where tests are only derived from the system specification**

> release testing is a **form of system testing**

requirements-based testing involves **examining each requirement and developing a test or tests for it**

scenario testing uses typical scenarios to develop test cases for the system
> 

### difference between RT and ST

1. **a separate team that has not been involved in the system development**, should be responsible for **release testing**
2. **system testing by the development team** should focus on discovering **bugs in the system (defect testing)**
3. the objective of release testing is to **check that the system meets its requirements** and is good enough for external use **(validation testing)**

## performance testing

- part of release testing may involve testing the emergent properties of a system, such as performance and reliability
- tests should reflect the profile of use of the system
- performance tests usually involve planning a series of tests where the **load is steadily increased until the system performance becomes unacceptable**
- **stress testing** is a form of performance testing where **the system is deliberately overloaded to test its failure behavior**

# user testing

- user or customer testing is a stage in the testing process in which **users or customers provide input and advice on system testing**
- user testing is essential, even when comprehensive system and release testing have been carried out
    - the reason for this is that influences from the user’s working environment have a major effect on a system's reliability, performance, usability, and robustness— **these cannot be replicated in a development environment**

| alpha testing | users of the software **work with the development team to test the software at the developer’s site**

used when **developing software products** or custom software |
| --- | --- |
| beta testing | a release of the software is **made available to users to allow them to experiment** with the software

mostly used for **software products** used in many different settings |
| acceptance testing | **customers test a system to decide whether or not it is ready to be accepted** from the system developers and deployed in the customer environment

an inherent part of custom systems development |

### stages in acceptance testing

![Screenshot 2024-10-20 at 6.59.44 PM.png](software%20testing%20125b756f812280518c71d181d6557f16/Screenshot_2024-10-20_at_6.59.44_PM.png)

> in **agile methods**, the **user/customer is part of the development team** and is responsible for making decisions on the acceptability of the system

there is **no separate acceptance testing process**

main problem here is whether or not **the embedded user is ‘typical’** and can represent the interests of all system stakeholders
>