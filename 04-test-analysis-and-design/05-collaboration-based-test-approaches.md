
# 4.5 Collaboration-Based Test Approaches

## 1. Introduction to Collaboration-Based Test Approaches

Collaboration-based test approaches involve collaboration between business representatives, developers and testers to establish a shared understanding of requirements and expected software behaviour.

The primary objective is to prevent misunderstandings, clarify requirements and ensure that the delivered functionality meets stakeholder expectations.

The two important concepts covered in this section are:

1. Collaborative User Story Writing
2. Acceptance Test-Driven Development (ATDD)

---

# 2. Collaborative User Story Writing

## 2.1 What is a User Story?

A **user story** represents a feature that will be valuable to either a user or purchaser of a system or software.

It describes a requirement from the perspective of the person who will benefit from the functionality.

A user story focuses on:
- Who needs the functionality?
- What functionality is required?
- Why is the functionality valuable?

### Common User Story Format

The most common format is:

```text
As a [role],
I want [goal to be accomplished],
so that I can [resulting business value].
```

### Example: E-commerce Application

```text
As a registered customer,
I want to add products to my wishlist,
so that I can save products for future purchases.
```

Breaking it down:

| Component | Description |
|---|---|
| Role | Registered customer |
| Goal | Add products to wishlist |
| Business Value | Save products for future purchases |

**Exam Point:** A user story represents a feature that provides value to a user or purchaser of the system.

## 2.2 The 3 C's of User Stories

User stories have three critical aspects, collectively known as the **3 C's**.

### 1. Card

The card is the medium used to describe or represent a user story.

Examples:
- Physical index card.
- Entry in an electronic board.
- User story in Jira.

It contains a brief description of the functionality.

### 2. Conversation

Conversation explains how the software will be used.

It involves discussions between relevant stakeholders to clarify:
- Requirements.
- Expected behaviour.
- Business rules.
- User expectations.
- Possible scenarios.

The conversation can be:
- Verbal.
- Documented.

### 3. Confirmation

Confirmation represents the **acceptance criteria** of the user story.

It defines the conditions that must be satisfied for the implementation to be accepted by stakeholders.

### Remember: 3 C's

| C | Meaning | Purpose |
|---|---|---|
| Card | Medium describing the story | Captures the user story |
| Conversation | Discussion about expected behaviour | Builds shared understanding |
| Confirmation | Acceptance criteria | Defines conditions for acceptance |

**Exam Trap:** Confirmation does not mean merely confirming that the story has been written. It refers to the acceptance criteria.

## 2.3 Collaborative Authorship of User Stories

User stories should be created collaboratively.

Collaboration can involve three important perspectives:

1. Business
2. Development
3. Testing

The team may use techniques such as:
- Brainstorming.
- Mind mapping.

### Why is Collaboration Important?

Collaboration helps the team obtain a **shared vision of what should be delivered**.

Each perspective contributes something different.

| Perspective | Contribution |
|---|---|
| Business | Explains business objectives and user value |
| Development | Identifies technical considerations and implementation implications |
| Testing | Identifies test conditions, risks and potential failure scenarios |

### Example

Consider a user story for online payment.

**Business perspective:**
- Customer should be able to make payments.
- Payment should be convenient and secure.

**Development perspective:**
- Payment gateway integration is required.
- Transaction status must be maintained.
- Duplicate payment requests must be handled.

**Testing perspective:**
- Verify successful payments.
- Verify failed payments.
- Test network interruption.
- Check duplicate payment handling.
- Verify transaction status and balance updates.

The collaboration ensures that the team understands what needs to be delivered from different perspectives.

## 2.4 INVEST Characteristics of Good User Stories

Good user stories should follow the **INVEST** characteristics.

| Letter | Characteristic | Explanation |
|---|---|---|
| I | Independent | The story should be as independent as possible from other stories. |
| N | Negotiable | The story is not a rigid contract; details can be discussed and negotiated. |
| V | Valuable | The story should provide value to users or other stakeholders. |
| E | Estimable | The team should be able to estimate the effort required. |
| S | Small | The story should be sufficiently small to be completed within an appropriate development period. |
| T | Testable | The story should have clear conditions that allow its implementation to be tested. |

### 1. Independent

A user story should have minimal dependencies on other stories.

Example:

A story for viewing a product should ideally be independent of a story for applying a discount coupon.

### 2. Negotiable

A user story should allow discussion and refinement.

It should not be treated as a fixed, unchangeable contract.

Example:

The team may discuss whether wishlist functionality should support multiple wishlists or just one.

### 3. Valuable

A user story should provide meaningful value.

Example:

```text
As a customer,
I want to track my order,
so that I can know when it will be delivered.
```

The feature provides value by improving order visibility.

### 4. Estimable

The team should have enough information to estimate the effort required.

If the story is unclear or excessively complex, the team may not be able to estimate it accurately.

### 5. Small

A user story should be small enough to be implemented and tested within a reasonable development period.

Example:

Too large:
- Implement the complete e-commerce platform.

Smaller stories:
- Register a customer.
- Log in to the application.
- Search for products.
- Add products to the cart.
- Make a payment.

### 6. Testable

A user story should be clear enough that the team can determine whether its implementation satisfies the expected behaviour.

Example:

Poorly defined:
- The application should be fast.

Better defined:
- The product search results should be displayed within the agreed response-time limit under the specified conditions.

**Important Exam Point:**

If a stakeholder does not know how to test a user story, it may indicate that:
- The story is not sufficiently clear.
- The story does not reflect something valuable to the stakeholder.
- The stakeholder needs assistance with testing.

Do not automatically conclude that the story is invalid. The stakeholder may simply need help understanding how to test it.

---

# 3. Acceptance Criteria

## 3.1 What are Acceptance Criteria?

**Acceptance criteria** are the conditions that an implementation of a user story must meet to be accepted by stakeholders.

From a testing perspective, acceptance criteria can be viewed as the **test conditions that should be exercised by tests**.

They are usually a result of the Conversation aspect of the 3 C's.

### Example

User Story:

```text
As a registered customer,
I want to reset my password,
so that I can regain access to my account if I forget it.
```

Acceptance criteria:

1. The user should be able to request a password reset.
2. A valid reset link should be sent to the registered email address.
3. An expired reset link should not be accepted.
4. The new password should satisfy the password policy.
5. The user should be able to log in using the new password.

These criteria describe the conditions that the implementation must satisfy.

## 3.2 Why are Acceptance Criteria Important?

Acceptance criteria are used to:

### 1. Define the Scope of the User Story

They clarify what is included in the story and what is outside its scope.

### 2. Reach Consensus Among Stakeholders

They help business representatives, developers and testers agree on expected behaviour.

### 3. Describe Positive and Negative Scenarios

They cover both:
- Expected successful behaviour.
- Invalid inputs and error conditions.

### 4. Serve as a Basis for User Story Acceptance Testing

Testers can derive acceptance tests from the acceptance criteria.

### 5. Allow Accurate Planning and Estimation

Clear acceptance criteria help the team understand the expected functionality and estimate the work.

## 3.3 Formats of Acceptance Criteria

There are two commonly used formats.

### A. Scenario-Oriented Format

Scenario-oriented acceptance criteria commonly use the **Given/When/Then** format associated with Behaviour-Driven Development (BDD).

Structure:

```text
Given [initial context or precondition]
When [action or event]
Then [expected outcome]
```

#### Example: Successful Login

```gherkin
Given the user is registered
And the user is on the login page

When the user enters valid credentials
And clicks the Login button

Then the user should be successfully logged in
And redirected to the dashboard
```

Explanation:

| Keyword | Meaning |
|---|---|
| Given | Initial context or precondition |
| When | Action or event |
| Then | Expected result |

#### Example: Invalid Login

```gherkin
Given the user is on the login page

When the user enters an incorrect password
And clicks the Login button

Then the login should fail
And an appropriate error message should be displayed
```

**Exam Point:** Given/When/Then is a scenario-oriented format associated with BDD.

### B. Rule-Oriented Format

Rule-oriented acceptance criteria use:
- Bullet-point verification lists.
- Tabulated input-output mappings.
- Business rules and conditions.

#### Example: Password Validation

| Input Condition | Expected Output |
|---|---|
| Password has fewer than 8 characters | Validation error |
| Password has at least 8 characters | Accepted, subject to other rules |
| Password is empty | Mandatory field error |
| Password does not contain a required special character | Validation error |

Rule-oriented criteria describe the expected behaviour through rules rather than a sequence of Given/When/Then steps.

### Scenario-Oriented vs Rule-Oriented

| Parameter | Scenario-Oriented | Rule-Oriented |
|---|---|---|
| Structure | Given/When/Then | Bullet points or tables |
| Focus | Specific scenarios | Business rules and conditions |
| Common association | BDD | Verification lists and input-output mapping |
| Example | Successful login scenario | Password length validation rule |

### Important Note

Most acceptance criteria can be documented using either of these formats.

However, a team may use a custom format as long as the acceptance criteria are:
- Well-defined.
- Unambiguous.

---

# 4. Acceptance Test-Driven Development (ATDD)

## 4.1 What is ATDD?

**Acceptance Test-Driven Development (ATDD)** is a test-first approach in which acceptance test cases are created before implementing the user story.

The test cases are created collaboratively by team members with different perspectives, such as:

- Customers or business representatives.
- Developers.
- Testers.

The objective is to develop a shared understanding of the expected behaviour before implementation begins.

### Key Characteristics

1. ATDD follows a test-first approach.
2. Acceptance test cases are created before implementing the user story.
3. Test cases are based on acceptance criteria.
4. Test cases can be executed manually or automated.
5. Test cases are created collaboratively.
6. Test design techniques may be applied while designing the test cases.

## 4.2 Steps Involved in ATDD

### Step 1: Specification Workshop

The first step is a specification workshop.

During this workshop:
- The user story is analysed.
- Acceptance criteria are discussed.
- Team members clarify requirements.
- Incompleteness is identified.
- Ambiguities are resolved.
- Defects in the user story are discussed and resolved.

The objective is to establish a common understanding before test case creation and implementation.

### Step 2: Create Test Cases

The next step is to create test cases based on the acceptance criteria.

Test cases can be created:
- By the team as a whole.
- By an individual tester.

These test cases serve as examples of how the software should work.

They help developers implement the user story correctly.

### Step 3: Execute Test Cases

The test cases may be executed:
- Manually.
- Automatically.

Test cases are usually designed to cover different types of behaviour.

#### A. Positive Test Cases

Typically, the first test cases are positive test cases.

They confirm correct behaviour without exceptions or error conditions.

Example:

- Enter valid login credentials.
- Click Login.
- Verify successful authentication.
- Verify redirection to the dashboard.

These represent the sequence of activities when everything works as expected.

#### B. Negative Test Cases

After positive test cases, the team should perform negative testing.

Examples:

- Invalid password.
- Empty username.
- Expired authentication token.
- Account locked.
- Invalid input.

These tests verify how the system behaves under invalid or exceptional conditions.

#### C. Non-Functional Test Cases

The team should also cover non-functional quality characteristics.

Examples:

- Performance efficiency.
- Usability.

Test cases should be expressed in a way that is understandable to stakeholders.

### Step 4: Implement the User Story

The developers implement the feature using the agreed user story and acceptance criteria.

When the acceptance tests are captured in a format supported by a test automation framework, developers can automate them by writing the supporting code while implementing the feature.

### Step 5: Acceptance Tests Become Executable Requirements

The acceptance tests represent the expected behaviour of the system.

They can therefore become **executable requirements**.

This means the requirements are expressed through tests that can be executed to verify whether the implementation satisfies the agreed expectations.

## 4.3 Structure of ATDD Test Cases

Typically, ATDD test cases are expressed in natural language.

They may involve:

1. Necessary preconditions, if any.
2. Inputs.
3. Postconditions.

### Example

User Story:

```text
As a customer,
I want to transfer money to a beneficiary,
so that I can make payments conveniently.
```

Acceptance Test:

```text
Precondition:
The customer is logged in and has sufficient balance.

Input:
Beneficiary account number and transfer amount.

Action:
The customer initiates the fund transfer.

Expected Postcondition:
The transfer is completed successfully,
and the account balance is updated.
```

## 4.4 Relationship Between User Story and Test Cases

The test cases must:

1. Cover all characteristics of the user story.
2. Not go beyond the user story.
3. Be based on the acceptance criteria.
4. Avoid duplication of the same user story characteristics across test cases.

Acceptance criteria may provide additional details about issues described in the user story.

### Example

User Story:

```text
As a customer,
I want to make an online payment,
so that I can purchase products.
```

Possible acceptance tests:

- Successful payment using a valid card.
- Payment failure using an invalid card.
- Payment failure due to insufficient funds.
- Handling of a payment gateway timeout.

These tests cover the expected payment functionality.

However, a test for generating monthly sales reports would be outside the scope of this particular user story unless that functionality is explicitly included.

## 4.5 Automation in ATDD

When acceptance test cases are captured in a format supported by a test automation framework:

- Developers can automate the acceptance tests.
- Supporting automation code can be written while implementing the feature.
- The tests can verify whether the implementation meets the agreed requirements.

### Practical SDET Example: Cucumber and Selenium

Feature file:

```gherkin
Feature: Customer Login

  Scenario: Successful login
    Given the customer is on the login page
    When the customer enters valid credentials
    And clicks the login button
    Then the customer should be redirected to the dashboard
```

This scenario can be automated using:
- Cucumber.
- Gherkin.
- Selenium WebDriver.
- Java step definitions.

The acceptance test provides an executable representation of the expected behaviour.

**Important:** ATDD test cases may be executed manually or automated. Automation is not mandatory for ATDD.

---

# 5. ATDD Execution Order — Important for Exams

Remember the following sequence:

1. Specification workshop.
2. Analyse and discuss the user story and acceptance criteria.
3. Resolve incompleteness, ambiguity and defects.
4. Create test cases based on acceptance criteria.
5. Execute positive test cases.
6. Perform negative testing.
7. Cover non-functional quality characteristics.
8. Implement the user story and supporting automation where applicable.
9. Use acceptance tests as executable requirements.

**Core Concept:** Tests are created before implementation because ATDD is a test-first approach.

---

# 6. Important Comparison Tables

## 6.1 User Story vs Acceptance Criteria

| User Story | Acceptance Criteria |
|---|---|
| Describes a feature valuable to a user or purchaser | Defines conditions the implementation must meet |
| Explains who wants what and why | Explains how the implementation will be accepted |
| Provides a high-level requirement | Provides specific conditions |
| Commonly follows the As a/I want/So that format | Can use Given/When/Then or rule-oriented format |

## 6.2 BDD vs ATDD

| Parameter | BDD | ATDD |
|---|---|---|
| Full Form | Behaviour-Driven Development | Acceptance Test-Driven Development |
| Focus | Describing expected system behaviour | Defining acceptance tests before implementation |
| Common format | Given/When/Then | Acceptance tests, often expressed as examples |
| Collaboration | Business, development and testing perspectives | Customers/business, developers and testers |
| Relationship | Given/When/Then is commonly associated with BDD | ATDD may use Given/When/Then to express acceptance tests |

**Exam Trap:** Given/When/Then is a scenario-oriented format associated with BDD. It is not exclusive to ATDD.

## 6.3 ATDD vs Traditional Test-After Development

| Parameter | ATDD | Traditional Test-After Approach |
|---|---|---|
| Test design | Before implementation | Generally after implementation |
| Approach | Test-first | Test-after |
| Collaboration | Tests created collaboratively | Test cases may be designed later by testers |
| Main objective | Shared understanding of expected behaviour | Verify implemented functionality |
| Requirements | Acceptance tests can become executable requirements | Requirements are generally verified through subsequently designed tests |

## 6.4 Positive vs Negative Testing in ATDD

| Positive Testing | Negative Testing |
|---|---|
| Tests expected behaviour | Tests invalid or exceptional behaviour |
| Uses valid inputs | Uses invalid inputs or conditions |
| Confirms normal operation | Checks error handling and robustness |
| Typically performed first in the described ATDD sequence | Performed after positive test cases |

---

# 7. Important Exam Traps

| Statement | Correct Answer |
|---|---|
| A user story represents a feature valuable to a user or purchaser. | TRUE |
| User stories have three critical aspects called the 3 C's. | TRUE |
| Card represents the medium describing a user story. | TRUE |
| Conversation explains how the software will be used. | TRUE |
| Confirmation represents acceptance criteria. | TRUE |
| User stories are commonly written using As a/I want/So that. | TRUE |
| User stories should only be written by developers. | FALSE |
| Collaborative authorship can use brainstorming and mind mapping. | TRUE |
| Collaboration considers business, development and testing perspectives. | TRUE |
| INVEST stands for Independent, Negotiable, Valuable, Estimable, Small and Testable. | TRUE |
| A good user story should be rigid and non-negotiable. | FALSE |
| A good user story should provide value. | TRUE |
| A good user story should be testable. | TRUE |
| Acceptance criteria define conditions for accepting implementation. | TRUE |
| Acceptance criteria can serve as test conditions. | TRUE |
| Acceptance criteria are usually a result of conversation. | TRUE |
| Acceptance criteria help define the scope of a user story. | TRUE |
| Acceptance criteria should cover only positive scenarios. | FALSE |
| Given/When/Then is a scenario-oriented format. | TRUE |
| Rule-oriented acceptance criteria can use bullet lists or tables. | TRUE |
| Custom acceptance criteria formats are prohibited. | FALSE |
| ATDD is a test-first approach. | TRUE |
| ATDD test cases are created after implementation. | FALSE |
| ATDD test cases are based on acceptance criteria. | TRUE |
| ATDD test cases may be executed manually or automatically. | TRUE |
| ATDD involves different perspectives, including customers, developers and testers. | TRUE |
| ATDD starts with a specification workshop. | TRUE |
| Positive test cases typically precede negative test cases in the described ATDD sequence. | TRUE |
| ATDD covers non-functional quality characteristics as well. | TRUE |
| Acceptance tests can become executable requirements. | TRUE |
| ATDD requires all acceptance tests to be automated. | FALSE |
| ATDD test cases should cover all characteristics of the user story. | TRUE |
| ATDD test cases should go beyond the scope of the user story. | FALSE |

---

# 8. Practice MCQs

These are original practice questions based on the uploaded study material. They are not verbatim official ISTQB questions.

## A. Conceptual Questions

### Q1. What does a user story represent?

A. A technical design document.

B. A feature valuable to a user or purchaser.

C. A list of defects.

D. A complete source code specification.

### Q2. Which of the following correctly represents the 3 C's of user stories?

A. Card, Code, Confirmation.

B. Conversation, Coverage, Confirmation.

C. Card, Conversation, Confirmation.

D. Card, Criteria, Coverage.

### Q3. What does the Card aspect of a user story represent?

A. The acceptance test execution result.

B. The medium describing the user story.

C. The conversation between developers.

D. The implementation code.

### Q4. Which aspect explains how the software will be used?

A. Card.

B. Conversation.

C. Confirmation.

D. Completion.

### Q5. Which of the following is represented by Confirmation?

A. Acceptance criteria.

B. Source code.

C. Technical architecture.

D. Defect reports.

### Q6. Which perspectives are considered during collaborative authorship of user stories?

A. Business, development and testing.

B. Only developers and testers.

C. Only business representatives.

D. Only project managers.

### Q7. What does the N in INVEST represent?

A. Necessary.

B. Negotiable.

C. Non-functional.

D. Non-repeatable.

### Q8. Which INVEST characteristic ensures that a user story provides benefit to users or stakeholders?

A. Independent.

B. Estimable.

C. Valuable.

D. Small.

### Q9. What are acceptance criteria?

A. Conditions that the implementation must meet to be accepted by stakeholders.

B. Conditions used only for unit testing.

C. A list of developer tasks.

D. A list of production incidents.

### Q10. Which of the following is a scenario-oriented acceptance criteria format?

A. Input-output mapping.

B. Bullet-point checklist.

C. Given/When/Then.

D. Defect classification.

### Q11. Which of the following is an example of a rule-oriented acceptance criteria format?

A. Given/When/Then.

B. Bullet-point verification list.

C. Exploratory testing charter.

D. Test session debriefing.

### Q12. What is the primary characteristic of ATDD?

A. Tests are created after implementation.

B. Tests are created before implementing the user story.

C. Only developers write test cases.

D. Only performance tests are created.

### Q13. What is the first step in the ATDD process described in the study material?

A. Test execution.

B. Code implementation.

C. Specification workshop.

D. Production deployment.

### Q14. Which of the following is true about ATDD test cases?

A. They can only be automated.

B. They can only be executed manually.

C. They may be executed manually or automatically.

D. They must be executed only after production deployment.

### Q15. What do acceptance tests become in ATDD?

A. Technical design documents.

B. Executable requirements.

C. Production logs.

D. Defect reports.

## B. Scenario-Based Questions

### Q16.

During an Agile discussion, a tester, developer and business representative collaboratively discuss a new feature. The team uses brainstorming to establish a shared understanding of what needs to be delivered.

Which concept is being demonstrated?

A. Error Guessing.

B. Collaborative User Story Writing.

C. Checklist-Based Testing.

D. Exploratory Testing.

### Q17.

A user story is written as:

"As a customer, I want to view my order history so that I can track my previous purchases."

Which part represents the business value?

A. Customer.

B. View my order history.

C. Track my previous purchases.

D. Order history page.

### Q18.

A development team receives a user story that depends heavily on another unfinished story. The team identifies that the stories should be split or reorganized to reduce dependencies.

Which INVEST characteristic is relevant?

A. Valuable.

B. Independent.

C. Testable.

D. Estimable.

### Q19.

A business representative cannot explain how the team would verify whether a user story has been implemented correctly.

What might this indicate?

A. The story is automatically invalid.

B. The story may not be clear or valuable enough, or the stakeholder may need help with testing.

C. The story must be automated.

D. The story must be moved to production.

### Q20.

During a specification workshop, developers and testers identify ambiguous requirements and incomplete acceptance criteria. They discuss and resolve these issues before creating test cases.

Which ATDD activity is being performed?

A. Test execution.

B. Specification workshop.

C. Production validation.

D. Regression testing.

### Q21.

A team writes the following acceptance criterion:

```gherkin
Given the customer has valid credentials
When the customer submits the login form
Then the customer should be redirected to the dashboard
```

Which format is being used?

A. Rule-oriented.

B. Scenario-oriented.

C. Checklist-based.

D. Error guessing.

### Q22.

A team defines password validation using a table containing input conditions and expected outputs.

Which acceptance criteria format is being used?

A. Scenario-oriented.

B. Rule-oriented.

C. Exploratory.

D. Session-based.

### Q23.

A team creates acceptance test cases for a feature before the developers start implementing it. The tests are created collaboratively by business representatives, developers and testers.

Which approach is being used?

A. ATDD.

B. Regression Testing.

C. Error Guessing.

D. Checklist-Based Testing.

### Q24.

During ATDD, the team first tests successful payment processing. After that, it tests insufficient balance, invalid card details and payment gateway failures.

What is the team doing?

A. Only positive testing.

B. Positive testing followed by negative testing.

C. Only non-functional testing.

D. Exploratory testing without objectives.

### Q25.

A team creates acceptance tests for a user story in a format supported by its automation framework. Developers write supporting automation code while implementing the feature.

What is a possible result?

A. Acceptance tests become executable requirements.

B. User stories become source code.

C. Acceptance criteria are no longer required.

D. Manual testing becomes prohibited.

### Q26.

A tester creates acceptance tests covering successful login, invalid password and account lockout. However, the tester also adds a test for monthly financial reporting, which is unrelated to the login story.

What is incorrect?

A. The test cases do not cover positive scenarios.

B. The test cases go beyond the characteristics and scope of the user story.

C. Acceptance tests cannot cover negative scenarios.

D. ATDD does not use test cases.

### Q27.

A team has completed positive acceptance tests. What should it typically do next according to the described ATDD approach?

A. Skip all remaining testing.

B. Perform negative testing.

C. Deploy directly to production.

D. Stop documenting requirements.

### Q28.

A team wants to ensure that acceptance criteria are understood by business representatives, developers and testers.

Which activity most directly supports this?

A. Reaching consensus among stakeholders.

B. Writing implementation code.

C. Executing performance tests.

D. Creating defect reports.

### Q29.

A user story is extremely large and cannot be completed within a reasonable development period. Which INVEST characteristic is most relevant?

A. Small.

B. Negotiable.

C. Valuable.

D. Independent.

### Q30.

A team creates acceptance criteria using a custom tabular format rather than Given/When/Then. The criteria are clear, complete and unambiguous.

Is this acceptable?

A. No, only Given/When/Then is allowed.

B. No, only bullet points are allowed.

C. Yes, custom formats are acceptable if criteria are well-defined and unambiguous.

D. Yes, but only for non-functional testing.

---

# 9. Answer Key with Explanations

| Question | Answer | Explanation |
|---|---|---|
| Q1 | B | A user story represents a feature valuable to a user or purchaser. |
| Q2 | C | The 3 C's are Card, Conversation and Confirmation. |
| Q3 | B | Card is the medium used to describe a user story. |
| Q4 | B | Conversation explains how the software will be used. |
| Q5 | A | Confirmation represents the acceptance criteria. |
| Q6 | A | Collaborative authorship considers business, development and testing perspectives. |
| Q7 | B | N stands for Negotiable. |
| Q8 | C | Valuable means the story should provide value to users or stakeholders. |
| Q9 | A | Acceptance criteria define the conditions the implementation must satisfy. |
| Q10 | C | Given/When/Then is a scenario-oriented format. |
| Q11 | B | Bullet-point verification lists are rule-oriented. |
| Q12 | B | ATDD creates acceptance tests before implementation. |
| Q13 | C | The process starts with a specification workshop. |
| Q14 | C | ATDD tests may be executed manually or automatically. |
| Q15 | B | Acceptance tests can become executable requirements. |
| Q16 | B | Multiple perspectives collaborate to establish a shared understanding. |
| Q17 | C | Tracking previous purchases is the business value. |
| Q18 | B | Independent stories should have minimal dependencies. |
| Q19 | B | The story may lack clarity or value, or the stakeholder may need testing assistance. |
| Q20 | B | The specification workshop identifies and resolves ambiguity and incompleteness. |
| Q21 | B | Given/When/Then is scenario-oriented. |
| Q22 | B | Input-output tables are rule-oriented. |
| Q23 | A | ATDD is a test-first approach with collaborative test creation. |
| Q24 | B | Positive tests are followed by negative tests in the described sequence. |
| Q25 | A | Acceptance tests can become executable requirements. |
| Q26 | B | Test cases should cover the user story without going beyond its scope. |
| Q27 | B | Negative testing follows positive testing in the described approach. |
| Q28 | A | Consensus among stakeholders establishes shared understanding. |
| Q29 | A | Small means the story should be manageable within an appropriate development period. |
| Q30 | C | A custom format is acceptable if the criteria are well-defined and unambiguous. |

---

# 10. Quick Revision Sheet

| Topic | Remember |
|---|---|
| User Story | Feature valuable to a user or purchaser |
| User Story Format | As a [role], I want [goal], so that [business value] |
| 3 C's | Card, Conversation, Confirmation |
| Card | Medium describing the story |
| Conversation | Explains how the software will be used |
| Confirmation | Acceptance criteria |
| Collaboration | Business, development and testing perspectives |
| Collaboration Techniques | Brainstorming and mind mapping |
| INVEST | Independent, Negotiable, Valuable, Estimable, Small, Testable |
| Acceptance Criteria | Conditions required for stakeholder acceptance |
| Acceptance Criteria Uses | Scope, consensus, positive/negative scenarios, acceptance testing, planning and estimation |
| Scenario-Oriented | Given/When/Then |
| Rule-Oriented | Bullet lists and input-output tables |
| ATDD | Test-first approach |
| ATDD Participants | Customers/business, developers and testers |
| ATDD First Step | Specification workshop |
| ATDD Test Cases | Based on acceptance criteria |
| ATDD Execution | Manual or automated |
| ATDD Test Sequence | Positive, negative and non-functional testing |
| Executable Requirements | Acceptance tests can become executable requirements |

---

# 11. Self-Assessment Checklist

- [ ] I understand what a user story represents.
- [ ] I can write a user story using the standard format.
- [ ] I understand all three C's of user stories.
- [ ] I understand collaborative authorship.
- [ ] I can explain the business, development and testing perspectives.
- [ ] I remember all six INVEST characteristics.
- [ ] I understand acceptance criteria and their purpose.
- [ ] I can distinguish scenario-oriented and rule-oriented formats.
- [ ] I can write Given/When/Then acceptance criteria.
- [ ] I understand ATDD as a test-first approach.
- [ ] I know the purpose of a specification workshop.
- [ ] I understand how acceptance test cases are created.
- [ ] I know the difference between positive and negative testing.
- [ ] I understand the role of non-functional testing in ATDD.
- [ ] I understand how acceptance tests can become executable requirements.
- [ ] I can solve scenario-based questions involving user stories, acceptance criteria and ATDD.

## Final Exam Memory Points

1. A user story represents a feature valuable to a user or purchaser.
2. The 3 C's are Card, Conversation and Confirmation.
3. Card is the medium describing the story.
4. Conversation explains how the software will be used.
5. Confirmation represents acceptance criteria.
6. Collaborative user story writing involves business, development and testing perspectives.
7. Brainstorming and mind mapping can support collaboration.
8. INVEST stands for Independent, Negotiable, Valuable, Estimable, Small and Testable.
9. Acceptance criteria define the conditions an implementation must meet for stakeholder acceptance.
10. Acceptance criteria help define scope, reach consensus and describe positive and negative scenarios.
11. Given/When/Then is a scenario-oriented acceptance criteria format associated with BDD.
12. Bullet-point lists and input-output tables are examples of rule-oriented formats.
13. ATDD is a test-first approach.
14. ATDD acceptance tests are created before implementation.
15. ATDD starts with a specification workshop.
16. ATDD test cases are based on acceptance criteria.
17. ATDD test cases may be executed manually or automatically.
18. Positive test cases typically precede negative test cases in the described approach.
19. Non-functional quality characteristics such as performance efficiency and usability should also be covered.
20. Acceptance tests can become executable requirements.
