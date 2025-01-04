# software reuse

Created: November 4, 2024 2:16 PM
Tags: LEC

# software reuse

- there has been a major switch to a **design process** that is based on **systematic software reuse** over the past 20 years
- reuse-based software engineering
    - **system reuse**
    - **application reuse**
    - **component reuse**
    - **object and function reuse**

- benefits
    - **accelerated development**
    - **effective use** of specialists
    - increased **dependability**
    - **lower development costs**
    - **reduced process risk**
    - standards **compliance**

- problems
    - creating, maintaining, and using a **component library**
    - finding, understanding, and **adapting reusable components**
    - **increased maintenance costs**
    - **lack of tool support**
    - not-invented-here syndrome

# the reuse landscape

- reuse is possible at a **range of levels from simple functions to complete application systems**
- the reuse landscape covers the range of possible reuse techniques
    
    > architectural patterns
    program libraries
    application frameworks
    software product lines
    component-based software engineering
    service-oriented systems
    design patterns
    model-driven engineerings
    application systems integration
    > 

## reuse planning factors

- the **development schedule** for the software
- the expected **software lifetime**
- the **background, skills and experience of the development team**
- the **criticality of the software** and its **non-functional requirements**
- the **application domain**
- the **execution platform** for the software
- reasons not to reuse
    - **unwillingness to compromise the requirements**
    - preference to **known risks of development over unknown risks of reuse**, even if the latter may be larger

# application frameworks

- an **integrated set of software artifacts** (such as classes, objects, and components) that **collaborate to provide a reusable architecture** for a family of related applications
    - **classes are reused directly** and may be extended using features such as **inheritance and polymorphism**
    - **frameworks support design reuse** (providing a skeleton architecture for the application) and the **reuse of specific classes in the system**
    - frameworks provide **support for generic features** that are **likely to be used in all applications** of a similar type
    - the problem with frameworks is their **complexity**, meaning it takes a **long time to use them effectively**

## web application frameworks

- WAFs are now available for **all commonly used web programming languages**
    - e.g., spring for java, django for python, and angular for javaScript
- support the **construction of dynamic websites** as a front-end for web applications
- security, dynamic web pages, database support, session management, user interaction
- the architecture of a WAF is **usually based on the MVC composite pattern**

## extending frameworks

- **frameworks are generic** and are **extended to create a more specific application or sub-system**
- extending the framework involves
    - **adding concrete classes** that **inherit operations from abstract classes** in the framework;
    - **adding (callback) methods** that are **called in response to events** that are recognized by the framework

# software product lines

- a software product line is a **set of applications with a common architecture and shared components**, with **each application specialized to reflect different requirements**
    - printer drivers
    - MS Office
- specialization may involve:
    - **selecting from a library of existing components**;
    - **component and system configuration**;
    - **modifying components** to meet new requirements
    - **adding new components** to the system;

### base systems for a software product line

- software product lines **usually emerge from existing applications**
- designing a generic product line involves **identifying common functionality in product instances** and **developing a base application to simplify reuse and reconfiguration**
- generally, **a base application includes**
    - **core components** that provide **infrastructure support**
    - **configurable components** that may be **modified and configured to specialize them** to a new application
    - **specialized, domain-specific components** some or all of which may be **replaced when a new instance of a product line is created**

### application frameworks and product liens

- they both
    - **support a common architecture and components**
    - **require new development to create a specific version** of a system
    

- differences
    - **application frameworks rely on object-oriented features** such as **polymorphism to implement extensions**— **product lines need not be object-oriented**
    - **application frameworks** provide **general rather than domain**- **specific support**— product lines embed **domain and platform information**
    - **software product lines** are **often control applications for equipment**— **application frameworks** are **usually software-oriented**
    - **software product lines** are made up of a **family of applications**, usually owned by the same organization

# CBSE

- an approach to software development that relies on the **reuse of entities called “software components”**
    - the failure of object-oriented development to **support effective reuse**: **single object classes are too detailed and specific**
    - **components are more abstract** than object classes and can be stand-alone service providers
- CBSE essentials
    - **independent components specified by their interfaces**
    - **component standards to facilitate component** integration
    - **middleware** that provides **support for component inter-operability**
    - a **development process** that is **geared to reuse**

### characteristics

| composable | for a component to be composable, **all external interactions must take place through publicly defined interfaces**

in addition, **it must provide external access to information about itself**, such as its methods and attributes |
| --- | --- |
| deployable | to be deployable, **a component has to be self-contained**

it must be able to **operate as a stand-alone entity** on a component platform that **implements the component model**— this usually means that the **component is binary and does not need to be compiled before deployment** |
| documented | components have to be **fully documented** so that **potential users can decide whether or not the components meet their needs**

the syntax and, ideally, the **semantics of all component interfaces should be specified** |
| independent | a component should be **independent**—it should be possible to **compose and deploy it without having to use other specific components**

in situations where the component needs externally provided services, **these should be explicitly set out in a “requires” interface specification** |
| standardized | component standardization means that **a component used in a CBSE process has to conform to a standard component model**

this model may define **component interfaces, component metadata, documentation, composition, and deployment** |

## components as providers of services

- think about a component as a **provider of one or more services** (even if the component is embedded rather than implemented as a service)
- the component is an **independent executable entity defined by its interfaces**
- in principle, all components have two related interfaces
    - the “**provides**” interface defines the **services provided by the component**
    - the “**requires**” interface **specifies the services that other components in the system must provide** if a component is to operate correctly

## component models

- a component model defines standards for component **implementation, documentation, and deployment**
    - EJB model (enterprise java beans)
    - COM+ model (.NET model)
    - CORBA component model (CCM)
- basic elements of a component model
    - **interfaces**
    - **usage information**
    - **deployment**

## component model implementation

- a component model implementation provides **platform services and support services**
    
    ![Screenshot 2024-11-04 at 2.30.36 PM.png](software%20reuse%20134b756f812280c6a5dfc68192033d69/Screenshot_2024-11-04_at_2.30.36_PM.png)
    
- components can be considered as being **deployed in containers**
    - a **container** is an **implementation of these services plus a definition of the interfaces** a component must provide to integrate it with the container

## CBSE process

- CBSE processes are **software processes that support component-based software engineering**
    - **development for reuse**: process concerned with **developing components or services that will be reused** in other applications
    - **development with reuse**: process of **developing new applications using existing components** and services

![Screenshot 2024-11-04 at 2.31.52 PM.png](software%20reuse%20134b756f812280c6a5dfc68192033d69/Screenshot_2024-11-04_at_2.31.52_PM.png)

### supporting processes

- component acquisition is the **process of acquiring components for reuse or development into a reusable component**
    - it may involve **accessing locally-developed components** or services or **finding these components from an external source**

- **component management** is concerned with **managing a company’s reusable components**, ensuring that they are **properly catalogued, stored and made available for reuse**

- **component certification** is the process of checking a component and **certifying that it meets its specification**

# service-oriented

- service-oriented SE is a way of **building distributed applications using web services**
    - a **web service** is a loosely coupled, **reusable software entity that encapsulates discrete functionality**, which may be **distributed and programmatically accessed**
- service-oriented SE vs. component-based SE
    - when you build a service-oriented system, **you reference the external service**
    - **each system that reused a component had to incorporate its own copy** of that component
    - components are **deployed in containers and rely on the containers’ support to communicate with each other**— **services communicate based on established protocols** (e.g., HTTP, HTTPS) and data format (e.g., XML, Schemata)

### benefits

1. **services can be offered by any service provider** inside or outside of an organization
2. the service provider **makes information about the service public** so that any authorized user can use the service
3. **applications can delay the binding of services until they are deployed** or until execution
4. **opportunistic construction** of new services is possible
5. **service users can pay for services according to their use** rather than their provision
6. **applications can be made smaller**, which is particularly important for mobile devices with limited processing and memory capabilities

## service-oriented architecture

- (SOA) is an architectural style that focuses on the **use of services to support business requirements**
    - service providers **design and implement services** and **specify the interface to these services**
    - service providers also **publish information about these services in an accessible registry**
    - **service requestors** (sometimes called service clients) who wish to make use of a service **discover the specification of that service and locate the service provider**
    - service requestors can then **bind their application to that specific service** and communicate with it, using standard service protocols

## service engineering

- the process of **developing services for reuse in service-oriented applications**
    - **service candidate identification**, where you **identify possible services that might be implemented** and **define the service requirements**
    - **service design**, where you **design the logical service interface** and its **implementation interfaces**
    - **service implementation and deployment**, where you **implement and test the service** and make it available for use

![Screenshot 2024-11-04 at 2.35.35 PM.png](software%20reuse%20134b756f812280c6a5dfc68192033d69/Screenshot_2024-11-04_at_2.35.35_PM.png)