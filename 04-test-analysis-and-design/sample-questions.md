# ISTQB CTFL v4.0.1 – Chapter 4: Test Techniques
# Sample Questions and Practice Question Bank

---

# Section A – User-Provided Sample Questions

*This section contains only the questions shared in your screenshots. The original wording and options are preserved.*

## Question 1 – Experience-Based Test Techniques

**Which of the following is a characteristic of experience-based test techniques?**

A. Test cases are created based on detailed design information.  
B. Items tested within the interface code section are used to measure coverage.  
C. The techniques heavily rely on the tester’s knowledge of the software and the business domain.  
D. The test cases are used to identify deviations from the requirements.

**Your answer: C**  
**Correct answer: C**

**Explanation:**

Experience-based testing techniques rely on the tester's knowledge, experience, intuition and understanding of the software, its usage and its business domain.

Examples include:
- Error guessing
- Exploratory testing
- Checklist-based testing

**Why the other options are incorrect:**

- A: Detailed design information is more closely associated with white-box testing.
- B: Measuring code coverage is associated with white-box testing.
- D: Identifying deviations from requirements is a general testing objective, not a defining characteristic of experience-based techniques.

**Syllabus mapping:** 4.4 – Experience-Based Test Techniques

**Exam takeaway:** Experience-based testing depends heavily on the tester's knowledge and experience.

---

## Question 2 – Statement Coverage

**Your test suite achieved 100% statement coverage. What is the consequence of this fact?**

A. Each instruction in the code that contains a defect has been executed at least once.  
B. Any test suite containing more test cases than your test suite will also achieve 100% statement coverage.  
C. Each path in the code has been executed at least once.  
D. Every combination of input values has been tested at least once.

**Your answer: A**  
**Correct answer: A (intended answer, with a wording caveat)**

**Explanation:**

Statement coverage measures the percentage of executable statements that have been executed by the test suite.

Formula:

Statement Coverage (%) =
(Number of executable statements executed / Total number of executable statements) × 100

100% statement coverage means every executable statement within the measured scope has been executed at least once.

However, the wording of option A is technically imprecise. Statement coverage does not establish that every defective instruction has been executed or that defects have been detected. It establishes that all executable statements in scope have been executed.

**Why the other options are incorrect:**

- B: More test cases do not automatically guarantee better coverage. Test-case quality and input selection matter.
- C: Statement coverage does not guarantee that every execution path has been tested.
- D: Statement coverage does not guarantee that every input combination has been tested.

**Example:**

    if (x > 0) {
        System.out.println("Positive");
    }
    System.out.println("Completed");

A test with `x = 5` executes both statements and achieves 100% statement coverage.

However, the false outcome of `x > 0` has not been tested.

**Syllabus mapping:** 4.3 – White-Box Test Techniques

**Exam takeaway:**
- Statement coverage = execution of statements.
- Branch coverage = execution of branch outcomes.
- 100% statement coverage does not guarantee 100% branch coverage.
- Coverage does not guarantee defect detection.

---

## Question 3 – Acceptance Criteria

**Which of the following BEST describes the way acceptance criteria can be documented?**

A. Performing retrospectives to determine the actual needs of the stakeholders regarding a given user story.  
B. Using the Given/When/Then format to describe an example test condition related to a given user story.  
C. Using verbal communication to reduce the risk of misunderstanding the acceptance criteria by others.  
D. Documenting risks related to a given user story in a test plan to facilitate risk-based testing of a given user story.

**Your answer: B**  
**Correct answer: B**

**Explanation:**

Acceptance criteria define the conditions that a software product or user story must satisfy to be accepted by stakeholders.

The Given/When/Then format is commonly used to document acceptance criteria in a structured, scenario-oriented way.

- Given: The initial context or precondition.
- When: The action or event.
- Then: The expected outcome.

**Example:**

    Given the user is on the login page
    When the user enters valid credentials
    Then the user should be redirected to the dashboard

**Why the other options are incorrect:**

- A: Retrospectives are used to inspect and improve the team's way of working.
- C: Verbal communication can help collaboration, but it does not provide structured documentation.
- D: Risk documentation supports risk-based testing, not the documentation of acceptance criteria itself.

**Syllabus mapping:** 4.5 – Collaboration-Based Test Approaches

**Exam takeaway:** Given/When/Then is a structured way to document scenario-oriented acceptance criteria.

---

# Section B – Additional Practice Questions

*The following are original ISTQB-style practice questions created for learning and revision. They are not official ISTQB examination questions.*

---

# Topic 4.1 – Test Techniques Overview

## Question 1 – Purpose of Test Techniques

A tester is preparing test cases for a banking application. The tester wants to select test inputs systematically rather than choosing random values.

Which of the following BEST describes the purpose of test techniques?

A. To replace the need for test analysis.  
B. To help derive test conditions, test cases and test data systematically.  
C. To guarantee that all defects will be detected.  
D. To eliminate the need for test execution.

**Correct answer: B**

**Explanation:**

Test techniques provide systematic approaches for identifying test conditions and deriving test cases and test data.

They help testers achieve better test coverage and reduce dependence on arbitrary test selection.

**Why the other options are incorrect:**

- A: Test techniques support test analysis; they do not replace it.
- C: No test technique guarantees detection of all defects.
- D: Test execution remains necessary to evaluate the software.

**Syllabus mapping:** 4.1 – Test Techniques Overview

---

## Question 2 – Selecting a Test Technique

A tester has limited time and needs to identify test cases for a field that accepts values between 1 and 100.

Which technique would BEST help identify test values around the boundaries?

A. Equivalence Partitioning  
B. Boundary Value Analysis  
C. Decision Table Testing  
D. Error Guessing

**Correct answer: B**

**Explanation:**

Boundary Value Analysis focuses on values at the boundaries of equivalence partitions.

For a valid range of 1–100, three-point boundary testing can include:

- 0 – just below the minimum
- 1 – minimum boundary
- 2 – just above the minimum
- 99 – just below the maximum
- 100 – maximum boundary
- 101 – just above the maximum

**Why the other options are incorrect:**

- A: Equivalence Partitioning divides input data into groups expected to behave similarly.
- C: Decision Table Testing is suitable for combinations of conditions and resulting actions.
- D: Error Guessing relies on tester experience and intuition.

**Syllabus mapping:** 4.2 – Black-Box Test Techniques

---

# Topic 4.2 – Black-Box Test Techniques

## Question 3 – Equivalence Partitioning

An application accepts a percentage value between 0 and 100, inclusive.

Which set represents the valid and invalid equivalence partitions?

A. 0, 50, 100  
B. Below 0, 0–100, above 100  
C. 0–50, 51–100  
D. 1–99, 100

**Correct answer: B**

**Explanation:**

Equivalence Partitioning divides input data into partitions where the system is expected to behave similarly.

For this example:

| Partition | Input range | Expected result |
|---|---|---|
| Invalid | Below 0 | Reject |
| Valid | 0–100 | Accept |
| Invalid | Above 100 | Reject |

A representative value can be selected from each partition.

**Why the other options are incorrect:**

- A: These are individual values, not a complete set of equivalence partitions.
- C: This splits the valid range unnecessarily and misses invalid partitions.
- D: This does not represent the complete valid and invalid input space.

**Syllabus mapping:** 4.2 – Equivalence Partitioning

---

## Question 4 – Boundary Value Analysis

A website allows users aged between 18 and 60 years, inclusive, to register.

Using three-point Boundary Value Analysis, which set of test values is MOST appropriate?

A. 18, 30, 60  
B. 17, 18, 19, 59, 60, 61  
C. 16, 18, 60, 62  
D. 18, 19, 20, 58, 59, 60

**Correct answer: B**

**Explanation:**

Three-point Boundary Value Analysis selects:

- One value below the boundary.
- The boundary value itself.
- One value above the boundary.

For the lower boundary of 18:

- 17 – invalid
- 18 – valid
- 19 – valid

For the upper boundary of 60:

- 59 – valid
- 60 – valid
- 61 – invalid

**Why the other options are incorrect:**

- A: Tests only the boundaries and one middle value.
- C: Does not test values immediately adjacent to both boundaries.
- D: Does not test the invalid values immediately outside the boundaries.

**Syllabus mapping:** 4.2 – Boundary Value Analysis

---

## Question 5 – Two-Point Boundary Value Analysis

A field accepts values from 10 to 50, inclusive.

Which set represents two-point Boundary Value Analysis?

A. 9, 10, 11, 49, 50, 51  
B. 10, 11, 49, 50  
C. 10, 30, 50  
D. 9, 30, 51

**Correct answer: B**

**Explanation:**

Two-point Boundary Value Analysis selects the boundary value and its nearest neighbour within the equivalence partition.

For the valid partition 10–50:

- 10 – lower boundary
- 11 – value immediately inside the lower boundary
- 49 – value immediately inside the upper boundary
- 50 – upper boundary

**Why the other options are incorrect:**

- A: This represents six-point boundary testing, including values outside the valid range.
- C: The middle value is not a boundary neighbour.
- D: This selects values outside the valid partition and omits the actual boundaries.

**Syllabus mapping:** 4.2 – Boundary Value Analysis

---

## Question 6 – Decision Table Testing

An online shopping application provides free delivery when:

- The customer is a premium member.
- The order value is greater than ₹1,000.

Free delivery is provided if either condition is true.

Which test technique is MOST suitable for identifying combinations of these conditions?

A. Equivalence Partitioning  
B. Boundary Value Analysis  
C. Decision Table Testing  
D. Statement Testing

**Correct answer: C**

**Explanation:**

Decision Table Testing is suitable when system behaviour depends on combinations of conditions.

| Rule | Premium member? | Order > ₹1,000? | Free delivery? |
|---|---|---|---|
| R1 | Yes | Yes | Yes |
| R2 | Yes | No | Yes |
| R3 | No | Yes | Yes |
| R4 | No | No | No |

The decision table helps identify the combinations that must be tested.

**Why the other options are incorrect:**

- A: EP groups input values into partitions.
- B: BVA focuses on values around boundaries.
- D: Statement testing is a white-box technique.

**Syllabus mapping:** 4.2 – Decision Table Testing

---

## Question 7 – Decision Table Rules

A system has three independent binary conditions.

How many rules are present in a complete decision table?

A. 3  
B. 6  
C. 8  
D. 9

**Correct answer: C**

**Explanation:**

For `n` independent binary conditions:

Number of combinations = \(2^n\)

For three conditions:

\(2^3 = 8\)

Therefore, a complete decision table contains eight rules before any reduction or combination of equivalent rules.

**Why the other options are incorrect:**

- A: This is the number of conditions, not combinations.
- B: This underestimates the possible combinations.
- D: This is not the result of the binary combination formula.

**Syllabus mapping:** 4.2 – Decision Table Testing

---

## Question 8 – State Transition Testing

An ATM card can be in one of the following states:

- Active
- Blocked

After three consecutive incorrect PIN attempts, the card becomes blocked.

Which technique is MOST suitable for testing this behaviour?

A. Equivalence Partitioning  
B. State Transition Testing  
C. Boundary Value Analysis  
D. Decision Table Testing

**Correct answer: B**

**Explanation:**

State Transition Testing verifies how a system changes from one state to another in response to events.

Example:

    Active
      |
      | Three consecutive incorrect PIN attempts
      v
    Blocked

Test scenarios should verify:

- One incorrect PIN attempt.
- Two consecutive incorrect PIN attempts.
- Three consecutive incorrect PIN attempts.
- A correct PIN before reaching the blocking threshold.
- Behaviour after the card becomes blocked.

**Why the other options are incorrect:**

- A: EP can partition PIN attempts but does not directly model state changes.
- C: BVA can test the threshold of three attempts, but does not comprehensively model state transitions.
- D: Decision tables model combinations of conditions and actions, rather than transitions between states.

**Syllabus mapping:** 4.2 – State Transition Testing

---

## Question 9 – State Transition Coverage

A login system has two states:

- Logged Out
- Logged In

The following transitions exist:

1. Valid login: Logged Out → Logged In
2. Logout: Logged In → Logged Out
3. Invalid login: Logged Out → Logged Out

A test suite executes transitions 1 and 2 only.

Which statement is correct?

A. 100% transition coverage has been achieved.  
B. 100% state coverage has been achieved, but transition coverage has not.  
C. No state coverage has been achieved.  
D. 100% transition coverage is guaranteed because all states were visited.

**Correct answer: B**

**Explanation:**

Both states have been visited:

- Logged Out
- Logged In

Therefore, state coverage is 100%.

However, only two out of three defined transitions have been executed.

Transition coverage:

\[
\frac{2}{3}\times100=66.67\%
\]

**Why the other options are incorrect:**

- A: The invalid-login transition was not executed.
- C: Both states were visited.
- D: Visiting every state does not guarantee execution of every transition.

**Syllabus mapping:** 4.2 – State Transition Testing

---

## Question 10 – Use Case Testing

A tester is validating an e-commerce checkout process.

The main flow is:

1. Add product to cart.
2. Enter delivery address.
3. Select payment method.
4. Confirm order.

Alternative flows include:

- Applying a discount coupon.
- Removing a product.
- Payment failure.
- Invalid delivery address.

Which technique is MOST suitable?

A. Use Case Testing  
B. Statement Testing  
C. Boundary Value Analysis  
D. Error Guessing

**Correct answer: A**

**Explanation:**

Use Case Testing derives tests from interactions between actors and the system to achieve a particular goal.

It can cover:

- Main success scenarios.
- Alternative flows.
- Exception flows.
- Interactions between users and the system.

**Why the other options are incorrect:**

- B: Statement Testing requires access to the code structure.
- C: BVA is used to test values around boundaries.
- D: Error Guessing is based on tester experience.

**Syllabus mapping:** 4.2 – Use Case Testing

---

## Question 11 – Equivalence Partitioning and Representative Values

A password field accepts passwords containing between 8 and 20 characters, inclusive.

A tester wants to apply Equivalence Partitioning.

Which set of partitions is MOST appropriate?

A. 7, 8, 9, 19, 20, 21  
B. Less than 8 characters, 8–20 characters, more than 20 characters  
C. 8, 12, 16, 20  
D. Empty password, valid password, special-character password

**Correct answer: B**

**Explanation:**

The input domain can be divided into three equivalence partitions:

| Partition | Range | Expected result |
|---|---|---|
| Invalid | Fewer than 8 characters | Reject |
| Valid | 8–20 characters | Accept |
| Invalid | More than 20 characters | Reject |

One representative value can be selected from each partition.

**Why the other options are incorrect:**

- A: These are boundary values, not partitions.
- C: These are individual values from the valid partition.
- D: These categories do not represent the specified length constraints.

**Syllabus mapping:** 4.2 – Equivalence Partitioning

---

# Topic 4.3 – White-Box Test Techniques

## Question 12 – Statement Coverage

A tester executes a test suite against a program containing 20 executable statements.

The test suite executes 15 statements.

What is the statement coverage?

A. 50%  
B. 65%  
C. 75%  
D. 80%

**Correct answer: C**

**Explanation:**

Statement coverage:

\[
\frac{\text{Executed statements}}{\text{Total executable statements}}\times100
\]

\[
\frac{15}{20}\times100=75\%
\]

**Why the other options are incorrect:**

- A: Incorrect calculation.
- B: Incorrect calculation.
- D: Incorrect calculation.

**Syllabus mapping:** 4.3 – Statement Testing

---

## Question 13 – Branch Coverage

Consider the following code:

    if (age >= 18) {
        System.out.println("Eligible");
    } else {
        System.out.println("Not Eligible");
    }

Which test set achieves 100% branch coverage?

A. age = 20  
B. age = 17  
C. age = 17 and age = 20  
D. age = 18 only

**Correct answer: C**

**Explanation:**

The decision has two possible outcomes:

- True: `age >= 18`
- False: `age < 18`

To achieve 100% branch coverage, both outcomes must be executed.

Test values:

- age = 20 → True branch
- age = 17 → False branch

**Why the other options are incorrect:**

- A: Executes only the true branch.
- B: Executes only the false branch.
- D: Executes only the true branch.

**Syllabus mapping:** 4.3 – Branch Testing

---

## Question 14 – Statement vs Branch Coverage

Consider the following code:

    if (x > 0) {
        System.out.println("Positive");
    }
    System.out.println("Completed");

A test suite executes the program with `x = 5`.

Which statement is correct?

A. 100% statement coverage and 100% branch coverage are achieved.  
B. 100% statement coverage is achieved, but 100% branch coverage is not achieved.  
C. 100% branch coverage is achieved, but statement coverage is not achieved.  
D. Neither statement nor branch coverage is achieved.

**Correct answer: B**

**Explanation:**

For `x = 5`:

- The condition `x > 0` evaluates to true.
- The `Positive` statement executes.
- The `Completed` statement executes.

Every executable statement has been executed.

However, the false outcome of the decision has not been executed.

Therefore:

- Statement coverage = 100%
- Branch coverage = 50%

**Why the other options are incorrect:**

- A: The false branch outcome has not been tested.
- C: All statements have been executed.
- D: Both statements have been executed.

**Syllabus mapping:** 4.3 – Statement and Branch Testing

---

## Question 15 – Branch Coverage and Statement Coverage

Which of the following statements is TRUE?

A. 100% statement coverage always guarantees 100% branch coverage.  
B. 100% branch coverage generally implies 100% statement coverage for executable code within the same measured scope.  
C. Statement coverage and branch coverage are identical.  
D. 100% branch coverage guarantees that all possible execution paths have been tested.

**Correct answer: B**

**Explanation:**

Branch coverage is generally stronger than statement coverage.

Executing every branch outcome normally requires executing every reachable statement associated with those branches.

However, branch coverage does not guarantee that every possible path has been executed.

**Why the other options are incorrect:**

- A: A test may execute every statement without executing every decision outcome.
- C: They measure different coverage objectives.
- D: A program can have many possible execution paths, including combinations of decisions and loops.

**Syllabus mapping:** 4.3 – White-Box Test Techniques

---

## Question 16 – Control Flow Graph

A developer wants to understand the flow of execution through a program and identify the decisions and possible paths.

Which representation is MOST useful?

A. Decision table  
B. Control Flow Graph  
C. Use case diagram  
D. State transition table

**Correct answer: B**

**Explanation:**

A Control Flow Graph (CFG) represents the flow of control through a program.

It consists of:

- Nodes representing statements or blocks of statements.
- Edges representing possible transfers of control.
- Decision nodes representing branching points.

CFGs are useful for understanding program structure and deriving white-box tests.

**Why the other options are incorrect:**

- A: Decision tables represent combinations of conditions and actions.
- C: Use case diagrams represent actor-system interactions.
- D: State transition tables represent states and transitions.

**Syllabus mapping:** 4.3 – White-Box Test Techniques

---

## Question 17 – White-Box Testing

A tester has access to the source code and wants to design tests based on the internal structure of the application.

Which technique should the tester use?

A. Equivalence Partitioning  
B. Boundary Value Analysis  
C. Statement Testing  
D. Use Case Testing

**Correct answer: C**

**Explanation:**

Statement Testing is a white-box technique because it derives tests from the internal code structure.

White-box testing focuses on the implementation and can use structural information to measure coverage.

**Why the other options are incorrect:**

- A: EP is a black-box technique.
- B: BVA is a black-box technique.
- D: Use Case Testing is a black-box technique.

**Syllabus mapping:** 4.3 – White-Box Test Techniques

---

# Topic 4.4 – Experience-Based Test Techniques

## Question 18 – Error Guessing

A tester has extensive experience with payment applications.

Based on previous defects, the tester decides to test:

- Duplicate payment submission.
- Negative transaction amount.
- Expired card.
- Session timeout during payment.

Which technique is being used?

A. Boundary Value Analysis  
B. Error Guessing  
C. Statement Testing  
D. Decision Table Testing

**Correct answer: B**

**Explanation:**

Error Guessing uses the tester's knowledge, experience and intuition to anticipate errors, defects and failures.

Typical examples include:

- Empty inputs.
- Invalid formats.
- Duplicate submissions.
- Unexpected special characters.
- Session timeout.
- Invalid sequences of operations.

**Why the other options are incorrect:**

- A: BVA focuses on boundaries.
- C: Statement Testing focuses on executable statements.
- D: Decision Table Testing focuses on combinations of conditions.

**Syllabus mapping:** 4.4 – Error Guessing

---

## Question 19 – Exploratory Testing

A tester receives a new application with limited documentation.

Instead of preparing detailed test cases beforehand, the tester explores the application, learns its behaviour and designs new tests based on observations.

Which technique is being applied?

A. Exploratory Testing  
B. Statement Testing  
C. Decision Table Testing  
D. Boundary Value Analysis

**Correct answer: A**

**Explanation:**

Exploratory Testing involves simultaneous learning, test design and test execution.

The tester continuously uses information gained during testing to guide further exploration.

It is particularly useful when:

- Documentation is limited.
- Requirements are unclear.
- Time is constrained.
- The tester needs to investigate unexpected behaviour.

**Why the other options are incorrect:**

- B: Statement Testing requires structural code coverage.
- C: Decision Table Testing focuses on condition combinations.
- D: BVA focuses on boundary values.

**Syllabus mapping:** 4.4 – Exploratory Testing

---

## Question 20 – Checklist-Based Testing

A testing team maintains a checklist containing common items such as:

- Verify mandatory fields.
- Check error messages.
- Validate session timeout.
- Verify access permissions.
- Check browser compatibility.

The tester uses this checklist while testing a new release.

Which technique is being used?

A. Error Guessing  
B. Checklist-Based Testing  
C. Statement Testing  
D. State Transition Testing

**Correct answer: B**

**Explanation:**

Checklist-Based Testing uses a checklist of conditions, rules or important test points to guide testing.

Checklists can be created using:

- Previous testing experience.
- Defect history.
- Business knowledge.
- Standards and regulations.
- Common quality expectations.

**Why the other options are incorrect:**

- A: Error Guessing relies on tester intuition to anticipate defects.
- C: Statement Testing measures executable statement coverage.
- D: State Transition Testing focuses on state changes.

**Syllabus mapping:** 4.4 – Checklist-Based Testing

---

## Question 21 – Choosing an Experience-Based Technique

A tester wants to investigate unexpected application behaviour without following a predefined sequence of test cases.

Which technique is MOST appropriate?

A. Exploratory Testing  
B. Statement Testing  
C. Decision Table Testing  
D. Boundary Value Analysis

**Correct answer: A**

**Explanation:**

Exploratory Testing allows testers to adapt their test approach based on observations and newly acquired information.

It is not the absence of structure. Exploratory testing can be guided by:

- Test charters.
- Testing objectives.
- Time-boxed sessions.
- Notes and observations.

**Why the other options are incorrect:**

- B: Statement Testing is code-oriented.
- C: Decision Table Testing is based on condition combinations.
- D: BVA is based on input boundaries.

**Syllabus mapping:** 4.4 – Exploratory Testing

---

## Question 22 – Error Guessing vs Exploratory Testing

A tester remembers that a previous application failed when users entered extremely long strings.

The tester deliberately enters a very long string into a text field to check whether the new application fails.

Which technique is MOST directly demonstrated?

A. Exploratory Testing  
B. Error Guessing  
C. Statement Testing  
D. Decision Table Testing

**Correct answer: B**

**Explanation:**

The tester is using previous experience and knowledge of common defects to predict a potential failure.

That is Error Guessing.

**Why the other options are incorrect:**

- A: Exploratory Testing involves learning, test design and execution together.
- C: Statement Testing measures code execution.
- D: Decision Table Testing evaluates combinations of conditions.

**Syllabus mapping:** 4.4 – Error Guessing

---

# Topic 4.5 – Collaboration-Based Test Approaches

## Question 23 – Acceptance Criteria

A development team is discussing a user story:

"As a customer, I want to reset my password so that I can regain access to my account."

Which of the following is the BEST example of an acceptance criterion?

A. The developer should implement password reset functionality.  
B. The application should be user-friendly.  
C. Given a registered user, when a valid reset request is submitted, then a password reset link should be sent to the registered email address.  
D. The QA team should test password reset functionality.

**Correct answer: C**

**Explanation:**

Acceptance criteria define specific conditions that must be satisfied for a user story to be accepted.

Option C follows Given/When/Then and describes an observable, testable outcome.

**Why the other options are incorrect:**

- A: This describes an implementation task.
- B: This is vague and not objectively testable.
- D: This describes a testing activity, not an acceptance criterion.

**Syllabus mapping:** 4.5 – Acceptance Criteria

---

## Question 24 – Given/When/Then

In the Given/When/Then format, which element describes the expected outcome?

A. Given  
B. When  
C. Then  
D. And

**Correct answer: C**

**Explanation:**

The Given/When/Then structure is:

- Given: Initial context or preconditions.
- When: Action or event.
- Then: Expected result or outcome.

**Why the other options are incorrect:**

- A: Defines the initial context.
- B: Defines the action or event.
- D: Connects additional conditions or actions; it is not the primary expected-outcome keyword.

**Syllabus mapping:** 4.5 – Given/When/Then

---

## Question 25 – Three Amigos

A product owner, developer and tester meet to discuss a user story before implementation.

They discuss requirements, possible scenarios, edge cases and acceptance criteria.

Which collaborative practice is being used?

A. Retrospective  
B. Three Amigos  
C. Pair Programming  
D. Code Review

**Correct answer: B**

**Explanation:**

Three Amigos is a collaborative approach involving three perspectives:

- Business: What problem or value needs to be delivered?
- Development: How might the functionality be implemented?
- Testing: What could go wrong, and how can the behaviour be verified?

The objective is to build a shared understanding of requirements and acceptance criteria.

**Why the other options are incorrect:**

- A: A retrospective examines and improves the team's working process.
- C: Pair Programming involves two developers working together.
- D: Code Review examines source code for quality and correctness.

**Syllabus mapping:** 4.5 – Collaboration-Based Test Approaches

---

## Question 26 – Collaboration and Defect Prevention

A tester participates in requirement discussions and identifies an ambiguous business rule before development starts.

What is the MOST likely benefit?

A. The tester eliminates the need for system testing.  
B. The team can prevent misunderstandings and defects earlier in the lifecycle.  
C. The developer no longer needs to perform reviews.  
D. The team can guarantee defect-free software.

**Correct answer: B**

**Explanation:**

Early collaboration helps identify ambiguity, inconsistencies and missing information before implementation.

This supports defect prevention and reduces the cost of correcting problems later.

**Why the other options are incorrect:**

- A: Early collaboration does not eliminate the need for system testing.
- C: Reviews remain valuable quality activities.
- D: No collaboration approach can guarantee defect-free software.

**Syllabus mapping:** 4.5 – Collaboration-Based Test Approaches

---

## Question 27 – Rule-Based vs Scenario-Based Acceptance Criteria

A team documents acceptance criteria using a table containing business conditions and corresponding expected outcomes.

Which approach is being used?

A. Scenario-oriented approach  
B. Rule-oriented approach  
C. Exploratory approach  
D. Statement-based approach

**Correct answer: B**

**Explanation:**

Acceptance criteria can be documented using different approaches.

**Rule-oriented approach:**
- Describes business rules.
- Often uses bullet lists or tables.
- Helps identify conditions and expected outcomes.

**Scenario-oriented approach:**
- Describes specific examples.
- Commonly uses Given/When/Then.
- Helps explain how the system should behave in a particular situation.

**Why the other options are incorrect:**

- A: Scenario-oriented acceptance criteria generally describe individual scenarios.
- C: Exploratory testing is an experience-based technique.
- D: Statement-based testing is a white-box technique.

**Syllabus mapping:** 4.5 – Acceptance Criteria

---

## Question 28 – Scenario-Based Acceptance Criteria

A team writes the following acceptance criterion:

    Given the user has items in the shopping cart
    When the user applies a valid discount coupon
    Then the order total should be reduced by the applicable discount

What is the primary advantage of this format?

A. It guarantees complete branch coverage.  
B. It provides a concrete example of expected system behaviour.  
C. It eliminates the need for test cases.  
D. It documents the internal code structure.

**Correct answer: B**

**Explanation:**

Given/When/Then provides a concrete, understandable and testable example of expected behaviour.

It helps business stakeholders, testers and developers share a common understanding.

**Why the other options are incorrect:**

- A: Acceptance criteria do not guarantee code coverage.
- C: Acceptance criteria can be used to derive test cases; they do not eliminate them.
- D: It describes external behaviour, not internal implementation.

**Syllabus mapping:** 4.5 – Scenario-Based Acceptance Criteria

---

# Additional Scenario-Based Questions – Mixed Chapter 4

## Question 29 – Technique Selection

A tester is testing a loan application.

The loan approval decision depends on:

- Applicant income.
- Credit score.
- Existing loan status.

Different combinations of these conditions produce different approval outcomes.

Which technique is MOST appropriate?

A. Boundary Value Analysis  
B. Decision Table Testing  
C. Statement Testing  
D. Exploratory Testing

**Correct answer: B**

**Explanation:**

Decision Table Testing is useful when combinations of multiple conditions determine system behaviour.

For example:

| Income sufficient? | Credit score acceptable? | Existing loan? | Expected result |
|---|---|---|---|
| Yes | Yes | No | Approve |
| Yes | No | No | Reject |
| No | Yes | No | Reject |
| Yes | Yes | Yes | Depends on business rule |

The complete decision table should reflect the actual business rules.

**Why the other options are incorrect:**

- A: BVA is useful for testing boundaries such as minimum income or credit score.
- C: Statement Testing focuses on executable statements.
- D: Exploratory Testing is useful for investigating behaviour but is not the most systematic technique for condition combinations.

**Syllabus mapping:** 4.2 – Decision Table Testing

---

## Question 30 – Technique Selection

A tester is validating a system where an account can move through these states:

- Created
- Verified
- Suspended
- Closed

The tester needs to verify that users cannot move directly from Created to Closed without following the required business process.

Which technique is MOST suitable?

A. Equivalence Partitioning  
B. State Transition Testing  
C. Statement Testing  
D. Boundary Value Analysis

**Correct answer: B**

**Explanation:**

The requirement is about valid and invalid transitions between states.

State Transition Testing can verify:

- Valid transitions.
- Invalid transitions.
- State-dependent behaviour.
- Events that trigger transitions.

**Why the other options are incorrect:**

- A: EP groups inputs into partitions.
- C: Statement Testing measures execution of statements.
- D: BVA tests values around boundaries.

**Syllabus mapping:** 4.2 – State Transition Testing

---

## Question 31 – Coverage Interpretation

A test suite achieves 100% statement coverage but only 60% branch coverage.

Which conclusion is MOST appropriate?

A. Every possible execution path has been tested.  
B. Every executable statement was executed, but some branch outcomes were not tested.  
C. All defects have been detected.  
D. The test suite is necessarily sufficient for release.

**Correct answer: B**

**Explanation:**

Statement coverage and branch coverage measure different aspects of structural testing.

100% statement coverage means all executable statements in scope were executed.

60% branch coverage means only 60% of the measured branch outcomes were executed.

The result indicates that some decision outcomes remain untested.

**Why the other options are incorrect:**

- A: Statement coverage does not guarantee path coverage.
- C: Coverage does not guarantee defect detection.
- D: Release readiness requires additional quality and risk considerations.

**Syllabus mapping:** 4.3 – White-Box Test Techniques

---

## Question 32 – Selecting an Experience-Based Technique

A tester is asked to test a feature in a short time. There is no detailed test documentation, but the tester has substantial domain experience.

The tester uses a list of frequently missed test conditions from previous projects.

Which technique is MOST directly being used?

A. Checklist-Based Testing  
B. Boundary Value Analysis  
C. Statement Testing  
D. Use Case Testing

**Correct answer: A**

**Explanation:**

Checklist-Based Testing uses an established list of test conditions or quality considerations to guide testing.

The checklist can be derived from experience, previous defects and domain knowledge.

**Why the other options are incorrect:**

- B: BVA focuses on input boundaries.
- C: Statement Testing is a white-box technique.
- D: Use Case Testing derives tests from user-system interactions.

**Syllabus mapping:** 4.4 – Checklist-Based Testing

---

## Question 33 – Acceptance Criteria and Collaboration

During refinement, the tester discovers that the requirement "The application should respond quickly" is unclear.

What should the tester do?

A. Accept the requirement and test it after development.  
B. Collaborate with stakeholders to define measurable and testable acceptance criteria.  
C. Ignore the requirement because performance testing is a separate activity.  
D. Convert the requirement directly into a code coverage target.

**Correct answer: B**

**Explanation:**

Vague requirements should be clarified through collaboration.

For example, "The application should respond quickly" can be converted into a measurable acceptance criterion:

"The search results should be displayed within two seconds for 95% of requests under the agreed test conditions."

The actual threshold must be agreed with stakeholders.

**Why the other options are incorrect:**

- A: Waiting until development is complete increases the risk of misunderstanding.
- C: Performance requirements are still requirements and need clarification.
- D: Code coverage does not define response-time expectations.

**Syllabus mapping:** 4.5 – Collaboration-Based Test Approaches

---

## Question 34 – Test Technique Classification

Which of the following is a correct classification?

A. Boundary Value Analysis – White-box  
B. Statement Testing – Experience-based  
C. Error Guessing – Experience-based  
D. Decision Table Testing – White-box

**Correct answer: C**

**Explanation:**

Correct classification:

| Test technique | Category |
|---|---|
| Equivalence Partitioning | Black-box |
| Boundary Value Analysis | Black-box |
| Decision Table Testing | Black-box |
| State Transition Testing | Black-box |
| Use Case Testing | Black-box |
| Statement Testing | White-box |
| Branch Testing | White-box |
| Error Guessing | Experience-based |
| Exploratory Testing | Experience-based |
| Checklist-Based Testing | Experience-based |

**Why the other options are incorrect:**

- A: BVA is black-box.
- B: Statement Testing is white-box.
- D: Decision Table Testing is black-box.

**Syllabus mapping:** 4.1–4.4 – Test Technique Classification

---

## Question 35 – Choosing Between Black-Box and White-Box

A tester does not have access to source code but has access to requirements and business rules.

Which category of test techniques can the tester primarily use?

A. White-box techniques  
B. Black-box techniques  
C. Code coverage techniques only  
D. Statement testing only

**Correct answer: B**

**Explanation:**

Black-box testing derives tests from specifications, requirements and expected system behaviour without requiring knowledge of the internal code structure.

Examples include:

- Equivalence Partitioning.
- Boundary Value Analysis.
- Decision Table Testing.
- State Transition Testing.
- Use Case Testing.

**Why the other options are incorrect:**

- A: White-box techniques depend on knowledge of internal structure.
- C: Code coverage requires access to executable code and appropriate measurement.
- D: Statement Testing is a white-box technique.

**Syllabus mapping:** 4.1–4.3 – Test Technique Classification

---

# Answer Key – Section B

| Question | Answer | Topic |
|---|---|---|
| 1 | B | Test Techniques Overview |
| 2 | B | Technique Selection |
| 3 | B | Equivalence Partitioning |
| 4 | B | Boundary Value Analysis |
| 5 | B | Boundary Value Analysis |
| 6 | C | Decision Table Testing |
| 7 | C | Decision Table Testing |
| 8 | B | State Transition Testing |
| 9 | B | State Transition Coverage |
| 10 | A | Use Case Testing |
| 11 | B | Equivalence Partitioning |
| 12 | C | Statement Coverage |
| 13 | C | Branch Coverage |
| 14 | B | Statement vs Branch Coverage |
| 15 | B | Coverage Relationships |
| 16 | B | Control Flow Graph |
| 17 | C | White-Box Testing |
| 18 | B | Error Guessing |
| 19 | A | Exploratory Testing |
| 20 | B | Checklist-Based Testing |
| 21 | A | Exploratory Testing |
| 22 | B | Error Guessing |
| 23 | C | Acceptance Criteria |
| 24 | C | Given/When/Then |
| 25 | B | Three Amigos |
| 26 | B | Collaboration |
| 27 | B | Rule-Oriented Acceptance Criteria |
| 28 | B | Scenario-Oriented Acceptance Criteria |
| 29 | B | Decision Table Testing |
| 30 | B | State Transition Testing |
| 31 | B | Coverage Interpretation |
| 32 | A | Checklist-Based Testing |
| 33 | B | Collaboration |
| 34 | C | Classification |
| 35 | B | Black-Box Testing |

---

# Quick Revision – Chapter 4

## 1. Test Technique Classification

| Category | Techniques | Main focus |
|---|---|---|
| Black-box | EP, BVA, Decision Table, State Transition, Use Case | External behaviour |
| White-box | Statement Testing, Branch Testing | Internal code structure |
| Experience-based | Error Guessing, Exploratory, Checklist-Based | Tester experience and knowledge |

## 2. Black-Box Techniques Comparison

| Technique | What it tests | Typical use case |
|---|---|---|
| Equivalence Partitioning | Groups of similar input values | Age, salary, password length |
| Boundary Value Analysis | Values at and around boundaries | Minimum/maximum age |
| Decision Table Testing | Combinations of conditions | Loan approval, discounts |
| State Transition Testing | States and transitions | Login, ATM, account status |
| Use Case Testing | User-system interactions | Checkout, booking, registration |

## 3. White-Box Techniques Comparison

| Technique | Coverage objective |
|---|---|
| Statement Testing | Execute every executable statement |
| Branch Testing | Execute every branch outcome |

Remember:

- 100% statement coverage does not guarantee 100% branch coverage.
- 100% branch coverage generally implies 100% statement coverage within the same measured scope.
- Neither statement nor branch coverage guarantees all possible paths.
- Coverage does not guarantee that defects have been detected.

## 4. Experience-Based Techniques Comparison

| Technique | Meaning | Example |
|---|---|---|
| Error Guessing | Predicting defects using experience | Trying duplicate payment submission |
| Exploratory Testing | Learning, designing and executing tests together | Exploring an unfamiliar application |
| Checklist-Based Testing | Using a prepared checklist | Verifying mandatory fields and permissions |

## 5. Acceptance Criteria

**Scenario-oriented:**

Given → Initial context  
When → Action or event  
Then → Expected outcome

**Rule-oriented:**

- Business rules.
- Conditions.
- Expected outcomes.
- Often documented using bullets or tables.

## 6. Important Exam Traps

1. 100% statement coverage does not mean all branches have been executed.
2. 100% branch coverage does not mean all possible paths have been executed.
3. More test cases do not automatically mean better coverage.
4. Equivalence Partitioning groups inputs with similar expected behaviour.
5. Boundary Value Analysis focuses on boundaries and their neighbours.
6. Decision Table Testing is suitable for combinations of conditions.
7. State Transition Testing is suitable when system behaviour depends on its current state.
8. Use Case Testing focuses on interactions between actors and the system.
9. Error Guessing uses tester experience to anticipate defects.
10. Exploratory Testing combines learning, test design and execution.
11. Checklist-Based Testing uses predefined test conditions.
12. Given/When/Then documents scenario-oriented acceptance criteria.
13. Three Amigos brings business, development and testing perspectives together.
14. Acceptance criteria should be clear, specific and testable.
15. No test technique guarantees defect-free software.

---

# Self-Assessment Checklist

Before moving to Chapter 5, ensure that you can:

- [ ] Explain why test techniques are used.
- [ ] Differentiate black-box, white-box and experience-based techniques.
- [ ] Identify valid and invalid equivalence partitions.
- [ ] Calculate three-point Boundary Value Analysis test values.
- [ ] Calculate two-point Boundary Value Analysis test values.
- [ ] Construct a basic decision table.
- [ ] Calculate the number of combinations for binary conditions.
- [ ] Explain state transition testing.
- [ ] Differentiate state coverage and transition coverage.
- [ ] Explain use case testing.
- [ ] Calculate statement coverage.
- [ ] Calculate branch coverage.
- [ ] Differentiate statement coverage and branch coverage.
- [ ] Explain Error Guessing.
- [ ] Explain Exploratory Testing.
- [ ] Explain Checklist-Based Testing.
- [ ] Write acceptance criteria using Given/When/Then.
- [ ] Differentiate rule-oriented and scenario-oriented acceptance criteria.
- [ ] Explain the Three Amigos approach.

---

# Recommended Revision Strategy

**First revision – Concepts**
- Revise all five Chapter 4 syllabus sections.
- Focus on the differences between similar techniques.

**Second revision – Application**
- Practise EP and BVA calculations.
- Solve decision table scenarios.
- Practise state transition diagrams.
- Calculate statement and branch coverage.

**Third revision – Exam readiness**
- Attempt Section A without looking at the answers.
- Attempt all 35 Section B questions.
- Review incorrect answers and their explanations.
- Revisit the exam traps before the examination.

**Important:** Prioritize understanding why an option is correct and why the other three options are incorrect. This is especially important for ISTQB scenario-based questions.