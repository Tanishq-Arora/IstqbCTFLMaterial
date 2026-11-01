
# Chapter 2 — Sample Questions
## ISTQB CTFL v4.0.1 — Testing Throughout the SDLC

This document contains original questions supplied for this chapter, additional implementation-oriented practice questions, detailed explanations, exam traps, and a final revision sheet.

---

# Question Structure

| Section | Coverage |
|---|---|
| Section A | Original questions supplied by the user |
| Section B | Additional implementation-oriented and scenario-based questions |
| Section C | Consolidated answer keys |
| Section D | Detailed explanations |
| Section E | Final revision sheet and exam traps |

**Section A answer key supplied by the user:** Q1 — D · Q2 — D · Q3 — B

---

# Section A — Questions Provided

These questions are retained from the screenshots supplied by the user.

## A1. Testing Across SDLC Models

**Question**

Consider the following rule:

"For every SDLC activity there is a corresponding test activity."

In which SDLC models does this rule hold?

**Options**

- A. Only in sequential SDLC models
- B. Only in iterative SDLC models
- C. Only in iterative and incremental SDLC models
- D. In sequential, incremental, and iterative SDLC models

<details>
<summary>Correct answer and explanation</summary>

**Correct answer: D**

Testing activities should be associated with development activities throughout the SDLC, regardless of whether the project follows a sequential, incremental, or iterative model.

- **Sequential:** Test activities are planned in relation to development activities and phases.
- **Incremental:** Each increment has associated development and testing activities. Previously delivered functionality may also need regression testing.
- **Iterative:** Development and testing activities are repeated across iterations. Feedback from one iteration can influence the next.

Testing is not an activity that should begin only after all development is complete.

**Why the other options are incorrect**

| Option | Reason |
|---|---|
| A | Testing activities are not limited to sequential models. |
| B | Sequential and incremental models also have corresponding test activities. |
| C | It incorrectly excludes sequential SDLC models. |
| D | Correct — the rule applies across all three model families. |

**Exam takeaway:** Testing is integrated into the SDLC; it is not restricted to a separate final phase.

**Syllabus mapping:** 2.1 — Testing in the context of the SDLC.

</details>

---

## A2. Shift-Left Approach

**Question**

Which of the following is NOT an example of the shift-left approach?

**Options**

- A. Reviewing the user requirements before they are formally accepted by the stakeholders
- B. Writing a component test before the corresponding code is written
- C. Executing a performance efficiency test for a component during component testing
- D. Writing a test script before setting up the configuration management process

<details>
<summary>Correct answer and explanation</summary>

**Correct answer: D**

Shift-left means performing testing activities earlier in the SDLC instead of postponing them until later stages.

Early testing helps identify defects when they are generally less expensive and easier to fix.

- **A:** Reviewing requirements before formal acceptance is an early testing activity. It can identify ambiguity, omissions, and inconsistencies.
- **B:** Writing a component test before the corresponding code is written is an example of an early testing practice, such as test-driven development.
- **C:** Performing performance-efficiency testing at component level brings testing of a quality characteristic to an earlier test level.
- **D:** Writing a test script before setting up configuration management does not, by itself, demonstrate that testing has been shifted earlier in the SDLC.

**Why the other options are incorrect**

| Option | Reason |
|---|---|
| A | Early review of requirements is shift-left. |
| B | Preparing tests before implementation is shift-left. |
| C | Testing performance efficiency at component level is shift-left. |
| D | Correct — this does not demonstrate the shift-left approach. |

**Exam takeaway:** Identify whether the option moves a testing activity earlier in the lifecycle. Merely changing the order of two unrelated tasks is not necessarily shift-left.

**Syllabus mapping:** 2.1 — Shift-left approach.

</details>

---

## A3. Confirmation Testing vs Regression Testing

**Question**

You are testing a user story with three acceptance criteria: AC1, AC2 and AC3.

- AC1 is covered by test case TC1.
- AC2 is covered by test case TC2.
- AC3 is covered by test case TC3.

The test execution history had three test runs on three consecutive versions of the software:

| Test Case | Execution 1 | Execution 2 | Execution 3 |
|---|---|---|---|
| TC1 / AC1 | (1) Failed | (4) Passed | (7) Passed |
| TC2 / AC2 | (2) Passed | (5) Failed | (8) Passed |
| TC3 / AC3 | (3) Failed | (6) Failed | (9) Passed |

Tests are repeated once you are informed that all defects found in the test run are corrected and a new version of the software is available.

Which of the above tests are executed as regression tests?

**Options**

- A. Only 4, 7, 8, 9
- B. Only 5, 7
- C. Only 4, 6, 8, 9
- D. Only 5, 6

<details>
<summary>Correct answer and detailed execution analysis</summary>

**Correct answer: B — Only 5, 7**

First, remember:

- **Confirmation testing (retesting):** Checks whether a previously reported defect has been fixed.
- **Regression testing:** Checks whether a change has caused adverse effects in areas that were previously working.

### Execution 1 → Execution 2

| Test | Previous Result | New Result | Classification |
|---|---|---|---|
| TC1 — (1) → (4) | Failed | Passed | Confirmation testing |
| TC2 — (2) → (5) | Passed | Failed | Regression testing |
| TC3 — (3) → (6) | Failed | Failed | Confirmation testing |

- TC1: Previously failed and now passes. The fix is confirmed.
- TC2: Previously passed and now fails. This indicates a possible regression.
- TC3: Previously failed and still fails. The original defect has not yet been fixed.

Therefore, **(5) is a regression test**.

### Execution 2 → Execution 3

| Test | Previous Result | New Result | Classification |
|---|---|---|---|
| TC1 — (4) → (7) | Passed | Passed | Regression testing |
| TC2 — (5) → (8) | Failed | Passed | Confirmation testing |
| TC3 — (6) → (9) | Failed | Passed | Confirmation testing |

- TC1: Previously passed and continues to pass after changes. It checks for adverse effects.
- TC2: Previously failed and now passes. The fix is confirmed.
- TC3: Previously failed and now passes. The fix is confirmed.

Therefore, **(7) is a regression test**.

### Final answer

The regression tests are:

- (5)
- (7)

**Why the other options are incorrect**

| Option | Reason |
|---|---|
| A | Includes confirmation tests (4), (8), and (9). |
| B | Correct — (5) and (7) check for adverse effects on previously working functionality. |
| C | Includes tests that check previously failing functionality and misses the correct regression classification. |
| D | Includes (6), a confirmation test, and misses (7). |

**Exam takeaway:** Classify a test by comparing its result with the previous relevant execution, not simply by looking at its latest Pass/Fail status.

**Syllabus mapping:** 2.2 — Confirmation testing and regression testing.

</details>

---

# Section B — Additional Implementation-Oriented and Scenario-Based Questions

These are original practice questions created for this notes repository. They are not claimed to be official ISTQB questions or actual past examination questions.

**Instructions:**

- Attempt all questions before checking the answer key.
- Focus on identifying the testing concept from the scenario.
- Pay attention to the distinction between test levels, test types, test approaches and testing activities.
- Some questions require applying multiple concepts.

---

## B1. Choosing a Test Activity for an SDLC Model

A team is developing an online banking application using an incremental model.

The first increment delivers login and account balance functionality. The second increment adds fund transfers.

Which approach best aligns testing with this SDLC model?

- A. Test the entire application only after all increments are completed.
- B. Test each increment and perform appropriate regression testing on existing functionality.
- C. Perform testing only during the first increment.
- D. Avoid testing until the application is deployed to production.

## B2. Identifying Shift-Left in Requirements Work

A business analyst has prepared requirements for a new payment feature.

Before developers begin implementation, a tester reviews the requirements and identifies that the handling of failed payments is not defined.

Which statement best describes this activity?

- A. It is regression testing because an existing feature may be affected.
- B. It is shift-left because a testing activity is performed early to identify a defect in the requirements.
- C. It is acceptance testing because the business analyst prepared the requirements.
- D. It is confirmation testing because the requirement is being checked again.

## B3. Shift-Left and Test-Driven Development

A developer follows this sequence while implementing a tax calculation component:

1. Writes a test for the expected tax calculation.
2. Executes the test and observes that it fails.
3. Implements the calculation logic.
4. Executes the test again and observes that it passes.

Which practice does this scenario most clearly demonstrate?

- A. Shift-left / test-first development
- B. Regression testing only
- C. Operational acceptance testing
- D. Maintenance testing

## B4. Selecting the Appropriate Test Level

A developer has completed a method that calculates the discount applicable to a shopping cart.

The tester wants to verify the method independently, without involving the database, user interface, or payment service.

Which test level is most appropriate?

- A. System testing
- B. System integration testing
- C. Component testing
- D. Acceptance testing

## B5. Identifying Component Integration Testing

An e-commerce application contains an Order component and an Inventory component.

The Order component calls the Inventory component to reserve stock.

The team wants to verify that the correct product ID and quantity are passed and that the reservation response is handled correctly.

What should be the primary focus?

- A. Testing the Order component in isolation
- B. Testing the interface and interaction between the Order and Inventory components
- C. Testing the complete application against business requirements
- D. Testing the application with real end users

## B6. Identifying System Integration Testing

An online travel booking system communicates with an external airline API and a payment gateway.

The team wants to verify the interactions between the booking system and these external services.

Which test level is most appropriate?

- A. Component testing
- B. Component integration testing
- C. System testing
- D. System integration testing

## B7. Identifying System Testing

A complete payroll application is deployed in a representative test environment.

The team verifies:

- End-to-end salary processing.
- Report generation.
- Usability.
- Response time against system requirements.

Which test level is being performed?

- A. Component testing
- B. System testing
- C. Component integration testing
- D. Unit testing

## B8. Choosing an Acceptance Testing Form

A software vendor has delivered a customized claims-processing application.

The customer executes tests to determine whether the system meets the agreed contractual acceptance criteria before formally accepting delivery.

Which form of acceptance testing is this?

- A. Operational acceptance testing
- B. Contractual acceptance testing
- C. Component testing
- D. System integration testing

## B9. Operational Acceptance Testing

A bank is preparing to deploy a new banking application.

Before go-live, its operations team verifies:

- Backup and restore procedures.
- Monitoring.
- Recovery.
- Operational readiness.

Which type of testing is most relevant?

- A. User acceptance testing
- B. Operational acceptance testing
- C. Component integration testing
- D. Confirmation testing

## B10. Functional vs Non-Functional Testing

A tester verifies that a user can reset a password using a registered email address.

Another tester measures whether the password-reset request is completed within two seconds under the expected workload.

How should these two tests be classified?

- A. Both are functional tests.
- B. Both are non-functional tests.
- C. The first is functional; the second is non-functional.
- D. The first is non-functional; the second is functional.

## B11. Black-Box vs White-Box Testing

A tester derives test cases from the documented business rules for an insurance premium calculator.

The tester does not inspect the source code or internal program structure.

Which test approach is being used?

- A. White-box testing
- B. Black-box testing
- C. Component integration testing
- D. Structural testing

## B12. White-Box Testing in Practice

A developer examines the source code of a method and designs tests to execute every decision outcome in its conditional logic.

Which test approach is being used?

- A. Black-box testing
- B. Acceptance testing
- C. White-box testing
- D. System integration testing

## B13. Confirmation Testing After a Defect Fix

A customer reports that applying a valid discount code causes the checkout page to display an incorrect total.

The developer fixes the defect and provides a new build.

The tester repeats the steps that previously reproduced the incorrect total.

What is the primary purpose of this test?

- A. Regression testing
- B. Confirmation testing
- C. System integration testing
- D. Operational testing

## B14. Regression Testing After a Change

A developer modifies the payment calculation logic to support a new payment method.

The tester reruns previously passing tests for existing card payments to ensure that the change has not broken them.

What is the primary purpose of this test?

- A. Confirmation testing
- B. Regression testing
- C. Acceptance testing
- D. Component testing

## B15. Maintenance Testing After Environment Migration

An organization migrates its application from an on-premises server to a cloud platform.

The application code is mostly unchanged, but the database, operating environment, and deployment configuration are different.

What is the most appropriate testing consideration?

- A. No testing is needed because the application code has not changed.
- B. Test only the user interface.
- C. Perform maintenance testing that considers the changed environment, migrated data, and possible regressions.
- D. Perform only component testing.

## B16. Maintenance Testing After Retirement

A company is retiring an old application but must retain its records for seven years.

The team needs to verify that archived data can be retrieved when required and that restore procedures work.

Which activity is most relevant?

- A. Testing data archiving, retrieval, and restoration procedures as part of maintenance/retirement activities
- B. Component integration testing of the old application
- C. Performance testing of a new feature
- D. Confirmation testing of every historical defect

## B17. Determining Maintenance Test Scope

A small change is made to a low-risk text label in an application.

The team is deciding how much maintenance testing is necessary.

Which set of factors should primarily guide the scope?

- A. Only the number of testers available
- B. The degree of risk of the change, the size of the existing system, and the size of the change
- C. Only the number of requirements in the original project
- D. Only the programming language used

## B18. Impact Analysis Before a Change

A team plans to modify a shared authentication service used by:

- The mobile application.
- The web portal.
- The partner API.

Before implementing the change, the tester identifies which components and integrations may be affected.

What is this activity called?

- A. Confirmation testing
- B. Impact analysis
- C. Acceptance testing
- D. Component testing

## B19. Identifying a Regression Risk

A defect is fixed in the order-placement workflow.

The fix changes a shared calculation method also used by order cancellation and refunds.

Which testing activity is especially important after confirming the original defect is fixed?

- A. Regression testing of potentially affected workflows
- B. Repeating only the original failing test
- C. Testing only the new code line
- D. Skipping testing because the original defect is fixed

## B20. Selecting a Suitable Test Environment

A team is testing whether a system can communicate correctly with an external payment service and a customer identity provider.

The interactions depend on:

- Network configuration.
- Service endpoints.
- Certificates.
- Environment-specific settings.

Which consideration is most important?

- A. Use any environment because test results are independent of the environment.
- B. Use a suitable test environment, preferably representative of the operational environment.
- C. Test only the individual methods in isolation.
- D. Replace all external interactions with manual checks.

---

# Section C — Consolidated Answer Keys

## Section A — Original Questions

| Question | Correct Answer | Topic |
|---|---|---|
| A1 | D | Testing across SDLC models |
| A2 | D | Shift-left approach |
| A3 | B | Confirmation vs regression testing |

## Section B — Additional Practice Questions

| Question | Answer | Topic | Difficulty |
|---|---|---|---|
| B1 | B | Incremental SDLC testing | K2 |
| B2 | B | Shift-left / early reviews | K2 |
| B3 | A | Test-first development | K2 |
| B4 | C | Component testing | K1/K2 |
| B5 | B | Component integration testing | K2 |
| B6 | D | System integration testing | K2 |
| B7 | B | System testing | K2 |
| B8 | B | Contractual acceptance testing | K2 |
| B9 | B | Operational acceptance testing | K2 |
| B10 | C | Functional vs non-functional testing | K2 |
| B11 | B | Black-box testing | K2 |
| B12 | C | White-box testing | K2 |
| B13 | B | Confirmation testing | K2 |
| B14 | B | Regression testing | K2 |
| B15 | C | Maintenance testing / migration | K2 |
| B16 | A | Maintenance testing / retirement | K2 |
| B17 | B | Maintenance test scope | K2 |
| B18 | B | Impact analysis | K2 |
| B19 | A | Regression testing | K2 |
| B20 | B | Test environment | K2 |

---

# Section D — Detailed Explanations: Section B

## B1 — Correct Answer: B

In an incremental model, functionality is delivered in increments.

Each increment should be tested, and existing functionality should be considered for regression testing when new functionality is added.

- **A:** Delays testing until the end and ignores testing within increments.
- **B:** Correctly combines testing of each increment with regression testing.
- **C:** Incorrectly limits testing to the first increment.
- **D:** Postpones testing until production, which is not an appropriate testing strategy.

**Remember:** Incremental development does not mean testing only once at the end.

## B2 — Correct Answer: B

The tester reviews requirements before implementation and identifies missing behavior.

This is an early testing activity and an example of shift-left.

- **A:** Incorrect because no existing behavior is being retested for side effects.
- **B:** Correct because the review takes place early.
- **C:** Incorrect because the scenario does not describe user acceptance of the finished system.
- **D:** Incorrect because no previously fixed defect is being checked.

**Remember:** Reviews of requirements and other work products are testing activities and can support shift-left.

## B3 — Correct Answer: A

The test is written and executed before the production code.

This is a test-first approach and an example of shift-left.

The initial failure is expected because the implementation does not yet exist. After implementation, the test passes.

**Remember:** A test failing before implementation does not automatically mean that a product defect has been found.

## B4 — Correct Answer: C

Component testing focuses on testing an individual component in isolation.

A method or class can be tested independently using suitable test support, such as a unit-testing framework or test harness.

- System testing evaluates the complete system.
- System integration testing focuses on interfaces with external systems or services.
- Acceptance testing evaluates readiness and fulfillment of user or business needs.

**Remember:** Component testing is commonly called unit testing.

## B5 — Correct Answer: B

The scenario concerns communication between two components within the same system.

Component integration testing focuses on interfaces and interactions between components.

**Remember the distinction:**

| Test Level | Focus |
|---|---|
| Component testing | One component in isolation |
| Component integration testing | Interactions between components |
| System integration testing | Interactions between the system under test and other systems or external services |

## B6 — Correct Answer: D

The booking system interacts with external systems: an airline API and a payment gateway.

Testing these interfaces and interactions is system integration testing.

**Remember:** The word "external" is an important clue when distinguishing system integration testing from component integration testing.

## B7 — Correct Answer: B

The application is tested as a complete system.

The team evaluates end-to-end behavior and both functional and non-functional characteristics.

**Remember:** System testing focuses on the overall behavior and capabilities of the system and is related to system specifications.

## B8 — Correct Answer: B

The customer checks the delivered application against agreed contractual acceptance criteria.

This is contractual acceptance testing.

- Operational acceptance testing focuses on operational readiness.
- User acceptance testing focuses on whether the system meets users' needs in their context.
- Component and system integration testing are not acceptance-testing forms.

## B9 — Correct Answer: B

Backup, restore, monitoring, recovery, and operational readiness are typical concerns of operational acceptance testing.

**Remember:** Operational acceptance testing asks whether the system can be operated and maintained effectively in its intended environment.

## B10 — Correct Answer: C

- Password reset using a registered email address checks **what** the system does: functional testing.
- Completing the request within a response-time target checks **how well** the system performs: non-functional testing, specifically performance efficiency.

**Remember:** Functional testing checks behavior; non-functional testing checks quality characteristics.

## B11 — Correct Answer: B

The tester derives tests from documented business rules without examining internal code or structure.

This is black-box, or specification-based, testing.

**Remember:** Black-box testing focuses on externally observable behavior against specifications.

## B12 — Correct Answer: C

The tester uses source code and decision logic to design tests.

This is white-box, or structure-based, testing.

**Remember:** White-box testing derives tests from internal structure, such as code, control flow, and data flow.

## B13 — Correct Answer: B

The tester repeats the steps that previously reproduced the defect to verify that the fix works.

This is confirmation testing.

**Remember:** Confirmation testing answers:

"Has the specific defect been fixed?"

## B14 — Correct Answer: B

Previously passing card-payment tests are rerun after a change to ensure that existing behavior has not been adversely affected.

This is regression testing.

**Remember:** Regression testing answers:

"Has the change broken anything that previously worked?"

## B15 — Correct Answer: C

A migration changes the operational environment even if most application code remains unchanged.

Maintenance testing may need to cover:

- The new environment.
- Data conversion or migration.
- Changed software.
- Possible regressions.

**Remember:** A change to the environment can trigger maintenance testing even when application code changes very little.

## B16 — Correct Answer: A

When a system is retired but data must be retained, testing may be needed for:

- Data archiving.
- Data retrieval.
- Restoration procedures.

**Remember:** Retirement does not mean that testing is unnecessary. Retained data may still need to be accessible and recoverable.

## B17 — Correct Answer: B

The scope of maintenance testing typically depends on:

1. The degree of risk of the change.
2. The size of the existing system.
3. The size of the change.

These factors help determine the appropriate extent of testing.

## B18 — Correct Answer: B

Impact analysis identifies which parts of a system may be affected by a proposed change.

It can be performed before implementation to help determine the likely consequences and testing scope.

**Remember:** Impact analysis helps answer:

"What could this change affect?"

## B19 — Correct Answer: A

The original defect should be confirmation tested.

Because the fix changes a shared method used by other workflows, regression testing of potentially affected workflows is also important.

**Remember:** Confirmation and regression testing are complementary; a change can require both.

## B20 — Correct Answer: B

The behavior depends on external endpoints, certificates, network configuration, and environment settings.

A suitable test environment, preferably representative of the operational environment, is important for meaningful results.

**Remember:** Environment differences can affect integration behavior and the reliability of test results.

---

# Section E — Final Revision Sheet

## 1. Test Levels

| Test Level | Main Focus | Example |
|---|---|---|
| Component testing | Individual component in isolation | Testing a discount-calculation method |
| Component integration testing | Interfaces/interactions between components | Order component communicating with Inventory component |
| System testing | Overall behavior and capabilities of the complete system | End-to-end checkout and system performance |
| System integration testing | Interfaces between the system and external systems/services | Application communicating with a payment gateway |
| Acceptance testing | Validation and readiness for deployment; fulfillment of business needs | Customer validating agreed business workflows |

## 2. Main Forms of Acceptance Testing

| Form | Main Focus |
|---|---|
| User acceptance testing (UAT) | Whether the system meets users' needs and expectations |
| Operational acceptance testing | Operational readiness, such as backup, recovery, and maintainability |
| Contractual acceptance testing | Agreed contractual acceptance criteria |
| Regulatory acceptance testing | Compliance with applicable regulations and standards |

## 3. Test Types and Test Approaches

| Concept | Main Question It Answers |
|---|---|
| Functional testing | What does the system do? |
| Non-functional testing | How well does the system work? |
| Black-box testing | Does behavior match the specification? |
| White-box testing | Is the internal structure adequately exercised? |

## 4. Confirmation Testing vs Regression Testing

| Confirmation Testing | Regression Testing |
|---|---|
| Verifies that a specific defect has been fixed | Checks for adverse consequences of a change |
| Re-executes previously failing tests | Often re-executes previously passing tests |
| Focuses on the reported defect | Focuses on areas that may have been affected |

## 5. Maintenance Testing

Maintenance testing may be triggered by:

1. **Modifications:** Planned enhancements, corrective changes, and hot fixes.
2. **Upgrades or migrations:** Changes to the operational environment, platform, or migrated data.
3. **Retirement:** Archiving data and testing retrieval or restoration procedures.

The scope of maintenance testing typically depends on:

- Risk of the change.
- Size of the existing system.
- Size of the change.

## 6. High-Value Exam Traps

- Testing activities are associated with SDLC activities across sequential, incremental, and iterative models.
- Shift-left means performing testing activities earlier; it does not simply mean doing any task before another task.
- Component testing is not the same as component integration testing.
- System integration testing focuses on interactions with external systems and services.
- Acceptance testing is about validation and readiness, not merely another name for system testing.
- Functional and non-functional testing can be performed at multiple test levels.
- Black-box and white-box describe test approaches, not test levels.
- Confirmation testing and regression testing may both be required after a change.
- Maintenance testing can be triggered by environment migration or system retirement, not only by code changes.

---

# Self-Assessment Checklist

- [ ] I can explain how testing relates to sequential, incremental, and iterative SDLC models.
- [ ] I can identify shift-left examples and non-examples.
- [ ] I can distinguish component, component integration, system, system integration, and acceptance testing.
- [ ] I can distinguish UAT, operational, contractual, and regulatory acceptance testing.
- [ ] I can classify functional and non-functional testing scenarios.
- [ ] I can distinguish black-box and white-box testing.
- [ ] I can classify confirmation and regression tests from execution histories.
- [ ] I can identify maintenance testing triggers.
- [ ] I can explain impact analysis and factors affecting maintenance test scope.

---

# Source and Accuracy Note

- **Section A:** Based on the three question screenshots supplied by the user.
- **Section A answer key:** Follows the user's stated answers (D, D, B).
- **Section B:** Newly authored practice material based on the Chapter 2 concepts represented in the supplied study material.
- Section B questions are not official ISTQB exam content or verified past examination questions.
- Explanations are provided to support conceptual understanding and scenario-based exam preparation.
