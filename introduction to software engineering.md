# introduction to software engineering

Created: August 29, 2024 9:21 AM
Tags: LEC

# software engineering

- an **engineering discipline** that is concerned with **all aspects of software production**

- engineering discipline
    - using appropriate theories and methods to solve problems, **considering organizational and financial constraints**

- all aspects of software production
    - technical process of development
    - development of tools, methods, etc. **to support software production**
    - project management

## necessity for software engineering

- we cannot run the modern world without software
- we need to produce reliable and trustworthy software systems economically and quickly

- **software costs**
    - software costs **often dominate computer system costs**
    - software costs **more to maintain** than it does to develop
        - it is **usually cheaper**, in the long run, **to use SE methods and techniques for software systems** — rather than just write the programs as if they were personal programming projects

- **causes of software project failures**
    - increasing system complexity/size
    - failure to use software engineering methods

### software engineering diversity

- there are many **different types of software systems**
    - **application types**: e.g. interactive transaction-based applications, embedded control systems, entertainment systems, data collection systems, and more
    - **software product types**: **generic** (decision made by company) vs. **customized** (decision made by a group of people)
- no universal set of techniques applies to all of them — the software engineering methods and tools used depend on the **type of application being developed, the requirements of the customer, and the background of the development team**

## software engineering fundamentals

- general issues that affect software
    - **heterogeneity** (all types of devices)
    - **business and social change** (need to adapt)
    - **security and trust** (risks)
- fundamental principles applicable to all types of software systems, irrespective of the development techniques used
    - software systems should be developed **using a managed and understood development process**
    - **understanding and managing the software specification and requirements** are important
    - when appropriate, **reuse software already developed** rather than write new software
    - **dependability and performance are important** for all types of software systems

| product characteristic | description |
| --- | --- |
| acceptability | software must be **acceptable to the types of users for which it is designed**  |
| dependability | software dependability includes a range of characteristics including **reliability, security, and safety** 

dependable software **should not cause physical or economic damage** in the event of system failure  |
| efficiency | software should not **make wasteful use of system resources** such as memory and processor cycles — efficiency includes **responsiveness, processing time, resource utilization** |
| maintainability | software should be written in such a way that **it can evolve to meet the changing needs of customers**, which is a critical attribute because software change is an inevitable requirement  |

### FAQs about SE

![Screenshot 2024-08-29 at 10.23.00 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_10.23.00_AM.png)

## scope of software engineering

### 1. historical aspects

- proposed in the **1968 NATO SE conference**
    - **software crisis**: software is delivered **late, over budget, and with faults**

### 2. economic aspects

- new coding techniques are 10% faster and 10% cheaper, should it be used?
    - need to take into account **the cost of training, the impact of introducing a new technology, and the effect of the new technique on maintenance**

### 3. maintenance aspects

- **software process model**: the **abstract steps to follow** when building software

- **software process**: the **actual steps performed** on a specific software product
- **waterfall model**
    1. **requirements** phase
    2. **analysis** (specification) phase
    3. **design** phase
    4. **implementation** phase 
    - post delivery **maintenance**
    - **retirement**
- software is a **model of reality, which is constantly changing** — good software is maintained for 10-20 years more

- **classical view**: development then maintenance
    - classification as developed or **maintenance** **depends on when an activity is performed**, which is **temporal and inconsistent**
    - developers have to **perform maintenance long before the product is installed**
    - **reuse is widespread**, and software product is seldom constructed from scratch

- **modern view**: the process that occurs when software undergoes modifications to code and associated documentation **due to a problem or the need for improvement or adaptation**

### 4. requirements, analysis, and design aspects

- the earlier we detect and correct a fault, **the less it costs us**
- the relative cost of fixing a fault at each phase of the classical software life cycle
    
    ![Screenshot 2024-08-29 at 10.36.06 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_10.36.06_AM.png)
    
- the cost of correcting a bug **depends on what has to be done**

- to correct a fault early in the life cycle
    - usually just **a document that needs to be changed**

- to correct a fault late in the life cycle
    1. **change code** and documentation
    2. **test** the change
    3. perform **regression testing**
    4. **reinstall** the product
- it is vital to improving our **requirements, analysis, and design techniques**
    - between 60 and 70% of all faults in large-scale products are requirements, analysis and design faults

### 5. software is often built by teams

- hardware is **cheap and more powerful**
- many software products are **too large to be written by one personc** in the available time
- problems caused
    - **interfacing problems between modules**
    - **communication problems among team members**

# software engineering ethics

- software engineering involves wider responsibilities than **simply the application of technical skills**
    - ethical behavior involves following a set of morally correct principles — **SEs must behave in an honest and ethically responsible way**

| confidentiality | engineers should normally **respect the confidentiality of their employers** irrespective of whether or not a formal confidentiality agreement has been signed |
| --- | --- |
| competence | **engineers should not misrepresent their level of competence** and knowingly accept work that is outside their competence |
| intellectual property rights | engineers should be aware of and abide by local laws governing the use of **intellectual property such as patents, copyrights** |
| computer misuse  | software engineers should not use their technical skills **to misuse other people’s computers** |

### SE code of ethics and professional practice

- approved by the **IEEE-CS and ACM**
- members of these organizations **sign up for the code of practice when they join**
- the code contains **eight principles related to the behavior** of and decisions made by
    - professional software engineers, including practitioners, educators, managers, supervisors, and policymakers, trainees and students of the profession
1. **public** - engineers shall act **consistently with the public interest**
2. **client and employer** - engineers shall act in a manner that is in **the best interest of their client and employer** consistent with the public interest
3. **product** - engineers shall ensure that **their products and related modifications meet the highest professional standards possible**
4. **judgement** - engineers shall **maintain integrity and independence** in their professional judgement 
5. **management** - engineering managers and leaders shall subscribe to and **promote an ethical approach to the management of software development and maintenance**
6. **profession** - engineers shall **advance the integrity and reputation of the profession** consistent with the public interest
7. **colleagues** - engineers shall be **fair to and supportive of their colleagues**
8. **self** - engineers shall participate in **lifelong learning regarding the practice of their profession** and shall promote an ethical approach to the practice of the profession

- on a personal level, a software engineer should
    - **never steal data for personal gain**
    - **never distribute or sell proprietary information** obtained as part of your work
    - never use computing technology to **facilitate discrimination**

## case studies

- a personal insulin pump
    - an embedded system in an insulin pump used by diabetics to maintain blood glucose control
    - architecture
        
        ![Screenshot 2024-08-29 at 11.23.59 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_11.23.59_AM.png)
        
    - activity model
        
        ![Screenshot 2024-08-29 at 11.24.03 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_11.24.03_AM.png)
        
- a mental health case patient management system
    - a system used to maintain records of people receiving care for mental health problems
    - organization
        
        ![Screenshot 2024-08-29 at 11.26.43 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_11.26.43_AM.png)
        
- a wilderness weather station
    - a data collection system that collects data about weather conditions in remote areas
- iLearn: a digital learning environment
    - a system to support learning in schools
    - architecture
        
        ![Screenshot 2024-08-29 at 11.27.15 AM.png](introduction%20to%20software%20engineering%20fac8eeaa63214cf49dae3843d195fbaa/Screenshot_2024-08-29_at_11.27.15_AM.png)