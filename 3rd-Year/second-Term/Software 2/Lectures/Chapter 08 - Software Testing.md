### 🧪 Software Testing Essentials 🧪

**Development Testing:**
- Purpose: Ensure software behaves as `intended` and `detect defects early`.
- Goals: 
  1. Demonstrate software meets requirements.
  2. Uncover incorrect behavior or defects.
- Two Approaches:
  - `Validation Testing`: Confirms correct system behavior with expected inputs.
  - `Defect Testing`: Aims to expose system flaws, often using obscure test cases.
- `Verification` vs. `Validation`:
  - Verification: Building the product right.
  - Validation: Building the right product.
- Aim: Establish confidence that software is `fit for purpose` and meets `customer expectations`.
- Considerations:
  - Software purpose, user expectations, and marketing environment affect testing rigor.
  
**Inspections and Reviews:**
- Static $V \& V$ techniques to `analyze requirements`, `design`, and `code`.
- Advantages over testing:
  1. Errors don't mask each other.
  2. Consider broader quality attributes.
  3. More effective for defect discovery.
- Limitations: Can't replace testing for certain defects and interactions.
- ![[Inspections.png]]

**Test Planning:**
- Involves `scheduling` and resourcing testing activities.
- Defines testing process, including test plan creation and execution.

**Development Testing Levels:**
1. **Unit Testing:** Testing `individual program` components.
2. **Component Testing:** Integrating units to test `composite components`.
3. **System Testing:** Testing the integrated `system as a whole`.

**Unit Testing:**
- Testing program components like methods or object classes.
- Ensures coverage of all features, operations, attributes, and states.
- Utilizes test automation frameworks like JUnit for efficiency and consistency.
- May involve mock objects to simulate dependencies or rare events.

**Conclusion:**
- `Development testing` crucial for early `defect detection` and `software quality assurance`.
- Combination of `validation`, `defect testing`, `inspections`, and `reviews` essential for comprehensive $V \& V$ process.
---
### 🎯 Choosing Effective Unit Test Cases 🎯

**Importance of Effective Testing:**
- Testing should demonstrate `expected behavior` and `reveal defects`.
- Two types of test cases: `normal operation` and `abnormal inputs`.

**Strategies for Test Case Selection:**
1. **Partition Testing:**
   - Identify input and output equivalence partitions.
   - Choose test cases from each partition, focusing on boundary values and midpoints.
   - Helps `uncover errors` at partition edges where failures often occur.

2. **Guideline-Based Testing:**
   - Use testing guidelines to select test cases effectively.
   - Examples include testing sequences with `single values`, `varying sizes`, and `accessing boundary elements`.

**Equivalence Partitioning:**
- Effective for `testing input/output` behaviors.
- Utilizes `program specification` or `user documentation` to identify partitions.
- Combines black-box testing (using specification) with white-box testing (examining code).
- ![[Equivalence Partitioning.png]]

**Testing Guidelines:**
- Examples include forcing system to `generate error messages`, `causing buffer overflows`, `repeating inputs`, and `generating invalid outputs`.
- Develop your own guidelines based on testing experience.

**Conclusion:**
- Effective test case selection crucial for thorough testing.
- Combination of `partition testing` and `guideline-based testing` helps uncover various types of defects.
- Experience enhances ability to choose effective test cases.
---
### 🧩 Component Testing Essentials 🧩

**Understanding Composite Components:**
- Composite components consist of multiple interacting objects.
- Focus of testing: Component interface behavior.

**Types of Component Interfaces:**
1. **Parameter Interfaces:** Passing data or function references.
2. **Shared Memory Interfaces:** Sharing memory blocks between components.
3. **Procedural Interfaces:** Encapsulating procedures for other components.
4. **Message Passing Interfaces:** Requesting services by passing messages.

**Common Interface Errors:**
- `Interface misuse`, `misunderstanding`, and `timing errors` are prevalent.
- Manifest under unusual conditions, challenging to detect.

**Testing Strategies for Interface Defects:**
1. **Extreme Values Testing:** Test with extreme parameter values to reveal inconsistencies.
2. **Null Pointer Testing:** Test interfaces with null pointer parameters.
3. **Failure Testing:** Design tests to deliberately cause component failures.
4. **Stress Testing:** Generate excessive messages to reveal timing issues.
5. **Order Variation Testing:** Vary activation order of interacting components.

**Addressing Interface Errors:**
- `Inspections` and `reviews` can complement testing for discovering interface errors.
- Strongly typed languages and static analyzers help trap interface errors.

**Conclusion:**
- `Interface testing` crucial for detecting `complex` system errors.
- Combination of testing strategies and inspections enhance interface defect detection.
- Utilize tools and techniques to complement testing efforts for thorough validation.
---
### 🌐 System Testing Essentials 🌐

**Integration and Emergent Behavior:**
- **`Integration`:** Combining components to form a system for testing.
- **`Emergent Behavior`:** Unanticipated system behavior arising from component interactions.

**Focus of System Testing:**
- Testing component `interactions` and `emergent` behavior.
- Identifying `planned` and `unplanned` system functionality.

**Use Case-Based Testing:**
- Effective approach for system testing.
- Testing interactions required by each use case.

**Example: Wilderness Weather Station System:**
- Illustration using a sequence diagram.
- Designing test `cases` based on expected `inputs` and `outputs`.

**Testing Considerations:**
- Handling exceptions in test scenarios.
- Difficulty in determining essential testing scope and stopping criteria.

**Guidelines for System Testing:**
- Testing all system functions accessible via menus.
- Testing combinations of functions, especially those accessed through the same menu.
- Testing functions with both `correct` and `incorrect` user input.

**Challenges of Automated System Testing:**
- Difficulty in predicting and automating `large` or `complex` outputs.
- Assessing output credibility without the ability to predict it in advance.

**Conclusion:**
- System testing crucial for assessing component `interactions` and `emergent` behavior.
- Use `case-based testing` aids in designing effective test scenarios.
- Challenges in automated system testing require careful consideration of output validation methods.
---
### 🛠️ Test-Driven Development 🛠️

**Introduction to TDD:**
- Approach to program development involving interleaved testing and code development.
- Introduced as part of agile methods like Extreme Programming, applicable in plan-driven processes.

**Fundamental TDD Process:**
1. **Identify Functionality Increment:** Begin with small, implementable chunks of functionality.
2. **Write Test:** Create an automated test for the identified functionality.
3. **Run Test:** Execute the test along with existing tests; expect failure initially.
4. **Implement Functionality:** Develop code to pass the test, possibly involving refactoring.
5. **Pass Test:** Once all tests run successfully, move on to the next functionality increment.

**Automation in TDD:**
- Automated testing environment like JUnit essential for running tests with each code increment.
- Allows running hundreds of tests in seconds, ensuring comprehensive code coverage.

**Benefits of TDD:**
1. **Code Coverage:** Each code segment should have at least one associated test, ensuring comprehensive testing and early defect detection.
2. **Regression Testing:** Incremental development leads to the creation of a test suite, enabling quick regression testing to detect new bugs.
3. **Simplified Debugging:** Test failures pinpoint code issues directly, minimizing the need for debugging tools.
4. **System Documentation:** Tests serve as documentation, aiding in understanding the code.

**Cost Reduction in Regression Testing:**
- Automated testing reduces regression testing costs significantly by enabling quick and cheap reruns of existing tests.
- Confidence in new functionality without causing problems in existing code.

**Limitations and Considerations:**
- Most effective in new software development or with well-tested standard libraries.
- Challenges with multi-threaded systems due to potential thread interleaving.

**Integration with System Testing:**
- TDD complements system testing, which validates system requirements and performance.
- Extension of testing tools can integrate some aspects of system testing with TDD.

**Success and Adoption:**
- Successful for small to medium-sized projects, with positive feedback from programmers.
- Improvements in code quality observed in some trials, inconclusive results in others, but no evidence of poorer quality code.

**Conclusion:**
- TDD offers a productive approach to software development, combining testing and code development iteratively.
- Automation, comprehensive testing, and early defect detection are key advantages of TDD.
- Integration with system testing ensures holistic validation of software systems.
---
### 📋 Requirements-Based Testing 📋

**Principles of Requirements-Based Testing:**
- Good requirements should be `testable`, allowing for systematic test case design.
- Focus on `validation` to demonstrate proper implementation of system requirements.

**Example Scenario - MHC-PMS:**
- Requirements regarding drug allergies lead to the development of multiple related tests.
- Tests cover scenarios such as issuing warnings for known allergies and handling prescriber overrides.

**Testing Strategy:**
- Develop a set of tests for each requirement to ensure comprehensive coverage.
- Maintain traceability records linking tests to specific requirements being tested.

### 📖 Scenario Testing 📖

**Concept of Scenario Testing:**
- Approach to release testing involving the creation of typical usage scenarios.
- Scenarios represent realistic stories of system use, aiding in the development of test cases.

**Characteristics of Effective Scenario Tests:**
- Credible and complex narrative stories that motivate stakeholders.
- Easy to evaluate, allowing release testing teams to recognize system problems.

**Example Scenario - MHC-PMS:**
- Illustration of system usage during a home visit, testing various features and interactions.
- Role-playing scenarios to observe system behavior and response to different inputs.

**Benefits of Scenario Testing:**
- Validates multiple requirements within the same scenario.
- Ensures that combinations of requirements do not cause unexpected problems.

### ⚙️ Performance Testing ⚙️

**Objective of Performance Testing:**
- Assess emergent properties like `performance` and `reliability` post system integration.
- Design tests to ensure the system can handle its intended load.

**Operational Profile for Performance Testing:**
- Reflects the actual mix of work handled by the system, ensuring accurate performance evaluation.
- Emphasizes tests that align with the majority of system transactions to provide reliable performance assessment.

**Stress Testing for Defect Discovery:**
- Pushes the system beyond its design limits to uncover defects and assess system failure behavior.
- Reveals defects that may not surface under normal operating conditions.

**Relevance to Distributed Systems:**
- Particularly crucial for distributed systems to detect performance degradation under heavy loads.
- Helps identify points of system degradation and implement necessary checks to maintain system integrity.

**Conclusion**
- Requirements-based testing ensures proper implementation of system requirements.
- Scenario testing aids in the validation of typical system usage scenarios.
- Performance testing assesses system performance and reliability post-integration, with stress testing revealing potential defects and system failure behavior.
---
### 🛠️ User Testing 🛠️

**Introduction to User Testing:**
- Involves users or customers providing input and advice on system testing.
- Essential for assessing reliability, performance, usability, and robustness influenced by the user's working environment.

**Types of User Testing:**
1. **Alpha Testing:**
   - Users collaborate with developers to test the system during development.
   - Identifies issues not apparent to the development team and aids in realistic test design.
   - Commonly used for shrink-wrapped software products and custom software development.
   
2. **Beta Testing:**
   - Early release of software made available to customers for evaluation.
   - Essential for discovering interaction problems in diverse environments.
   - Also serves as a form of marketing, allowing customers to learn about system features.

3. **Acceptance Testing:**
   - Customers formally test the system to determine readiness for deployment.
   - Six-stage process involving defining acceptance criteria, planning, deriving tests, execution, negotiation, and system acceptance/rejection.

**Agile Perspective on Acceptance Testing:**
- In Agile methods like XP, user involvement is integral throughout the development process.
- User stories define system requirements, and acceptance tests are automated and must pass before development proceeds.
---
### 🔑 Key Points 🔑

- Testing reveals errors in a program but cannot guarantee the absence of faults.
- Development testing includes unit, component, and system testing.
- Automated tests are preferred for efficiency, especially in Test-first development.
- Scenario testing replicates practical system usage and aids in test case derivation.
- Acceptance testing determines system readiness for deployment.
---
### 📝 Exercises 📝

8.1. **Explain why it is not necessary for a program to be completely free of defects before it is delivered to its customers.**
   - Answer: Customers prioritize timely deployment despite minor defects.

8.2. **Explain why testing can only detect the presence of errors, not their absence.**
   - Answer: Testing cannot ensure error absence due to system complexity.

8.3. **Some people argue that developers should not be involved in testing their own code but that all testing should be the responsibility of a separate team. Give arguments for and against testing by the developers themselves.**
   - Answer: Arguments for developer testing include familiarity, but impartiality may be compromised.

8.4. **You have been asked to test a method called 'catWhiteSpace' in a 'Paragraph' object that, within the paragraph, replaces sequences of blank characters with a single blank character. Identify testing partitions for this example and derive a set of tests for the 'catWhiteSpace' method.**
   - Answer: Identify partitions like empty string, single space, multiple spaces, etc., and derive tests accordingly.

8.5. **What is regression testing? Explain how the use of automated tests and a testing framework such as JUnit simplifies regression testing.**
   - Answer: Regression testing verifies unchanged functionality; automation simplifies this process.

8.6. **The MHC-PMS is constructed by adapting an off-the-shelf information system. What do you think are the differences between testing such a system and testing software that is developed using an object-oriented language such as Java?**
   - Answer: Differences include testing integration and adaptation versus object-oriented code.

8.7. **Write a scenario that could be used to help design tests for the wilderness weather station system.**
   - Answer: Develop a scenario for testing the wilderness weather station system.

8.8. **What do you understand by the term 'stress testing'? Suggest how you might stress test the MHC-PMS.**
   - Answer: Stress testing assesses system performance under extreme conditions; stress MHC-PMS by simulating heavy user loads.

8.9. **What are the benefits of involving users in release testing at an early stage in the testing process? Are there disadvantages in user involvement?**
   - Answer: Early user involvement aids in identifying issues but may not represent typical users.

8.10. **A common approach to system testing is to test the system until the testing budget is exhausted and then deliver the system to customers. Discuss the ethics of this approach for systems that are delivered to external customers.**
   - Answer: Exhausting the testing budget before delivery may prioritize quantity over quality; ethical considerations arise.

