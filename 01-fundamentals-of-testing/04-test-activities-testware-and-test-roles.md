# 1.4 Test Activities, Testware & Test Roles

## ISTQB CTFL v4.0.1 — Chapter 1: Fundamentals of Testing

## 1. Learning Objectives

By the end of this chapter, you should be able to:

- **FL-1.4.1 (K2):** Explain the various test activities and tasks.
- **FL-1.4.2 (K2):** Explain how testing is influenced by the context.
- **FL-1.4.3 (K2):** Distinguish the testware that supports the test activities.
- **FL-1.4.4 (K2):** Explain the benefits of traceability between the test basis and testware.
- **FL-1.4.5 (K2):** Compare the different roles in testing.

> **Exam focus:** Understand what each activity does, the work products it creates, how context changes testing, why traceability matters, and the difference between test management and the testing role.

---

# 2. Understanding the Test Process

Testing is not performed in isolation. It is an integral part of software development and is influenced by the project's objectives, stakeholders, resources, constraints, and development approach.

Although testing is context-dependent, there are common sets of test activities that help achieve test objectives.

These activities together form the **test process**.

The test process can be tailored according to the specific situation. The activities included, their implementation, and when they occur are normally determined during test planning.

### Key points

- Testing activities are not necessarily performed in a rigid, sequential order.
- Activities may be adapted, repeated, or performed concurrently.
- The process depends on the project and product context.
- Test planning establishes the approach for the particular situation.
- Testing must support stakeholder and business needs.

### Example

Consider an e-commerce application.

- Payment functionality may require rigorous risk-based testing.
- A frequently changing checkout feature may be tested continuously.
- A small internal utility may need a lighter testing process.
- A safety-critical application may require extensive documentation and traceability.

The test process differs because the risks, objectives, constraints, and compliance requirements differ.

**Exam trap:** There is no single test process that must be followed identically by every project.

---

# 3. The Seven Test Activities

The CTFL syllabus identifies six main test activities:

1. Test planning
2. Test monitoring and control
3. Test analysis
4. Test design
5. Test implementation
6. Test execution
7. Test completion

> Note: Test monitoring and test control are grouped together as one activity, so the list contains seven named activities when monitoring and control are described separately.

## 3.1 Test Planning

### Definition

Test planning consists of defining the test objectives and selecting an approach that best achieves those objectives within the constraints of the overall context.

### Main tasks

- Define test objectives.
- Determine the test strategy and approach.
- Identify the scope of testing.
- Estimate the effort and cost.
- Identify resources, roles, and responsibilities.
- Define the test schedule.
- Identify risks and appropriate responses.
- Define entry and exit criteria.
- Decide the required level of documentation and reporting.

### Example

A team has two weeks to test a new payment feature.

The test lead decides:
- Which payment scenarios must be tested.
- Which devices and browsers are required.
- How many testers are available.
- Which high-risk scenarios must be tested first.
- What conditions must be met before testing starts and finishes.

These decisions are part of test planning.

### Remember

**Test planning answers:** What are our test objectives, and how will we approach achieving them?

---

## 3.2 Test Monitoring and Control

Monitoring and control are closely related but have different purposes.

### A. Test Monitoring

Test monitoring involves continuously checking test activities and comparing actual progress against the test plan.

It provides information about the current status of testing.

Typical monitoring information includes:
- Tests planned versus tests executed.
- Tests passed, failed, or blocked.
- Defects identified.
- Testing effort consumed.
- Progress against milestones.
- Remaining risks and coverage.

### B. Test Control

Test control involves taking corrective or guiding actions necessary to achieve the test objectives.

It uses monitoring information to decide what should change.

Examples:
- Reprioritizing test cases.
- Assigning additional testers.
- Changing the test schedule.
- Allocating more effort to a high-risk area.
- Escalating a blocker.
- Revising the testing approach when circumstances change.

### Example

A team planned to execute 100 test cases by Friday.

On Wednesday:
- 40 tests were planned to be completed.
- Only 20 have been executed.
- A critical payment defect is blocking several scenarios.

**Monitoring:** The test lead identifies and reports that actual progress is behind the plan.

**Control:** The test lead reallocates a tester, prioritizes payment-related tests, and escalates the blocker.

### Exam distinction

| Test monitoring | Test control |
|---|---|
| Checks progress and status | Takes corrective or guiding action |
| Compares actual results with the plan | Acts on the information obtained |
| Answers: “Where are we now?” | Answers: “What should we do about it?” |

**Memory trick:** Monitoring = Measure. Control = Correct.

---

## 3.3 Test Analysis

### Definition

Test analysis involves analyzing the test basis to identify testable features and define and prioritize the associated test conditions, together with related risks and risk levels.

The **test basis** is the information used as the foundation for test analysis and test design. Examples include requirements, user stories, acceptance criteria, specifications, and other relevant documentation.

### Main tasks

- Analyze the test basis.
- Identify testable features.
- Define test conditions.
- Prioritize test conditions.
- Identify risks and assess their levels.
- Examine the test basis and test object for possible defects.
- Assess testability.

Test analysis can reveal defects such as:
- Ambiguous requirements.
- Missing requirements.
- Contradictory statements.
- Inconsistencies.
- Unclear acceptance criteria.

Test techniques can support test analysis.

### Example

Requirement:

> A user can withdraw money from an ATM.

During test analysis, the tester identifies test conditions such as:
- Withdrawal with sufficient balance.
- Withdrawal with insufficient balance.
- Withdrawal exceeding the daily limit.
- Withdrawal with an invalid PIN.
- Withdrawal when the ATM has insufficient cash.

These are **test conditions**, not yet fully specified test cases.

### Key question

**Test analysis answers: “What to test?”**

It identifies testable conditions and measurable coverage criteria.

---

## 3.4 Test Design

### Definition

Test design elaborates test conditions into test cases and other testware.

It often involves identifying coverage items that guide the specification of test case inputs.

### Main tasks

- Elaborate test conditions into test cases.
- Identify coverage items.
- Specify test data requirements.
- Define test environment requirements.
- Identify required tools and infrastructure.
- Determine expected results.
- Use test techniques to support the design.

### Example

Test condition:

> Verify that an ATM rejects withdrawals exceeding the daily withdrawal limit.

Test design specifies:
- **Precondition:** The customer has already withdrawn ₹20,000 today.
- **Input:** Another withdrawal request of ₹5,000 when the daily limit is ₹25,000 and the applicable rules prohibit exceeding that limit.
- **Expected result:** The request is rejected if it would exceed the permitted limit, and the appropriate message is displayed.

The test case turns the general condition into a specific, verifiable test.

### Key question

**Test design answers: “How to test?”**

### Important distinction

| Test analysis | Test design |
|---|---|
| Identifies test conditions | Elaborates conditions into test cases |
| Determines what needs testing | Determines how testing will be performed |
| Assesses risks and prioritizes conditions | Defines inputs, expected results, and coverage items |
| Produces prioritized test conditions | Produces test cases and design-related testware |

---

## 3.5 Test Implementation

### Definition

Test implementation involves creating or acquiring the testware necessary for test execution.

### Main tasks

- Create or acquire test data.
- Develop manual or automated test scripts.
- Organize test cases into test procedures.
- Assemble test procedures into test suites.
- Prioritize test procedures.
- Arrange procedures in a test execution schedule.
- Build and verify the test environment.
- Prepare required tools and infrastructure.

### Important terminology

**Test procedure:** A sequence of test cases, or the steps used to execute them, organized for execution.

**Test suite:** A collection of test cases or test procedures organized for a particular purpose.

**Test script:** Instructions, often executable, for performing a test. Scripts may be manual or automated.

### Example from an SDET workflow

Suppose the team has designed API test cases for login, token refresh, and logout.

During test implementation, the SDET:
- Creates the required test data.
- Writes automated API test scripts.
- Configures the test environment.
- Organizes the scripts into a regression suite.
- Arranges execution according to priority.

These activities prepare the tests for execution.

### Key distinction

**Test design creates the specification of tests; test implementation prepares the testware needed to execute them.**

---

## 3.6 Test Execution

### Definition

Test execution involves running tests according to the test execution schedule.

Execution may be manual or automated.

### Main tasks

- Execute the tests.
- Compare actual results with expected results.
- Record test outcomes.
- Log test results.
- Analyze anomalies.
- Report observed failures and associated defects.

### Example

An automated API test sends a request to create an account.

Expected result:
- HTTP status code: `201 Created`.
- A valid account identifier is returned.

Actual result:
- HTTP status code: `500 Internal Server Error`.

The test execution records the discrepancy. The team investigates the anomaly and reports the observed failure.

### Important distinction

A **failure** is observed when the system's actual behavior differs from the expected behavior. The underlying defect may need investigation.

Test execution does not automatically mean that every anomaly is caused by a software defect; environmental or test-data issues may also need to be investigated.

---

## 3.7 Test Completion

### Definition

Test completion activities usually occur at project milestones, such as the end of a test level, iteration, or release.

### Main tasks

- Prepare a test completion report.
- Document lessons learned.
- Identify improvements for future testing.
- Archive useful testware or hand it over to appropriate teams.
- Record unresolved defects and change requests.
- Create improvement actions or product backlog items.
- Shut down the test environment or return it to an agreed state.
- Communicate the testing outcome to stakeholders.

### Example

After a release:
- The team prepares a report describing the testing performed and its results.
- Useful regression scripts are retained for future releases.
- Unresolved defects are documented.
- The team records that test environment setup took too long and creates an improvement action.

These are test completion activities.

### Exam trap

Test completion is not simply stopping test execution. It includes reporting, archiving, handover, and improvement activities.

---

# 4. Test Activities — Quick Comparison

| Activity | Main purpose | Key question |
|---|---|---|
| Test planning | Define objectives and approach | What are we trying to achieve, and how will we approach it? |
| Test monitoring | Check progress against the plan | Where are we now? |
| Test control | Take corrective or guiding action | What action is needed? |
| Test analysis | Identify testable conditions | What to test? |
| Test design | Specify test cases and coverage | How to test? |
| Test implementation | Prepare testware and the environment | What must be ready to run the tests? |
| Test execution | Run tests and record results | What happened when the tests ran? |
| Test completion | Report, archive, hand over, and improve | What must be wrapped up? |

---

# 5. The Test Process in Context

Testing is influenced by contextual factors. These factors affect the test strategy, test techniques, automation level, coverage, documentation, and reporting.

## 5.1 Factors Influencing Testing

### 1. Stakeholders
Their needs, expectations, requirements, willingness to cooperate, and availability affect testing.

### 2. Team members
Their skills, knowledge, experience, availability, and training needs influence what the team can achieve.

### 3. Business domain
The criticality of the product, identified risks, market needs, and legal or regulatory requirements affect testing rigor.

### 4. Technical factors
Software type, architecture, technology, and technical complexity influence the testing approach.

### 5. Project constraints
Scope, time, budget, and available resources affect test coverage and priorities.

### 6. Organizational factors
Organizational structure, policies, standards, and established practices influence how testing is conducted.

### 7. Software development lifecycle
The development approach and engineering practices affect when and how testing takes place.

### 8. Tools
The availability, usability, and suitability of tools influence test activities and automation.

## 5.2 Practical Example

Consider two projects.

**Project A: Banking payment system**
- High financial risk.
- Strong regulatory requirements.
- Detailed traceability and reporting may be necessary.
- Extensive security and reliability testing may be required.

**Project B: Internal prototype**
- Limited business impact.
- Short delivery timeline.
- A lighter testing process may be appropriate.

The test process is tailored to the context rather than copied identically across both projects.

### Exam trap

Context affects the test process, but it does not mean testing objectives should be ignored. The approach should still be selected to achieve the objectives within the constraints.

---

# 6. Testware

## 6.1 What Is Testware?

Testware consists of the work products created during test activities and used to support testing.

Examples include test plans, test conditions, test cases, test scripts, test data, test logs, and test completion reports.

Different organizations may produce, name, organize, and manage testware differently.

**Configuration management** helps maintain the consistency and integrity of work products.

## 6.2 Testware Produced by Each Activity

### A. Test Planning
Examples:
- Test plan.
- Test schedule.
- Risk register.
- Entry and exit criteria.

A risk register records risks and information such as their likelihood, impact, and mitigation.

The schedule, risk register, and entry/exit criteria may be included within the test plan.

### B. Test Monitoring and Control
Examples:
- Test progress reports.
- Documentation of control directives.
- Risk information and updates.

### C. Test Analysis
Examples:
- Prioritized test conditions.
- Defect reports concerning defects found in the test basis, where they are not corrected directly.

### D. Test Design
Examples:
- Prioritized test cases.
- Test charters.
- Coverage items.
- Test data requirements.
- Test environment requirements.

### E. Test Implementation
Examples:
- Test procedures.
- Automated test scripts.
- Test suites.
- Test data.
- Test execution schedule.
- Test environment elements.

Test environment elements may include:
- Stubs.
- Drivers.
- Simulators.
- Service virtualization components.

### F. Test Execution
Examples:
- Test logs.
- Defect reports.

### G. Test Completion
Examples:
- Test completion report.
- Lessons learned.
- Improvement action items.
- Change requests, such as product backlog items.

## 6.3 Testware Mapping Table

| Test activity | Typical testware |
|---|---|
| Planning | Test plan, schedule, risk register, entry/exit criteria |
| Monitoring and control | Progress reports, control directives, risk information |
| Analysis | Test conditions, test-basis defect reports |
| Design | Test cases, test charters, coverage items, data/environment requirements |
| Implementation | Test procedures, test suites, scripts, test data, execution schedule |
| Execution | Test logs, defect reports |
| Completion | Completion report, lessons learned, improvement actions |

### Common exam trap

A test case and a test script are not interchangeable terms.

- **Test case:** Specifies a test, including relevant conditions, inputs, and expected results.
- **Test script:** Provides instructions for carrying out a test, often in an executable or automated form.

Also, do not assume that every testware item is a document. Testware may include data, scripts, tools or environment elements, and other work products.

---

# 7. Traceability Between the Test Basis and Testware

## 7.1 What Is Traceability?

Traceability means establishing and maintaining links between relevant test basis elements and related testware, test results, and detected defects.

For example:

`Requirement → Test condition → Test case → Test result → Defect`

These links help the team understand which requirements are tested, what the results were, and which defects are associated with them.

## 7.2 Benefits of Traceability

### 1. Evaluating test coverage
Traceability from requirements to test cases helps determine whether requirements are covered.

### 2. Evaluating residual risk
Links between risks and test results help assess the remaining risk in the test object.

### 3. Assessing the impact of changes
When a requirement changes, related test conditions and test cases can be identified.

### 4. Supporting audits and governance
Traceability helps demonstrate what was tested and supports compliance with applicable requirements.

### 5. Improving reporting
Progress and completion reports can show the status of test basis elements.

### 6. Communicating with stakeholders
Traceability makes technical testing information easier to understand.

### 7. Assessing product and process information
It provides information that helps assess product quality, process capability, and project progress against business goals.

## 7.3 Practical Example

A requirement states:

> Users must be locked out after five consecutive failed login attempts.

The team creates:
- Requirement: `REQ-LOGIN-005`
- Test condition: Verify account lockout after repeated failed attempts.
- Test case: `TC-LOGIN-021`
- Test result: Failed.
- Defect: `BUG-1042`

If the requirement changes from five attempts to three, traceability helps identify the affected test cases and related testware.

### Exam traps

- Traceability is not only about linking requirements to test cases.
- It can connect the test basis, testware, test results, risks, and defects.
- Traceability supports coverage evaluation, but the existence of links alone does not guarantee that testing is adequate.
- Traceability supports change-impact analysis, audits, reporting, and risk evaluation.

---

# 8. Roles in Testing

The CTFL syllabus covers two principal roles:

1. **Test management role**
2. **Testing role**

The allocation of tasks depends on the project context, product context, people's skills, and the organization.

The roles are responsibilities, not necessarily separate job titles.

## 8.1 Test Management Role

### Main responsibility

The test management role takes overall responsibility for the test process, the test team, and leadership of test activities.

### Main focus
- Test planning.
- Test monitoring and control.
- Test completion.

### Typical responsibilities
- Establishing the testing approach.
- Coordinating test activities.
- Managing the test schedule and resources.
- Monitoring progress.
- Taking or coordinating corrective actions.
- Reporting test status.
- Managing test-related risks.
- Ensuring completion activities are performed.

### Example

A test lead reviews test progress, identifies that the release is at risk, reallocates resources, updates stakeholders, and coordinates the completion report.

These tasks are associated with test management.

## 8.2 Testing Role

### Main responsibility

The testing role takes overall responsibility for the engineering or technical aspects of testing.

### Main focus
- Test analysis.
- Test design.
- Test implementation.
- Test execution.

### Typical responsibilities
- Analyzing requirements.
- Identifying test conditions.
- Designing test cases.
- Preparing test data.
- Creating automated scripts.
- Executing tests.
- Recording results.
- Reporting observed defects.

### Example

An SDET analyzes an API requirement, designs boundary and negative test cases, implements automated tests, executes them in the pipeline, and reports failures.

These tasks are associated with the testing role.

## 8.3 Comparison Table

| Test management role | Testing role |
|---|---|
| Overall responsibility for the test process and team | Overall responsibility for technical testing activities |
| Primarily planning, monitoring/control, completion | Primarily analysis, design, implementation, execution |
| Focuses on coordination, oversight, progress, and direction | Focuses on engineering and execution of tests |
| May be performed by a test manager, team leader, development manager, or others | May be performed by testers, test analysts, test engineers, SDETs, or others |

## 8.4 Can One Person Perform Both Roles?

Yes.

The roles do not necessarily require different people.

For example, in a small team, one SDET may design and execute tests while also planning the work, monitoring progress, and coordinating reporting.

In an Agile team, some test management tasks may be handled by the team itself. Tasks spanning multiple teams or the organization may be handled by people outside the development team.

### Exam traps

- Test management and testing are roles, not mandatory job titles.
- The roles may be performed by different people or by the same person.
- Agile teams may distribute test management tasks among team members.
- The test management role is not limited to a person titled “Test Manager.”
- The testing role is not limited to manual testers; it includes technical testing activities such as automation.

---

# 9. High-Value Comparison Tables

## 9.1 Test Analysis vs Test Design vs Test Implementation vs Test Execution

| Stage | Core question | Example output/action |
|---|---|---|
| Analysis | What to test? | Identify the condition that an invalid PIN must be rejected |
| Design | How to test? | Specify the input, preconditions, and expected rejection |
| Implementation | How do we prepare to run it? | Prepare test data, script, environment, and execution suite |
| Execution | What happened when we ran it? | Run the test, compare actual and expected results, log the outcome |

## 9.2 Test Monitoring vs Test Control

| Scenario | Classification |
|---|---|
| Comparing executed tests with the plan | Monitoring |
| Reporting that testing is behind schedule | Monitoring |
| Reassigning testers to a critical feature | Control |
| Reprioritizing tests due to a new risk | Control |
| Checking whether exit criteria are met | Monitoring |
| Taking corrective action because exit criteria are not met | Control |

## 9.3 Testware Recognition

| If the question mentions… | Think of… |
|---|---|
| Objectives, approach, schedule, risk register | Planning |
| Progress status, actual versus planned | Monitoring |
| Corrective or guiding action | Control |
| Testable features and test conditions | Analysis |
| Inputs, expected results, coverage items | Design |
| Scripts, suites, test procedures, environment setup | Implementation |
| Running tests and recording outcomes | Execution |
| Lessons learned, archiving, final report | Completion |

---

# 10. Common ISTQB Exam Traps

1. **Confusing analysis and design:** Analysis identifies what to test; design determines how to test it.
2. **Confusing monitoring and control:** Monitoring checks status; control acts on it.
3. **Confusing design and implementation:** Design specifies test cases; implementation prepares executable testware and the environment.
4. **Assuming execution is only automated:** Execution can be manual or automated.
5. **Assuming the test process is rigid:** Activities are adapted to context and may be repeated or performed concurrently.
6. **Confusing a test case with a test procedure:** A test case specifies a test; a procedure organizes instructions or sequences for execution.
7. **Assuming testware means only documents:** Testware can include scripts, data, test suites, reports, and environment elements.
8. **Limiting traceability to requirements and test cases:** Traceability may link test basis elements, risks, testware, results, and defects.
9. **Assuming test roles equal job titles:** A person may perform more than one role.
10. **Assuming test management belongs only to a test manager:** Tasks may be distributed, especially in Agile teams.
11. **Treating test completion as simply stopping execution:** Completion includes reporting, archiving, handover, and lessons learned.
12. **Assuming every observed anomaly proves a software defect:** Anomalies need investigation; environmental or test-related causes may also exist.

---

# 11. Practice Questions — Foundation Level

These are original practice questions written for revision. They are **not reproduced official ISTQB exam questions**.

## Questions 1–12

### Q1. Which test activity identifies testable features and defines test conditions?

A. Test design  
B. Test analysis  
C. Test implementation  
D. Test completion

### Q2. A test lead compares actual test execution progress with the approved schedule. Which activity is this?

A. Test control  
B. Test design  
C. Test monitoring  
D. Test completion

### Q3. After identifying that testing is behind schedule, the lead reallocates resources to a critical feature. What is this?

A. Test monitoring  
B. Test control  
C. Test analysis  
D. Test execution

### Q4. Which activity primarily answers “How to test?”

A. Test analysis  
B. Test planning  
C. Test design  
D. Test completion

### Q5. Which of the following is most closely associated with test implementation?

A. Identifying ambiguous requirements  
B. Creating automated test scripts and organizing test suites  
C. Comparing actual progress with planned progress  
D. Preparing the final test completion report

### Q6. Which activity includes comparing actual test results with expected results?

A. Test execution  
B. Test planning  
C. Test analysis  
D. Test completion

### Q7. Which is a typical test completion work product?

A. Test condition  
B. Test data requirement  
C. Test completion report  
D. Test execution schedule

### Q8. Which statement about the test process is correct?

A. Every project must perform all activities in a fixed sequence.  
B. The process can be tailored to the context.  
C. Test execution must always precede test design.  
D. Test management must always be performed by a separate person.

### Q9. Which is an example of testware produced during test analysis?

A. Prioritized test conditions  
B. Test execution logs  
C. Test completion report  
D. Test environment shutdown record

### Q10. What is a key benefit of traceability between requirements and test cases?

A. It guarantees the absence of defects.  
B. It proves that every test case will pass.  
C. It helps evaluate requirement coverage.  
D. It removes the need for test reporting.

### Q11. Which role primarily focuses on test analysis, design, implementation, and execution?

A. Test management role  
B. Testing role  
C. Product ownership role  
D. Configuration management role

### Q12. Which statement about testing roles is correct?

A. Every role must be performed by a different person.  
B. Only a test manager can perform test management tasks.  
C. The roles can be allocated according to the context.  
D. The testing role only includes manual execution.

---

# 12. Practice Questions — Scenario-Based

## Questions 13–32

### Q13. Requirement analysis

A tester reviews a requirement and discovers that it does not define what should happen when an account has insufficient funds. The tester raises the ambiguity before test cases are written.

Which activity is being performed?

A. Test design  
B. Test analysis  
C. Test implementation  
D. Test completion

### Q14. Test case specification

A tester has identified the condition “the system rejects an expired card.” They now specify the card data, preconditions, steps, and expected result.

Which activity is this?

A. Test analysis  
B. Test monitoring  
C. Test design  
D. Test completion

### Q15. Automation preparation

An SDET writes automated API scripts, prepares test data, configures environment variables, and groups scripts into a regression suite.

Which activity best describes this work?

A. Test analysis  
B. Test implementation  
C. Test monitoring  
D. Test completion

### Q16. Release progress

A dashboard shows that only 45% of planned regression tests have been executed, compared with the 70% target for that date. The test lead reports the variance.

Which activity is demonstrated?

A. Test control  
B. Test monitoring  
C. Test design  
D. Test completion

### Q17. Corrective action

After reviewing the progress report, the lead assigns an additional tester to the payment module and changes the test execution priorities.

Which activity is demonstrated?

A. Test monitoring only  
B. Test analysis  
C. Test control  
D. Test completion

### Q18. Actual versus expected

An automated test expects HTTP `200 OK` but receives HTTP `403 Forbidden`. The result is recorded for investigation.

Which activity is being performed?

A. Test execution  
B. Test planning  
C. Test design  
D. Test completion

### Q19. Lessons learned

After a release, the team documents that unstable test data caused repeated delays and creates an action to improve test data management in the next iteration.

Which activity is this?

A. Test design  
B. Test implementation  
C. Test completion  
D. Test monitoring

### Q20. Context and compliance

A team testing software for a regulated industry introduces detailed traceability, formal reviews, and documented evidence because of compliance obligations.

What best explains this decision?

A. All projects must use the same documentation level.  
B. Testing is influenced by business and organizational context.  
C. Traceability is only necessary after a defect is found.  
D. Test execution determines all process requirements.

### Q21. Resource constraints

A team has a limited budget and only three days to test a low-risk internal feature. The team tailors its approach to the objectives and constraints.

Which statement best applies?

A. Tailoring means test objectives can be ignored.  
B. Testing must always follow an identical process.  
C. The test process can be adapted to the situation.  
D. Testing is unnecessary when resources are limited.

### Q22. Risk and coverage

A tester links each high-risk requirement to relevant test cases and their execution results. The team uses the links to assess whether important risks remain insufficiently tested.

What is the main benefit?

A. Automatic elimination of defects  
B. Traceability supporting coverage and residual-risk evaluation  
C. Replacement of test execution  
D. Removal of all project constraints

### Q23. Change impact

A requirement for the maximum transaction amount changes. The team uses traceability links to identify affected test cases and regression scripts.

Which benefit of traceability is demonstrated?

A. Test environment creation  
B. Change-impact analysis  
C. Test completion reporting only  
D. Test data generation

### Q24. Testware classification

A test lead creates a document showing planned milestones, the testing schedule, major risks, and the testing approach.

Which test activity is most closely associated with this work product?

A. Test planning  
B. Test analysis  
C. Test execution  
D. Test completion

### Q25. Work product identification

A tester identifies test conditions and reports an ambiguity in the requirements that cannot be corrected directly.

Which combination is most appropriate?

A. Test analysis — prioritized test conditions and a test-basis defect report  
B. Test execution — test logs and test completion report  
C. Test completion — automated scripts and test data  
D. Test implementation — risk register and entry criteria

### Q26. Test environment

An SDET configures a test environment and verifies that required services and infrastructure are available before the regression suite runs.

Which activity is most closely associated with this preparation?

A. Test analysis  
B. Test implementation  
C. Test completion  
D. Test monitoring only

### Q27. Test suite organization

A team groups related test procedures into a suite and prioritizes the execution order before the scheduled test run.

Which activity is being performed?

A. Test design only  
B. Test implementation  
C. Test completion  
D. Test monitoring

### Q28. Test roles in Agile

In an Agile team, developers and testers collectively estimate testing effort and coordinate test activities. A separate test manager is not assigned to the team.

Which statement is correct?

A. Testing is invalid without a dedicated test manager.  
B. Test management tasks may be distributed among Agile team members.  
C. Test management tasks must always be performed outside the team.  
D. Testers may only execute tests.

### Q29. Combined responsibilities

A senior SDET writes automation scripts and also coordinates test schedules, monitors progress, and communicates status to stakeholders.

What is the most accurate interpretation?

A. This is not permitted because the roles must be separate.  
B. The SDET is performing tasks from both the testing and test management roles.  
C. The SDET is performing only the test completion activity.  
D. Automation scripts are test management work products.

### Q30. Test role classification

A team member coordinates the test team, monitors progress, guides corrective actions, and ensures that completion reporting is performed.

Which role is primarily represented?

A. Testing role  
B. Test management role  
C. Development role only  
D. Business analysis role

### Q31. Test role classification

A team member analyzes user stories, specifies test cases, prepares test data, creates automated scripts, and executes regression tests.

Which role is primarily represented?

A. Test management role  
B. Testing role  
C. Test completion role only  
D. Product management role

### Q32. Distinguishing testware

A tester has specified a test case, but the team has not yet created the executable script or prepared the test environment. Which statement is most accurate?

A. Test design is complete, and test implementation may still be needed.  
B. Test execution is complete because the test case exists.  
C. Test completion must occur before implementation.  
D. Test monitoring automatically creates the script.

---

# 13. Answer Key and Explanations

| Q | Answer | Explanation |
|---|---|---|
| 1 | B | Test analysis identifies testable features and defines test conditions. |
| 2 | C | Monitoring checks actual progress against the plan. |
| 3 | B | Reallocating resources is corrective action, so it is control. |
| 4 | C | Test design answers “How to test?” |
| 5 | B | Scripts, test suites, test data, and environment preparation are implementation activities. |
| 6 | A | Execution includes running tests and comparing actual and expected results. |
| 7 | C | A test completion report is a typical completion work product. |
| 8 | B | The test process is tailored to the context. |
| 9 | A | Prioritized test conditions are test analysis work products. |
| 10 | C | Traceability helps assess whether requirements are covered by test cases. |
| 11 | B | The testing role focuses on the technical aspects of testing. |
| 12 | C | Roles may be allocated according to context and people’s skills. |
| 13 | B | Reviewing the requirement and identifying an ambiguity is test analysis. |
| 14 | C | Specifying inputs, preconditions, steps, and expected results is test design. |
| 15 | B | Creating scripts, preparing data, and assembling suites are implementation tasks. |
| 16 | B | Reporting the difference between actual and planned progress is monitoring. |
| 17 | C | Reassigning resources and changing priorities are control actions. |
| 18 | A | Running a test and recording its outcome are test execution activities. |
| 19 | C | Lessons learned and improvement actions belong to test completion. |
| 20 | B | Regulatory and business needs influence the testing process. |
| 21 | C | The process can be tailored to objectives, constraints, and context. |
| 22 | B | Traceability supports coverage evaluation and assessment of residual risk. |
| 23 | B | Traceability helps identify the testware affected by a change. |
| 24 | A | The approach, milestones, schedule, and risks are associated with planning. |
| 25 | A | Test conditions and reports of test-basis defects are associated with analysis. |
| 26 | B | Building and verifying the test environment are implementation tasks. |
| 27 | B | Organizing procedures and suites and arranging execution order are implementation tasks. |
| 28 | B | Agile teams may distribute test management responsibilities among members. |
| 29 | B | The same person may perform both testing and test management tasks. |
| 30 | B | Coordination, progress control, and completion oversight fit test management. |
| 31 | B | Analysis, design, implementation, and execution fit the testing role. |
| 32 | A | Specifying the test case is design; preparing scripts and the environment is implementation. |

---

# 14. Last-Minute Revision Sheet

## The Activity Sequence

**Plan → Monitor & Control → Analyze → Design → Implement → Execute → Complete**

Remember that this is a useful learning sequence, not a rigid rule that every project must follow without iteration.

## The Most Important Distinctions

- **Planning:** Define objectives and approach.
- **Monitoring:** Check actual progress against the plan.
- **Control:** Take corrective or guiding action.
- **Analysis:** Identify what to test.
- **Design:** Specify how to test.
- **Implementation:** Prepare testware and the test environment.
- **Execution:** Run tests and record results.
- **Completion:** Report, archive, hand over, and improve.

## Testware by Activity

- Planning → Test plan, schedule, risk register.
- Monitoring/control → Progress reports, control directives.
- Analysis → Test conditions, test-basis defect reports.
- Design → Test cases, coverage items, data/environment requirements.
- Implementation → Scripts, procedures, suites, data, execution schedule.
- Execution → Test logs, defect reports.
- Completion → Completion report, lessons learned, improvement actions.

## Test Roles

- **Test management:** Planning, monitoring/control, completion.
- **Testing:** Analysis, design, implementation, execution.
- The roles may be performed by the same person.
- Agile teams may distribute test management tasks among team members.

## Traceability Benefits

Remember these six uses:

1. Evaluate coverage.
2. Assess residual risk.
3. Analyze change impact.
4. Support audits and governance.
5. Improve reporting and communication.
6. Assess product quality, process capability, and project progress.

---

# 15. Self-Assessment Checklist

Before moving to the next topic, make sure you can explain each item without looking at the notes.

- [ ] I can distinguish test monitoring from test control.
- [ ] I can explain the purpose of all seven named test activities.
- [ ] I know why test analysis answers “What to test?”.
- [ ] I know why test design answers “How to test?”.
- [ ] I can distinguish test design from test implementation.
- [ ] I can match common testware to the activity that produces it.
- [ ] I can explain how the project context influences testing.
- [ ] I can explain the benefits of traceability.
- [ ] I can distinguish the test management role from the testing role.
- [ ] I understand that roles are responsibilities, not necessarily separate job titles.
- [ ] I have answered the 32 practice questions and reviewed every mistake.

## Recommended revision target

Aim for **at least 28/32 correct** on your first closed-book attempt. For every wrong answer, identify whether you confused an activity, a work product, traceability, or a role.

**Source note:** These notes are organized around the supplied study screenshots and the CTFL v4.0.1 topic structure. The practice questions are original learning questions, not verified official sample-exam questions or past live-exam questions.