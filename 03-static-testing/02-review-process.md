# 3.2 Feedback and Review Process

**ISTQB CTFL v4.0.1 — Chapter 3: Static Testing**

---

## Scope

This module covers:

- Benefits of early and frequent stakeholder feedback.
- Review process activities.
- Roles and responsibilities in reviews.
- Different review types.
- Factors contributing to successful reviews.

## Learning Objectives

| Learning Objective | K-Level | What You Must Know |
|---|---|---|
| FL-3.2.1 | K1 | Recall the benefits of early and frequent stakeholder feedback. |
| FL-3.2.2 | K1 | Recall the activities in the review process. |
| FL-3.2.3 | K1 | Recall the roles and responsibilities in reviews. |
| FL-3.2.4 | K2 | Explain the differences between review types. |
| FL-3.2.5 | K1 | Recall factors that contribute to successful reviews. |

---

# 1. Benefits of Early and Frequent Stakeholder Feedback

## 1.1 What Is Stakeholder Feedback?

Stakeholder feedback is the information, opinions, suggestions and responses provided by stakeholders about a work product or software being developed.

Stakeholders may include:

- Customers.
- End users.
- Product owners.
- Business analysts.
- Developers.
- Testers.
- Project managers.
- Operations teams.

### Ways to Collect Stakeholder Feedback

- Requirement reviews.
- Sprint reviews and demonstrations.
- Prototype evaluations.
- User acceptance testing.
- Backlog refinement.
- Collaborative user story discussions.

## 1.2 Why Is Early and Frequent Feedback Important?

Early and frequent feedback helps identify misunderstandings and quality problems before they become expensive to fix.

### Key Benefits

**1. Early Identification of Quality Problems**

Stakeholders can identify incorrect assumptions, missing requirements and misunderstandings before significant development effort is invested.

**2. Avoids Costly Rework**

Changes made during requirement analysis or design are generally less expensive than changes made after implementation or production release.

**3. Prevents Project Failure**

Lack of stakeholder involvement may result in software that does not satisfy the original or evolving business requirements.

**4. Improves Requirement Understanding**

Frequent communication ensures that changes in requirements are understood and implemented correctly.

**5. Helps Prioritize Valuable Features**

The development team can focus on features that provide the greatest business value and have the most positive impact on identified risks.

**6. Reduces Misunderstandings**

Continuous feedback creates a shared understanding between stakeholders and the development team.

### Practical Example — E-commerce Application

Consider an e-commerce application.

The product owner provides the following requirement:

> Users should be able to cancel an order.

During a requirement review, the tester asks:

- Can users cancel an order after it has been shipped?
- Is cancellation allowed after payment?
- Will the refund be automatic?
- Is there a cancellation deadline?
- What happens if the order contains multiple products?

The stakeholder clarifies that cancellation is allowed only before shipment and the refund must be initiated automatically.

**Without early feedback:**

Developers might implement cancellation for all order statuses, resulting in rework and incorrect business behaviour.

**With early feedback:**

Ambiguities are resolved before implementation.

### What Happens When Stakeholder Feedback Is Missing?

| Problem | Possible Consequence |
|---|---|
| Limited stakeholder involvement | Product may not meet stakeholder expectations. |
| Misunderstood requirements | Incorrect functionality gets developed. |
| Late requirement changes | Increased rework and development costs. |
| Poor communication | Missed deadlines and disagreements. |
| Incorrect prioritization | Low-value features receive development effort. |
| Lack of shared understanding | Increased risk of project failure. |

### Exam Traps

- Early feedback helps prevent misunderstandings and costly rework.
- Feedback should happen throughout the SDLC, not only at the end.
- Stakeholder feedback does not eliminate the need for testing.
- Frequent feedback helps ensure that the product meets stakeholders' current expectations.

**Remember:** Early and frequent feedback reduces the risk of developing the wrong product.

---

# 2. Review Process Activities

## 2.1 What Is a Review?

A review is a type of static testing in which a work product is examined by one or more people to identify anomalies and evaluate its quality.

The review process consists of five activities:

1. Planning.
2. Review initiation.
3. Individual review.
4. Communication and analysis.
5. Fixing and reporting.

## 2.2 The Five Review Process Activities

### 1. Planning

**Purpose:** Define how the review will be conducted.

Activities include:

- Defining the review scope.
- Identifying the work product to be reviewed.
- Establishing review objectives.
- Identifying quality characteristics to evaluate.
- Selecting participants and assigning roles.
- Defining entry and exit criteria.
- Estimating effort and setting timelines.
- Providing supporting information such as standards and checklists.

**Practical Example:**

A team plans a review of the payment module's requirements.

The review leader defines:

- Scope: Payment and refund requirements.
- Objective: Identify ambiguity and missing requirements.
- Participants: Tester, developer, business analyst and product owner.
- Exit criteria: All major anomalies are addressed.

**Exam Keyword:** Scope, objectives, resources, participants and exit criteria.

### 2. Review Initiation

**Purpose:** Ensure that everything and everyone is ready for the review.

Activities include:

- Distributing the work product.
- Providing access to supporting documents.
- Ensuring reviewers understand their responsibilities.
- Confirming participants have sufficient information.
- Checking readiness to begin the review.

**Practical Example:**

Before reviewing a test plan, the review leader shares the document, requirement specifications and review checklist with all participants.

**Exam Keyword:** Distribution of documents and participant readiness.

### 3. Individual Review

**Purpose:** Each reviewer independently examines the work product.

Activities include:

- Identifying anomalies.
- Identifying questions and concerns.
- Suggesting improvements.
- Evaluating the quality of the work product.

Review techniques may include:

- Checklist-based reviewing.
- Scenario-based reviewing.

Reviewers record their findings for further discussion.

**Practical Example:**

A tester reviews a login requirement and identifies that the requirement does not specify the maximum number of failed login attempts.

This is an anomaly identified during individual review.

**Exam Keyword:** Independent examination and identification of anomalies.

### 4. Communication and Analysis

**Purpose:** Discuss and analyse the anomalies identified during individual review.

Important: An anomaly identified during a review is not necessarily a defect.

It may be:

- An actual defect.
- A question requiring clarification.
- A recommendation for improvement.
- An issue that is not valid after discussion.

Activities include:

- Discussing identified anomalies.
- Determining whether each anomaly is a defect.
- Assigning ownership.
- Deciding required actions.
- Determining the quality status of the work product.
- Deciding whether a follow-up review is required.

This is typically done in a review meeting.

**Practical Example:**

A reviewer identifies that a requirement does not specify password complexity.

During discussion, the business analyst confirms that password complexity is defined in a separate security policy.

The anomaly may be resolved through clarification rather than a change to the requirement.

**Exam Keyword:** Discussion, classification, ownership and action decisions.

### 5. Fixing and Reporting

**Purpose:** Correct identified defects and communicate review results.

Activities include:

- Fixing defects identified during the review.
- Creating defect reports where appropriate.
- Tracking corrective actions.
- Checking whether exit criteria are achieved.
- Reporting review results.
- Accepting the work product when exit criteria are met.

A follow-up review may be needed if corrections require further examination.

**Practical Example:**

The developer updates the incorrect requirement. The review leader checks the review status and confirms that the exit criteria have been satisfied.

**Exam Keyword:** Correcting defects and reporting review outcomes.

## 2.3 Review Process — Quick Comparison

| Activity | Main Purpose | Key Action |
|---|---|---|
| Planning | Define the review | Scope, objectives, resources and criteria |
| Review initiation | Prepare participants | Distribute work product and supporting information |
| Individual review | Find anomalies | Independent examination |
| Communication and analysis | Evaluate findings | Discuss, classify and assign actions |
| Fixing and reporting | Complete the review | Correct defects and report results |

### Exam Traps — Review Activities

| Scenario | Correct Activity |
|---|---|
| Defining review scope and objectives | Planning |
| Defining exit criteria | Planning |
| Distributing documents to reviewers | Review initiation |
| Ensuring reviewers are ready | Review initiation |
| Independently examining a document | Individual review |
| Identifying anomalies | Individual review |
| Discussing identified anomalies | Communication and analysis |
| Assigning ownership of defects | Communication and analysis |
| Correcting defects | Fixing and reporting |
| Reporting review results | Fixing and reporting |

**Important Distinction:**

- Finding anomalies = Individual review.
- Discussing and classifying anomalies = Communication and analysis.
- Correcting defects = Fixing and reporting.

---

# 3. Roles and Responsibilities in Reviews

Reviews involve different stakeholders who may perform different roles.

There are six principal roles.

## 3.1 Manager

**Responsibility:** Decides what is to be reviewed and provides resources.

Typical responsibilities:

- Selecting the work product for review.
- Providing sufficient staff.
- Allocating time and other resources.
- Supporting the review process.

**Example:**

A QA manager allocates two testers and a developer to review a test strategy.

**Remember:** Manager = Resources.

## 3.2 Author

**Responsibility:** Creates and fixes the work product under review.

Typical responsibilities:

- Preparing the work product.
- Explaining the work product when necessary.
- Addressing identified defects.
- Making agreed corrections.

**Example:**

A business analyst writes a requirement document and later corrects the ambiguities identified during the review.

**Remember:** Author = Creates and fixes.

## 3.3 Moderator (Facilitator)

**Responsibility:** Ensures the effective running of review meetings.

Typical responsibilities:

- Facilitating review meetings.
- Managing time.
- Mediating disagreements.
- Creating a safe environment.
- Ensuring everyone can participate freely.

**Example:**

During a requirement review, the developer and business analyst disagree. The moderator ensures that the discussion remains constructive and focused.

**Remember:** Moderator = Facilitates meetings.

## 3.4 Scribe (Recorder)

**Responsibility:** Records review information and collates anomalies.

Typical responsibilities:

- Recording identified anomalies.
- Documenting review decisions.
- Recording actions and ownership.
- Maintaining review meeting records.

**Example:**

During a code review, the scribe records the issues raised by reviewers and the agreed corrective actions.

**Remember:** Scribe = Records findings.

## 3.5 Reviewer

**Responsibility:** Examines the work product and identifies anomalies.

Typical responsibilities:

- Reviewing the work product.
- Identifying defects and inconsistencies.
- Raising questions.
- Suggesting improvements.

A reviewer may be:

- A project team member.
- A subject matter expert.
- A tester.
- Another relevant stakeholder.

**Example:**

A security tester reviews an authentication design and identifies a potential security weakness.

**Remember:** Reviewer = Identifies anomalies.

## 3.6 Review Leader

**Responsibility:** Takes overall responsibility for the review.

Typical responsibilities:

- Deciding who will participate.
- Organizing when the review will take place.
- Organizing where the review will take place.
- Ensuring the review is properly organized.

**Example:**

A senior QA engineer selects reviewers, schedules the review and coordinates the overall review process.

**Remember:** Review leader = Overall organization.

## 3.7 Roles — Quick Revision Table

| Role | Primary Responsibility | Keyword |
|---|---|---|
| Manager | Provides resources and decides what to review | Resources |
| Author | Creates and fixes work product | Creates and fixes |
| Moderator | Facilitates review meetings | Facilitates |
| Scribe | Records anomalies and decisions | Records |
| Reviewer | Examines work product | Identifies |
| Review leader | Overall responsibility for organizing review | Organizes |

### Important Exam Traps

1. **Author is not the same as Reviewer.**
    - Author creates and fixes the work product.
    - Reviewer examines the work product.

2. **Moderator is not the same as Review Leader.**
    - Moderator facilitates review meetings.
    - Review leader has overall responsibility for organizing the review.

3. **Scribe is not the same as Reviewer.**
    - Scribe records findings.
    - Reviewer identifies findings.

4. **Manager is not the same as Review Leader.**
    - Manager provides resources and decides what should be reviewed.
    - Review leader organizes the review.

---

# 4. Review Types

Reviews range from informal to formal.

The four commonly used review types are:

1. Informal review.
2. Walkthrough.
3. Technical review.
4. Inspection.

The required level of formality depends on:

- The SDLC being followed.
- Maturity of the development process.
- Criticality and complexity of the work product.
- Legal and regulatory requirements.
- Need for an audit trail.
- Project needs and available resources.

The same work product can be reviewed using different review types at different stages.

## 4.1 Informal Review

**Definition:** An informal review does not follow a defined review process and does not require a formal documented output.

**Main Objective:** Detect anomalies.

Characteristics:

- Minimal or no formal process.
- No mandatory formal documentation.
- Flexible participation.
- Quick feedback.
- Often used for everyday reviews.

**Practical Example:**

A developer asks another developer to quickly inspect a code change before merging it into the main branch.

There is no formal meeting, assigned scribe or documented review report.

**Exam Keyword:** No defined process and no formal documented output.

## 4.2 Walkthrough

**Definition:** A walkthrough is led by the author of the work product.

**Main Objectives:**

- Evaluating quality.
- Building confidence in the work product.
- Educating reviewers.
- Gaining consensus.
- Generating new ideas.
- Motivating and enabling the author to improve.
- Detecting anomalies.

Characteristics:

- Led by the author.
- Reviewers may perform individual reviews beforehand, but this is not mandatory.
- Can be used for knowledge sharing and discussion.
- May help reviewers understand complex work products.

**Practical Example:**

A business analyst explains a new payment workflow to testers and developers, walking them through each step and collecting feedback.

**Exam Keyword:** Author-led review.

## 4.3 Technical Review

**Definition:** A technical review is performed by technically qualified reviewers and led by a moderator.

**Main Objectives:**

- Gaining consensus.
- Making decisions about technical problems.
- Detecting anomalies.
- Evaluating quality.
- Building confidence in the work product.
- Generating new ideas.
- Motivating and enabling the author to improve.

Characteristics:

- Conducted by technically qualified reviewers.
- Led by a moderator.
- Focuses on technical issues.
- Supports technical decision-making and consensus.

**Practical Example:**

Senior developers, architects and testers examine a proposed microservices architecture to evaluate scalability, reliability and integration design.

**Exam Keyword:** Technically qualified reviewers + moderator.

## 4.4 Inspection

**Definition:** Inspection is the most formal type of review and follows the complete generic review process.

**Main Objective:** Find the maximum number of anomalies.

Other objectives:

- Evaluate quality.
- Build confidence in the work product.
- Motivate and enable authors to improve.
- Collect metrics to improve the SDLC and review process.

Characteristics:

- Most formal review type.
- Follows the complete generic review process.
- Uses defined roles.
- Metrics are collected.
- Has defined entry and exit criteria.
- The author cannot act as the review leader or scribe.

**Practical Example:**

A financial application undergoes a formal inspection of its regulatory compliance requirements.

Reviewers follow a documented process, record anomalies and track corrective actions.

**Exam Keyword:** Most formal review + complete review process + metrics.

## 4.5 Comparison of All Four Review Types

| Characteristic | Informal Review | Walkthrough | Technical Review | Inspection |
|---|---|---|---|---|
| Formality | Low | Varies | Varies | Highest |
| Main objective | Detect anomalies | Multiple objectives | Technical consensus and decisions | Maximum anomaly detection |
| Leader | No defined leader required | Author | Moderator | Trained moderator |
| Participants | Flexible | Relevant stakeholders | Technically qualified reviewers | Defined participants and roles |
| Documentation | Not mandatory | Varies | Usually documented | Formal documentation |
| Metrics | Not required | Not essential | May be collected | Collected |
| Process | No defined process | Structured but flexible | Structured | Complete generic process |

## 4.6 How to Identify the Review Type in an Exam?

| Scenario Clue | Correct Review Type |
|---|---|
| Developer asks a colleague to quickly check code | Informal review |
| Author explains a document to the team | Walkthrough |
| Architects discuss technical design and reach consensus | Technical review |
| Formal process with defined roles, metrics and documented results | Inspection |

### Most Important Distinctions

- Walkthrough → Author-led.
- Technical review → Moderator-led, technically qualified reviewers.
- Inspection → Most formal review.
- Informal review → No defined process or formal output required.

---

# 5. Success Factors for Reviews

A review is successful when it achieves its objectives and improves the quality of the work product.

The following factors contribute to successful reviews.

## 5.1 Define Clear Objectives and Measurable Exit Criteria

- Establish clear review objectives.
- Define measurable exit criteria.
- Ensure the review focuses on the work product.
- Evaluating participants should never be an objective.

**Example:** The objective is to identify missing acceptance criteria, not to evaluate the performance of the business analyst.

## 5.2 Choose the Appropriate Review Type

Select the review type based on:

- Review objectives.
- Work product type.
- Participants.
- Project requirements.
- Business context.
- Available resources.

**Example:** A quick code check may require an informal review, whereas a safety-critical system may require a formal inspection.

## 5.3 Conduct Reviews in Small Chunks

- Divide large work products into smaller sections.
- Avoid overwhelming reviewers.
- Maintain concentration.
- Improve the effectiveness of individual reviews and meetings.

**Example:** Instead of reviewing a 300-page requirement document in one session, divide it into smaller modules.

## 5.4 Provide Feedback to Stakeholders and Authors

- Communicate review results.
- Share findings with relevant stakeholders.
- Help authors improve their work products.
- Use findings to improve development activities.

## 5.5 Provide Adequate Preparation Time

- Reviewers should receive sufficient time to prepare.
- Supporting documents should be available.
- Reviewers should understand the scope and objectives.

## 5.6 Obtain Management Support

Management should:

- Provide time and resources.
- Encourage reviews.
- Support the review process.
- Avoid treating reviews as unnecessary overhead.

## 5.7 Make Reviews Part of Organizational Culture

- Encourage continuous learning.
- Promote quality awareness.
- Use reviews for process improvement.
- Avoid a blame-oriented environment.

## 5.8 Provide Adequate Training

Participants should understand:

- Their responsibilities.
- Review procedures.
- Review techniques.
- How to identify and report anomalies.

## 5.9 Facilitate Meetings

- Ensure meetings remain focused.
- Manage time effectively.
- Encourage constructive discussion.
- Prevent personal criticism and unnecessary arguments.

## 5.10 Success Factors — Quick Revision

| Success Factor | Why It Matters |
|---|---|
| Clear objectives and exit criteria | Keeps the review focused |
| Appropriate review type | Matches review approach to requirements |
| Small chunks | Maintains reviewer concentration |
| Feedback to authors and stakeholders | Enables improvement |
| Adequate preparation time | Improves review effectiveness |
| Management support | Provides resources and commitment |
| Review-friendly culture | Encourages learning and improvement |
| Adequate training | Ensures participants understand their roles |
| Facilitated meetings | Maintains productive discussions |

### Important Exam Trap

The objective of a review is to improve the work product and identify anomalies, **not to evaluate or blame the author**.

---

# 6. End-to-End Practical Example — Reviewing a User Story

Consider a banking application with the following user story:

> As a user, I want to transfer money to another account so that I can make payments.

## Step 1 — Planning

The review leader defines:

- Objective: Identify missing or ambiguous requirements.
- Scope: Fund transfer functionality.
- Participants: Tester, developer, business analyst and product owner.
- Exit criteria: Critical ambiguities and anomalies are addressed.

## Step 2 — Review Initiation

The business analyst shares:

- User story.
- Acceptance criteria.
- Business rules.
- Existing transfer workflow.

All participants receive the required documents.

## Step 3 — Individual Review

The tester identifies questions:

- What is the maximum transfer amount?
- Is there a daily transaction limit?
- What happens if the beneficiary account is invalid?
- How should duplicate transactions be handled?
- What happens if the network fails after debit but before credit?

## Step 4 — Communication and Analysis

The team discusses the findings.

They identify missing requirements for:

- Transaction limits.
- Duplicate transaction handling.
- Failure recovery.
- Transaction status.

The business analyst takes ownership of updating the requirements.

## Step 5 — Fixing and Reporting

The business analyst updates the user story and acceptance criteria.

The review results are reported, and the team checks whether the review exit criteria are satisfied.

**Learning:** A review can identify requirement defects before the application is implemented or executed.

---

# 7. Exam Traps and Important Distinctions

| Exam Statement | Correct Understanding |
|---|---|
| Every anomaly found in a review is a defect. | False. Anomalies require analysis. |
| A walkthrough is led by a moderator. | False. It is led by the author. |
| A technical review is led by the author. | False. It is led by a moderator. |
| Inspection is the most formal review type. | True. |
| The author can act as the scribe during inspection. | False. |
| Individual review involves independent examination. | True. |
| Communication and analysis involves discussing anomalies. | True. |
| Fixing and reporting includes correcting defects. | True. |
| The moderator provides resources for reviews. | False. This is the manager's responsibility. |
| The scribe facilitates meetings. | False. The moderator facilitates meetings. |
| The review leader has overall responsibility for organizing the review. | True. |
| The objective of reviews is to evaluate individual performance. | False. |

---

# 8. Practice Questions

**Question Distribution**

- Section A: Core concepts and knowledge-based questions.
- Section B: Implementation-oriented and scenario-based questions.

These are original practice questions created for preparation, not official ISTQB examination questions or verified past-paper questions.

---

# Section A — Core Concept Questions

### Q1. What is the primary benefit of early and frequent stakeholder feedback?

A. It eliminates the need for dynamic testing.

B. It helps identify misunderstandings and quality problems early.

C. It guarantees that no defects will be introduced.

D. It removes the need for requirement documentation.

### Q2. Which of the following is NOT a typical benefit of early stakeholder feedback?

A. Reduced rework.

B. Better understanding of requirements.

C. Increased likelihood of project failure.

D. Improved prioritization of features.

### Q3. Which activity involves defining review scope, objectives, resources and exit criteria?

A. Review initiation.

B. Individual review.

C. Planning.

D. Fixing and reporting.

### Q4. During which review activity do reviewers independently examine the work product?

A. Planning.

B. Individual review.

C. Communication and analysis.

D. Review initiation.

### Q5. Anomalies identified during individual review are discussed and classified during which activity?

A. Fixing and reporting.

B. Planning.

C. Communication and analysis.

D. Review initiation.

### Q6. Who is responsible for providing resources such as staff and time for a review?

A. Author.

B. Manager.

C. Scribe.

D. Reviewer.

### Q7. Who is responsible for recording anomalies and decisions during a review meeting?

A. Moderator.

B. Author.

C. Scribe.

D. Review leader.

### Q8. Which role is responsible for facilitating review meetings and managing time?

A. Manager.

B. Moderator.

C. Author.

D. Scribe.

### Q9. Which review type is led by the author?

A. Inspection.

B. Technical review.

C. Walkthrough.

D. Informal review.

### Q10. Which review type is performed by technically qualified reviewers and led by a moderator?

A. Walkthrough.

B. Technical review.

C. Informal review.

D. Inspection.

### Q11. Which review type is the most formal and follows the complete generic review process?

A. Informal review.

B. Walkthrough.

C. Technical review.

D. Inspection.

### Q12. Which statement about inspections is correct?

A. The author can act as the review leader.

B. The author can act as the scribe.

C. Metrics are collected to improve the SDLC and inspection process.

D. No formal process is followed.

### Q13. Which of the following is a success factor for reviews?

A. Reviewing very large documents in one sitting.

B. Evaluating the performance of the author.

C. Providing adequate preparation time to reviewers.

D. Avoiding management involvement.

### Q14. What is the main objective of an informal review?

A. Collecting metrics.

B. Detecting anomalies.

C. Reaching technical consensus.

D. Following the complete generic review process.

### Q15. Which statement about anomalies found during reviews is correct?

A. Every anomaly must be treated as a defect.

B. Anomalies must be analysed and discussed.

C. All anomalies must be fixed immediately.

D. Only the author can classify anomalies.

---

# Section B — Implementation-Oriented and Scenario-Based Questions

### Q16. A tester reviews a user story before development begins. The requirement states, "The application should respond quickly." The tester asks for a measurable response-time target. Which benefit of static testing is demonstrated?

A. Detecting runtime failures.

B. Identifying ambiguity in a work product before execution.

C. Measuring application performance.

D. Performing regression testing.

### Q17. A team receives a 200-page requirements document for review. Reviewers lose concentration when reviewing the entire document in one session. What should the review leader do?

A. Remove individual review activities.

B. Divide the document into smaller chunks.

C. Ask only the author to review the document.

D. Skip the review meeting.

### Q18. A developer asks a colleague to quickly inspect a small code change. There is no formal process or documented output. Which review type is being performed?

A. Inspection.

B. Technical review.

C. Walkthrough.

D. Informal review.

### Q19. A business analyst presents a new requirement document to testers and developers, explaining its functionality and collecting suggestions. Who is leading this review?

A. Moderator.

B. Author.

C. Scribe.

D. Manager.

### Q20. A group of architects and senior developers examines a proposed system architecture. A moderator leads the discussion, and the objective is to reach consensus on technical decisions. Which review type is appropriate?

A. Walkthrough.

B. Informal review.

C. Technical review.

D. Inspection.

### Q21. A financial application undergoes a formal review. The process includes defined roles, documented findings, metrics and formal exit criteria. Which review type is this?

A. Informal review.

B. Walkthrough.

C. Technical review.

D. Inspection.

### Q22. During a review, a tester identifies that the password policy is missing from the requirements. During discussion, the business analyst confirms that it is defined in another approved document. What should the team do?

A. Automatically classify it as a defect.

B. Ignore the observation without discussion.

C. Analyse the anomaly and determine the appropriate action.

D. Ask the tester to fix the requirement.

### Q23. During a review meeting, two developers disagree about a design decision. One person manages the discussion, controls the time and ensures that both parties can express their views. Which role is being performed?

A. Scribe.

B. Moderator.

C. Author.

D. Manager.

### Q24. A review meeting is completed, but no one records the anomalies or decisions. Which role was most likely not fulfilled?

A. Reviewer.

B. Author.

C. Scribe.

D. Manager.

### Q25. A project manager selects a critical requirements document for review and allocates three testers and two developers to perform it. Which role is being performed?

A. Review leader.

B. Manager.

C. Moderator.

D. Scribe.

### Q26. A review leader schedules the review, selects participants and arranges the meeting location. Which role is being performed?

A. Author.

B. Reviewer.

C. Review leader.

D. Manager.

### Q27. A reviewer finds an issue in a requirement document. During the review meeting, the team decides that it is a valid defect and assigns it to the author for correction. Which review process activity is taking place?

A. Planning.

B. Review initiation.

C. Communication and analysis.

D. Individual review.

### Q28. After a review, the author corrects the identified defects. The review results are documented and the exit criteria are checked. Which activity is taking place?

A. Review initiation.

B. Individual review.

C. Fixing and reporting.

D. Planning.

### Q29. A company conducts reviews only to identify which employee made mistakes. As a result, employees hesitate to report problems. Which success factor is being violated?

A. Adequate preparation time.

B. Making reviews part of the organization's culture.

C. Selecting appropriate review types.

D. Reviewing small chunks.

### Q30. A review team is asked to examine a complex work product. The reviewers are not familiar with the review techniques or their assigned responsibilities. What would most improve the review's success?

A. Reduce the number of reviewers.

B. Provide adequate training.

C. Remove the review leader.

D. Avoid documenting anomalies.

### Q31. A team has limited time and wants to review a simple internal document. There is no legal requirement for a formal audit trail. Which approach is most appropriate?

A. Inspection is always mandatory.

B. An informal review may be sufficient.

C. A technical review must be conducted.

D. The document should not be reviewed.

### Q32. During an inspection, the author is asked to act as the scribe. What is the correct response?

A. Accept, because the author created the document.

B. Accept, because the author knows the document best.

C. Reject, because the author cannot act as the review leader or scribe in an inspection.

D. Accept, if the moderator agrees.

### Q33. A review leader distributes the work product, supporting documents and review instructions to participants before the review starts. Which activity is being performed?

A. Planning.

B. Review initiation.

C. Individual review.

D. Fixing and reporting.

### Q34. During individual review, a tester identifies an incorrect calculation in a financial requirement. What should happen next?

A. The tester should directly modify the requirement.

B. The finding should be recorded and later analysed.

C. The finding should immediately be closed.

D. The review should be terminated.

### Q35. A review team has clear objectives, suitable participants, adequate preparation time and management support. However, the team reviews an entire large document in one sitting. What improvement is most appropriate?

A. Remove management support.

B. Divide the work product into smaller chunks.

C. Eliminate review objectives.

D. Reduce the number of review activities.

### Q36. A team conducts an author-led session to explain a complex design, educate reviewers and generate new ideas. Which review type is being used?

A. Technical review.

B. Inspection.

C. Walkthrough.

D. Informal review.

### Q37. A company wants to improve its SDLC by collecting review metrics and analysing the effectiveness of its review process. Which review type is most suitable?

A. Informal review.

B. Walkthrough.

C. Inspection.

D. Any informal discussion.

### Q38. A reviewer identifies an anomaly during a review. The team determines that it is a valid suggestion for improvement rather than a defect. What is the correct interpretation?

A. The reviewer made an error because all anomalies are defects.

B. Anomalies may include defects, questions and recommendations.

C. The review must be repeated.

D. The author must reject the suggestion.

### Q39. A team conducts a review, but participants have not received the work product or supporting information beforehand. Which activity was inadequately performed?

A. Review initiation.

B. Fixing and reporting.

C. Communication and analysis.

D. Individual review.

### Q40. A review leader wants to ensure that reviews contribute to continuous improvement rather than becoming a blame exercise. Which action is most appropriate?

A. Use review findings to evaluate individual employees.

B. Make reviews part of the organizational culture and promote learning.

C. Avoid sharing feedback with authors.

D. Conduct reviews only when defects reach production.

---

# 9. Answer Key with Detailed Explanations

## Section A — Answers

| Q | Answer | Explanation |
|---|---|---|
| 1 | **B** | Early feedback helps identify misunderstandings and quality problems before they become costly. |
| 2 | **C** | Early feedback reduces project risk; it does not increase the likelihood of failure. |
| 3 | **C** | Planning defines scope, objectives, resources and exit criteria. |
| 4 | **B** | Individual review is the independent examination of the work product. |
| 5 | **C** | Communication and analysis involves discussing and classifying anomalies. |
| 6 | **B** | The manager provides resources such as staff and time. |
| 7 | **C** | The scribe records anomalies and review decisions. |
| 8 | **B** | The moderator facilitates meetings and manages time. |
| 9 | **C** | A walkthrough is led by the author. |
| 10 | **B** | A technical review uses technically qualified reviewers and a moderator. |
| 11 | **D** | Inspection is the most formal review type. |
| 12 | **C** | Inspection collects metrics to improve the SDLC and review process. |
| 13 | **C** | Reviewers need adequate preparation time. |
| 14 | **B** | Detecting anomalies is the main objective of an informal review. |
| 15 | **B** | Anomalies must be analysed; they are not automatically defects. |

## Section B — Answers

| Q | Answer | Explanation |
|---|---|---|
| 16 | **B** | Ambiguity in a requirement is identified without executing the software. |
| 17 | **B** | Reviewing smaller chunks helps maintain concentration. |
| 18 | **D** | No defined process or formal output indicates an informal review. |
| 19 | **B** | The author leads a walkthrough. |
| 20 | **C** | Technical experts and a moderator indicate a technical review. |
| 21 | **D** | Formal process, roles, metrics and exit criteria indicate inspection. |
| 22 | **C** | Anomalies must be analysed before deciding their status and action. |
| 23 | **B** | The moderator facilitates the meeting and manages disagreements. |
| 24 | **C** | The scribe records anomalies and decisions. |
| 25 | **B** | The manager decides what is reviewed and provides resources. |
| 26 | **C** | The review leader organizes the review and selects participants. |
| 27 | **C** | The team is discussing and classifying an anomaly and assigning ownership. |
| 28 | **C** | Correcting defects and reporting results are part of fixing and reporting. |
| 29 | **B** | A blame-oriented environment contradicts a learning and improvement culture. |
| 30 | **B** | Training ensures participants understand their roles and review techniques. |
| 31 | **B** | An informal review may be appropriate for a simple document without formal audit requirements. |
| 32 | **C** | In an inspection, the author cannot act as review leader or scribe. |
| 33 | **B** | Distributing work products and supporting documents is review initiation. |
| 34 | **B** | Findings are recorded during individual review and analysed later. |
| 35 | **B** | Smaller chunks improve reviewer concentration. |
| 36 | **C** | Author-led explanation and education indicate a walkthrough. |
| 37 | **C** | Inspections collect metrics and support process improvement. |
| 38 | **B** | An anomaly may be a defect, question or recommendation. |
| 39 | **A** | Review initiation ensures participants have the required materials and information. |
| 40 | **B** | A learning-oriented organizational culture supports successful reviews. |

---

# 10. Last-Minute Revision Sheet

## Five Review Process Activities

| Order | Activity | Keyword |
|---|---|---|
| 1 | Planning | Define |
| 2 | Review initiation | Prepare |
| 3 | Individual review | Examine |
| 4 | Communication and analysis | Discuss |
| 5 | Fixing and reporting | Correct and report |

## Six Review Roles

| Role | Keyword |
|---|---|
| Manager | Resources |
| Author | Creates and fixes |
| Moderator | Facilitates |
| Scribe | Records |
| Reviewer | Identifies anomalies |
| Review leader | Organizes |

## Four Review Types

| Type | Keyword |
|---|---|
| Informal review | No defined process |
| Walkthrough | Author-led |
| Technical review | Technical experts + moderator |
| Inspection | Most formal + metrics |

## Nine Success Factors

1. Clear objectives and measurable exit criteria.
2. Appropriate review type.
3. Small chunks.
4. Feedback to stakeholders and authors.
5. Adequate preparation time.
6. Management support.
7. Reviews as part of organizational culture.
8. Adequate training.
9. Facilitated meetings.

---

# 11. Self-Assessment Checklist

Use this checklist before moving to the next topic.

- [ ] I can explain the benefits of early and frequent stakeholder feedback.
- [ ] I can identify the five review process activities in the correct order.
- [ ] I can distinguish individual review from communication and analysis.
- [ ] I can explain the responsibilities of all six review roles.
- [ ] I can differentiate informal reviews, walkthroughs, technical reviews and inspections.
- [ ] I know why an inspection is the most formal review type.
- [ ] I know the restriction on the author's role during an inspection.
- [ ] I can recall all nine success factors.
- [ ] I can solve scenario-based questions involving review roles and activities.

**Suggested target:** Aim for at least 34/40 correct answers before considering this topic exam-ready.

---

# 12. Final Exam Takeaways

1. Early and frequent stakeholder feedback prevents misunderstandings and costly rework.
2. The review process has five activities: Planning, Review Initiation, Individual Review, Communication and Analysis, Fixing and Reporting.
3. An anomaly is not necessarily a defect.
4. The manager provides resources; the review leader organizes the review.
5. The author creates and fixes the work product.
6. The moderator facilitates meetings.
7. The scribe records anomalies and decisions.
8. The reviewer identifies anomalies.
9. A walkthrough is author-led.
10. A technical review is led by a moderator and involves technically qualified reviewers.
11. Inspection is the most formal review type.
12. During an inspection, the author cannot act as the review leader or scribe.
13. Reviews should promote learning and improvement, not blame.