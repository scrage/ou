**Stakeholders** are individuals and/or organisations that are affected by the success or failure of the system. Typical stakeholders include: customers (who are going to pay for the system), users (who are going to use the system) and software developers (who are going to design and build the system).
    
**Requirements** are the expression of the things the system must do or the qualities the system must have in order to meet the stakeholders’ need in their context.

Eliciting and analysing requirements are fundamental activities in any software development process.

**Elicitation** is the activity of discovering and describing requirements, most often in consultation with stakeholders.

**Analysis** is the activity of elaborating the elicited requirements in terms of understanding their real-world context and their impact on the way the system should be designed, and leading to descriptions of the system’s intended interaction with users in their context.

# Requirement properties

 Characteristics a set of requirements should possess:
 -   **necessary** – each requirement should fulfil a purpose
-   **traceable** – it should be clear where each requirement comes from
-   **non-ambiguous** – there should be no alternative interpretations of a requirement
-   **feasible** – it should be possible to carry each through to development
-   **consistent** – requirements should not contradict each other
-   **testable** – it should be possible to check that a requirement has been implemented.

A **fit criterion** is a quantification or measurement of a requirement that will ultimately enable a tester to determine whether or not the delivered solution satisfies that requirement.

Note: another common term encountered is **acceptance criterion**, in particular when set by the customer as the basis for accepting the product at the end of development.

Fit criteria must be capable of being tested in an objective fashion: they are like benchmarks that allow the tester to compare the delivered solution against the original requirements. Fit criteria which are set by the customer are often part of the contract between the customer and developers, on the basis of which the customer can decide to accept or reject the product developed.

>-   **Requirement:** The ATM machine will allow the customer to make a withdrawal as fast as possible.
>   ** Fit criterion:** 90% of experienced customers should take no more than 30 seconds to make a withdrawal.
>-   **Requirement:** The public information kiosk will be usable by a member of the public who may not speak or read English.
 >   **Fit criterion:** Of every 20 users who do not speak and/or read English, 15 will be able to use the kiosk without either referring to the online help or walking away without the desired information.
>-   **Requirement:** The railway ticketing machine will be usable in a very humid environment.
>    **Fit criterion:** The product will function correctly even when exposed to a humidity of greater than 80% for up to 48 hours at a time.
>-  ** Requirement:** The product procurement prices will only be accessible to warehouse staff.
>    **Fit criterion:** Non-warehouse staff will be unable to access product procurement prices.

# Requirement types
Software requirements are often classified as:
-   **Functional requirements**: things the software must do; and
-   **Quality requirements** (also known as non-functional requirements): properties the software must have.

# Documenting requirements
Requirements need to be documented within a project for many reasons: requirements documents are often the basis of contractual agreements between customers and suppliers; they are the starting point on the basis of which the system is specified, designed and built; and they are the basis for the validation and verification of the system, once it is built.

> ## Requirements document template
> This has three sections.
> 
 >_Product overview_
> In this section you should record the following types of information.
>-   Purpose of the product: the reason for building the product, and the business advantage gained. This requirement describes the problem faced by the customer or a business opportunity the customer wants to exploit, and explains how the product will help here. For instance:
>-   We are expanding our business internationally. Our current billing system is based on sterling, but we need a new system that can deal with non-UK currency.
>-   Stakeholders (including customers and users): the people and organisations with a vested interest in the product as well as the intended end-users of the product. Their description should also include how they affect the product’s usability requirements. For instance:
>-   The users of the system would be rail passengers – i.e., people interested in train timetables and journey information. We can’t assume that such users would be in any way familiar with the technology; they should be able to use the system with hardly any support.
>
> _Product functionality_
> Here you should include the following.
>-   Scope of the product: this defines the product boundaries. To be able to set such boundaries you first need to understand the context of the system, i.e. the working environment in which it will operate.
>-   Functional requirements: what the product must do to contribute to the product goal. These could be functions or actions that the product must perform. For instance:
		>     -   The product should record weather conditions on the road
is a function, while
		>     -   The product should alert the operator when the temperature falls below 0°C
is an action.
>
>_Quality requirements_
These are the properties the product must have. They may include (but will not be limited to) the following.
>
>-   ‘Look-and-feel’ requirements: the intended appearance of the product.
>-   Usability requirements: based on the intended users.
>-   Performance requirements: how fast, accurate, reliable, and so on the product must be.
>-   Operational requirements: the product’s intended operating environment.
>-   Maintainability and portability requirements: how easily the product can change.
>-   Security requirements: the security, confidentiality and integrity of the product.
>-   Cultural and political requirements: human factors that may affect the product.
>-   Legal and compliance requirements: conformance of the product to applicable laws, regulations or standards.

>## Requirement template
**Requirement number**: to identify the requirement uniquely.
**Description**: a one-sentence statement of the intent of the requirement.
**Rationale**: why the requirement is considered important or necessary.
**Source**: who raised the requirement in the first instance.
**Fit criteria**: criteria written in a quantified manner so that the solution can be tested against the requirement.
**Dependencies**: other requirements that have an impact on this one.
**Conflicts**: requirements that contradict this one, or make this one less feasible.
**History**: origin of and changes to the requirement.

# Use cases
A **use case** represents one way to use the system to achieve a specific goal, from a user’s viewpoint.

A use case has three essential components:
-   **goal**: what the user wants to achieve through his or her use of the system; the use case must deliver a clear benefit in helping the user achieve his or her goal
-   **start and stop points**: every use case must have a definite starting point, and there must also be a clear condition which indicates that the use case is complete
-   **external initiator**: every use case is initiated by an entity outside the system – say, a user or another system or device.

A use case abstracts a sequence of interactions between the actor and the system, usually referred to as a **scenario**. Many scenarios are possible. First, we consider the so-called **main scenario** or **success scenario**, which captures a typical interaction between actor and system in which the goal is met. Later on we will see how this scenario can be extended to capture other scenarios.

A use case also has to account for situations in which things don’t go according to plan: it must provide a way to capture alternative scenarios which deviate from the main scenario and could lead to success or failure, depending on whether the goal is met. This is done through **extensions**. An extension refers to a specific step within the success scenario from which an alternative path may branch out.

Use cases can be ranked by order of importance and should be developed in that order. Risk, coverage and criticality should be considered criteria for deciding which use case should be covered in each development iteration.

**Risk**: high-risk use cases should be handled as early as possible. The following risk factors should be considered: poorly defined requirements, complexity of requirements, unknown required effort (e.g., significant research, new and uncertain technology), or political issues.

**Coverage**: the initial set of use cases should provide a good overview of the whole system, allowing for an early definition of the latter’s overall structure (‘software architecture’) that will influence the rest of the development.

**Criticality**: the critical functions of the system should be covered early – with their criticality established, for instance, in terms of business value and main business processes.


