+++
date = '2026-04-05T23:11:47+05:30'
draft = false
title = 'White Box Testing'
image = '/images/White Box Testing.png'
weight = 1
+++

#### **By Garvit Singh**

- White box testing is a way of testing the external functionality of the code by examining and testing the program code that realizes the external functionality.
- Also known as *clear box*, or *glass box* or *open box* testing.
- Takes into account the program code, code structure and internal design flow.
- White box testing is done to check various paths in the code and make sure they are exercised correctly. 
- Knowing which code paths should be exercised for a given test enables making necessary changes to ensure that appropriate paths are covered.
- WBT is classified into two type - *Static* & *Structural* Testing

<div style="page-break-after: always;"></div>

![](https://i.imgur.com/D0uk6Dy.png)

**Static Testing**
Requires only the source code of the product, not the binaries or executables. Can be done manually by humans or by using specialized tools. Static testing doesn't involve executing the programs but involves select people going through the code to find out wether :
1. The code works according to functional requirement.
2. The code has been written in accordance with the design developed earlier in the project life cycle.
3. The code for any functionality has been missed out.
4. The code handles errors properly.

<div style="page-break-after: always;"></div>

**Static Testing By Humans**
Relies on people reading the program code to detect errors rather than computers executing the code to find errors. The advantages include :
1. Sometimes humans can find errors that machines cannot. This can happen when the program has no errors in syntax and runs error free, but has logical errors, like making use of the wrong variable.
2. By making multiple people read the program, we can get multiple perspectives and have more problems identified than a computer could.
3. A human evaluation of code can compare it against the specifications or design and thus ensure it does what is intended to do. This may not always be possible when a computer runs a test.
4. A human evaluation can detect many problems at one go and can even try to identify root causes of the problems. Reactive testing only identifies and fixes the symptoms, not the root cause. Fixing the root cause by human evaluation can fix multiple defects at one go.
5. Computer resources can be saved by making people test the code. This might come at the expense of human resources.
6. A proactive method like static testing minimizes the delay in identification of the problems. The sooner a defect is identified and corrected, lesser is the cost of fixing the defect.
7. Finding defects later in the cycle puts immense pressure on the programmers as they have to fix defects with less time to spare.

Methods to achieve static testing by humans in increasing order of formalism :
1. Desk Checking of Code
2. Code Walkthrough
3. Code Review
4. Code Inspection

<div style="page-break-after: always;"></div>

**Desk Checking**
Done manually by authors of the code, this is a method to verify portions of code for correctness. The code is compared with the design specifications to make sure the code does what it is intended to do. Desk checking relies completely on the programmer's diligence and skills. This method is characterized by:
1. No structured method or formalism to ensure completeness.
2. No maintaining of a log or checklist.

==*Advantages*==
1. Programmer who knows the code and the programming language well can read and understand his own code very well.
2. There are few schedulings and logistics over-heads as it is done by one individual.
3. The defects are detected and corrected with minimum time delay.

==*Disadvantages*==
1. A developer is not the best person to detect problems in his or her own code. They may be tunnel visioned and have blind spots to certain types of problems.
2. Developers prefer to write new code rather than do any testing.
3. This method is essentially person dependent and informal, and thus may not work consistently across all developers.

<div style="page-break-after: always;"></div>

**Code Walkthrough**
Walkthroughs are group-oriented and less formal than inspections. The line drawn between walkthroughs and inspections is very thin and varies from one organisation to another.

In walkthroughs, a set of people look at the program code and raise questions for the author. The author explains the logic of the code and answers the questions. If the author is unable to answer some questions, he or she takes those questions and find their answers.

<div style="page-break-after: always;"></div>

**Formal Inspection**
Code Inspection, also called Fagan Inspection, is a method with high degree of formalism. The focus is to detect all faults, violations, and other side-effects. The number of defects detected increases by :
1. Demanding thorough preparation before an inspection/review.
2. Enlisiting multiple diverse views.
3. Assigning specific roles to the multiple participants.
4. Going sequentially through the code in a structured manner.

A formal inspection takes place only when the author has made sure the code is ready for inspection by performing basic desk checking and walkthroughs. There has to be a level of readiness in the code before an inspection meeting is arranged. There are four roles in the inspection :
1. *Author*, who writes the code.
2. *Moderator*, who is expected to run the inspection formally according to the process.
3. *Inspectors*, there are typically many of them, and together they review the code.
4. *Scribe*, who takes detailed notes during the inspection meeting and circulates them to the inspection team after the meeting.

Challenges in conducting formal inspections:
1. *Time consuming*, since the process calls for preparation as well as formal meetings.
2. The *logistics* and *scheduling* can become an issue since multiple people are involved.
3. It is not possible to go through every line of code.
4. It may also not be necessary to subject the entire code to formal inspection.

Portions of code can be classified on the basis of their criticality or complexity as 'High', 'Medium' or 'Low'. High or medium complex or critical code should be subjected to formal inspections. The low complexity code can do with walkthroughs or even desk checking.

<div style="page-break-after: always;"></div>

**Static Analysis Tools**
Static analysis tools can find errors such as:
1. Wether there are unreachable codes.
2. Variables declared but not used.
3. Mismatch in definition and assignment of values to variables.
4. Illegal or error prone typecasting of variables.
5. Use of non-portable or architecture dependent programming constructs.
6. Memory allocated but not having corresponding statements for freeing the memory.
7. Calculation of cylomatic complexity.

These static analysis tools can also be considered as an extension of compliers as they use the same concept and implementation to locate errors. A good compiler is also a static analysis tool.

<div style="page-break-after: always;"></div>

**Code Review Checklist**
Every organization develops it's own code review checklist. In multi-product organizations, the checklist may be at two levels, first an organization wide checklist that will include issues such as organization coding standards, documentation standards, second, a product or project specific checklist that addresses issues specific to the product. The checklist is as follows:

==Data Item Declaration Related==
- Are the names of the variables meaningful?
- If the programming language allows mixed case names, are there variable names with confusing use of lower case letters and capital letters?
- Are the variables initialized?
- Are there similar sounding names?
- Are all the common structures, constants and flags to be used defined in a header file rather than in each file separately?

==Data Usage Related==
- Are values of right data types being assigned to the variables?
- Is the access of data from any standard files, repositories, or databases done through publicly supported interfaces?
- If pointers are used, are they initialized correctly?
- Are bounds to array subscripts and pointers properly checked?
- Has the usage of similar looking operators(like = and == or & and &&) checked?

==Control Flow Related==
- Are all the conditional paths reachable?
- Are all the individual conditions in a complex condition separately evaluated?
- If there is a nested IF statement, are the THEN and ELSE parts properly delimited?
- In the case of a multi-way branch like SWITCH/CASE statements, is a default clause provided? Are the breaks after each CASE appropriate?
- Is there any part of code that is unreachable?
- Are there any loops that will never execute?
- Are there any loops where the final condition will never be met and hence cause the program to go into an infinite loop?
- What is the level of nesting of the conditional statements? Can the code be simplified to reduce complexity?

==Standards Related==
- Does the code follow the coding conventions of the organization?
- Does the code follow any coding conventions that are platform specific?

==Style Related==
- Are unhealthy programming constructs being used in the program?
- Is there usage of specific idiosyncrasies of a particular machine architecture or a given version of an underlying product?
- Is sufficient attention being paid to readability issues like indentation of code?

==Miscellaneous==
- Have you checked for memory leaks?

==Documentation Related==
- Is the code adequately documented, especially where the logic is complex or the section of code is critical for product functioning?
- Is appropriate change history documented?
- Are the interfaces and the parameters thereof properly documented?

<div style="page-break-after: always;"></div>

**Structural Testing**
Structural testing takes into account the code, code structure, internal design, and how they are coded. These tests are run by the computer on the built product, unlike static testing which is tested by humans.

It involves running the actual product against some pre-designed test cases. Further classified into:
1. Unit/Code Functional Testing
2. Code Coverage Testing
3. Code Complexity Testing

==Unit/Code Functional Testing==
These are some quick checks that a developer performs before subjecting the code to more extensive code coverage testing or code complexity testing.
1. Initially, the developer can perform certain obvious tests, knowing the input variables and the corresponding output values. Repeat this test for multiple input values. This can also be done prior to formal reviews in static testing.
2. For more complex logic or conditions, the developer can build a '*debug version*' of the product by putting intermediate print statements and making sure the program is passing through the right loops and iterations the right number of times. The print statements are removed after the defects are removed.
3. Another approach is to do the initial test to run the product under a debugger or an IDE. These tools allow single stepping of instructions.
These fall more into the '*debugging*' category rather than testing.

==Code Coverage Testing==
Code coverage testing involves designing and executing test cases and finding out the percentage of code that is covered by the testing. The percentage of code covered by a test is found by adopting a technique called *instrumentation* of code.

Instrumentation rebuilds the product, linking the product with a set of libraries provided by the tool vendors. This instrumented code can monitor and keep an audit of what portions are covered.

Code coverage testing is made up of the following types of coverage:
1. Statement coverage
2. Path coverage
3. Condition coverage
4. Function coverage

Few other uses of code coverage testing include:
1. Performance analysis and optimization
2. Resource usage analysis
3. Checking of critical sections or concurrency related parts of code.
4. Identifying memory leaks.
5. Dynamically generated code.

<div style="page-break-after: always;"></div>

==Code Complexity Testing==
Cyclomatic complexity is a metric that quantifies the complexity of a program. A program is represented in the form of a *flow graph*, which consists of *node* and *edges*.

![](https://i.imgur.com/4XOkRH7.png)

A standard flow chart can be converted into a flow graph with these steps:
1. Identify the predicates or decision points in the program, which are usually boolean statements or conditions.
2. Ensure that the predicates are simple, containing no 'and/or'. Complex predicates have to be broken down into simple predicates.
3. Combine all sequential statements into a single node.
4. When a set of sequential statements are followed by a simple predicate, combine all the sequential statements and the predicate check into one node and have two edges emanating from this node. Such nodes with two edges emanating from them are called *predicate nodes*.
5. Make sure that all edges terminate at some node, add a node to represent all the sets of sequential statements at the end of the program.

Cyclomatic Complexity = Edges(E) - Node(N) + 2 = Number of Predicate Nodes + 1

| Complexity | What It Means |
| ---- | ---- |
| 1 - 10 | Well written code, testability is high, cost/effort to maintain is low. |
| 10 - 20 | Moderately complex, testability is medium, cost/effort to maintain is medium. |
| 20 - 40 | Very complex, testability is low, cost/effort to maintain is high. |
| > 40 | Not testable, any amount of money/effort to maintain may not be enough. |


**Challenges In White Box Testing**
- White box testing requires sound knowledge of the program code and the programming language.
- Developers, in general do not like to perform testing functions, both static and structural.
- Programmers may not 'find time' due to timeline pressures.
- Human tendency of a developer being unable to find the defects in his or her own code.
- Fully tested code may not correspond to realistic scenarios.
- This doesn't mean white box testing is ineffective. These challenges can be overcome by involving other types of testing along with white box testing.
