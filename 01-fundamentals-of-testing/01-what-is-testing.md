
# 1.1 What Is Testing?

## Purpose of These Notes

Understand the meaning of software testing, its objectives, the activities involved in testing, and the difference between testing and debugging.

**Syllabus mapping:** ISTQB CTFL — Chapter 1, Fundamentals of Testing, Topic 1.1, What Is Testing?

**Exam focus:**
- Define software testing accurately.
- Understand testing objectives.
- Recognize static and dynamic testing.
- Understand testing as more than test execution.
- Distinguish testing from debugging.
- Identify the appropriate testing objective in a scenario.

> These notes are based on the concepts discussed in this chapter and the standard CTFL terminology. The practice questions are original, not verified official ISTQB questions or past examination questions.

---

## 1. What Is Software Testing?

### Definition

Software testing is a set of activities intended to discover defects and evaluate the quality of software work products.

These work products, when being tested, are called **test objects**.

A test object may include:
- Requirements
- User stories
- Design documents
- Source code
- Test scripts
- APIs
- Individual software components
- Integrated systems
- Complete applications

### Important Concepts

**Testing is not just test execution.**

A common misconception is that testing consists only of running software and checking the results.

Testing also includes:
- Planning
- Analysis
- Design
- Implementation
- Monitoring
- Control
- Completion activities

**Testing is not exclusively verification.**

Testing may evaluate whether specified requirements have been fulfilled and whether the product meets stakeholder needs and expectations.

**Testing may be static or dynamic.**

- **Static testing:** Evaluates a work product without executing the software. Examples include reviews and static analysis.
- **Dynamic testing:** Evaluates software by executing it and examining its behavior and results.

**Testing is not purely a technical activity.**

Testing also requires planning, management, estimation, monitoring, and control.

### Practical SDET Example

Suppose you are testing a payment application.

Your responsibilities may include:

1. Reviewing payment requirements.
2. Identifying test conditions.
3. Designing API test cases.
4. Preparing test data.
5. Executing automated tests.
6. Comparing actual and expected results.
7. Reporting defects.
8. Monitoring execution progress.
9. Reporting quality risks to stakeholders.

Only some of these activities involve executing tests, but all can contribute to the overall testing effort.

### Exam Trap

**Incorrect:** Testing means executing test cases.

**Correct:** Test execution is one activity within the broader testing process.

---

## 2. Test Objectives

### Definition

Test objectives describe what testing is intended to achieve.

The appropriate objectives depend on the project, test level, test type, risks, and stakeholder needs.

### The Typical Test Objectives

#### 1. Evaluating Work Products

Testing can evaluate requirements, user stories, designs, code, and other work products.

**Example:** Reviewing an API specification to identify ambiguous error-handling requirements.

#### 2. Triggering Failures and Finding Defects

Dynamic testing may trigger failures caused by defects. Static testing can directly identify defects in work products.

**Example:** An API returns an incorrect HTTP status code when an invalid token is supplied.

#### 3. Ensuring Required Coverage

Testing helps establish whether the required coverage of a test object has been achieved.

**Example:** Confirming that all specified payment methods have been covered by the planned tests.

#### 4. Reducing Risk

Testing provides information that helps reduce the risk associated with inadequate software quality.

**Example:** Testing transaction integrity before releasing a banking application.

#### 5. Verifying Requirements

Testing evaluates whether specified requirements have been fulfilled.

**Example:** Checking whether a password must contain the characters required by the specification.

#### 6. Checking Compliance

Testing may verify whether a test object complies with contractual, legal, and regulatory requirements.

**Example:** Evaluating whether a system satisfies applicable requirements for handling financial records.

#### 7. Supporting Stakeholder Decisions

Testing provides information that stakeholders can use to make informed decisions.

**Example:** Reporting unresolved critical defects before a release decision.

#### 8. Building Confidence

Testing provides evidence that helps stakeholders develop confidence in the quality of the test object.

**Example:** A successful regression test cycle provides evidence about the behavior of previously tested functionality.

#### 9. Validating User Needs

Testing can help evaluate whether a test object is complete and works as expected by stakeholders.

**Example:** Confirming that a customer can complete a realistic checkout journey successfully.

### Exam Trap

Do not assume that finding defects is the only objective of testing.

Testing can also evaluate work products, measure coverage, reduce risk, verify requirements, support decisions, build confidence, and validate stakeholder needs.

---

## 3. Static Testing vs Dynamic Testing

| Aspect | Static Testing | Dynamic Testing |
|---|---|---|
| Software execution | Does not require execution of the software | Requires execution of the software |
| Typical activities | Reviews, static analysis | Functional and non-functional test execution |
| Defect detection | Can directly identify defects in work products | Can reveal failures caused by defects |
| Example | Reviewing an ambiguous requirement | Executing an API request and checking its response |
| Test object | Documents, code, and other work products | Executable software and its behavior |

### Example

A tester identifies that a requirement does not define the expected response for an expired token.

This is a defect identified through static testing.

Later, an API test executes a request with an expired token and receives an incorrect response.

This is dynamic testing that reveals a failure.

### Exam Trap

**Static testing does not mean testing without tools.**

Static analysis tools can examine code without executing it.

**Dynamic testing involves execution**, whereas static testing does not require execution of the software.

---

## 4. Testing and Debugging

### Definition of Testing

Testing evaluates a test object to discover defects, trigger failures, and provide information about quality.

### Definition of Debugging

Debugging is the development activity concerned with finding, analyzing, and removing the causes of failures or defects.

**Testing and debugging are separate activities.**

### Dynamic Testing Followed by Debugging

When dynamic testing triggers a failure, debugging typically involves:

1. Reproducing the failure.
2. Diagnosing the root cause.
3. Fixing the cause.

### Example

An API test expects a response status of `401 Unauthorized` for an invalid token but receives `200 OK`.

**Testing activity:**
- Executes the API request.
- Compares the actual result with the expected result.
- Reports the failure.

**Debugging activity:**
- Investigates the authentication logic.
- Identifies why the invalid token was accepted.
- Corrects the underlying defect.

### Static Testing Followed by Debugging

When static testing identifies a defect, debugging is concerned with removing it.

Because static testing directly identifies a defect in a work product without executing the software, reproducing a runtime failure is not necessary to establish that particular static finding.

### Key Differences

| Aspect | Testing | Debugging |
|---|---|---|
| Primary purpose | Evaluate quality and identify defects or failures | Investigate causes and remove defects |
| Typical responsibility | Tester or testing team | Developer or another person responsible for debugging |
| Dynamic scenario | Detects a failure | Reproduces, diagnoses, and fixes the cause |
| Static scenario | Identifies a defect in a work product | Removes the identified defect |
| Output | Test results, findings, defect reports, quality information | Corrected code or another corrected work product |

### Exam Traps

- Testing can reveal a failure; it does not itself fix the defect.
- Debugging investigates and removes the cause of a failure.
- Testing and debugging are related but distinct activities.
- A tester may also debug software in practice, but the activities remain conceptually distinct.

---

## 5. Testing Activities Beyond Execution

Testing involves more than running test cases.

| Activity | Purpose | Example |
|---|---|---|
| Planning | Define objectives, scope, approach, and resources | Plan regression testing for a release |
| Analysis | Identify test conditions | Identify invalid-token scenarios |
| Design | Develop test cases and expected results | Design API tests for token expiration |
| Implementation | Prepare test procedures, data, and environments | Create automated tests and test data |
| Execution | Run tests and evaluate results | Execute API automation |
| Monitoring and control | Track progress and take corrective action | Investigate missed coverage or execution delays |
| Completion | Record results and preserve useful test assets | Summarize defects and archive test results |

The exact activities and their order depend on the project and lifecycle.

### Exam Trap

Testing activities are not necessarily performed once in a rigid sequence. In iterative and agile development, activities can overlap and be repeated.

---

## 6. Common Exam Traps

| Incorrect Statement | Correct Understanding |
|---|---|
| Testing is only test execution | Testing includes a broader set of activities |
| Testing only finds defects | Testing also evaluates quality, coverage, risk, and requirements |
| Static testing requires executing software | Static testing does not require software execution |
| Testing and debugging are identical | Testing evaluates; debugging investigates and removes causes |
| Only executable code can be tested | Requirements, designs, and other work products can also be tested |
| Testing is purely technical | Testing also involves planning, management, estimation, monitoring, and control |
| Passing tests prove the software is perfect | Test results provide evidence, not proof of complete correctness |

---

## 7. Comparison and Revision Table

| Concept | Remember This |
|---|---|
| Software testing | A set of activities to discover defects and evaluate quality |
| Test object | The work product being tested |
| Static testing | Evaluation without executing the software |
| Dynamic testing | Evaluation involving execution of the software |
| Test objective | The intended purpose of testing |
| Testing | Evaluates behavior and quality, identifies defects or failures, and provides information |
| Debugging | Finds, analyzes, and removes the causes of failures or defects |

---

## 8. Foundational CTFL-Style MCQs: Questions 1–12

> These are original practice questions, not official ISTQB questions or verified past examination questions.

### Question 1: Definition of Testing

Which statement best describes software testing?

A. Testing consists exclusively of executing test cases.  
B. Testing is a set of activities intended to discover defects and evaluate the quality of work products.  
C. Testing is the activity of fixing defects in source code.  
D. Testing is performed only after software development is complete.

### Question 2: Test Objects

A tester reviews a requirements specification and identifies an ambiguous acceptance criterion.

What is the requirements specification in this situation?

A. A test object  
B. A debugging result  
C. A runtime failure  
D. A test environment

### Question 3: Test Objectives

Which of the following is a typical test objective?

A. Guaranteeing that no defects remain  
B. Replacing all development activities  
C. Providing information that supports release decisions  
D. Fixing every defect found during execution

### Question 4: Static Testing

A tester reviews source code using a static analysis tool without executing the application.

Which type of testing is being performed?

A. Dynamic testing  
B. Static testing  
C. Debugging only  
D. Acceptance testing necessarily

### Question 5: Dynamic Testing

A tester sends a request to an API, executes the application behavior, and compares the response with the expected result.

Which activity is this?

A. Static testing  
B. Dynamic testing  
C. Requirements inspection only  
D. Debugging only

### Question 6: Testing vs Debugging

An automated test reveals that an invalid authentication token is accepted by the application.

Which activity does the test execution represent?

A. Debugging  
B. Testing  
C. Root-cause removal  
D. Code correction

### Question 7: Debugging

After an automated test reveals an authentication failure, a developer investigates the code and corrects the underlying condition.

Which activity is the developer performing?

A. Test design only  
B. Static testing only  
C. Debugging  
D. Test execution only

### Question 8: Verification Objective

A tester checks whether the application enforces the password-length requirement specified in the requirements document.

What is the main objective?

A. Verifying specified requirements  
B. Fixing the implementation  
C. Estimating the project budget  
D. Guaranteeing the absence of defects

### Question 9: Coverage Objective

A team checks whether all specified payment methods are represented in its test suite.

Which test objective is most directly relevant?

A. Debugging  
B. Ensuring required coverage  
C. Removing root causes  
D. Replacing requirements analysis

### Question 10: Stakeholder Decisions

A test manager reports unresolved high-impact defects to the release manager before deployment.

Which test objective is most directly supported?

A. Providing information for informed decisions  
B. Proving defect absence  
C. Eliminating the need for release management  
D. Executing all possible tests

### Question 11: Testing Activities

Which activity involves identifying test conditions from a test basis?

A. Test analysis  
B. Debugging  
C. Defect fixing  
D. Production deployment

### Question 12: Failure Investigation

A dynamic test triggers a failure. The team reproduces it, diagnoses its cause, and corrects the defect.

Which sequence is most appropriate?

A. Debugging, test planning, test design  
B. Test execution followed by debugging activities  
C. Static analysis followed by release approval only  
D. Test completion followed by requirements gathering only

---

## 9. Advanced Scenario-Based MCQs: Questions 13–32

### Question 13: Testing Is More Than Execution

A QA engineer spends time reviewing requirements, designing test cases, preparing data, executing tests, and reporting quality risks. A manager says only the execution time counts as testing.

Which statement is most accurate?

A. The manager is correct because only executed tests are testing.  
B. Only automated test execution counts as testing.  
C. Testing includes multiple activities beyond execution.  
D. Requirements reviews are always debugging activities.

### Question 14: A Document Can Be Tested

A tester identifies contradictory business rules in a design document before any code is written.

Which statement best describes the situation?

A. Testing cannot occur until executable code exists.  
B. The design document can be a test object.  
C. The tester must execute the design document.  
D. The finding is necessarily a runtime failure.

### Question 15: Static Analysis Finding

A static analysis tool identifies a potentially unsafe operation in source code without running the program.

Which statement is correct?

A. This is dynamic testing because source code exists.  
B. This is static testing because the software was not executed.  
C. This is debugging because the tool automatically identifies a problem.  
D. This proves that the application will fail in production.

### Question 16: Dynamic Failure

An API test sends a request with an expired token. The application returns a success response instead of the expected authentication error.

What has the test most directly demonstrated?

A. A failure in the observed behavior  
B. The root cause has been removed  
C. The application is defect-free  
D. The requirement has been corrected

### Question 17: Correcting a Defect

After a test reveals a failure, a developer inspects the authentication code, identifies the incorrect condition, and corrects it.

Which activity is primarily being performed?

A. Test planning  
B. Debugging  
C. Test completion  
D. Test estimation

### Question 18: Test Objective vs Debugging

A team executes tests to determine whether a new application meets its specified requirements. Developers later investigate and fix the defects identified.

Which statement is correct?

A. Both activities are debugging.  
B. Both activities are test execution.  
C. Testing evaluates the application; debugging investigates and removes defects.  
D. Testing begins only after debugging is complete.

### Question 19: Release Decision

A test report shows that critical transaction scenarios have not passed. The release manager uses this information to postpone deployment.

Which test objective is most directly illustrated?

A. Providing information for informed decisions  
B. Guaranteeing defect absence  
C. Removing every root cause  
D. Replacing all requirements

### Question 20: Requirements Review

A tester participates in a user-story review and identifies an unclear acceptance criterion before development begins.

Which conclusion is correct?

A. Testing cannot begin until the feature is implemented.  
B. The review can contribute to testing and early defect detection.  
C. The tester is performing dynamic testing.  
D. The tester has necessarily debugged the application.

### Question 21: Test Coverage

A team reports that all planned scenarios for the specified payment methods have been covered, but several tests have failed.

Which statement is most accurate?

A. Required coverage and successful test results are different considerations.  
B. Coverage can be claimed only if every test passes.  
C. Failed tests automatically mean no coverage exists.  
D. Coverage guarantees defect absence.

### Question 22: Testing Is Not Only Technical

A test lead estimates the effort required, monitors progress, manages risks, and reports test status to stakeholders.

Which statement is correct?

A. These are unrelated to testing.  
B. These activities can be part of testing management and control.  
C. They are exclusively debugging activities.  
D. They are possible only after release.

### Question 23: Multiple Test Objectives

A team evaluates requirements, tests transaction behavior, assesses coverage, and reports remaining risks.

Which statement best describes the team's work?

A. The team is pursuing several legitimate test objectives.  
B. Only defect detection is a valid test objective.  
C. The team is performing debugging exclusively.  
D. Risk assessment is never relevant to testing.

### Question 24: Incorrect Classification of Debugging

A tester reports that a payment calculation produces an incorrect total. A developer then investigates the calculation logic.

Which statement best distinguishes the activities?

A. The tester is debugging, while the developer is necessarily performing test execution.  
B. Both activities are identical.  
C. The tester is reporting a test finding, while the developer is investigating the cause through debugging.  
D. Neither activity is related to software quality.

### Question 25: A Test Object Without Execution

A reviewer examines a test plan and finds that a critical requirement is missing from the planned coverage.

Which statement is correct?

A. The test plan cannot be a test object.  
B. Static evaluation can identify defects in testing work products.  
C. The reviewer must run the entire application.  
D. The finding proves that a production failure has occurred.

### Question 26: Testing Objective and User Expectations

A team evaluates whether a completed application works as expected by stakeholders, rather than checking only isolated technical requirements.

Which test objective is most directly relevant?

A. Validating stakeholder needs and expectations  
B. Removing all source-code defects  
C. Proving the absence of defects  
D. Replacing debugging

### Question 27: Execution Does Not Equal Debugging

An automated test reports an incorrect API response. The tester logs the actual response and raises a defect report without modifying the application.

What is the most accurate classification?

A. The tester has completed debugging.  
B. The tester has performed a testing activity, not necessarily debugging.  
C. The tester has removed the defect.  
D. The test result proves the root cause.

### Question 28: Static Testing and Runtime Failures

A tester identifies an incorrect calculation formula in a spreadsheet used as a requirements artifact. The spreadsheet itself is reviewed without executing the software under test.

Which statement is most accurate?

A. Static testing can directly identify a defect in a work product.  
B. Dynamic testing must have occurred.  
C. The finding is necessarily a production failure.  
D. The defect can be removed only by executing test cases.

### Question 29: Test Objective of Compliance

A team tests whether a financial application satisfies specified contractual and regulatory requirements.

Which objective is most directly relevant?

A. Verifying compliance with applicable requirements  
B. Guaranteeing no defects remain  
C. Debugging the application  
D. Proving exhaustive coverage

### Question 30: Test Planning and Control

A team defines testing objectives and scope, estimates effort, monitors progress, and adjusts its plan when execution falls behind.

Which statement is correct?

A. Testing consists exclusively of executing test cases.  
B. Planning, estimation, monitoring, and control can be part of testing.  
C. These activities are necessarily defects.  
D. These activities can occur only after debugging.

### Question 31: Testing and Confidence

A test team completes a planned regression cycle and shares the results with stakeholders. The results increase confidence in previously tested functionality, but the team makes no claim that every defect has been found.

Which statement is most accurate?

A. The team has misunderstood testing because it cannot prove defect absence.  
B. Testing can build confidence without proving that no defects remain.  
C. Confidence is never a test objective.  
D. Only debugging can provide quality information.

### Question 32: Complete Understanding of Testing

Which statement best describes software testing?

A. Testing is exclusively the execution of software to find failures.  
B. Testing is exclusively the correction of defects.  
C. Testing is a broader set of activities that evaluates work products, identifies defects or failures, and provides quality information for decisions.  
D. Testing begins only after all software development activities are complete.

---

## 10. Answer Key and Explanations

### Questions 1–12

| Q | Answer | Explanation |
|---:|:---:|---|
| 1 | B | Testing includes activities to discover defects and evaluate work-product quality. |
| 2 | A | The requirements specification is the work product being evaluated. |
| 3 | C | Testing provides information that supports informed stakeholder decisions. |
| 4 | B | Static analysis does not require executing the software. |
| 5 | B | Executing an API request and evaluating its behavior is dynamic testing. |
| 6 | B | The automated test reveals the failure; it does not itself fix the cause. |
| 7 | C | Investigating and correcting the underlying cause is debugging. |
| 8 | A | The tester is checking conformance to a specified requirement. |
| 9 | B | The team is evaluating required coverage. |
| 10 | A | The report helps stakeholders make an informed release decision. |
| 11 | A | Test analysis identifies test conditions from the test basis. |
| 12 | B | Dynamic testing reveals a failure, after which debugging investigates and corrects its cause. |

### Questions 13–32

| Q | Answer | Explanation |
|---:|:---:|---|
| 13 | C | Testing includes planning, analysis, design, implementation, execution, monitoring, control, and completion activities. |
| 14 | B | Documents and designs can be test objects even before executable code exists. |
| 15 | B | Static analysis evaluates code without executing the software. |
| 16 | A | The observed behavior differs from the expected behavior, demonstrating a failure. |
| 17 | B | Investigating and correcting the underlying cause is debugging. |
| 18 | C | Testing evaluates quality and identifies findings; debugging investigates and removes causes. |
| 19 | A | The test report supports a release decision. |
| 20 | B | Reviewing requirements can identify defects before implementation. |
| 21 | A | Coverage and test pass/fail status are different considerations. |
| 22 | B | Estimation, monitoring, management, and control can be part of testing. |
| 23 | A | Testing has multiple objectives beyond defect detection. |
| 24 | C | Reporting a finding and investigating its root cause are distinct activities. |
| 25 | B | A test plan is a work product that can be evaluated statically. |
| 26 | A | The team is evaluating whether the product meets stakeholder expectations. |
| 27 | B | Reporting a test finding does not necessarily involve debugging. |
| 28 | A | Static testing can directly identify a defect in a work product. |
| 29 | A | The team is evaluating compliance with contractual and regulatory requirements. |
| 30 | B | Testing includes planning, estimation, monitoring, and control. |
| 31 | B | Testing can increase confidence without proving defect absence. |
| 32 | C | Testing is broader than execution and provides information about quality. |

---

## 11. How to Review Your Mistakes

| Mistake Type | What to Revise |
|---|---|
| Definition error | Section 1 |
| Confusing objectives | Section 2 |
| Static vs dynamic confusion | Section 3 |
| Testing vs debugging confusion | Section 4 |
| Forgetting testing activities | Section 5 |
| Misreading a scenario | Reattempt Questions 13–32 |

### Score Guide: Questions 1–12

| Score | Recommended Action |
|---:|---|
| 11–12 / 12 | Strong understanding |
| 9–10 / 12 | Review missed questions |
| 7–8 / 12 | Revisit concepts and examples |
| 0–6 / 12 | Re-study the topic |

### Score Guide: Questions 13–32

| Score | Recommended Action |
|---:|---|
| 18–20 / 20 | Strong application skills |
| 15–17 / 20 | Review confusing scenarios |
| 11–14 / 20 | Revisit testing objectives and terminology |
| 0–10 / 20 | Re-study the topic before proceeding |

These are study guidelines, not predictions of the official examination result.

---

## 12. Quick Revision Sheet

- **Testing:** A set of activities intended to discover defects and evaluate quality.
- **Test object:** The work product being tested.
- **Test objectives:** The intended purposes of testing.
- **Static testing:** Evaluation without executing the software.
- **Dynamic testing:** Evaluation involving execution of the software.
- **Testing:** Evaluates quality, identifies defects or failures, and provides information.
- **Debugging:** Investigates and removes the causes of failures or defects.

### Important Distinctions

| If the scenario describes... | Think of... |
|---|---|
| Reviewing a requirement without execution | Static testing |
| Executing an API request | Dynamic testing |
| Comparing actual and expected results | Test execution |
| Investigating why a failure occurred | Debugging |
| Fixing the underlying cause | Debugging |
| Reporting quality risks to a release manager | Supporting stakeholder decisions |
| Reviewing test coverage | Test analysis or coverage evaluation |
| Estimating and monitoring test effort | Testing management activities |

---

## 13. Self-Assessment Checklist

- [ ] I can define software testing accurately.
- [ ] I understand what a test object is.
- [ ] I can recall the typical test objectives.
- [ ] I can distinguish static from dynamic testing.
- [ ] I can explain why testing is more than execution.
- [ ] I can distinguish testing from debugging.
- [ ] I understand how testing and debugging interact.
- [ ] I can recognize test activities from scenarios.
- [ ] I can explain why test results support decisions without proving complete correctness.
- [ ] I can score at least 10/12 on the foundational MCQs.
- [ ] I can score at least 18/20 on the advanced MCQs.

---

## 14. Final Exam Takeaways

1. Testing is a set of activities, not just test execution.
2. A test object is the work product being tested.
3. Testing objectives include defect detection, coverage, risk reduction, verification, compliance, confidence, and stakeholder decision support.
4. Static testing does not require executing the software.
5. Dynamic testing evaluates software behavior through execution.
6. Testing and debugging are distinct activities.
7. Testing can reveal a failure; debugging investigates and removes its cause.
8. Requirements, designs, code, and other work products can be evaluated.
9. Testing involves planning, management, estimation, monitoring, and control.
10. Test results provide useful quality information without proving that no defects remain.
