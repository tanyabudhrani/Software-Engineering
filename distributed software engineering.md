# distributed software engineering

Created: November 9, 2024 9:49 PM
Tags: LEC

# distributed systems

- virtually all large computer-based systems are **now distributed systems**, where a collection of **independent computers appears to the user as a single coherent system**
- five benefits of developing systems as distributed systems
    - **resource sharing**
    - **openness**
    - **concurrency**
    - **scalability**
    - **fault tolerance**

# distributed systems issues

- distributed systems are **more complex** than systems that run on a single processor
    - **a top-down model of control of the system is impossible**
- design issues
    - **transparency**
    - **openness**
    - **scalability**
    - **security**
    - **quality of service**
    - **failure management**

## transparency

- ideally, **users should not be aware that a system is distributed**, and **services should be independent of distribution characteristics**
    - to achieve transparency, **resources should be abstracted and addressed logically rather than physically**, e.g., via middleware
- it is often better to make users aware of the distribution **so that they can cope with problems**— in practice, this is impossible
    - **individual computers may behave differently at different times**
    - the **length of network delays** depends on a number of things
- users are aware that they are dealing with a distributed system

## openness

- open distributed systems are **systems that are built according to generally accepted standards**
- components can be **independently developed in any programming language by different suppliers and integrated into the system to inter-operate with the other system components** that conform to standards
- **web service standards for service-oriented architectures were developed to be open standards**

## scalability

- the scalability of a system reflects its **ability to deliver high- quality service as demands on the system increase**
    - **size**: the number of users
    - **distribution**: the **locations of system components**
    - **manageability**: the **management of system components**
- scaling-up vs scaling-out
    - scaling up means **replacing resources in the system with more powerful resources**
    - scaling out means **adding more resources to the system**
    - **scaling out is often more cost-effective** than scaling up

## security

- when a system is distributed, **the number of ways that the system may be attacked is significantly increased** compared to centralized systems
    - types of attack
        - interception
        - interruption
        - modification
        - fabrication
        - back doors
- **mutually incompatible security policies and security mechanisms** for different parts of the system

## quality of service

- the QoS offered by a distributed system **reflects the system’s ability to deliver its services dependably and efficiently**
- the QoS requirements should be **specified in advance**, and the system should be **designed and configured to deliver that QoS**
    - it is not always practical
        - undesirable to design and configure the system to **deliver a high quality of service under peak load**
        - the QoS parameters may be **mutually contradictory**

## failure management

- distributed systems should **include failure discovery, tolerance, and recovery mechanisms** because failures are inevitable in such systems

- fault-tolerant architectures
    - **protection systems**
    - **n-version programming**

- programming for reliability
    - **information hiding**
    - **avoid magic numbers**
    - **check boundary values**

## models of interaction

- two types of interaction between components in a distributed system
    - **procedural interaction**, where **one computer calls on a known service offered by another computer** and waits for a response
    - **message-based interaction**, which involves the **sending computer sending information to another computer**— there is **no necessity to wait for a response**

![Screenshot 2024-11-09 at 9.59.27 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_9.59.27_PM.png)

## remote procedure calls

- procedural communication in a distributed system is **implemented using remote procedure calls** (RPC)
    - in a remote procedure call, **one component calls another component as if it was a local procedure or method**
    - the **middleware** in the system **intercepts this call and passes it to a remote component**
    - **the remote component carries out the required computation and, via the middleware, returns the result to the calling component**
- a problem with RPCs is that **the caller and the callee need to be available at the time of the communication, and they must know how to refer to each other**

## message passing

- message-based interaction normally involves **one component creating a message that details the services required from another component**
    - through the system middleware, **this is sent to the receiving component**
    - **the receiver parses the message, carries out the computations, and creates a message for the sending component with the required results**
- in a message-based approach, it is **not necessary for the sender and receiver to be aware of each other**— they simply **communicate with the middleware**

## middleware

- middleware is software that **can manage the diverse parts in a distributed system and ensure they can communicate and exchange data**
    - the components in a distributed system may be **implemented in different programming languages, execute on different types of processors, and be based on different data models, information representations, and communication protocols**

![Screenshot 2024-11-09 at 10.01.51 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.01.51_PM.png)

# client-server computing

- distributed systems accessed over the internet are **normally organized as client-server systems**
    - in a client-server system, **the user interacts with a program running on their local computer, which interacts with another program running on a remote computer**
    - the remote computer provides services that are **available to external clients**

![Screenshot 2024-11-09 at 10.02.39 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.02.39_PM.png)

| presentation | concerned with presenting information to the user and managing all user interactions |
| --- | --- |
| data handling | m**anages the data that is passed to and from the client**

implement **checks on the data**, generate web pages, etc |
| application processing layer | concerned with **implementing the logic of the application and so providing the required functionality** to end users |
| database | **stores data and provides transaction management services**, etc |

# architectural patterns

- widely used ways of **organizing the architecture of a distributed system**
    - master-slave architecture
    - two-tier client-server architecture
    - multi-tier client-server architecture
    - distributed component architecture
    - peer-to-peer architecture

## master-slave architecture

- commonly used in **real-time system**
    - in those systems, **separate processors may be associated with data acquisition** from the system’s environment, data processing and computation, and actuator management
    - the ‘**master**’ process is usually responsible for **computation, coordination, and communications and controls the ‘slave’ processes**
    - the ‘**slave**’ processes are dedicated to **specific actions, such as acquiring data from an array of sensors**

![Screenshot 2024-11-09 at 10.07.46 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.07.46_PM.png)

## two-tier client server

- the system is implemented as **a single logical server plus an indefinite number of clients** that use that server
    - **thin-client model**, where the **presentation layer is implemented on the client,** and **all other layers** (data handling, application processing, and database) **are implemented on a server**
    - **fat-client model**, where **some or all of the application processing is carried out on the client**— **data handling and database functions are implemented on the server**

![Screenshot 2024-11-09 at 10.08.55 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.08.55_PM.png)

## thin and fat clients

- **thin client model**
    - an advantage is that it is **simple to manage the clients**, which is important when there are a large number of clients
    - a major disadvantage is that it **places a heavy processing load on both the server and the network**

- **fat client model**
    - **more complex** than a thin client model especially for management
    - **new versions of the application have to be installed on all clients**
- distinction between thin and fat client architectures has **become blurred**
    - java script allows local processing in a browser so ‘fat-client’ functionality is available without software installation
    - mobile apps carry out some local processing to minimize demands on the network
    - auto-update of apps reduces management problems
- in practice, **very few web-based applications implement all processing on remote servers now**

## multi-tier client-server

- **the different layers of the system are separate processes that may execute on different processors**
    - this avoids some problems with the thin-/fat-client two-tier models
- example: three-tier architecture for an internet banking system
    - from three-tier to multi-tier
        - **adding an integration server that collects data from multiple databases and presents it to the application server as if it were from a single database**

![Screenshot 2024-11-09 at 10.13.44 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.13.44_PM.png)

## distributed component architecture

- there is **no distinction in a distributed component architecture between clients and servers**
    - each distributable entity **is a component that provides services to other components and receives services from other components**
    - component communication is through a **middleware system**
- a distributed component architecture

![Screenshot 2024-11-09 at 10.16.11 PM.png](distributed%20software%20engineering%20139b756f812280cd9927d5a4c7d7310d/Screenshot_2024-11-09_at_10.16.11_PM.png)

| advantages | disadvantages |
| --- | --- |
| the system designer **can delay decisions on where and how services should be provided** | they are **more complex to design than client–server systems** |
| **new resources can be added as required** | there are **no universal standards for distributed component models** or middleware |
| the systems can be **easier to extend or reconfigure** |  |
- **service-oriented architectures are replacing distributed component architectures** in many situations

## peer-to-peer

- decentralized systems where **computations may be carried out by any node in the network**
    - the overall system is designed to **take advantage of the computational power and storage of many networked computers**
    - the systems are **harder to monitor, which leads to a higher level of communication privacy**, since there are no central servers
- the logical network architecture
    - **decentralized architectures**
    - **semi-centralized architectures**
- use of P2P architecture

- when a system is **computationally intensive**, and **it is possible to separate the processing required into a large number of independent computations**

- when a **system primarily involves the exchange of information between individual computers on a network**, and there is **no need for this information to be centrally-stored or managed**

### security issues

- **security concerns are the principal reason why p2p architectures are not widely used**
    - the **lack of central management** means that **malicious nodes can be set up to deliver spam and malware** to other nodes in the network
    - P2P communications **require careful setup to protect local information**— if not done correctly, your **system is insecure and vulnerable to external corruption**

# software as a service

- software as a service (SaaS) involves **hosting the software remotely and providing access to it over the internet**
    - software is **deployed on a server** (or more commonly a number of servers) and is **accessed through a web browser**
    - it is **not deployed on a local PC**
    - the software is **owned and managed by a software provider rather than the organizations using the software**
    - users may **pay for the software according to their use** or through an annual or monthly subscription
- implementation factors
    - **configurability**
    - **multi-tenancy**
    - **scalability**

| advantages | disadvantages |
| --- | --- |
| for service providers, **the number of servers can quickly change to match the user demands** for that service, and **the costs for these providers have been dramatically reduced** | **data transfer with the remote service** |
| for software purchasers, **the costs of management of software are transferred to the provider**, and the software may be accessed from different devices | **lack of control over software evolution** and problems with laws and regulations |

## saas and sos

- SaaS is a way of **providing functionality on a remote server with client access through a web browser**
    - **the server maintains the user’s data and state during an interaction session**— transactions are usually long transactions, e.g., editing a document
    - SaaS applications for business may be **implemented using components rather than services**

- SOA is an approach to **structuring a software system as a set of separate, stateless services**
    - these may be provided by **multiple providers and may be distributed**— typically, **transactions are short transactions where a service is called, does something then returns a result**
    - systems that are implemented using SOA **do not have to be accessed by users as web services**