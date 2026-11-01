# ISTQB CTFL v4.0.1 — Chapter 3: Static Testing
## Sample Questions & Exam Practice

**Syllabus Coverage:** Chapter 3 — Static Testing  
**Topics:** 3.1 Static Testing Basics | 3.2 Feedback and Review Process

> **Important:** Section A contains the questions supplied for this chapter. Section B contains original, exam-oriented practice questions created for preparation. Section B questions are not official ISTQB questions or verified past-paper questions.

---

# Section A — Questions Provided

## Question 1 — Benefits of Static Testing

**Which of the following is NOT a benefit of static testing?**

A. Having less expensive defect management, due to the ease of detecting defects later in the SDLC.

B. Fixing defects found during static testing is generally much less expensive than fixing defects found during dynamic testing.

C. Finding coding defects that might not have been found by only performing dynamic testing.

D. Detecting gaps and inconsistencies in requirements.

**Correct Answer: A**

### Explanation

Static testing helps identify defects early in the SDLC. Early detection generally reduces the cost and effort required to correct defects.

Option A is incorrect because it suggests that defects are easier to detect later in the SDLC.

| Option | Explanation |
|---|---|
| A | Incorrect statement. Static testing promotes early detection, not later detection. |
| B | Correct benefit. Early defect correction is generally cheaper. |
| C | Correct benefit. Static analysis can identify certain defects that dynamic testing may miss. |
| D | Correct benefit. Reviews can identify missing, ambiguous and inconsistent requirements. |

**Exam Trap:** Remember the relationship between early testing and the cost of fixing defects.

---

## Question 2 — Identifying Review Types

The reviews being used in your organization have the following attributes:

- There is the role of a scribe.
- The main purpose is to evaluate quality.
- The meeting is led by the author of the work product.
- There is individual preparation.
- A review report is produced.

**Which of the following review types is MOST likely being used?**

A. Informal review

B. Walkthrough

C. Technical review

D. Inspection

**Correct Answer: B**

### Explanation

A walkthrough is led by the author of the work product.

Its objectives may include:

- Evaluating the quality of the work product.
- Educating reviewers.
- Building consensus.
- Generating new ideas.
- Identifying anomalies.
- Helping the author improve the work product.

Individual preparation may happen before a walkthrough, but it is not mandatory.

| Review Type | Key Characteristic |
|---|---|
| Informal review | No defined process or mandatory formal output. |
| Walkthrough | Led by the author. |
| Technical review | Conducted by technically qualified reviewers and led by a moderator. |
| Inspection | Most formal review type; follows the complete review process. |

**Exam Trap:** The author leading the review is a strong indicator of a walkthrough.

Do not select Inspection merely because the question mentions a scribe, individual preparation or a review report.

---

## Question 3 — Success Factors for Reviews

**Which of these statements is NOT a factor that contributes to successful reviews?**

A. Participants should dedicate adequate time for the review.

B. Splitting large work products into small parts to make the required effort less intense.

C. Participants should avoid behaviors that might indicate boredom, exasperation, or hostility to other participants.

D. Failures found should be acknowledged, appreciated, and handled objectively.

**Correct Answer: D**

### Explanation

This question tests the distinction between a defect/anomaly and a failure.

Static testing does not execute software. Therefore, it cannot directly identify runtime failures.

- A failure is observed when software executes and behaves incorrectly.
- A defect is a flaw in a work product.
- An anomaly is a finding that indicates a possible problem and requires investigation.

Reviews identify defects and anomalies in work products. They do not directly observe runtime failures.

| Option | Evaluation |
|---|---|
| A | Success factor — participants need adequate preparation and review time. |
| B | Success factor — reviewing smaller chunks helps maintain concentration. |
| C | Success factor — professional and constructive behaviour supports successful reviews. |
| D | NOT technically correct — static reviews identify defects/anomalies, not runtime failures. |

**Important Exam Trap:**

Do not confuse the following:

| Static Testing | Dynamic Testing |
|---|---|
| Software is not executed. | Software is executed. |
| Identifies defects directly in work products. | Can reveal failures, which may lead to identifying defects. |
| Reviews and static analysis. | Test execution. |
| Can examine non-executable work products. | Requires executable software. |

---

# Section B — Predicted Implementation & Scenario-Based Questions

These questions are designed to test whether you can apply the syllabus concepts to realistic software development situations.

## Q1. Static Testing in an Agile Team

A tester reviews a user story before the development team starts implementation.

The tester identifies that the acceptance criterion "The application should respond quickly" does not specify a measurable response time.

Which testing activity is being performed?

A. Dynamic testing

B. Static testing through a review

C. Component testing

D. Confirmation testing

**Correct Answer: B**

### Explanation

The tester is examining a requirement without executing the software.

The ambiguity can be identified through a review before implementation begins.

**Exam Trap:** Static testing can be performed on requirements, user stories and acceptance criteria. It is not limited to source code.

---

## Q2. Static Analysis in CI/CD

A development team integrates SonarQube into its CI pipeline.

Whenever a developer pushes code, the tool checks for:

- Unused variables.
- Code complexity.
- Potential security vulnerabilities.
- Coding-standard violations.

Which technique is being used?

A. Dynamic testing

B. Static analysis

C. Regression testing

D. Performance testing

**Correct Answer: B**

### Explanation

Static analysis uses tools to examine work products without executing the software.

It can identify coding defects, maintainability issues and certain security vulnerabilities.

**Real-world example:** SonarQube analysing Java code during a GitLab CI pipeline.

---

## Q3. Identifying a Work Product for Static Testing

A tester is asked to identify which of the following work products can be examined through static testing.

Which option is MOST appropriate?

A. An executed application session.

B. A running production server.

C. A requirement specification document.

D. A live performance test execution.

**Correct Answer: C**

### Explanation

A requirement specification is a non-executable work product.

It can be examined through a review to identify:

- Ambiguities.
- Missing requirements.
- Contradictions.
- Inconsistencies.

**Remember:** Almost any readable and understandable work product can be reviewed.

---

## Q4. Review vs Static Analysis

A QA engineer manually examines an API specification to identify missing response codes and ambiguous field definitions.

Which technique is being used?

A. Static analysis

B. Review

C. Dynamic testing

D. Load testing

**Correct Answer: B**

### Explanation

A review involves manual examination of a work product by one or more people.

Static analysis, in contrast, is performed using a tool.

**Exam Trap:** Static testing is the broader concept. Reviews and static analysis are its two main forms.

---

## Q5. Defect Detection Through Static Testing

A static analysis tool identifies a variable that is declared but never used.

Why is this defect easier to identify through static testing?

A. The application must be executed with high traffic.

B. The tool can examine the source code without executing it.

C. The tester must perform acceptance testing.

D. The application must be deployed to production.

**Correct Answer: B**

### Explanation

Static analysis examines source code without executing the application.

It can identify issues such as:

- Unused variables.
- Undeclared variables.
- Unreachable code.
- Duplicate code.
- Excessive complexity.

---

## Q6. Limitation of Static Testing

A QA engineer reviews a source code file and confirms that the code follows coding standards.

However, the application still takes 15 seconds to load when 10,000 users access it simultaneously.

Which statement is correct?

A. Static testing should always detect performance failures.

B. Static testing can replace performance testing.

C. Dynamic testing is required to evaluate runtime performance.

D. Code reviews cannot identify any defects.

**Correct Answer: C**

### Explanation

Performance efficiency under a given workload depends on executing the software.

Dynamic testing is required to measure characteristics such as:

- Response time.
- Throughput.
- Resource utilization.
- Scalability.

Static testing can identify certain design or code issues that may affect performance, but it cannot directly measure runtime performance.

---

## Q7. Early Stakeholder Feedback

A product team develops an entire application over six months without showing progress to the customer.

During final acceptance, the customer explains that the application does not meet the expected business requirements.

What could have reduced this risk?

A. Increasing regression testing at the end.

B. Early and frequent stakeholder feedback.

C. Performing only static code analysis.

D. Reducing stakeholder involvement.

**Correct Answer: B**

### Explanation

Early and frequent feedback helps identify misunderstandings and quality problems before they become expensive to correct.

It also helps ensure that the developed product continues to meet stakeholder expectations.

**Exam Trap:** Feedback is not restricted to the final acceptance stage.

---

## Q8. Consequence of Delayed Feedback

A business analyst changes an important requirement during development.

However, the development and testing teams are not informed until the release candidate is ready.

What is the MOST likely consequence?

A. Reduced rework.

B. Improved requirement understanding.

C. Increased rework and possible project delays.

D. Automatic improvement in product quality.

**Correct Answer: C**

### Explanation

Delayed communication of requirement changes can cause teams to implement outdated expectations.

This may result in:

- Rework.
- Missed deadlines.
- Misunderstandings.
- Increased project costs.
- Potential project failure.

---

## Q9. Review Process — Planning

A review leader defines the purpose of a review, the work product to be examined, quality characteristics, review scope, exit criteria and required effort.

Which review activity is being performed?

A. Review initiation

B. Planning

C. Individual review

D. Communication and analysis

**Correct Answer: B**

### Explanation

Planning defines how the review will be conducted.

It establishes:

- Review objectives.
- Scope.
- Work product.
- Quality characteristics.
- Areas of focus.
- Exit criteria.
- Resources and timeframes.

---

## Q10. Review Process — Review Initiation

A review leader distributes the work product and ensures that all reviewers understand their responsibilities and have access to the required information.

Which activity is being performed?

A. Planning

B. Review initiation

C. Individual review

D. Fixing and reporting

**Correct Answer: B**

### Explanation

Review initiation ensures that everyone involved is prepared to start the review.

This includes:

- Providing access to the work product.
- Communicating roles and responsibilities.
- Providing supporting information.
- Ensuring reviewers are ready.

---

## Q11. Review Process — Individual Review

Four reviewers independently examine a test plan.

One reviewer uses a checklist, another follows a user scenario, and the remaining reviewers examine the document for inconsistencies.

Which review activity is being performed?

A. Planning

B. Individual review

C. Communication and analysis

D. Fixing and reporting

**Correct Answer: B**

### Explanation

During individual review, each reviewer examines the work product independently.

Reviewers may use techniques such as:

- Checklist-based reviewing.
- Scenario-based reviewing.

They record anomalies, recommendations and questions.

---

## Q12. Review Process — Communication and Analysis

During a review meeting, the team discusses several identified anomalies.

They decide:

- Whether each anomaly is a defect.
- Who is responsible for fixing it.
- What action is required.
- Whether another review is necessary.

Which review activity is being performed?

A. Review initiation

B. Individual review

C. Communication and analysis

D. Planning

**Correct Answer: C**

### Explanation

The findings identified during individual reviews are analysed and discussed.

The team determines their status, ownership and required actions.

**Exam Trap:** Not every anomaly identified during a review is automatically a defect.

---

## Q13. Review Process — Fixing and Reporting

After a review meeting, the author corrects the identified defects.

The review leader checks whether the exit criteria have been achieved and prepares the review results.

Which activity is being performed?

A. Planning

B. Review initiation

C. Communication and analysis

D. Fixing and reporting

**Correct Answer: D**

### Explanation

Fixing and reporting involves:

- Correcting identified defects.
- Following up on corrective actions.
- Confirming whether exit criteria are achieved.
- Accepting the work product when appropriate.
- Reporting review results.

---

## Q14. Identifying Review Roles

During a formal review:

- One person provides staff and time.
- Another creates the work product.
- One person facilitates the meeting.
- One person records anomalies and decisions.

Which option correctly identifies these roles?

A. Manager, Author, Moderator, Scribe

B. Author, Manager, Reviewer, Moderator

C. Reviewer, Author, Manager, Review leader

D. Scribe, Moderator, Author, Reviewer

**Correct Answer: A**

### Explanation

| Responsibility | Role |
|---|---|
| Provides resources and decides what is reviewed | Manager |
| Creates and fixes the work product | Author |
| Facilitates the review meeting | Moderator |
| Records anomalies and decisions | Scribe |

---

## Q15. Distinguishing Moderator and Review Leader

A review needs someone to decide who participates, arrange the review location and organize the review schedule.

Who is responsible?

A. Scribe

B. Author

C. Review leader

D. Reviewer

**Correct Answer: C**

### Explanation

The review leader takes overall responsibility for organizing the review.

The moderator focuses on facilitating the review meeting, including time management and maintaining a constructive environment.

**Exam Trap:** Review leader and moderator are different roles.

---

## Q16. Identifying a Walkthrough

A developer presents a design document to the team and explains its contents step by step.

The objective is to educate participants, collect suggestions and identify possible anomalies.

Which review type is being conducted?

A. Inspection

B. Walkthrough

C. Informal review

D. Technical review

**Correct Answer: B**

### Explanation

A walkthrough is led by the author.

It can be used for education, knowledge sharing, consensus building and identifying anomalies.

---

## Q17. Identifying a Technical Review

A group of technically qualified engineers examine an architecture design.

A moderator leads the discussion, and the team aims to reach consensus on technical decisions.

Which review type is MOST appropriate?

A. Informal review

B. Walkthrough

C. Technical review

D. Inspection

**Correct Answer: C**

### Explanation

A technical review:

- Is performed by technically qualified reviewers.
- Is led by a moderator.
- Focuses on technical issues.
- Aims to reach consensus and make technical decisions.
- Can identify anomalies and improve confidence in the work product.

---

## Q18. Identifying an Inspection

A regulated organization conducts a highly structured review.

It includes defined entry and exit criteria, individual preparation, documented findings, a review report and metrics.

Which review type is MOST likely being used?

A. Informal review

B. Walkthrough

C. Technical review

D. Inspection

**Correct Answer: D**

### Explanation

Inspection is the most formal review type.

It follows the complete generic review process and typically collects metrics to improve both the work product and the review process.

**Important:** In an inspection, the author cannot act as the review leader or scribe.

---

## Q19. Review Success Factors

A team conducts reviews of large requirement documents.

Reviewers lose concentration because each review session lasts several hours.

What is the BEST improvement?

A. Remove individual preparation.

B. Divide the work product into smaller sections.

C. Stop collecting review findings.

D. Allow only the author to review the document.

**Correct Answer: B**

### Explanation

Reviewing smaller chunks helps reviewers maintain concentration and makes the review effort more manageable.

Other success factors include:

- Clear objectives.
- Appropriate review type.
- Adequate preparation time.
- Management support.
- Training.
- Constructive feedback.
- Facilitated meetings.

---

## Q20. Choosing the Appropriate Review Type

A team needs to review a small internal document quickly. The objective is simply to identify obvious anomalies, and there is no requirement for a documented review output.

Which review type is MOST suitable?

A. Inspection

B. Technical review

C. Informal review

D. Walkthrough

**Correct Answer: C**

### Explanation

An informal review:

- Does not follow a defined process.
- Does not require a formal documented output.
- Primarily aims to detect anomalies.

It is appropriate when a lightweight review is sufficient.

---

# Section C — Answer Key

## Section A

| Question | Answer | Topic |
|---|---|---|
| 1 | A | Benefits of static testing |
| 2 | B | Review types — Walkthrough |
| 3 | D | Static testing terminology |

## Section B

| Question | Answer | Topic |
|---|---|---|
| 1 | B | Static testing in Agile |
| 2 | B | Static analysis |
| 3 | C | Work products |
| 4 | B | Review vs static analysis |
| 5 | B | Static analysis |
| 6 | C | Static vs dynamic testing |
| 7 | B | Stakeholder feedback |
| 8 | C | Delayed feedback |
| 9 | B | Review planning |
| 10 | B | Review initiation |
| 11 | B | Individual review |
| 12 | C | Communication and analysis |
| 13 | D | Fixing and reporting |
| 14 | A | Review roles |
| 15 | C | Review leader |
| 16 | B | Walkthrough |
| 17 | C | Technical review |
| 18 | D | Inspection |
| 19 | B | Review success factors |
| 20 | C | Informal review |

---

# Section D — High-Value Exam Traps

| Concept | Remember |
|---|---|
| Static testing | Does not execute software. |
| Dynamic testing | Requires software execution. |
| Review | Manual examination of a work product. |
| Static analysis | Tool-based examination without execution. |
| Static testing findings | Defects and anomalies, not observed runtime failures. |
| Walkthrough | Led by the author. |
| Technical review | Technically qualified reviewers; led by a moderator. |
| Inspection | Most formal review type. |
| Informal review | No defined process or mandatory formal output. |
| Review leader | Organizes and takes overall responsibility. |
| Moderator | Facilitates review meetings. |
| Scribe | Records findings and decisions. |
| Individual review | Reviewers independently examine the work product. |
| Communication and analysis | Findings are discussed and ownership is decided. |
| Early feedback | Reduces misunderstandings and costly rework. |

---

# Section E — Self-Assessment Checklist

Before moving to the next chapter, ensure that you can:

- [ ] Explain static testing and dynamic testing.
- [ ] Differentiate reviews from static analysis.
- [ ] Identify work products suitable for static testing.
- [ ] Explain the benefits of static testing.
- [ ] Explain why early and frequent stakeholder feedback matters.
- [ ] Recall all five review process activities in the correct order.
- [ ] Differentiate manager, author, moderator, scribe, reviewer and review leader.
- [ ] Differentiate informal review, walkthrough, technical review and inspection.
- [ ] Identify review types from practical scenarios.
- [ ] Explain the success factors for reviews.
- [ ] Distinguish defects, anomalies and failures.

---

## Final Revision — Review Process Sequence

Remember the sequence:

**Planning → Review Initiation → Individual Review → Communication and Analysis → Fixing and Reporting**

A simple way to understand it:

1. **Planning:** Decide what and how to review.
2. **Review initiation:** Make everyone ready.
3. **Individual review:** Reviewers examine the work product.
4. **Communication and analysis:** Discuss and classify findings.
5. **Fixing and reporting:** Correct defects and report results.

**Chapter 3 preparation tip:** Pay particular attention to scenario-based questions involving review types, review roles, review process activities and the distinction between static and dynamic testing.