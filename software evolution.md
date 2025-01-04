# software evolution

Created: October 28, 2024 1:09 PM
Tags: LEC

## software change

- errors must be repaired;
- the performance or reliability of the system may have to be improved
- the business environment changes;
- new computers and equipment is added to the system;
- new requirements emerge when the software is used;

## importance of evolution

- software systems are **critical business assets to organizations**
- to maintain the value of these assets, **they must be changed and updated**
- most of the **software budget** in large companies is **devoted to changing and evolving existing software** rather than developing new software

### evolution

- **the software system is in operational use**
- **significant changes to the architecture and functionality are made**

### servicing

- the software remains useful
- **only small tactical changes are made**

### retirement

- **only essential changes are made**, and users must work around problems
- **the software is taken out of use after its data is transferred**

# evolution

- proposals for change are the driver for system evolution
    - **bug reports** from system stakeholders
    - requests for **adaptation to the new environment**
    - **new ideas for software improvement** from the system development team
    - requests for **new requirements**

## a general model

![Screenshot 2024-10-28 at 1.13.06 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.13.06_PM.png)

- change implementation
    - **iteration of the development process** where the **revisions to the system are designed, implemented, and tested**
    - **critical difference between development and evolution** is that the **first stage of change implementation may involve program understanding**

## change management process

- the process of **analyzing the costs and benefits of proposed changes**, approving those changes that are **cost-effective**, and tracking **which components in the system have been changed**
    
    ![Screenshot 2024-10-28 at 1.37.39 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.37.39_PM.png)
    

## agile methods and evolution

- agile methods are based on incremental development so **the transition from development to evolution is a seamless one**
    - evolution is simply **a continuation of the development process** based on frequent system releases
    - **automated regression testing** is particularly valuable when **changes are made to a system**
    - changes may be expressed as **additional user stories**
- **handover problems**:

- the development team have used an agile approach, **but the evolution team prefers a plan-based approach**

- a plan-based approach has been used for development, **but the evolution team prefer to use agile methods**

# software maintenance

- **generic software products evolve to create new versions**
- **modifying a custom software after it has been put into use** is called **software maintenance**
    - maintenance **does not normally involve major changes** to the system’s architecture
    - changes are implemented by **modifying existing components and adding new components** to the system
- types of maintenance
    - **fault repairs**
    - **environmental adaptation**
    - **functionality addition and modification**

## maintenance costs

- **usually greater than development costs** (2* to 100* depending on the application)
- **increases as software is maintained**
- it is usually more expensive to **add new features to a system during maintenance** than it is to add the same features during development
    1. program maintenance work is unpopular: **maintenance staff are often inexperienced and have limited domain knowledge**
    2. separating maintenance and development means **there is no incentive for the development team to write maintainable software**
    3. a new team has to **understand the programs being maintained**
    4. as programs age, their structure degrades, **and they become harder to change**

## software reengineering

- restructuring or rewriting part or all of a legacy system **without changing its functionality**—to make them easier to maintain
    - applicable where some but not all sub-systems of a **larger system require frequent maintenance**

![Screenshot 2024-10-28 at 1.42.59 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.42.59_PM.png)

- advantages of reengineering over replacement
    - **reduced risk**
    - **reduced cost**

### reengineering cost factors

- the **quality of the software** to be reengineered
- the **tool support available** for reengineering
- the **extent of the data conversion** which is required
- the **availability of expert staff** for reengineering

### limitations of software reengineering

- converting the programming paradigm is impossible
- major architectural or data management changes are **expensive**
- the resulting system probably is **not as maintainable as a new system**

## refactoring

- **a continuous process of improvement throughout the development and evolution process**
    - when refactoring a program, **you should not add functionality** but rather concentrate on **program improvement**
    - **“preventative maintenance”**
- it is intended to **avoid the structure and code degradation** that increases the costs and difficulties of maintaining a system

## re-engineering

- it takes place **after a system has been maintained** for some time and maintenance costs are increasing
- it uses **automated tools to process and re-engineer a legacy system** to create a new, more maintainable system

# version management

- the process of **keeping track of different versions of software components or configuration items** and the systems in which these components are used
    - ensures that changes made by different developers to these versions **do not interfere with each other**
- **manages codelines and baselines**

- a **codeline** is a **sequence of versions of source code** with **later versions in the sequence derived from earlier versions**
    
    ![Screenshot 2024-10-28 at 1.50.22 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.50.22_PM.png)
    

- a **baseline** specifies the **component versions included in a specific system and the libraries and configuration files**, etc., used
    
    ![Screenshot 2024-10-28 at 1.50.28 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.50.28_PM.png)
    
- the **mainline** is a **sequence of system versions developed from an original baseline**

## version control systems

- version control (VC) systems **identify, store and control access to the different versions** of components
- there are two types of modern version control system
    - **centralized** systems: there is a **single master repository that maintains all versions** of the software components that are being developed
        - example: subversion
    - **distributed** systems: **multiple versions of the component repository exist simultaneously**
        - example: git

❖ version control systems vs. cloud storage systems

### key features of VCS

1. version and release identification
2. change history recording
3. support for independent development
4. project support
5. storage management

## project repository and private

- the project repository **maintains the ‘master’ version of all components**, which is used to **create baselines for system building**
- when modifying components, **developers copy (check-out) these from the repository into their workspace** and work on these copies
- when they have finished their changes, **the changed components are returned (checked-in) to the repository**

- in centralized version control, **a private workspace contains only components from the project repository**
    
    ![Screenshot 2024-10-28 at 1.54.12 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.54.12_PM.png)
    
    - it is **easier to learn** and set up
    - it **takes less time and space** to download part of a project

- in distributed version control, **a private workspace is a clone of the project repository**
    
    ![Screenshot 2024-10-28 at 1.54.17 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.54.17_PM.png)
    
    - it provides a **backup mechanism** for the repository
    - it allows for **offline working**
    - it is **faster**
    - **project support is the default way of working**
    - working on branches is **easier**
    - **fewer merge conflicts** with other developer’s code

## branching and merging

- **rather than a linear sequence of versions** that reflect changes to the component over time, **there may be several independent sequences**
- at some stage, it may be necessary to **merge codeline branches to create a new version of a component** that includes **all changes that have been made**
- depending on the complexity and relation of the changes in individual branches, **merging can be easy or difficult**

## storage management

- when version control systems were first developed, storage management was one of their most important functions
    - instead of keeping a complete copy of each version, **the system stores a list of differences (deltas) between one version and another, because disk space was expensive**
    - by applying these to a **master version** (usually the most recent version), **a target version can be recreated**

### in git

- as disk storage is now relatively cheap, **git uses an alternative, faster approach**
- git does not use deltas but **applies a standard compression algorithm to stored files and their associated meta-information**
- **it does not store duplicate copies of files**— retrieving a file simply involves **decompressing it, with no need to apply a chain of operations**

# legacy systems

- **older systems** that rely on languages and technology that are no longer used for new systems development
    - they are not just software systems but are **broader socio-technical systems that include hardware, software, libraries and other supporting software and business processes**
    
    ![Screenshot 2024-10-28 at 1.59.19 PM.png](software%20evolution%2012db756f81228055ac77ee8a36f0a488/Screenshot_2024-10-28_at_1.59.19_PM.png)
    

## replacement and change

- legacy system replacement is risky and expensive
    - **lack of complete system specification**
    - **tight integration** of system and business processes
    - **undocumented business rules** embedded in the legacy system
    - new software development may be **late and/or over budget**

- legacy systems are expensive to change
    - **no consistent programming style**
    - use of **obsolete programming languages** with few people available with these language skills
    - **inadequate system documentation**
    - system structure **degradation**
    - program optimizations may make them **hard to understand**
    - **data errors, duplication, and inconsistency**

## legacy system management

- organizations that rely on legacy systems must choose a **strategy for evolving these systems**
    - **continue maintaining** the system;
    - transform the system by **re-engineering to improve its maintainability**;
    - **replace the system** with a new system
    - **scrap the system completely** and modify business processes so that it is no longer required;

## selection of evolving strategy

- depends on the **system’s business value and its quality**

- **business value assessment**: interview stakeholders about
    - **the use of the system**
    - **the business processes that are supported**
    - **system dependability**
    - **the system outputs**

- **system quality assessment**:
    - assess factors like **understandability, documentation, data, performance, programming language, configuration management, test data, personnel skills**
    - **consider the number of system change requests, the number of user interfaces, and the volume of data used by the system**

| low quality, low business value | **scrap** |
| --- | --- |
| low-quality, high-business value | **re-engineer or replace** if a suitable system is available |
| high-quality, low-business value | **scrap completely or maintain** |
| high-quality, high business value | **keep in operation with
normal system maintenance** |