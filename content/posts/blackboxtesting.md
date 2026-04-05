+++
date = '2026-04-05T23:11:47+05:30'
draft = false
title = 'Black Box Testing'
image = '/images/Black Box Testing.png'
weight = 2
+++

#### __By Garvit Singh__

__What is Black Box Testing?__
- Black box testing is done to know the external functionality of what the product should do.
- Doesn't look at the program code but looks at the product from an external perspective.
- Done without the knowledge of internals of system under test.
- Done from the customer's viewpoint.
- The test engineer engaged in BBT only knows set of inputs and expected outputs, and is unaware of how these inputs are processed internally by the product.
- Convenient to administer because they use the complete finished product and do not require any knowledge of its construction.

==Why Black Box Testing?==  
BBT helps in overall functionality verification of the system under test.
1. Done based on requirements. Helps in identifying any incomplete, inconsistent requirements or issues involved when the system is tested as a complete entity.
2. Addresses the stated requirements as well as implied requirements. All requirements are not stated explicitly, but are deemed implicit.
3. Encompasses the end user perspectives.
4. Handles valid and invalid inputs.

<div style="page-break-after: always;"></div>

==When To Do Black Box Testing?==
- BBT requires involvement of the testing team right from the beginning of the software project life cycle. 
- Testers get involved right from requirements gathering phase. 
- Test scenarios and test data are prepared during the test construction phase of the test life cycle, when the software is in design phase.
- Once the code is ready and delivered for testing, test execution is done. 
- All the test scenarios developed during the construction phase are executed.
- A subset of these test scenarios are selected for regression testing.

<div style="page-break-after: always;"></div>

==How To Do Black Box Testing?==
BBT exploits specifications to generate test cases in a methodical way to avoid redundancy and to provide better coverage. The techniques include :
1. Requirements Based Testing
2. Positive Testing
3. Negative Testing
4. Boundary Value Analysis
5. Decision Tables
6. Equivalence Partitioning
7. State Based or Graph Based Testing
8. Compatibility Testing
9. User Documentation Testing
10. Domain Testing

<div style="page-break-after: always;"></div>

**Requirements Based Testing**
- Requirements testing deals with validating the requirements given in the Software Requirements Specification(SRS) of the software product.
- Explicit requirements are stated and documented clearly in the SRS. Implied or implicit requirements are those that are not documented but assumed to be incorporated in the system.
- Precondition is a detailed review of the requirements specifications to ensure they are consistent, correct, complete and testable.
- The review ensures that some implied requirements are converted and documented as explicit requirements, making the testing more effective.
- All explicit and implied requirements are collected and documented as '*Test Requirements Specification(TRS)*'.
- The TRS documented is used for Requirements based testing.
- Requirements are tracked by a '*Requirements Traceability Matrix(RTM)*'. An RTM traces all the requirements from their beginning through design, development and testing.
- The matrix evolves through the life cycle of the project. Each requirement is given a unique id along with a brief description, which are taken from the Requirements specification.
- The requirements are named with a naming convention, which depends on each organization.
- Each requirement is assigned a requirement priority, classified as high, medium or low. Tests for high priority requirements will get precedence over low priority ones, which ensures that the functionality with high risk or high stakes is tested earlier, and the defects fixed at the earliest.
- The RTM contains columns like '*test conditions*', '*test case IDs*' and '*phase of testing*'.
- A requirement is subjected to multiple phases of testing - unit, component, integration, system testing etc.

The RTM helps in identifying the relationship between the requirements and test cases. The following combinations are possible:
1. One to one
2. One to many
3. Many to one
4. Many to many
5. One to none

The Requirements Traceability Matrix or RTM provides a wealth of information on various test metrics:
1. Requirements addressed priority wise helps addressing the high priority requirements first.
2. Number of test cases requirement wise
3. Total number of test cases prepared.

Once the test cases are executed, the test results can be used to collect metrics such as:
1. Total number of test cases passed.
2. Total number of test cases failed.
3. Total number of defects in requirements.
4. Number of requirements completed.
5. Number of requirements pending.

These metrics can also be displayed graphically to better visualize what we are dealing with.

<div style="page-break-after: always;"></div>

**Positive Testing**
- Positive testing tries to prove that a given product does what it is supposed to do.
- When a test case verifies the requirements of the product with a set of expected output, it is called positive test case.
- The purpose of positive testing is to prove that the product works as per specification and expectation.
- A product delivering an error when it is expected to give an error, is also a part of positive testing.
- Positive testing is done to verify the known test conditions.

<div style="page-break-after: always;"></div>

 **Negative Testing**
 - Negative testing is done to show that the product does not fail when an unexpected input is given.
 - The purpose of negative testing is to try and break the system with unknowns.
 - Covers scenarios for which the product is not designed and coded. The input values may not have been represented in the specification of the product. These are termed as unknown conditions.
 - It is important to know for testers to know the negative situations that may occur at end-user level so that the application can be tested and made foolproof.
 - A negative test would be a product not delivering an error when it should or delivering an error when it should not.

The difference between Positive and negative testing is in their coverage. For positive testing, if all documented requirements and test conditions are covered, then coverage can be said to be 100 percent. In contrast, there is no end to negative testing, and 100 percent coverage is impractical. Negative testing requires a high degree of creativity among the testers to cover as many unknowns as possible to avoid failure.

<div style="page-break-after: always;"></div>

**Boundary Value Analysis**
- Most of the defects in software product hover around *conditions* and *boundaries*. Boundaries means the 'limits' of values of the various variables.
- BVA is useful for catching defects that happen at boundaries. It believes that the density of defects is more towards boundaries.
- Boundary Value Analysis is useful to generate test cases when the input(or output) data is made up of clearly indentifiable boundaries or ranges.
- Another instance where boundary value testing is extremely useful in uncovering defects is when there are internal limits placed on certain resources, variables, or data structures.
- Look for any kind of gradation or discontinuity in data values which affect computation - the discontinuities are the boundary values, which require thorough testing.
- Look for internal limits on resources.
- Look for documented limits on hardware resources.
- BVA applies for white box testing as well. Internal data structures like arrays, stacks etc need to be checked for boundary or limit conditions. The way linked lists behave in the beginning and ending have to be tested thoroughly.
- Boundary values and decision tables help identify the test cases that are most likely to uncover defects. A generalization of both these concepts is the concept of *equivalence classes*.

<div style="page-break-after: always;"></div>

**Decision Tables**
A *decision table* lists the various decision variables, the conditions assumed by each of the decision variables, and actions to take in each combination of conditions.

The steps in forming a decision table are as follows:
1. Identify the decision variables.
2. Identify the possible values of each of the decision variables.
3. Enumerate the combinations of the allowed values of each of the variables.
4. Identify the cases when values assumed by a variable are immaterial for a given combination of other input variables. Represent such variables by 'dont care' symbol, which is usually the greek character *phi*.
5. For each combination of values of decision variables, list out the action or expected result.
6. From a table, listing in each but the last column a decision variable. In the last column, list the action item for the combination of variables in that row, including dont cares, as appropriate.

<div style="page-break-after: always;"></div>

**Equivalence Partitioning**
- Equivalence partitioning is a software testing technique that involves identifying a small set of representative input values that produce many different outputs conditions as possible.
- Reduces the effort involved in testing and increases coverage.
- The set of input values that generate one single expected output is called a *partition*.
- When the behavior of the software is the same for a set of values, then the set is termed as an *equivalence class* or a *partition*.
- One representative sample from each partition, also called member of equivalence class is picked up for testing.
- The benefits of using equivalence classes : choosing a minimal set of input values that are truly representative of the entire spectrum and uncovering a higher number of defects.
- Equivalence partioning is useful to minimize the number of test cases when the input data can be divided into distinct sets, where the behaviour or outcome of the product within each member of the set is the same.

The equivalence partitions table has columns:
1. Partitions definition
2. Type of input(valid/invalid)
3. Representative test data for that partition
4. Expected results

The steps to prepare an equivalence partitions table are:
1. Choose criteria for doing the equivalence partitioning(range, list of values etc).
2. Identify the valid equivalence classes based on the above criteria.
3. Select a sample data from that partition.
4. Write the expected results based on the requirements given.
5. Identify special values, if any, and include them in the table.
6. Check to have expected results for all the cases prepared.
7. If the expected result is not clear for any particular test case, mark it and escalate for corrective actions.

<div style="page-break-after: always;"></div>

**State Based or Graph Based Testing**
State or graph based testing is useful in situations where:
1. The product under test is a language processor(like a compiler), wherein the syntax of the language automatically lends itself to a state machine.
2. Workflow modeling, where, depending on the current state and appropriate combinations of input variables, specific workflows are carried out, resulting in new output and state.
3. Dataflow modeling, where the system is modeled as a set of dataflow, leading from one state to another.

![](https://i.imgur.com/ZFdesTj.png)

A general outline for using state based testing methods with respect to language processors is :
1. Identify the grammar for the scenario.
2. Design test cases corresponding to each valid state-input combination.
3. Design test cases corresponding to the most common invalid combinations of state-input.

<div style="page-break-after: always;"></div>

**Compatibility Testing**
Compatibility Testing(CT) is done to ensure that the product features work consistently with different infrastructure components is called compatibility testing. Requires high degree of effort as there are a large number of parameter combinations.

The parameters that generally affect the comptability of the product are:
1. Processor and number of processors.
2. Architecture(32bit, 64bit and so on).
3. Resource availability(RAM, disk space, network card etc).
4. Equipment that the product is expected to work with.
5. Operating system.
6. Middle-tier infrastructure components such as web server, application server, network server.
7. Backend components such as database servers.
8. Services that require special hardware-cum-software solutions like clusters, load balancers etc.
9. Any software used to generate product binaries.
10. Various technological components used to generate components(SDK, JDK etc).

A *compatibility matrix* is created. It has its columns as various parameters the combinations of which have to be tested. Each row represents a unique combination of a specific set of values of the parameters.

Techniques for CT include:
1. Horizontal Combination
2. Intelligent Sampling

Compatibility testing of a product involving parts of itself can be classified into two types:
1. Backward compatibility testing
2. Forward compatibility testing

<div style="page-break-after: always;"></div>

**User Documentation Testing**
User documentation covers all the manuals, user guides, installation guides, setup guides, read me file, software release notes, and online help that are provided along with the software to help the end user to understand the software system.

User documentation testing has two objectives:
1. To check if what is stated in the document is available in the product.
2. To check if what is there in the product is explained correctly in the document.

Benefits of user documentation testing include:
1. User documentation testing aids in highlighting problems overlooked during reviews.
2. Ensures consistency of documentation and product.
3. Results in less difficult calls for the support staff.
4. New programmers and testers who join a project group can use the documentation to learn the external functionality of the product.
5. Customers need less training and can proceed more quickly to advanced training and product usage if the documentation is of high quality and is consistent with the product.

<div style="page-break-after: always;"></div>

**Domain Testing**
 - Domain testing goes beyond white box and black box testing, where we do not even look at the specifications of a software product but are testing the product, purely based on domain knowledge and expertise in the domain of application.
 - This testing approach requires critical understanding of the day to day business activities for which the software is designed.
 - Domain testing is an extension of black box testing.
 - The test engineers performing this type of testing are selected because they have in-depth knowledge of the business domain.
 - Domain testing exploits the tester's domain knowledge to test the suitability of the product to what the users do on a typical day.
 - Domain testing is the ability to design and execute test cases that related to the people who will buy and use that software.
 - Domain testing involves testing the product, not by going through the logic built into the product. The business flow determines the steps, not the software under test. This is also called 'business vertical testing'.
 - Domain testing is done after all components are integrated and after the product has been tested by other black box techniques.

| Scenarios | Most Effective Black Box Testing Technique |
| ---- | ---- |
| Output values dictated by certain conditions depending upon values of input variables. | Decision Tables |
| Input values in ranges, with each range exhibiting a particular functionality. | Boundary Value Analysis |
| Input values divided into classes, with each class exhibiting a particular functionality. | Equivalence Partitioning |
| Checking for expected and unexpected input values. | Positive & Negative Testing |
| Workflows, process flows, or language processors. | Graph or State Based Testing |
| To ensure that requirements are tested and met properly. | Requirements Based Testing |
| To test domain expertise rather than product specification. | Domain Testing |
| To ensure that the documentation is consistent with the product. | Documentation Testing |

<div style="page-break-after: always;"></div>

###### Integration Testing
- A system is made up of multiple components or modules comprising hardware and software.
- Integration is defined as the set of interactions among components.
- Testing the interaction between the modules and interaction with other systems externally is called integration testing.
- Integration testing is done to make sure that the different components fit together.
- The final round of integration involving all components is called Final Integration Testing (FIT), also known as System Integration.
- Integration is both a phase and a type of testing.
- 4 orders of integration testing : Top-down integration, Bottom-up integration, Bi-directional integration, System integration.

**Top-Down Integration**
![](https://i.imgur.com/fTonekE.png)

Step Interfaces tested
1. 1-2
2. 1-3
3. 1-4
4. 1-2-5
5. 1-3-6
6. 1-3-6-(3-7)
7. (1-2-5)-(1-3-6-(3-7))
8. 1-4-8
9. (1-2-5)-(1-3-6-(3-7))-(1-4-8)

- The integration starts with testing the interface between component 1 and component 2, then component 1 and 3 and so on.
- To optimize the number of steps in integration testing, steps 6 and 7 can be combined and executed as a single step.
- Similarly, steps 8 and 9 also can be combined and tested in a single step.

<div style="page-break-after: always;"></div>

**Bottom-Up Integration**
![](https://i.imgur.com/0cR7thv.png)

Step Interfaces tested
1. 1-5
2. 2-6, 3-6
3. 2-6-(3-6)
4. 4-7
5. 1-5-8
6. 2-6-(3-6)-8
7. 4-7-8
8. (1-5-8)-(2-6-(3-6)-8)-(4-7-8)

- Bottom-up integration is just the opposite of top-down integration, where the components for a new product development become available in reverse order, starting from the bottom.

<div style="page-break-after: always;"></div>

**Bi-Directional Integration**
![](https://i.imgur.com/REtTbBD.png)

Step Interfaces tested
1. 6-2
2. 7-3-4
3. 8-5
4. (1-6-2)-(1-7-3-4)-(1-8-5)

- Bi-directional integration is a combination of the top-down and bottom-up integration together to derive integration steps.
- Comes handy when migrating from a two-tier to a three-tier environment.

<div style="page-break-after: always;"></div>

**System Integration**
System integration means that all the components of the system are integrated and tested as a single unit.

Integration testing, which is testing of interfaces, can be divided into two types:
1. Components or sub-system integration
2. Final integration testing or system integration

Instead of integrating component by component and testing, this approach waits till all components arrive and one round of integration testing is done.

This approach is also called *big-bang integration.* It reduces testing effort and removes duplication in testing.

Big bang integration is ideal for a product where the interfaces are stable with less number of defects.

While this approach saves time and effort, it is also not without disadvantages:
1. When a failure or defect is encountered during system integration, it is very difficult to locate the problem, to find out in which interface the defect exists. The debug cycle may involve focusing on specific interfaces and testing them again.
2. The ownership for correcting the root cause of the defect may be a difficult issue to pinpoint.
3. When integration testing happens in the end, the pressure from the approaching release date is very high. This pressure on the engineers may cause them to compromise on the quality of the product.
4. A certain component may take an excessive amount of time to be ready. This precludes testing other interfaces and wastes time till the end.

Choosing Integration Method

| Factors | Suggested Integrated Method |
| ---- | ---- |
| Clear requirements and design. | Top-down |
| Dynamically changing requirements, design, architecture. | Bottom-up |
| Changing architecture, stable design. | Bi-directional |
| Limited changes to existing architecture with less impact. | Big bang |

<div style="page-break-after: always;"></div>

**Integration Testing as a Phase of Testing**
- Starts from the point where two components can be tested together, to the point where all the components work together as a complete system, delivering the product functionality.
- It tests how different components work in isolation and also when they are connected to each other.
- Focuses predominantly on defects that arise due to combing various components.
- Focuses on interfaces as well as usage flow.
- When the functionality of different components are combined and tested together for a sequence of related operations, they are called *scenarios.*

<div style="page-break-after: always;"></div>

**Scenario Testing**
- Scenario testing is a planned activity to explore different usage patterns and combine them into test cases called scenario test cases.
- Scenario testing is defined as a “set of realistic user activities that are used for evaluating the product.”
- It is also defined as the testing involving customer scenarios.
- Two methods to create scenarios : System Scenarios & Use-case/Role-based Scenarios

<div style="page-break-after: always;"></div>

==*System Scenarios*==
System scenario is a method whereby the set of activities used for scenario testing covers several components in the system. Follow these approaches : 
1. Story line - Develop a story line that combines various activities of the product that may be executed by an end user.
2. Life cycle/state transition - Consider an object, derive the different transitions/modifications that happen to the object, and derive scenarios to cover them.
3. Deployment/implementation stories from customer - Develop a scenario from a known customer deployment/implementation details and create a set of activities by various users in that implementation.
4. Business verticals - Visualize how a product/software will be applied to different verticals and create a set of activities as scenarios to address specific vertical businesses.
5. Battle ground - Create some scenarios to justify that “the product works” and some scenarios to “try and break the system” to justify “the product doesn't work.”
6. These approaches have to be used in combination, not in isolation

==*Use Case Scenarios*==
A use case scenario is a stepwise procedure on how a user intends to use a system, with different user roles and associated parameters.

<div style="page-break-after: always;"></div>

**Defect Bash**
1. Defect bash is an ad hoc testing where people performing different roles in an organization test the product together at the same time.
2. Ad hoc testing means that the testing is unplanned.
3. The testing by all the participants during defect bash is not based on written test cases.
4. What is to be tested is left to an individual's decision and creativity.

<div style="page-break-after: always;"></div>

==Good Practices Encouraged By Defect Bash==
1. Enabling people cross boundaries and test beyond assigned areas.
2. Bringing different people performing different roles together in the organization for testing. Testing isn't for testers alone.
3. Letting everyone in the organization use the product before delivery.
4. Bringing fresh pairs of eyes to uncover new defects.
5. Bringing in people who have different levels of product understanding to test the product together randomly.
6. Let testing doesn't wait for lack of/time taken for documentation.
7. Enabling people to say “system works” as well as enabling them to “break the system”.

<div style="page-break-after: always;"></div>

All the activities in the defect bash are planned activities, except for what to be tested. It involves several steps:
1. Choosing the frequency and duration of defect bash.
2. Selecting the right product build.
3. Communicating the objective of each defect bash to everyone.
4. Setting up and monitoring the lab for defect bash.
5. Taking actions and fixing issues.
6. Optimizing the effort involved in defect bash.

<div style="page-break-after: always;"></div>
