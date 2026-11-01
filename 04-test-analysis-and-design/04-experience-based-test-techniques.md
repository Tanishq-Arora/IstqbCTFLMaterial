
# 4.4 Experience-Based Test Techniques

## 1. Introduction to Experience-Based Test Techniques

### 1.1 What are Experience-Based Test Techniques?

**Experience-based test techniques** use the tester's skills, intuition and experience of similar applications, technologies and systems to identify test conditions and design test cases.

These techniques rely on the tester's knowledge of:
- Common defects and failures.
- How applications have behaved in the past.
- Mistakes developers commonly make.
- Similar applications and technologies.
- Areas where users are likely to face problems.

### Key Characteristics

1. They use the tester's skill, intuition and experience.
2. They help identify special tests that may not be easily captured by formal test techniques.
3. They are useful as a complement to formal test techniques.
4. They are particularly useful when specifications are poorly defined or inadequate.
5. They can be valuable under significant time pressure.
6. They may be the only practical option when the testing team lacks formal training in testing techniques.

### When are Experience-Based Techniques Useful?

| Situation | Why Useful? |
|---|---|
| Poorly defined specifications | Testers can use their understanding and experience to identify potential problems. |
| Time pressure | Testers can focus on areas where defects are more likely. |
| Inadequate documentation | Previous experience can help identify relevant test conditions. |
| Limited formal testing knowledge | Experience can provide practical testing guidance. |
| Complementing formal techniques | They can identify additional tests that formal techniques may not reveal. |

**Important:** Experience-based techniques do not replace formal techniques. They are often used alongside them to improve test coverage and defect detection.

### Example

A tester has previously worked on multiple e-commerce applications.

Based on experience, the tester decides to investigate:
- Applying multiple discount coupons.
- Refreshing the payment page after payment.
- Clicking the Pay button multiple times.
- Using an expired coupon.
- Changing the cart quantity during checkout.
- Navigating backward after payment.

These tests may reveal defects that were not explicitly identified through formal test design.

---

# 2. Error Guessing

## 2.1 What is Error Guessing?

**Error guessing** is a test technique in which test cases are designed based on the tester's knowledge of defects, errors and failures that commonly occur.

The tester uses experience and intuition to anticipate where defects might exist and designs tests to expose them.

### Key Characteristics

1. Requires knowledge of defects and experience with the application.
2. Identifies possible defects and designs tests that target them.
3. Can use historical defect and failure data.
4. Considers mistakes developers commonly make.
5. Can use failures observed in other applications.
6. Can be performed systematically using a technique called a **fault attack**.

## 2.2 Fault Attack

A **fault attack** is a systematic approach to error guessing.

The tester creates or uses a list of possible defects and designs tests to expose them.

The defect and failure list can be built using:

- Tester experience.
- Typical defect and failure data.
- Historical application failures.
- Knowledge of common developer mistakes.
- Defects found in similar applications.

### Example: Login Functionality

A tester knows that login functionality commonly contains defects.

Possible error guesses:

| Possible Defect | Test Idea |
|---|---|
| Empty username accepted | Submit login without username. |
| Empty password accepted | Submit login without password. |
| Case sensitivity issue | Enter username using different letter cases. |
| Incorrect password handling | Enter an incorrect password. |
| Account lockout failure | Enter incorrect passwords repeatedly. |
| Password field exposes text | Check password masking. |
| SQL injection vulnerability | Enter SQL-like input in login fields. |
| Session handling issue | Log out and try accessing a protected page using the previous session. |

These tests are based on likely failure areas and tester experience.

## 2.3 What is Error Guessing Based On?

According to the study material, error guessing is based on:

### 1. How the Application Worked in the Past

Historical application behaviour can help identify recurring problems.

Example:
- Previous releases had payment failures during peak traffic.
- The tester focuses on payment processing under high load.

### 2. Mistakes Developers Tend to Make

Testers use knowledge of common programming mistakes.

Examples:
- Incorrect comparison operators.
- Null pointer exceptions.
- Incorrect boundary conditions.
- Incorrect date calculations.
- Missing input validation.

### 3. Failures That Have Occurred in Other Applications

Defects observed in similar applications can provide ideas for testing the current application.

Example:

A tester knows that e-commerce applications sometimes calculate discounts incorrectly when multiple coupons are applied.

The tester specifically investigates that scenario.

## 2.4 Practical SDET Example

Consider a REST API:

`POST /api/orders`

A tester uses error guessing to identify possible defects.

| Error Guess | Test Scenario |
|---|---|
| Missing mandatory fields | Send request without orderId. |
| Invalid data types | Send quantity as a string instead of an integer. |
| Null values | Send customerId as null. |
| Negative values | Send quantity as -5. |
| Duplicate requests | Submit the same order request twice. |
| Invalid authentication | Send request without an authorization token. |
| Expired token | Send request with an expired JWT. |
| Large payload | Submit an unusually large request body. |
| Invalid content type | Send an unsupported Content-Type header. |

**Remember:** These test ideas are generated from experience and knowledge of common defects rather than solely from a formal specification.

---

# 3. Exploratory Testing

## 3.1 What is Exploratory Testing?

**Exploratory testing** is a test technique in which tests are simultaneously designed, executed and evaluated while the tester learns about the test object.

It combines:
- Learning
- Test design
- Test execution
- Evaluation

Unlike predefined test cases, exploratory testing allows the tester to adapt the next test based on discoveries made during the current test.

### Key Characteristics

1. Tests are designed, executed and evaluated simultaneously.
2. The tester learns about the test object during testing.
3. It helps explore the application more deeply.
4. It helps identify untested areas.
5. It can reveal unexpected defects.
6. It is useful when specifications are inadequate or time pressure is significant.

## 3.2 How Exploratory Testing Works

Consider testing an online shopping application.

The tester starts by exploring the checkout functionality.

During testing:

1. The tester adds an item to the cart.
2. The tester changes the quantity.
3. The tester applies a discount coupon.
4. The tester observes an unexpected discount calculation.
5. The tester investigates whether the issue occurs with multiple products.
6. The tester discovers another issue when the cart is refreshed.

The next test is influenced by what the tester discovers during the previous test.

This is the core idea of exploratory testing.

### Traditional Testing vs Exploratory Testing

| Parameter | Traditional Predefined Testing | Exploratory Testing |
|---|---|---|
| Test design | Designed before execution | Designed during execution |
| Execution | Follows predefined test cases | Adapts based on discoveries |
| Learning | May happen before execution | Happens continuously |
| Flexibility | Generally lower | Higher |
| Documentation | Detailed test cases | Test charters and session notes may be used |
| Test direction | Predetermined | Changes based on observations |

**Exam Point:** In exploratory testing, test design, execution and evaluation happen simultaneously.

## 3.3 Session-Based Exploratory Testing

Exploratory testing is sometimes conducted using **session-based testing** to provide structure.

In a session-based approach:

1. Testing is conducted within a defined time-box.
2. The tester uses a test charter containing test objectives.
3. The tester explores the application based on the charter.
4. Coverage items are identified and exercised.
5. The tester documents steps followed and discoveries made.
6. The session is usually followed by a debriefing.

### Important Terminology

#### A. Test Charter

A **test charter** contains the objectives and scope that guide an exploratory testing session.

It provides direction without prescribing every individual test step.

Example:

```text
Test Charter:

Explore the payment functionality of the
e-commerce application.

Focus on:
- Multiple payment attempts.
- Payment cancellation.
- Network interruption.
- Duplicate payment requests.
- Payment status updates.
```

#### B. Time-Box

A **time-box** is a defined period within which the exploratory testing session is conducted.

Example:

A tester is given 60 minutes to explore the payment functionality.

#### C. Test Session Sheet

A test session sheet is used to document:
- Steps followed.
- Areas explored.
- Coverage items exercised.
- Defects discovered.
- Observations and findings.

#### D. Debriefing

A **debriefing** is a discussion between the tester and relevant stakeholders after the test session.

It helps communicate:
- What was tested.
- What was discovered.
- Which defects were found.
- What risks remain.
- Whether additional testing is required.

## 3.4 Test Objectives as High-Level Test Conditions

In exploratory testing, test objectives may be treated as high-level test conditions.

Example:

Test objective: Explore the login functionality.

High-level test conditions:
- Valid login.
- Invalid login.
- Account lockout.
- Password reset.
- Session management.

The tester explores these areas and creates further tests based on discoveries.

## 3.5 Coverage in Exploratory Testing

Coverage items are identified and exercised during the test session.

The tester may use test session sheets to document:
- What was covered.
- What was not covered.
- What was discovered.
- Which areas need further testing.

## 3.6 When is Exploratory Testing Useful?

Exploratory testing is particularly useful when:

1. There are few or inadequate specifications.
2. There is significant time pressure.
3. The tester needs to learn more about the application.
4. The tester wants to investigate areas not covered by existing test cases.
5. It is used to complement formal test techniques.

### Skills Required for Effective Exploratory Testing

Exploratory testing becomes more effective when the tester has:

- Experience.
- Domain knowledge.
- Analytical skills.
- Curiosity.
- Creativity.

### Practical SDET Example

Suppose a mobile banking application has a new fund-transfer feature.

The tester does not have detailed test cases.

They start exploring:

1. Transfer money to a valid beneficiary.
2. Transfer money with insufficient balance.
3. Minimize the application during transfer.
4. Turn off the internet after clicking Transfer.
5. Press the Transfer button repeatedly.
6. Check transaction status after reopening the application.
7. Verify whether the account balance is updated correctly.

A failure discovered during one test may lead to further exploratory tests.

**Exam Takeaway:** Exploratory testing is not random testing. It is guided by learning, objectives, observations and tester expertise.

---

# 4. Checklist-Based Testing

## 4.1 What is Checklist-Based Testing?

**Checklist-based testing** is a test technique in which the tester designs, implements and executes tests to cover test conditions from a checklist.

The checklist provides a set of items that guide testing.

Checklists can be created based on:

- Tester experience.
- Knowledge of what is important to users.
- Understanding of why and how software fails.
- Historical defects and failures.
- Requirements and quality characteristics.

## 4.2 Example: Login Checklist

Consider a login page.

A tester prepares the following checklist:

| Checklist Item | Expected Verification |
|---|---|
| Is the username field mandatory? | Empty username should be handled correctly. |
| Is the password field mandatory? | Empty password should be handled correctly. |
| Is the password masked? | Password should not be displayed in plain text. |
| Is invalid login handled correctly? | Appropriate error message should appear. |
| Is the Forgot Password link working? | User should be able to initiate password recovery. |
| Is account lockout implemented? | Repeated invalid attempts should be handled according to requirements. |
| Is the login page usable on mobile? | Layout should work on supported screen sizes. |

The tester uses the checklist to guide test design and execution.

## 4.3 Characteristics of a Good Checklist

### 1. Items Should Be Independently Checkable

Each checklist item should be possible to verify separately and directly.

Example:

Good:
- Is the password masked?
- Is the username mandatory?

Bad:
- Is the login page working properly?

The bad example is too general and difficult to evaluate consistently.

### 2. Items Are Often Written as Questions

Checklist items are frequently phrased as questions.

Examples:
- Is the error message displayed correctly?
- Is the mandatory field validation working?
- Is the application responsive on supported devices?

### 3. Avoid Overly General Items

Checklist items should be specific enough to guide testing.

### 4. Avoid Items That Can Be Checked Automatically

According to the study material, checklists should not contain items that can be checked automatically.

They should also avoid:
- Items better suited as entry or exit criteria.
- Items that are too general.

### 5. Support Different Test Types

Checklists can be created for:
- Functional testing.
- Non-functional testing.

They may also cover requirements, graphical user interface properties and quality characteristics.

## 4.4 Maintaining Checklists

Checklists must be regularly reviewed and updated.

Why?

1. Developers may learn to avoid previously common mistakes.
2. Some checklist items may become less effective over time.
3. New high-severity defects may be discovered.
4. New entries may be needed based on defect analysis.

### Example

An application repeatedly experiences defects related to session expiration.

The testing team adds the following checklist item:

"Does the application handle an expired session correctly?"

This helps ensure the newly discovered risk is considered in future testing.

## 4.5 Why Should a Checklist Not Become Too Long?

A checklist should be useful, focused and manageable.

If it becomes excessively long:
- It may become difficult to maintain.
- Testers may overlook important items.
- Repetitive or low-value checks may reduce its usefulness.

Therefore, checklist items should be reviewed and unnecessary items should be removed.

## 4.6 Checklist-Based Testing Without Detailed Test Cases

In the absence of detailed test cases, checklist-based testing provides:

- Guidelines for testing.
- A degree of consistency.
- A common reference for testers.

However, when checklists are high-level, some variation in actual testing is likely.

This can result in:

- Potentially greater coverage.
- Less repeatability.

### Why?

Different testers may interpret and explore a high-level checklist item differently.

Example:

Checklist item: Verify payment failure handling.

Tester A may test insufficient balance.

Tester B may test network interruption.

Tester C may test a bank server timeout.

The same checklist item can lead to different test execution and potentially broader coverage.

---

# 5. Comparison of Experience-Based Test Techniques

This comparison is important for scenario-based questions.

| Parameter | Error Guessing | Exploratory Testing | Checklist-Based Testing |
|---|---|---|---|
| Main basis | Knowledge of common defects and failures | Learning and exploration | Predefined checklist |
| Test design | Based on experience and intuition | During test execution | Guided by checklist items |
| Main focus | Anticipating defects | Exploring the test object | Covering listed test conditions |
| Documentation | Defect lists and test ideas may be used | Test charter and session sheet | Checklist |
| Structure | Can be systematic through fault attack | Can use time-boxed sessions | Guided by checklist |
| Key benefit | Finds likely defects | Finds unexpected issues and untested areas | Provides guidelines and consistency |
| Key limitation | Depends on tester experience | Effectiveness depends on tester skills | High-level checklists can reduce repeatability |

## 5.1 How to Identify the Technique in an Exam Scenario

| Scenario Clue | Technique |
|---|---|
| Tester uses knowledge of common programming mistakes | Error Guessing |
| Tester creates tests based on historical failures | Error Guessing |
| Tester systematically creates a list of possible defects | Error Guessing / Fault Attack |
| Tester designs and executes tests simultaneously | Exploratory Testing |
| Tester learns about the application while testing | Exploratory Testing |
| Tester uses a time-boxed session and test charter | Exploratory Testing |
| Tester conducts a debriefing after the session | Exploratory Testing |
| Tester uses a predefined list of questions | Checklist-Based Testing |
| Checklist is updated using defect analysis | Checklist-Based Testing |
| Different testers interpret high-level checklist items differently | Checklist-Based Testing |

---

# 6. Important Exam Traps

| Statement | Correct Answer |
|---|---|
| Experience-based testing uses tester skills, intuition and experience. | TRUE |
| Experience-based testing can complement formal test techniques. | TRUE |
| Experience-based techniques are useful only when formal techniques are unavailable. | FALSE |
| Error guessing uses knowledge of common defects and failures. | TRUE |
| Fault attack is a systematic approach associated with error guessing. | TRUE |
| Error guessing can use historical defect data. | TRUE |
| Exploratory testing involves simultaneous test design, execution and evaluation. | TRUE |
| Exploratory testing is always random testing. | FALSE |
| Exploratory testing can use a test charter. | TRUE |
| A test charter contains test objectives. | TRUE |
| Session-based exploratory testing uses a defined time-box. | TRUE |
| A debriefing may follow an exploratory test session. | TRUE |
| Exploratory testing is useful when specifications are inadequate. | TRUE |
| Checklist-based testing uses a checklist to guide test conditions. | TRUE |
| Checklist items should be independently checkable. | TRUE |
| Checklists should contain very general items. | FALSE |
| Checklists should be updated based on defect analysis. | TRUE |
| Checklists should be allowed to grow indefinitely. | FALSE |
| High-level checklists can result in greater coverage but less repeatability. | TRUE |
| Checklist-based testing supports only functional testing. | FALSE |

---

# 7. Practice MCQs

These are original practice questions based on the uploaded study material. They are not verbatim official ISTQB questions.

## A. Conceptual Questions

### Q1. Which of the following best describes experience-based test techniques?

A. Techniques based entirely on formal specifications.

B. Techniques based on tester skills, intuition and experience.

C. Techniques that require complete automation.

D. Techniques that only examine source code.

### Q2. Which technique uses knowledge of common defects and failures to design tests?

A. Statement Testing

B. Boundary Value Analysis

C. Error Guessing

D. Equivalence Partitioning

### Q3. What is a fault attack?

A. A technique used to measure statement coverage.

B. A systematic approach to error guessing.

C. A method of measuring performance.

D. A technique for reviewing requirements.

### Q4. Which of the following is a basis for error guessing?

A. Historical application failures.

B. Common developer mistakes.

C. Failures in similar applications.

D. All of the above.

### Q5. Which statement best describes exploratory testing?

A. Tests are designed before execution and never changed.

B. Tests are simultaneously designed, executed and evaluated.

C. Only predefined checklists are executed.

D. Only automated test cases are executed.

### Q6. What is the purpose of a test charter in exploratory testing?

A. To define the complete source code.

B. To provide objectives that guide the testing session.

C. To record only the final test results.

D. To define the exit criteria of the project.

### Q7. What is a time-box in session-based exploratory testing?

A. A fixed period allocated to a testing session.

B. A list of all defects.

C. A document containing requirements.

D. A tool used to automate testing.

### Q8. Which activity usually follows an exploratory testing session?

A. Code compilation.

B. Debriefing.

C. Deployment.

D. Unit testing.

### Q9. Which of the following is the primary basis of checklist-based testing?

A. Random inputs.

B. Source code structure.

C. A checklist of test conditions.

D. Mathematical models.

### Q10. Which of the following is a characteristic of a good checklist?

A. Items should be too general.

B. Items should be independently checkable.

C. Items should never be updated.

D. Items should contain only entry criteria.

## B. Scenario-Based Questions

### Q11.

A tester has worked on multiple banking applications. Based on previous experience, the tester knows that fund transfers sometimes fail when users click the Transfer button repeatedly.

The tester designs tests specifically to investigate this issue.

Which technique is being used?

A. Exploratory Testing

B. Error Guessing

C. Checklist-Based Testing

D. Statement Testing

### Q12.

A tester is assigned a new application with very limited documentation. They begin testing the application, learning its behaviour and designing new tests based on their observations.

Which technique is being used?

A. Equivalence Partitioning

B. Branch Testing

C. Exploratory Testing

D. Statement Testing

### Q13.

A tester is given 45 minutes to investigate the payment functionality. They receive a document describing the objectives of the session and explore the application accordingly.

Which two concepts are involved?

A. Fault attack and checklist

B. Time-box and test charter

C. Statement coverage and branch coverage

D. Boundary Value Analysis and equivalence partitioning

### Q14.

After an exploratory testing session, the tester meets with stakeholders to discuss the findings, defects and remaining risks.

What is this activity called?

A. Test execution

B. Test design

C. Debriefing

D. Fault attack

### Q15.

A tester prepares a list of common defects based on historical production incidents and uses it to design test cases.

Which technique is being used?

A. Error Guessing

B. Checklist-Based Testing

C. Exploratory Testing

D. Branch Testing

### Q16.

A testing team uses a checklist containing the following item:

"Is the application working correctly?"

Why is this checklist item problematic?

A. It is too specific.

B. It is too general and difficult to check independently.

C. It cannot be used in functional testing.

D. It is an example of branch coverage.

### Q17.

A team discovers a high-severity defect related to expired user sessions. The team adds a new item to its existing testing checklist.

What is the most appropriate reason for doing this?

A. Checklists should never change.

B. Checklists should be updated based on defect analysis.

C. Exploratory testing requires every checklist to be updated.

D. Statement coverage has decreased.

### Q18.

Two testers receive the same high-level checklist item: "Verify payment failure handling."

One tests insufficient balance, while the other tests network interruption.

What is a possible consequence of this approach?

A. Greater variation and potentially greater coverage, but less repeatability.

B. Identical test execution and guaranteed repeatability.

C. 100% statement coverage.

D. Elimination of all payment defects.

### Q19.

A tester explores a mobile application, discovers that the application crashes after network interruption and then designs additional tests around network recovery.

Which characteristic of exploratory testing does this demonstrate?

A. Test execution is completely predefined.

B. Test design adapts based on discoveries.

C. Only checklist items can be executed.

D. Tests must be automated.

### Q20.

A tester identifies possible defects based on how developers commonly make mistakes and on failures observed in similar applications.

Which technique is most appropriate?

A. Error Guessing

B. Exploratory Testing

C. Checklist-Based Testing

D. Branch Testing

---

# 8. Answer Key with Explanations

| Question | Answer | Explanation |
|---|---|---|
| Q1 | B | Experience-based techniques use tester skills, intuition and experience. |
| Q2 | C | Error guessing uses knowledge of common defects and failures. |
| Q3 | B | Fault attack is a systematic approach to error guessing. |
| Q4 | D | Error guessing can use historical failures, common mistakes and similar application failures. |
| Q5 | B | Exploratory testing combines test design, execution and evaluation. |
| Q6 | B | A test charter provides objectives that guide the exploratory session. |
| Q7 | A | A time-box defines the duration of the testing session. |
| Q8 | B | Exploratory sessions are usually followed by a debriefing. |
| Q9 | C | Checklist-based testing uses a checklist of test conditions. |
| Q10 | B | Checklist items should be independently and directly checkable. |
| Q11 | B | The tester uses knowledge of previous failures to anticipate a defect. |
| Q12 | C | The tester learns, designs and executes tests during exploration. |
| Q13 | B | A time-box defines the duration, while a charter defines the session objectives. |
| Q14 | C | Debriefing is the discussion following the exploratory testing session. |
| Q15 | A | Historical defect data is a basis for error guessing. |
| Q16 | B | The item is too general to be checked independently. |
| Q17 | B | Checklists should be updated using defect analysis and newly discovered risks. |
| Q18 | A | High-level checklists can lead to variation, potentially increasing coverage but reducing repeatability. |
| Q19 | B | Exploratory testing allows further test design based on discoveries. |
| Q20 | A | Error guessing uses knowledge of developer mistakes and failures in similar applications. |

---

# 9. Quick Revision Sheet

| Topic | Key Point |
|---|---|
| Experience-based testing | Uses tester skill, intuition and experience |
| Error guessing | Anticipates defects based on experience |
| Fault attack | Systematic approach to error guessing |
| Error guessing basis | Historical failures, common mistakes and similar applications |
| Exploratory testing | Test design, execution and evaluation happen simultaneously |
| Test charter | Defines objectives for exploratory testing |
| Time-box | Defines the duration of a session |
| Test session sheet | Documents steps, coverage and discoveries |
| Debriefing | Discussion after an exploratory session |
| Checklist-based testing | Uses a checklist to guide test conditions |
| Good checklist | Specific, independently checkable items |
| Checklist maintenance | Update based on defect analysis |
| High-level checklist | Potentially greater coverage but less repeatability |

---

# 10. Self-Assessment Checklist

- [ ] I understand experience-based test techniques.
- [ ] I can explain when experience-based techniques are useful.
- [ ] I understand error guessing.
- [ ] I can explain fault attack.
- [ ] I know the three main bases of error guessing.
- [ ] I understand exploratory testing.
- [ ] I know the meaning of simultaneous test design, execution and evaluation.
- [ ] I understand test charters and time-boxes.
- [ ] I understand test session sheets and debriefing.
- [ ] I understand checklist-based testing.
- [ ] I can identify characteristics of a good checklist.
- [ ] I understand why checklists need regular updates.
- [ ] I understand the coverage and repeatability trade-off of high-level checklists.
- [ ] I can distinguish all three experience-based techniques using scenarios.

## Final Exam Memory Points

1. Experience-based techniques use tester skills, intuition and experience.
2. Error guessing uses knowledge of common defects and failures.
3. Fault attack is a systematic approach to error guessing.
4. Error guessing can be based on historical failures, developer mistakes and failures in similar applications.
5. Exploratory testing involves simultaneous test design, execution and evaluation.
6. A test charter contains objectives that guide exploratory testing.
7. Session-based exploratory testing uses a defined time-box.
8. Exploratory testing sessions are usually followed by debriefing.
9. Checklist-based testing uses a checklist to cover test conditions.
10. Checklist items should be specific and independently checkable.
11. Checklists should be updated based on defect analysis.
12. High-level checklists can provide potentially greater coverage but less repeatability.
