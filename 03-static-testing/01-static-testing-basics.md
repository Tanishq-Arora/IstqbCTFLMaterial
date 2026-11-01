# 3.1 Static Testing Basics
**ISTQB CTFL v4.0.1 — Chapter 3: Static Testing**

**Scope:** Static testing basics, work products that can be examined, value of static testing, and differences between static and dynamic testing.

---

## Learning Objectives

| LO Code | Learning Objective | K-Level |
|---|---|---|
| FL-3.1.1 | Recognize work products that can be examined by static testing. | K1 |
| FL-3.1.2 | Explain the benefits of static testing. | K2 |
| FL-3.1.3 | Explain the differences between static testing and dynamic testing. | K2 |

**Source basis:** These notes follow the five slide images supplied for this module. Practical examples, exam traps and practice questions have been added for preparation.

---

# 1. What is Static Testing?

**Static testing** is a form of testing in which a work product is examined without executing the software.

Unlike dynamic testing, the software under test does not need to be run.

Static testing evaluates work products through:

1. **Manual examination** – Reviews performed by one or more people.
2. **Tool-supported examination** – Static analysis performed using specialized tools.

### Two Main Forms of Static Testing

| Form | Meaning | Example |
|---|---|---|
| Reviews | Manual examination of a work product by one or more people. | Reviewing a requirement document, user story, test plan or source code. |
| Static Analysis | Examination of a work product using a tool without executing the software. | Running SonarQube or a static code analyzer to identify coding issues. |

### Practical Example 1 – Requirement Review

Consider this requirement:

> The application should load quickly.

A tester reviews the requirement and asks:

- What does "quickly" mean?
- Is there a measurable response-time target?
- Under what workload should the target be achieved?
- Which user action does the requirement cover?

**Finding:** The requirement is ambiguous and lacks measurable acceptance criteria.

The tester identifies the problem without executing the application.

This is static testing through a review.

### Practical Example 2 – Static Code Analysis

A static-analysis tool scans source code and reports:

- Unused variables.
- Undeclared variables.
- Unreachable code.
- Coding-standard violations.
- Potential security vulnerabilities.

The application does not need to be executed.

**Important:** Static analysis can be integrated into CI pipelines to identify problems early.

---

# 2. Objectives of Static Testing

Static testing has several objectives:

1. Improve the quality of work products.
2. Detect defects at an early stage of the SDLC.
3. Assess characteristics such as:
    - Readability.
    - Completeness.
    - Correctness.
    - Testability.
    - Consistency.
4. Build confidence in work products.
5. Support both verification and validation.

### Static Testing: Verification and Validation

| Verification | Validation |
|---|---|
| Are we building the product right? | Are we building the right product? |
| Checks whether the work product conforms to specified requirements or standards. | Checks whether the work product meets stakeholder needs. |
| Example: Reviewing whether an API specification follows the agreed format. | Example: Reviewing requirements with stakeholders to confirm that they describe the actual business need. |

**Exam Point:** Static testing can support both verification and validation.

---

# 3. Collaboration During Static Testing

Static testing is not limited to testers.

Different stakeholders collaborate during activities such as:

- Example mapping.
- Collaborative user story writing.
- Backlog refinement.
- Reviewing acceptance criteria.
- Reviewing requirements and other work products.

### Participants

| Participant | Contribution |
|---|---|
| Testers | Identify ambiguity, missing scenarios and testability issues. |
| Developers | Identify technical issues, design problems and implementation constraints. |
| Business Representatives | Ensure requirements reflect actual business needs. |

### Practical Example – Agile Backlog Refinement

Consider a user story:

"As a customer, I want to reset my password."

During backlog refinement, the team discusses:

- What happens if the email address is not registered?
- Does the reset link expire?
- Can the reset link be reused?
- What happens if the user requests multiple reset links?
- Are there security restrictions?

The team identifies missing acceptance criteria before development begins.

This is an example of static testing through collaborative review.

### Definition of Ready (DoR)

The **Definition of Ready** is a set of criteria that a user story or work item should satisfy before the team considers it ready for implementation.

Static reviews can help ensure that user stories:

- Are understandable.
- Are sufficiently complete.
- Have testable acceptance criteria.
- Meet the team's agreed readiness criteria.

---

# 4. Work Products Examined by Static Testing

Almost any work product can be examined using static testing.

### Examples of Work Products

| Work Product | Example of Defect Identified |
|---|---|
| Requirement specifications | Ambiguous or contradictory requirements. |
| Source code | Unused variables or coding-standard violations. |
| Test plans | Missing test scope or unclear responsibilities. |
| Test cases | Missing test conditions or incorrect expected results. |
| Product backlog items | Incomplete user stories or missing acceptance criteria. |
| Test charters | Unclear exploratory testing objectives. |
| Project documentation | Inconsistent information. |
| Contracts | Ambiguous contractual obligations. |
| Models | Incorrect or inconsistent system models. |

### Important Distinction: Reviews vs Static Analysis

**Reviews**

- Any work product that can be read and understood by humans can potentially be reviewed.
- Examples: Requirements, contracts, project documentation, user stories and test plans.

**Static Analysis**

- Requires a work product with a structure against which it can be checked.
- Examples: Source code, models or text with a formal syntax.

### Work Products Not Appropriate for Static Testing

Some work products are difficult for humans to interpret and should not be analyzed by tools.

Example:
- Third-party executable code that cannot legally be analyzed.

**Exam Trap:** Do not assume that every work product suitable for review is automatically suitable for static analysis.

---

# 5. Value and Benefits of Static Testing

Static testing provides several benefits.

## 5.1 Early Defect Detection

Static testing can identify defects in the earliest phases of the SDLC.

It supports the principle of early testing.

It can also identify defects that may not be detected by dynamic testing, such as:

- Unreachable code.
- Design patterns not implemented as intended.
- Defects in non-executable work products.

**Example:** A requirement document contains contradictory business rules. A reviewer can identify the contradiction before development begins.

## 5.2 Improved Quality and Confidence

Static testing evaluates the quality of work products and builds confidence in them.

By verifying documented requirements, stakeholders can also ensure that requirements describe their actual needs.

**Example:** Reviewing an API specification ensures that the documented request parameters, response fields and error codes are consistent.

## 5.3 Improved Communication and Shared Understanding

Static testing encourages collaboration among stakeholders.

Since it can be performed early in the SDLC, a shared understanding can be established among:

- Testers.
- Developers.
- Business analysts.
- Product owners.
- Other stakeholders.

**Example:** A backlog refinement meeting helps the team agree on the expected behavior of a feature before implementation.

## 5.4 Reduced Overall Project Cost

Reviews may require time and effort. However, the overall project cost is usually lower than when no reviews are performed.

Why?

- Defects are identified earlier.
- Less rework is required later.
- Expensive downstream fixes can be avoided.
- Defects are less likely to propagate into later development stages.

**Example:** Finding an incorrect requirement before coding is generally cheaper than correcting the implementation and associated test cases after release.

## 5.5 More Efficient Code Defect Detection

Static analysis can identify certain code defects more efficiently than dynamic testing.

This can result in:

- Fewer code defects.
- Lower overall development effort.
- Improved maintainability.
- Improved security.

**Example:** A static-analysis tool detects an unused variable or a potential null dereference without running the application.

---

# 6. Static Testing vs Dynamic Testing

Static testing and dynamic testing complement each other.

Both support defect detection, but their approaches and the types of defects they can identify differ.

| Basis | Static Testing | Dynamic Testing |
|---|---|---|
| Execution | Software is not executed. | Software is executed. |
| Focus | Examination of work products. | Behavior of the software during execution. |
| Test object | Executable and non-executable work products. | Executable work products. |
| Defect detection | Finds defects directly. | Causes failures from which associated defects are identified through subsequent analysis. |
| Defect discovery | Can identify defects in requirements, design, code and documentation. | Can identify defects that cause observable failures during execution. |
| Rarely executed paths | Can more easily identify defects in rarely executed or difficult-to-reach code paths. | May struggle to expose defects in rarely executed paths. |
| Quality characteristics | Can assess characteristics not dependent on code execution, such as maintainability. | Can assess characteristics dependent on execution, such as performance efficiency. |
| Examples | Reviews, static code analysis. | Functional testing, performance testing. |

### Important Differences Explained

**1. Static testing finds defects directly**

A reviewer identifies an ambiguous requirement or a contradiction in a design document.

No software execution is required.

**2. Dynamic testing causes failures**

A tester executes an application and observes an unexpected result.

The failure is analyzed to identify the underlying defect.

**3. Static testing can identify difficult-to-reach code defects**

A static-analysis tool can identify unreachable code even if that code is never executed during testing.

**4. Static testing can examine non-executable work products**

A requirement document can be reviewed without having an executable application.

Dynamic testing requires an executable test object.

**5. Different quality characteristics can be assessed**

- Static testing: Maintainability, readability and consistency.
- Dynamic testing: Performance efficiency and runtime behavior.

---

# 7. Defects Easier to Find Through Static Testing

Typical defects that are easier and/or cheaper to find through static testing include:

| Defect Category | Examples |
|---|---|
| Requirement defects | Inconsistencies, ambiguities, contradictions, omissions, inaccuracies and duplications. |
| Design defects | Inefficient database structures and poor modularization. |
| Coding defects | Variables with undefined values, undeclared variables, unreachable code, duplicated code and excessive code complexity. |
| Standards violations | Lack of adherence to coding standards and naming conventions. |
| Interface defects | Incorrect interface specifications, such as mismatched number, type or order of parameters. |
| Security vulnerabilities | Certain types of vulnerabilities, such as buffer overflows. |
| Test basis defects | Missing or inaccurate test coverage, such as missing tests for an acceptance criterion. |

### SDET Examples

**Example 1 – Coding Standard Violation**

A developer uses inconsistent naming conventions.

A static-analysis tool detects the violation without executing the application.

**Example 2 – Interface Specification Defect**

An API specification defines a parameter as an integer, while the corresponding interface definition expects a string.

A review or suitable static-analysis tool can identify the mismatch.

**Example 3 – Missing Acceptance Criterion**

A user story has three acceptance criteria, but the test cases cover only two.

Reviewing the test basis and test cases can reveal the missing coverage.

**Example 4 – Unreachable Code**

A conditional branch can never be reached because of an incorrect condition.

Static analysis may identify this without executing the application.

---

# 8. Static Testing in CI/CD

Static analysis is often incorporated into Continuous Integration (CI) frameworks.

A typical pipeline can include:

1. Developer commits code.
2. CI pipeline starts.
3. Static-analysis tools scan the source code.
4. Issues such as coding-standard violations, complexity and potential vulnerabilities are reported.
5. The pipeline can enforce quality gates.
6. If the defined quality gate fails, the team is notified or the pipeline is prevented from progressing.

### Example Tools

| Tool | Typical Use |
|---|---|
| SonarQube | Static code analysis and code quality checks. |
| Checkstyle | Java coding-standard checks. |
| PMD | Identifying potential code problems and coding practices. |
| SpotBugs | Detecting potential bugs in Java bytecode. |
| ESLint | JavaScript and TypeScript code analysis. |

**Important:** These tools are examples of static-analysis tools. They do not replace dynamic testing.

---

# 9. Exam Traps and Important Points

1. Static testing does not require software execution.
2. Reviews and static analysis are the two main forms of static testing.
3. Reviews involve manual examination of work products.
4. Static analysis uses tools to examine work products without executing the software.
5. Any readable and understandable work product can potentially be reviewed.
6. Static analysis requires a structure against which the work product can be checked.
7. Static testing can support both verification and validation.
8. Static testing can be performed early in the SDLC.
9. Static testing can identify defects that dynamic testing may not detect.
10. Static and dynamic testing complement each other.
11. Static testing identifies defects directly.
12. Dynamic testing produces failures from which defects are identified through subsequent analysis.
13. Static testing can identify defects in non-executable work products.
14. Dynamic testing requires executable work products.
15. Static analysis can be integrated into CI pipelines.
16. Static testing is not limited to source code.
17. Static testing can assess maintainability, while dynamic testing can assess performance efficiency.

---

# 10. Important Comparison Table for Last-Minute Revision

| Concept | Remember |
|---|---|
| Static Testing | Examination without executing software. |
| Dynamic Testing | Testing by executing software. |
| Review | Manual examination of a work product. |
| Static Analysis | Tool-supported examination without execution. |
| Reviewable Work Product | Any work product that can be read and understood. |
| Static Analysis Work Product | A work product with a structure that can be checked. |
| Early Testing | Static testing helps detect defects early. |
| Verification | Checking conformity to specified requirements or standards. |
| Validation | Checking whether the product meets stakeholder needs. |
| Static Testing Benefit | Early defect detection, improved quality, communication and lower overall costs. |
| Dynamic Testing Outcome | Observable failures that require analysis to identify associated defects. |

---

# 11. Practice Questions

**Important:** The questions below are original practice questions created for preparation. They are not represented as official ISTQB questions or verified past examination questions.

## Section A – Core Concept MCQs

### Q1. Which statement best describes static testing?

A. Testing performed only after software deployment.

B. Testing that requires executing the software with different inputs.

C. Examination of a work product without executing the software.

D. Testing performed exclusively by developers.

### Q2. Which of the following are the two main forms of static testing?

A. Unit testing and integration testing.

B. Reviews and static analysis.

C. Regression testing and confirmation testing.

D. Functional testing and non-functional testing.

### Q3. Which of the following work products can be examined through static testing?

A. Requirement specifications.

B. Source code.

C. Test plans and test cases.

D. All of the above.

### Q4. Which statement about reviews is correct?

A. Reviews require the application to be executed.

B. Reviews are only applicable to source code.

C. Any work product that can be read and understood can potentially be reviewed.

D. Reviews can only be conducted by testers.

### Q5. Which statement about static analysis is correct?

A. It always requires executing the application.

B. It requires a work product with a structure against which it can be checked.

C. It is applicable only to requirement documents.

D. It is the same as dynamic testing.

### Q6. Which of the following is a benefit of static testing?

A. It eliminates the need for dynamic testing.

B. It detects defects only after deployment.

C. It can identify defects early in the SDLC.

D. It guarantees that the software is defect-free.

### Q7. Which of the following can be evaluated through static testing?

A. Readability.

B. Completeness.

C. Consistency.

D. All of the above.

### Q8. Which statement regarding verification and validation is correct?

A. Static testing supports verification only.

B. Static testing supports validation only.

C. Static testing can support both verification and validation.

D. Neither verification nor validation can be performed through static testing.

### Q9. Which defect is generally easier to identify through static testing?

A. Incorrect response time under heavy production load.

B. An ambiguous requirement specification.

C. A runtime crash occurring only under a specific workload.

D. An intermittent network timeout during execution.

### Q10. Which statement best describes the relationship between static and dynamic testing?

A. Static testing completely replaces dynamic testing.

B. Dynamic testing completely replaces static testing.

C. Both approaches complement each other.

D. Both approaches have exactly the same objectives and methods.

### Q11. Which of the following is an example of static analysis?

A. Executing an API request and checking its response.

B. Running a load test against an application.

C. Using a static-analysis tool to identify unreachable code.

D. Performing a UI regression test.

### Q12. Which defect can be identified through static testing?

A. Incorrect parameter order in an interface specification.

B. A slow response time during execution.

C. A crash caused by a production traffic spike.

D. A failed database connection during runtime.

### Q13. Which of the following is NOT a typical benefit of static testing?

A. Early defect detection.

B. Improved communication among stakeholders.

C. Reduced overall project costs.

D. Guaranteeing that no defects exist in the final product.

### Q14. Which statement about dynamic testing is correct?

A. It can be applied to non-executable work products.

B. It involves executing software.

C. It never requires test data.

D. It identifies all defects directly without further analysis.

### Q15. Which quality characteristic can be assessed through static testing without executing the software?

A. Performance efficiency.

B. Runtime response time.

C. Maintainability.

D. Throughput under load.

---

## Section B – Implementation-Oriented and Scenario-Based MCQs

### Q16. Requirement Review

A business analyst provides the following requirement:

"The payment should be processed within a reasonable time."

Before development begins, a tester reviews the requirement and identifies that "reasonable time" is not measurable.

Which testing activity is being performed?

A. Dynamic testing.

B. Confirmation testing.

C. Static testing through a review.

D. Performance testing.

### Q17. Static Analysis in CI/CD

A Java developer commits code to GitLab. The CI pipeline executes SonarQube and reports unused variables, code complexity and potential security issues. The application has not been started.

Which activity is being performed?

A. Dynamic testing.

B. Static analysis.

C. System testing.

D. Acceptance testing.

### Q18. Work Product Selection

A QA team wants to review the following items:

1. Requirement specification.
2. Contract document.
3. User story.
4. Test plan.

Which of these can potentially be reviewed using static testing?

A. Only 1 and 2.

B. Only 3 and 4.

C. All four.

D. None of them.

### Q19. Review vs Static Analysis

A tester reads an API specification and identifies that the same endpoint is described with two different HTTP methods in different sections.

Which approach is being used?

A. Static analysis only.

B. Dynamic testing.

C. Review.

D. Performance testing.

### Q20. Unreachable Code

A developer writes a conditional statement where one branch can never execute due to the logical condition.

Which approach is most suitable for identifying this issue without executing the application?

A. Load testing.

B. Static analysis.

C. Acceptance testing.

D. Exploratory testing.

### Q21. Early Defect Detection

During requirement analysis, testers identify that two requirements contradict each other. Development has not started.

What is the most important benefit demonstrated here?

A. Improved runtime performance.

B. Early defect detection and reduced rework.

C. Increased production traffic capacity.

D. Confirmation of a previously fixed defect.

### Q22. Static Testing and Validation

A product owner and testers review a user story to ensure that it represents the actual business need rather than simply following a documented technical specification.

Which concept is primarily supported?

A. Validation.

B. Load testing.

C. Confirmation testing.

D. Regression testing.

### Q23. Static Analysis Limitations

A tester wants to review a third-party executable file that is difficult to interpret and cannot legally be analyzed using available tools.

Which statement is most appropriate?

A. Every work product must be analyzed through static analysis.

B. All executable files are automatically suitable for static analysis.

C. Some work products may not be appropriate for static analysis.

D. Static analysis always requires executing the file.

### Q24. Dynamic vs Static Testing

A tester executes an application and observes that the total amount displayed is incorrect. The tester then analyzes the behavior to identify the underlying coding defect.

Which statement is correct?

A. Static testing directly detected the defect.

B. Dynamic testing exposed a failure, and subsequent analysis helped identify the defect.

C. Static analysis caused the failure.

D. No testing activity was performed.

### Q25. Test Basis Coverage

During a review, a tester discovers that one acceptance criterion in a user story has no corresponding test case.

Which defect category does this represent?

A. Performance defect.

B. Interface defect.

C. Gap in test basis coverage.

D. Runtime defect.

### Q26. Maintainability

A team wants to assess whether source code is readable, consistent and easy to maintain without executing it.

Which approach is appropriate?

A. Dynamic performance testing.

B. Static testing.

C. Load testing.

D. End-to-end testing.

### Q27. CI Quality Gate

A CI pipeline runs a static-analysis tool. The tool reports a critical security vulnerability, and the configured quality gate prevents the build from progressing.

What is the primary purpose of this setup?

A. To execute all functional test cases.

B. To detect potential code issues early and enforce quality standards.

C. To replace integration testing.

D. To verify application response time.

### Q28. Interface Specification

An API specification defines a method with three parameters, but the documented interface contract describes only two parameters.

Which defect can static testing identify?

A. Incorrect interface specification.

B. Runtime performance degradation.

C. Database availability failure.

D. Incorrect production deployment.

### Q29. Complementary Testing

A team performs requirement reviews and static code analysis. Later, the team executes functional and performance tests.

Why are both approaches necessary?

A. Static testing guarantees defect-free software.

B. Dynamic testing can only identify documentation defects.

C. Static and dynamic testing can identify different types of defects and complement each other.

D. Dynamic testing is unnecessary when static analysis is used.

### Q30. Stakeholder Collaboration

During backlog refinement, testers, developers and business representatives jointly discuss missing acceptance criteria and clarify expected system behavior.

Which activity is this an example of?

A. Dynamic system testing.

B. Collaborative static testing.

C. Production monitoring.

D. Confirmation testing.

### Q31. Defect Identification

A static-analysis tool identifies duplicated code and excessive code complexity.

Which category best describes these findings?

A. Coding defects or code-quality issues.

B. Runtime failures.

C. Production environment failures.

D. Acceptance failures.

### Q32. Static Testing and Performance

A tester wants to determine whether an application responds within two seconds under 10,000 concurrent users.

Which approach is required to measure this behavior?

A. Static testing.

B. Review.

C. Dynamic testing.

D. Static code analysis alone.

### Q33. Incomplete Requirements

A tester identifies that a requirement document does not mention what should happen when a customer enters an invalid payment card number.

When can this defect be detected?

A. Only after production deployment.

B. During static testing through a requirement review.

C. Only through load testing.

D. Only through regression testing.

### Q34. Testability Assessment

A tester reviews a requirement and finds that it does not define expected inputs, outputs or measurable acceptance criteria.

Which characteristic of the work product is being assessed?

A. Portability.

B. Testability.

C. Throughput.

D. Availability.

### Q35. Choosing the Correct Approach

A team needs to identify:

1. Ambiguity in a requirement.
2. An unused variable in source code.
3. Actual response time under heavy load.

Which combination is most appropriate?

A. Dynamic testing for all three.

B. Review for 1, static analysis for 2, dynamic testing for 3.

C. Static analysis for all three.

D. Review for all three.

### Q36. Rarely Executed Paths

A critical code branch is rarely executed during normal testing. A static-analysis tool identifies that the branch contains unreachable code.

Why is static testing useful in this situation?

A. It can identify certain defects in code paths without requiring their execution.

B. It automatically executes all possible paths.

C. It replaces all functional testing.

D. It measures the branch's runtime performance.

### Q37. Verification vs Validation

A reviewer checks whether a requirement follows the organization's documented requirement-writing standards.

Which concept is primarily being demonstrated?

A. Validation.

B. Verification.

C. Dynamic testing.

D. Regression testing.

### Q38. Review Cost

An organization initially spends time reviewing requirements and design documents. Later, it observes a reduction in expensive rework during development.

Which benefit of static testing does this demonstrate?

A. Increased execution speed.

B. Reduced overall project cost through early defect detection.

C. Elimination of dynamic testing.

D. Improved production hardware capacity.

### Q39. Security Analysis

A static-analysis tool identifies a potential buffer overflow vulnerability in source code without executing the application.

Which statement is correct?

A. This is dynamic security testing.

B. This is static analysis.

C. This is acceptance testing.

D. This is performance testing.

### Q40. Comprehensive Understanding

Which statement is MOST accurate about static testing?

A. It is limited to source code and must be performed by developers.

B. It can examine different work products without executing software and can support early defect detection.

C. It guarantees that the final product will have no failures.

D. It is performed only after dynamic testing is completed.

---

# 12. Answer Key – Section A

| Question | Answer | Concept |
|---|---|---|
| Q1 | C | Definition of static testing |
| Q2 | B | Reviews and static analysis |
| Q3 | D | Work products |
| Q4 | C | Review suitability |
| Q5 | B | Static analysis suitability |
| Q6 | C | Early defect detection |
| Q7 | D | Quality characteristics |
| Q8 | C | Verification and validation |
| Q9 | B | Requirement defects |
| Q10 | C | Complementary approaches |
| Q11 | C | Static analysis |
| Q12 | A | Interface specification defects |
| Q13 | D | Static testing limitations |
| Q14 | B | Dynamic testing |
| Q15 | C | Maintainability |

## Section A – Explanations

**Q1 – C:** Static testing examines a work product without executing the software.

**Q2 – B:** The two main forms are reviews and static analysis.

**Q3 – D:** Requirements, source code, test plans and test cases are all possible work products for static testing.

**Q4 – C:** Any work product that can be read and understood can potentially be reviewed.

**Q5 – B:** Static analysis needs a structure against which the work product can be checked.

**Q6 – C:** Static testing can detect defects early, before they become more expensive to fix.

**Q7 – D:** Readability, completeness and consistency are all characteristics that can be assessed.

**Q8 – C:** Static testing supports verification and validation.

**Q9 – B:** Ambiguity in a requirement can be identified through review without executing the application.

**Q10 – C:** Static and dynamic testing complement each other and can identify different types of defects.

**Q11 – C:** Identifying unreachable code using a tool without executing the software is static analysis.

**Q12 – A:** A mismatch in parameter number, type or order is an interface specification defect.

**Q13 – D:** Static testing cannot guarantee defect-free software.

**Q14 – B:** Dynamic testing involves executing software.

**Q15 – C:** Maintainability can be assessed without executing the software. Performance efficiency requires execution.

---

# 13. Answer Key – Section B

| Question | Answer | Concept |
|---|---|---|
| Q16 | C | Requirement review |
| Q17 | B | Static analysis in CI/CD |
| Q18 | C | Reviewable work products |
| Q19 | C | Manual review |
| Q20 | B | Unreachable code |
| Q21 | B | Early defect detection |
| Q22 | A | Validation |
| Q23 | C | Static analysis limitations |
| Q24 | B | Dynamic testing and failure analysis |
| Q25 | C | Test basis coverage |
| Q26 | B | Maintainability |
| Q27 | B | CI quality gate |
| Q28 | A | Interface specification |
| Q29 | C | Complementary testing |
| Q30 | B | Collaborative static testing |
| Q31 | A | Coding defects and code quality |
| Q32 | C | Dynamic performance testing |
| Q33 | B | Requirement review |
| Q34 | B | Testability |
| Q35 | B | Selecting appropriate techniques |
| Q36 | A | Rarely executed paths |
| Q37 | B | Verification |
| Q38 | B | Reduced project costs |
| Q39 | B | Static security analysis |
| Q40 | B | Overall understanding |

## Section B – Detailed Explanations

**Q16 – C:** The tester identifies ambiguity in a requirement without running the application. This is static testing through a review.

**Q17 – B:** SonarQube examines source code without executing the application. This is static analysis.

**Q18 – C:** Requirements, contracts, user stories and test plans can all be reviewed if they can be read and understood.

**Q19 – C:** A person manually examines the API specification and identifies an inconsistency. This is a review.

**Q20 – B:** Static analysis can identify unreachable code without executing it.

**Q21 – B:** Finding contradictory requirements before development reduces rework and supports early testing.

**Q22 – A:** The team checks whether the user story reflects actual business needs. This supports validation.

**Q23 – C:** Not every work product is appropriate for static analysis. Some are difficult to interpret or cannot legally be analyzed.

**Q24 – B:** Dynamic testing exposes the failure. Subsequent analysis helps identify the underlying defect.

**Q25 – C:** A missing test for an acceptance criterion represents a gap in test basis coverage.

**Q26 – B:** Readability and maintainability can be assessed through static examination without executing the software.

**Q27 – B:** A quality gate helps identify potential issues early and enforce defined quality standards.

**Q28 – A:** A mismatch in parameter count between an API specification and interface contract is an interface specification defect.

**Q29 – C:** Static and dynamic testing complement each other. Neither approach identifies every possible defect.

**Q30 – B:** Jointly reviewing and improving user stories and acceptance criteria is collaborative static testing.

**Q31 – A:** Duplicated code and excessive complexity are coding and code-quality issues that static analysis can identify.

**Q32 – C:** Measuring response time under concurrent load requires executing the application, making it dynamic testing.

**Q33 – B:** Missing business scenarios can be identified by reviewing the requirement before implementation.

**Q34 – B:** A requirement with unclear inputs, outputs and acceptance criteria may not be sufficiently testable.

**Q35 – B:** Requirement ambiguity is identified through review, unused variables through static analysis, and actual response time through dynamic testing.

**Q36 – A:** Static analysis can identify certain defects in code paths without executing those paths.

**Q37 – B:** Checking whether a requirement follows documented standards is verification.

**Q38 – B:** Detecting defects early reduces the effort and cost of fixing them later.

**Q39 – B:** Identifying a potential buffer overflow through source-code analysis without execution is static analysis.

**Q40 – B:** Static testing can examine multiple work products without executing software and supports early defect detection.

---

# 14. Last-Minute Revision Checklist

Before moving to the next module, ensure that you can answer all of these:

- [ ] Define static testing.
- [ ] Differentiate reviews and static analysis.
- [ ] Identify work products that can be examined through static testing.
- [ ] Explain why reviewable work products are not necessarily suitable for static analysis.
- [ ] Explain the benefits of static testing.
- [ ] Explain how static testing supports early testing.
- [ ] Differentiate verification and validation.
- [ ] Explain how static testing improves communication.
- [ ] Explain why static testing reduces overall project costs.
- [ ] Differentiate static testing and dynamic testing.
- [ ] Explain how dynamic testing exposes failures and subsequent analysis identifies defects.
- [ ] Identify defects that are easier to detect through static testing.
- [ ] Explain how static analysis can be integrated into CI/CD.
- [ ] Understand why static and dynamic testing complement each other.

---

# 15. Self-Assessment

| Performance | Assessment |
|---|---|
| 36–40 correct | Excellent – Strong understanding |
| 31–35 correct | Good – Revise incorrect concepts |
| 26–30 correct | Average – Revisit comparisons and scenarios |
| 20–25 correct | Needs improvement – Revise the module |
| Below 20 | Re-study the module before proceeding |

**Exam reminder:** Focus particularly on the distinction between reviews and static analysis, suitability of work products, benefits of static testing, and static vs dynamic testing. These concepts are especially suitable for scenario-based questions.

**End of Module 3.1 – Static Testing Basics**