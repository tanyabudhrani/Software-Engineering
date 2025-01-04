# agile development

Created: September 11, 2024 12:32 PM
Tags: LEC

# agile development

- **dissatisfaction with the overheads** involved in plan-driven software design methods of the 1980s and 1990s led to the creation of agile methods
    - the plan-driven approach was mainly used for **developing large, long-lived software systems** such as aerospace and government systems
- the aim of agile development is to **reduce overheads in the software process** (e.g., by limiting documentation) and to be able to **respond quickly to changing requirements without excessive rework**
    - all agile methods suggest that **software should be developed and delivered incrementally**

## plan driven

- based around **separate development stages** with the outputs to be produced at each stage
- **iteration occurs within activities**

![Screenshot 2024-09-11 at 12.34.19 PM.png](agile%20development%206b039839c3464007b91f5f4e9ddc1793/Screenshot_2024-09-11_at_12.34.19_PM.png)

## agile development

- specification, design, implementation, and testing are inter-leaved and **the outputs from the development process are negotiated during the software development process**
- **iteration occurs across activities**

![Screenshot 2024-09-11 at 12.34.26 PM.png](agile%20development%206b039839c3464007b91f5f4e9ddc1793/Screenshot_2024-09-11_at_12.34.26_PM.png)

## agile manifesto

| principle | description |
| --- | --- |
| customer involvement | customers should be **closely involved throughout the development process**— their role is to **provide and prioritize new system requirements** and to **evaluate the iterations of the system** |
| incremental delivery | the **software is developed in increments** with the customer specifying the **requirements to be included in each increment** |
| people not process | the skills of the development team should be **recognized and exploited**— team members should be left to develop their own ways of working without prescriptive processes |
| embrace change | expect the system requirements to change and so **design the system to accommodate these changes** |
| maintain simplicity | **focus on simplicity in both the software being developed and in the development process**— wherever possible, actively work to eliminate complexity from the system |

### agile method applicability

- agile methods have been **particularly successful for two kinds of system development**

- product development where a software company is developing a **small or medium-sized product for sale**
    - most software products and apps are now developed using an agile approach

- **custom system development within an organization**, where there is a clear commitment from the customer to become involved in the development process and where there are few external rules and regulations that affect the software

# extreme programming

- a very influential agile method, developed in the late 1990s, that introduced a range of agile development techniques
- pushing recognized good practice to “extreme” levels
    - new versions may be built several times per day
    - **increments are delivered to customers every 2 weeks**
    - all tests must be run for every build and the **build is only accepted if tests run successfully**
- the extreme programming release cycle

![Screenshot 2024-09-11 at 12.39.44 PM.png](agile%20development%206b039839c3464007b91f5f4e9ddc1793/Screenshot_2024-09-11_at_12.39.44_PM.png)

| incremental planning | requirements are recorded on story cards and the stories to be included in a release are **determined by the time available and their relative priority**

the developers break these stories into **development ‘tasks’** |
| --- | --- |
| small releases | the **minimal useful set of functionality** that provides business value is developed first

releases of the system are frequent and **incrementally add functionality to the first release** |
| simple design  | **enough design** is carried out to meet the current requirements |
| test-first development | an automated unit test framework is used to write **tests for a new piece of functionality before that functionality itself is implemented** |
| refactoring | all developers are expected to **refactor the code continuously** as soon as possible code improvements are found |
| pair programming | **developers work in pairs**, checking each other’s work and providing the support to always do a good job |
| collective ownership | **the pairs of developers work on all areas of the system**, so that no islands of expertise develop and all the developers take responsibility for all of the code |
| continuous integration | as soon as the work on a task is complete, **it is integrated into the whole system**

after any such integration, all the unit tests in the system must pass |
| sustainable pace | **large amounts of overtime are not considered acceptable** as the net effect is often to reduce code quality and medium term productivity |
| on-site customer | **a representative of the end-user of the system (the customer) should be available full time for the use of the XP team**

in an extreme programming process, the customer is a member of the development team and is responsible for bringing system requirements to the team for implementation |

## support for agile principles in XP

1. incremental delivery is **supported through small releases**
2. customer involvement is **supported through on-site customers**
3. **people, not process, are supported through pair programming**, collective ownership, and sustainable pace
4. change is embraced through **small releases, test-first development, refactoring, and continuous integration**
5. maintaining simplicity is supported by **refactoring and simple design**

## influential XP practices

- extreme programming has a **technical focus** and is difficult to integrate with most organizations' management practice
- consequently, while agile development uses practices from XP, the method as originally defined is not widely used
- key practices
    - user stories for specification
    - refactoring
    - test-first development
    - pair programming

### user stories

- in XP, **user requirements are expressed as user stories**
    - a **customer or user is part of the XP team** and is responsible for making decisions on requirements
    - a user story is a **scenario of use that a system user might experience**
    - they are written on cards, and **the customer chooses the stories for inclusion in the next release based on their priorities and the schedule estimates**
    - the development team breaks the selected user stories **into implementation tasks**
- people find it easier to **relate to these stories** than a conventional requirements document or use cases
- it is difficult to judge **if enough user stories have been developed to cover all the essential requirements** or if a single story gives a true picture of an activity

## design for change vs refactoring

- conventional wisdom in software engineering is to **design for change**
    - it is worth **spending time and effort anticipating changes** as this reduces costs later in the life cycle
- XP proposes **constant code improvement (refactoring) to make changes easier** when they have to be implemented
    - “design for change” is not worthwhile as **changes cannot be reliably anticipated**

## refactoring

- look for possible software improvements and make them **even when there is no immediate need**
    - **local changes tend to degrade software structure** and readability
    - this **improves the understandability of the software** and **reduces the need for documentation**
    - changes are easier to make because the **code is well-structured and clear**
    - however, refactoring sometimes gets delayed, and **some changes require expensive architecture refactoring**
- examples
    - tidying up and renaming attributes and methods to make them easier to understand
    - the replacement of inline code with calls to methods included in a program library

## testing in XP

- with XP, **no system specification can be used by an external testing team** to develop system tests
    - **user stories are user requirements but not system requirements** as they often miss important information about the system
- XP has developed an approach to **test the program after every change**— XP testing features:
    1. incremental test development from scenarios
    2. test-first development
    3. user involvement in test development and validation
    4. use of automated testing frameworks

# test-driven development

- **tests are written as programs before code**
    - writing tests first **avoids the problem of “test-lag”**
    - writing tests **implicitly defines both an interface and a specification of behavior** for the functionality being developed
- each test includes a check of **whether its execution is correct**
- all previous and new tests are **run automatically when new functionality is added**, thus checking that the new functionality has not introduced errors
- usually relies on a testing framework (such as junit)

## customer involvement

- the customer helps **develop acceptance tests for the stories** to be implemented in the next release of the system
- **limitations:**

- people adopting the customer role have **limited time and cannot work full-time** with the development team

- they may feel that **providing the requirements was enough of a contribution** and may be reluctant to get involved in the testing process

## test automation

- test automation means that **tests are written as executable components** (before the task is implemented)
    - these **testing components should be stand-alone**, simulate the submission of input to be tested, and check that the result meets the output specification
    - an **automated test framework** (e.g., JUnit) is a **system that makes it easy to write executable tests** and submit a set of tests for execution
- as testing is automated, there is always a **set of tests that can be quickly and easily executed**
- **whenever any functionality is added to the system, the tests can be run, and problems introduced by the new code can be caught immediately**

### problems with test-first development

- programmers prefer programming to testing and sometimes they **take short cuts when writing tests**
    - for example, they may write incomplete tests that do not check for all possible exceptions that may occur
- **some** **tests can be very difficult to write incrementally**
    - for example, in a complex user interface, it is often difficult to write unit tests for the code that implements the ‘display logic’ and workflow between screens
- it difficult to **judge the completeness of a set of tests**
- although you may have a lot of system tests, your test set may not provide complete coverage

# pair programming

- **programmers sit together at the same computer to develop the software**
- pairs are created dynamically so that **all team members work with each other** during the development process
- **benefits**
    - it supports the idea of **collective ownership** and responsibility for the system
    - it acts as an **informal review process** because at least two people look at each line of code
    - it encourages **refactoring to improve the software structure**
    - it is not necessarily inefficient

# agile project management

- plan-driven software development requires a **manager to have a stable view of everything** that has to be developed and the development processes
- the informal planning and project control proposed by the early adherents of agile methods clashed with this business requirement for visibility
    - self-organizing teams
    - little or no documentation
    - short-term development plans
- agile project management requires a different approach, **adapted to incremental development and the practices used in agile methods**

## scrum

- scrum is an **agile method that focuses on managing iterative development rather than specific agile practices**
- there are three phases:
    1. the initial phase is an **outline planning phase where you establish the general objectives** for the project and **design the software architecture**
    2. that is followed by a **series of sprint cycles**, where each cycle develops an increment of the system
    3. the **project closure phase** wraps up the project, completes required documentation, and assesses the lessons learned

![Screenshot 2024-09-11 at 1.46.34 PM.png](agile%20development%206b039839c3464007b91f5f4e9ddc1793/Screenshot_2024-09-11_at_1.46.34_PM.png)

### scrum sprint cycle

- **sprints are fixed length**, normally 2–4 weeks
- the starting point for planning is the **product backlog, which is the list of work on the project**
- the **selection phase** **involves the whole project team who works with the customer to select the features and functionalities** from the product backlog to be developed during the sprint
- once these are agreed on, **the team organizes itself to develop the software**
- during this stage, **the team is isolated from the customer and the organization**, with all communications channelled through the so-called ‘scrummaster’
- the role of the **scrummaster** is to **protect the development team from external distractions**
- at the end of the sprint, **the work done is reviewed and presented to stakeholders**— the next sprint cycle then begins

### teamwork in scrum

- the **scrummaster is a facilitator** who arranges daily meetings, tracks the backlog of work to be done, records decisions, measures progress against the backlog, and communicates with customers and management outside of the team
- **the whole team attends short daily meetings** (i.e., scrums) where all team members share information and describe their progress since the last meeting, problems that have arisen, and what is planned for the following day
- this means that **everyone on the team knows what is happening** and, if problems arise, can re-plan short-term work to cope with them

## scrum benefits

- the product is broken down into a **set of manageable and understandable chunks that stakeholders can relate to**
- **unstable requirements do not hold up progress**
- the whole team has **visibility of everything**, and consequently, team communication is improved
- **customers see on-time delivery of increments** and gain feedback on how the product works
- **trust between customers and developers is established**, and a positive culture is created in which everyone expects the project to succeed