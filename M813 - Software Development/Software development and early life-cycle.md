# Software development processes
Although effective software development processes remain the holy grail of software development, there are some fundamental development activities that are well understood and common to most approaches:
-  **Analysis** involves understanding the problem which the software is intended to solve, i.e., the requirements in context, with **validation** as the means to check that understanding.
-   **Design** involves describing, conceptually, a software solution that meets the requirements of the problem.
-   **Implementation** involves realising such a solution in software.
-   **Testing** involves making sure that the solution has certain inherent qualities, with **verification** as a means to check its adequacy with respect to the specified requirements and **validation** as a means to check that the solution does address the problem.
-   **Deployment** involves making the developed solution available in its context of operation and use.

> Note: **validation** and **verification** are sometimes confused. One way to understand the distinction is to think of validation as addressing the question ‘are we solving the right problem?’ and verification as addressing the question ‘are we solving the problem right?’

The full **software life-cycle** also includes:

-   **Maintenance**: makes sure that the deployed solution continues to address the problem throughout the time it is in operation, and handles its **decommissioning** at the end of the life-cycle.
> Note: Although software maintenance is a well understood term, some authors prefer to talk about **software evolution**, meaning that software continually changes over its life-cycle, with changes often triggered by changes in context and in stakeholders’ needs. As a consequence, software development activities typically carry on post-deployment as new releases of the software are developed and deployed.

# OOP basics
When we design software with the objects in mind around which actions revolve, we call it an **object-oriented** approach.

To represent real-world objects or conceptual units, we use objects. We define what and how is accessible of that object from the relative outside world, and we do that by **encapsulating** the object and by defining an **interface** for it.

In most languages an object is defined as an **instance** of a homogeneous **class**, wioth the class prividing an abstraction for the common characteristics of all its instances.

Classes can have relations between objects and between other classes, which makes up for an even higher degree of design possibilities: We say objects are instances of classes, classes can have child-parent relations, and classes can be treated _as_ other classes. This creates ground for **polymorphism**, **inheritance** and **abstraction** along with encapsulation. These four concepts consist the basic principles of object-oriented programming.

Serious software systems consists of multiple objects, however. **Collaboration** occurs when one object requests a service from another object in order to perform some task. To fulfil a particular collaboration, each object takes on a different role: the object that makes the request can be seen as the **client**, and the object that receives the request (and provides the service in response) as the **supplier**. The request is communicated to the supplier from the client by **message passing** based on the objects’ interfaces: the client sends a **message** to the supplier which on receipt executes a corresponding operation; when the supplier has completed the execution of its operation it returns a **message answer** to the client.
