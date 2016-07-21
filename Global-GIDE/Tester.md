##EOT : "Tester" 

---

###OBJECTIVES
1. How to write good test cases
2. Using MS Test Manager (MTM) to  manage test processes

###REQUIREMENTS
1. TFS 2013 Update 3
2. Visual Studios 2013

###OTHER
1. Professional Application Lifecycle Management with Visual Studio 2013 ISBN-13: 978-1118836583
2. Software Testing with Visual Studio 2010 – ISBN 978 – 321 – 73448 - 8

---

##Testing In Context : **An "End-To-End Flow"**
**Components of an "End-To-End Flow":**
  - User Story
  - Test Approaches
  - Writing good test plans
  - Creating a test plan
  - Managing test cases
  - Executing manual test cases
  - Managing Bugs

**A General Work Flow:**  
  1. Be involved in creating the requirements    
  2. Write inital test cases   
  3. Review with customes  
  4. Work with developers to track updates  
  5. Attend the code review / demo  
  6. Update test cases for specific UI's  
  7. Validate requirements  
  8. Perform exploratory testing  
  9. File / Validate bugs  

##User Stories
**Template: "As a [user] I want [feature] so that [benefit]"**:
Should contain or clearly imply acceptance criteria - *Definition of* ***DONE***  

  **INVEST:**  
  - **I** - Independent
  - **N** - Negotiable
  - **V** - Valuable
  - **E** - Estimatable
  - **S** - Small
  - **T** - Testable

###Requirements != Implementation
  - Requirements and Implementation are not the same.
  - Requirements specify attributes of a system, whether functional or non-functional. 
  - Implementation explains ***how*** the software fulfills the requirement. **It is the realization of a specification.**

###User Story Example: 
**[User] Requirement:** *"Registered Users will be able to purchase music from the Music Store"*  
**Test Approaches:**  
  - *Required Tests:*
    - Static Tests:
      - Code Reviews
    - Dynamic Tests:
      - Functional Testing  
      - Regression Testing  
      - Integration  
      - Security  
  - *Extraneous Tests (ie. time permitting):*  
    - Performance    
    - Usability    
    - Compatibility
  
**Testing Types:**  
  - Unit (Single Module)  
  - Integration (Group of Modules)  
  - System (Whole Systems)  
**Achieve Test Objectives By:**  
  - Acceptance + Qualifications
  - Installation
  - Alpha & Beta
  - Conformance/Functional/Correctness
  - Internationalization & Localization
  - Reliability achievement and evaluation
  - Regression testing
  - Performance testing 
  - Stress
  - Back-to-back
  - Recovery testing
  - Configuration
  - Usability

###**Targets of Testing**  
**Testing** can be performed at different levels during the development and maintenance process. The target of the test can be focused on a small unit such as a single module, or range to include a whole system.  These test stages can be distinguished conceptually as Unit, Integration and System tests.

A **Unit Test** is an automated piece of code that invokes the method or class being tested and then checks some assumptions about the logical behavior of that method or class. A unit test is almost always written using a unit testing framework. It can be written easily and runs quickly. It's fully automated, trustworthy, readable and maintainable. Unit Tests are (**FIRST**): **Fast**, **Independent**, **Repeatable**, **Self Validating** and **Timely**.

**Integration Testing** is the phase in software testing in which individual software modules are combined and tested as a group.  It occurs after unit testing and before validation testing. Its purpose is to verify functional, performance and reliability requirements placed on major design items.

**System Testing** is concerned with the behavior of a whole system. The majority of functional failures should already have been identified during unit and integration testing. System testing is usually considered appropriate for comparing the system to the non-functional system requirements, such as security, speed, accuracy, and reliability. External interfaces to other applications, utilities, hardware devices, or the operating environment are also evaluated at this level.

**Acceptance/Qualification Testing** checks the system behavior against the customer’s requirements, however these may have been expressed; the customers undertake, or specify, typical tasks to check that their requirements have been met or that the organization has identified these for the target market for the software. This testing activity may or may not involve the developers of the system.  

**Installation Testing** occurs after completion of software and acceptance testing, when the software can be verified upon installation in the target environment. Installation testing can be viewed as system testing conducted once again according to hardware configuration requirements. Installation procedures may also be verified.

**Alpha and Beta Testing** occurs before the software is released, where it is sometimes given to a small, representative set of potential users for trial use, either in-house (alpha testing) or external (beta testing). These users report problems with the product. Alpha and beta use is often uncontrolled, and is not always referred to in a test plan.

**Conformance Testing** / Functional Testing / Correctness Testing** is aimed at validating whether or not the observed behavior of the tested software conforms to its specifications.  Internationalization & Localization essentially asks, "can the software support localization or did someone hard code all of the strings?" Localization is actually the implementation of localized strings to support a specific locale

**Reliability Achievement and Evaluation** In helping to identify faults, testing is a means to improve reliability. By contrast, by randomly generating test cases according to the operational profile, statistical measures of reliability can be derived. Using reliability growth models, both objectives can be pursued together 

**Regression Testing** is the “selective retesting of a system or component to verify that modifications have not caused unintended effects…” In practice, the idea is to show that software which previously passed the tests still does.  Beizer defines it as any repetition of tests intended to show that the software’s behavior is 

###Test Types Characterization (vv)
  1. **Static v. Dynamic**
    - **Static Testing** refer to Reviews, walkthroughs or inspections of code. Testing can begin with a visual inspection of code before actual execution.
    - **Dynamic Testing** is testing performed while executing the code. Typically this happens with a given set of test cases.  Most tests are considered Dynamic tests. 
  2. **Manual v. Automatic**
  3. **Functional v. Non-Functional**
    - **Functional testing** refer to tests that would check the calculations, any link on the page, or any other field on which given input, output may be expected. Functional test include Unit Tests, exploratory, Integration, System, Acceptance (System & User), Release and Deployment tests.
    - **Non-Functional** tests refer to test that validate performance, compatibility, fitness, security and usability of an application.
  4. **Exploratory**
  5. **Traditional v. "Agile"**
    - **Traditional Testing** performed after development is complete. Tests are created from requirements gathered at beginning of the project. Separated stage of implementation
    - **"Agile"** performed at regular iterations (sprints). Tests occur asynchronously with development and included in development in the form of Test Driven Development

###Testing For Agile Teams
  - User Stories & Acceptance Tests (ATDD)
  - Pair Programming & Testing
  - Unit Testing
    - Test Driven Development (TDD)
    - Behavior Driven Development (BDD)

Agile teams will approach testing decidedly different from Traditional development teams:  
  - Agile teams commit to the completion of user stories by the end of an iteration.
  - Teams work with customers to define the acceptance criteria (Now known as Acceptance Test Driven Development) of the user stories and developers develop small increments of working software.
  - Testers work with the developers to test the software as it is being developed, ensuring testing doesn’t wait until the end to be complete.
  - Some advanced techniques used by Agile teams are pair programming, pair testing and unit testing. 
  - Studies have found that programmers working in pairs produce shorter programs, with better designs and fewer bugs, than programmers working alone. Additional studies have found reduction in defect rates of 15% to 50%, varying depending on programmer experience and task complexity. 
  - Pairs typically consider more design alternatives than programmers working solo, and arrive at simpler, more-maintainable designs; they also catch design defects early.  
  - Pairs usually complete work faster than one programmer assigned to the same task. 
  - Pairs often find that seemingly "impossible" problems become easy or even quick, or at least possible to solve when they work together. 

**Test Driven Development** focuses on developers and testers developing tests for each module created.  These unit tests are continuously invoked as code is built in order to ensure code continuously meets requirements.

**Promiscuous Pairing** – each programmer cycling through all the other programmers on the team rather than pairing only with one partner – knowledge of the system spreads throughout the whole team, reducing risk to management if one programmer leaves the team.

###Writing Good Test Cases
A key element of effective testing is ensuring we optimize our testing resources against the time we have to test. Based on Claude Shannon’s Theory of Information, Testing effort should be focused on areas & test types that result in near 50% failure in order to optimized limited testing resources.  
  1.  A good test case has a high probability of finding an error
  2.  A good test is not redundant
  3.  A good test should be the "best"
  4.  A good test should neither be overly complex or simple
    - **Story Testing**
    - **Epic Testing**

**Characteristics of a good Test Case:**  
    1. Should be accurate and test what it is intended to test
    2. No unnecessary steps should be included in it
    3. Reusable and repeatable 
    4.Traceable to requirements
    5. Compliant to regulations
    6. Independent i.e. You should be able to execute it in any order without any dependency on other test cases
    7. Simple and clear; any tester should be able to understand it by reading it once
    8. Small; Tests only 1 user story
    9. Likely to find a defect

**"GIVEN [] WHEN [] WHAT [] THEN..." Acceptance Criteria Formatting**  
*Given:* <Scenario>  
*When:*  <Condition>  
*Then:*  <Result>  

(Ex:)  
*Given:* A form that searches a dataset for a surname,
*When:* Text is entered into a search field.
*Then:* The corresponding dataset is searched using the text entered into the search field.

*Given:* A form that searches a dataset for a surname,
*When:* Text with a wildcard (*) is entered into a search field.
*Then:* The corresponding dataset is searched using the text and wildcard entered into the search field

###Creating Master Plans for MTM:    
*Test Suite Hierarchy*  
**Steps:**  
  1. Create a Master Test Plan
    - For end-to-end test that span more than one sprint. Can also be used for service level agreements. This test plan does not have to be associated with a specific iteration, because it spans multiple iterations and can only be completed when all milestones have been completed.
  2. Create Test Plan for each sprint, milestone or other iteration  
  3. Create Test plans for concurrent development of varying functional areas 
  
**Properties of a Test Plan:**  
  - Project Area, Iteration, Build
  - Test Configurations
  - Test Enviroments
  - Test Settings

###Managing Bugs  
**Defect Management Flow For Developers**
  1. Bug/Defect Found and Filed
    - Details, repor steps, enviroment, video, screen, captures, Build
  2. Bugs added to backlog (PBI)
  3. Developer query for open User Stories/Bugs/Requirements
  4. Bug set to Active
  5. Bug fixed in code, checked in, associated in task and bug. Bug set to resolved
  6. Build kicked off
  7. Tester selects build with bug fixes 
    - Included User Stories, Requirements & Bug Fixes will be displayed
    - Create Regression test from filed bug
  8. Verify bug using associated test cases
  9. Close bug

###Useage Flow using Test Hub
  1. Test Manager creates Test Plan(s)
  2. Test Manager creates Test Suite(s)
  3. (Optional) Test Manager creates Test Case stubs to test suites
  4. *(Optional) Tester creates test cases
  5. *Tester executes manual test cases
  6. Test results analyze  
* Test Hub, else MS Test Manager

**Note:** After filing bug, team needs to decide when they fix bug. During **Triage**, customer decides whether bug should be fixed in current iteration or next.  
  - If fix during current iteration, set User Story from *Resolved* to *Active*.  Set bug to active. Once fixed, Bug and Story *Resolved*.
  - If fixed during future iteration, User Story will be *Closed* because customer is accepting work.

###What exploratory tests should I perform?

The most important categories of test are:
  - **Exercise the story**. Can you perform the actions promised in the user story or product backlog item?
  - **Exercise key values**. Can you perform the user story with differing sets of input – for example, an empty shopping cart, a single item, one of everything, two of some things, and so forth?
  - **Break the application**. Can you make the application fail, for example by providing unexpected inputs or too much input?
