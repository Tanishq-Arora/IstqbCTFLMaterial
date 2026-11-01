# 4.1 Test Techniques Overview
**ISTQB CTFL v4.0.1 — Chapter 4: Test Analysis and Design**

**Scope:** Overview of black-box, white-box and experience-based test techniques.

---

## Learning Objective

- **FL-4.1.1 (K2):** Explain the categories of test techniques.

---

# 1. What Are Test Techniques?

Test techniques are systematic approaches used by testers to identify what should be tested and how the tests should be designed.

They support two important testing activities:

### 1.1 Test Analysis — What to Test?

Test analysis involves identifying:

- Test conditions.
- Coverage items.
- Aspects of the test object that need to be tested.
- Requirements and behaviours that need verification.

### 1.2 Test Design — How to Test?

Test design involves:

- Deriving test cases.
- Identifying appropriate test data.
- Defining expected results.
- Determining how identified test conditions will be tested.

### Why Do We Need Test Techniques?

Test techniques help testers:

1. Develop a relatively small but sufficient set of test cases systematically.
2. Identify test conditions that need to be covered.
3. Identify coverage items.
4. Determine appropriate test data.
5. Improve test coverage and reduce unnecessary duplication.
6. Make testing systematic rather than relying entirely on intuition.

### Practical Example — Login Functionality

Suppose you are testing a login page.

Without a test technique, you might randomly test different usernames and passwords.

Using test techniques, you can systematically identify:

- Valid username and password.
- Invalid username.
- Invalid password.
- Empty username and password.
- Account locked after repeated failed attempts.
- Password length restrictions.
- Password case sensitivity.

This helps create a smaller, more meaningful set of test cases.

---

# 2. Classification of Test Techniques

ISTQB classifies test techniques into three major categories:

1. Black-box test techniques.
2. White-box test techniques.
3. Experience-based test techniques.

## 2.1 Overview

| Category | Also Known As | Main Focus |
|---|---|---|
| Black-box | Specification-based techniques | Specified behaviour |
| White-box | Structure-based techniques | Internal structure and processing |
| Experience-based | Experience-based techniques | Tester knowledge and experience |

### Easy Way to Remember

- **Black-box:** What should the system do?
- **White-box:** How does the system work internally?
- **Experience-based:** Where do I think defects might exist?

---

# 3. Black-Box Test Techniques

**Also known as: Specification-based techniques**

## 3.1 Definition

Black-box test techniques are based on analysing the specified behaviour of the test object without referring to its internal structure.

The tester focuses on:

- Inputs.
- Outputs.
- Functional requirements.
- Business rules.
- Expected behaviour.
- System specifications.

The tester does not need to know how the software is internally implemented.

## 3.2 Key Characteristics

1. Test cases are derived from requirements and specifications.
2. Test cases are independent of the software's internal implementation.
3. The same test cases can remain useful even if the implementation changes, provided the required behaviour remains unchanged.
4. These techniques help verify whether the system behaves as expected.

## 3.3 Techniques Under Black-Box Testing

The four techniques are:

1. Equivalence Partitioning.
2. Boundary Value Analysis.
3. State Transition Testing.
4. Decision Table Testing.

These techniques will be covered individually in the upcoming sections.

## 3.4 Practical Example — ATM Withdrawal

Consider an ATM withdrawal application.

Requirements:

- Minimum withdrawal: ₹500.
- Maximum withdrawal: ₹10,000.
- Withdrawal must be in multiples of ₹500.

A tester can derive test cases using these requirements without knowing the internal code.

| Test Input | Expected Result |
|---|---|
| ₹500 | Accepted |
| ₹1,000 | Accepted |
| ₹10,000 | Accepted |
| ₹400 | Rejected |
| ₹10,500 | Rejected |
| ₹750 | Rejected |

The tester is checking externally specified behaviour, not internal implementation.

## 3.5 When to Use Black-Box Techniques?

- Functional testing.
- Requirement-based testing.
- API testing based on API specifications.
- Acceptance testing.
- Business workflow validation.
- Testing when source code is unavailable.

**SDET Example:** You can use black-box techniques to derive API test cases from a Swagger/OpenAPI specification without examining the API's implementation.

---

# 4. White-Box Test Techniques

**Also known as: Structure-based techniques**

## 4.1 Definition

White-box test techniques are based on analysing the internal structure and processing of the test object.

Unlike black-box testing, the tester considers how the software is designed or implemented.

The focus is on internal elements such as:

- Source code.
- Statements.
- Branches.
- Conditions.
- Control flow.
- Internal processing paths.

## 4.2 Key Characteristics

1. Test cases are derived from the internal structure of the software.
2. Knowledge of the implementation or design is required.
3. Test cases depend on how the software is structured.
4. These techniques help measure structural coverage.
5. They can identify unexecuted statements or branches.

## 4.3 Techniques Under White-Box Testing

The two techniques are:

1. Statement Testing and Coverage.
2. Branch Testing and Coverage.

## 4.4 Practical Example — Statement Coverage

Consider the following Java code:

```java
public void checkAge(int age) {

    if (age >= 18) {
        System.out.println("Eligible");
    }

    System.out.println("Verification completed");
}
```

There are three executable statements:

1. `if (age >= 18)`
2. `System.out.println("Eligible")`
3. `System.out.println("Verification completed")`

Suppose we execute:

```java
checkAge(20);
```

All three statements are executed.

Therefore:

Statement Coverage = (Executed Statements / Total Executable Statements) × 100

Statement Coverage = (3 / 3) × 100 = 100%

Now consider:

```java
checkAge(15);
```

Only the condition and the final print statement are executed.

The statement inside the `if` block is not executed.

Statement Coverage = (2 / 3) × 100 = 66.67%

## 4.5 Practical Example — Branch Coverage

Using the same code:

```java
if (age >= 18) {
    System.out.println("Eligible");
}
```

There are two possible outcomes:

- TRUE: Age is 18 or above.
- FALSE: Age is below 18.

To achieve 100% branch coverage, both outcomes must be exercised.

| Test Case | Input | Branch Outcome |
|---|---:|---|
| TC01 | 20 | TRUE |
| TC02 | 15 | FALSE |

Branch Coverage = (Executed Branches / Total Branches) × 100

Branch Coverage = (2 / 2) × 100 = 100%

**Important:** Statement coverage and branch coverage are not the same.

A test suite can achieve 100% statement coverage without achieving 100% branch coverage.

We will explore this distinction in depth in the white-box testing section.

## 4.6 When to Use White-Box Techniques?

- Unit testing.
- Component testing.
- Code coverage analysis.
- Testing conditional logic.
- Testing complex algorithms.
- Identifying unexecuted code paths.

**SDET Example:** JaCoCo can measure Java statement and branch coverage during automated unit test execution.

---

# 5. Experience-Based Test Techniques

## 5.1 Definition

Experience-based test techniques use the knowledge, skills and experience of testers to design and implement test cases.

Unlike black-box and white-box techniques, these techniques rely heavily on the tester's ability to anticipate problems and identify potential defects.

## 5.2 Key Characteristics

1. Effectiveness depends heavily on the tester's skills and experience.
2. Testers use their knowledge of the application, technology and common defect patterns.
3. These techniques can detect defects that might be missed using black-box and white-box techniques.
4. They complement black-box and white-box testing rather than replacing them.

## 5.3 Techniques Under Experience-Based Testing

The three techniques are:

1. Error Guessing.
2. Exploratory Testing.
3. Checklist-Based Testing.

## 5.4 Error Guessing

**Definition:** Error guessing is a technique in which testers use their experience and knowledge of common errors to anticipate where defects might exist.

The tester predicts likely failure areas based on previous experience.

### Example — Login Page

An experienced tester might anticipate:

- Login with blank credentials.
- Login with extremely long input.
- SQL injection attempts.
- Special characters in usernames.
- Repeated login attempts.
- Password case sensitivity.
- Session handling after logout.

The tester uses knowledge of common defects to derive test cases.

**Key Point:** Error guessing depends on tester experience and intuition.

## 5.5 Exploratory Testing

**Definition:** Exploratory testing is an approach in which testers simultaneously learn about the test object, design tests and execute those tests.

Testing is not completely predefined in advance.

The tester explores the application, learns its behaviour and adjusts subsequent testing based on observations.

### Example — E-commerce Application

You are testing an e-commerce application.

During exploration:

1. You add a product to the cart.
2. You change its quantity.
3. You apply a coupon.
4. You remove the product.
5. You navigate back.
6. You observe whether the cart and price are updated correctly.

Based on what you discover, you decide what to test next.

**Key Point:** Learning, test design and test execution happen together.

## 5.6 Checklist-Based Testing

**Definition:** Checklist-based testing uses a predefined list of items or conditions that testers should verify.

The checklist is generally created using:

- Previous testing experience.
- Common defect patterns.
- Business requirements.
- Industry practices.
- Organizational standards.

### Example — API Testing Checklist

A tester may use the following checklist:

- [ ] Correct HTTP status code.
- [ ] Response time within the expected limit.
- [ ] Required fields present.
- [ ] Invalid input handled correctly.
- [ ] Authentication and authorization verified.
- [ ] Error messages are meaningful.
- [ ] Sensitive information is not exposed.

The tester follows the checklist while testing the API.

**Key Point:** Checklist-based testing provides systematic coverage of predefined checks, but its effectiveness depends on checklist quality.

---

# 6. Comparison of the Three Test Technique Categories

This is one of the most important comparison areas for the CTFL examination.

| Basis | Black-Box | White-Box | Experience-Based |
|---|---|---|---|
| Also called | Specification-based | Structure-based | Experience-based |
| Main focus | Expected behaviour | Internal structure | Tester knowledge and experience |
| Based on | Requirements and specifications | Design and source code | Skills and previous experience |
| Internal code knowledge | Not required | Required | Not necessarily required |
| Test cases derived from | External behaviour | Internal implementation | Experience and intuition |
| Main purpose | Verify specified behaviour | Verify structural coverage | Identify potential defects |
| Examples | EP, BVA, State Transition, Decision Table | Statement and Branch Testing | Error Guessing, Exploratory, Checklist-based |

## Easy Way to Remember

- **Black-box:** What should the system do?
- **White-box:** How does the system work internally?
- **Experience-based:** Where do I think defects might exist?

---

# 7. How These Techniques Complement Each Other

No single test technique is sufficient to identify every possible defect.

Different techniques focus on different aspects of the software.

Consider a banking application.

| Testing Category | Example |
|---|---|
| Black-box | Verify that a transfer of ₹5,000 debits and credits the correct accounts. |
| White-box | Verify that both TRUE and FALSE outcomes of the transfer validation logic are executed. |
| Experience-based | Try transferring money after session expiry or rapidly submitting the transfer button multiple times. |

Combining these approaches improves the likelihood of identifying different types of defects.

**Exam Point:** Experience-based techniques complement black-box and white-box techniques.

Do not assume that one category replaces the others.

---

# 8. Important Exam Traps

| Statement | Correct Understanding |
|---|---|
| Black-box testing requires knowledge of source code. | False |
| Black-box test cases depend on internal implementation. | False |
| Black-box testing is based on specified behaviour. | True |
| White-box testing examines internal structure. | True |
| White-box test cases are independent of implementation. | False |
| Experience-based testing depends on tester skills. | True |
| Exploratory testing is completely predefined. | False |
| Error guessing uses previous experience. | True |
| Checklist-based testing uses predefined checks. | True |
| Experience-based techniques replace black-box testing. | False |
| Test techniques help identify test data. | True |
| Test techniques support test analysis and test design. | True |

## Common Confusions

### 1. Black-Box vs White-Box

- Black-box focuses on specified behaviour.
- White-box focuses on internal structure.

### 2. Error Guessing vs Exploratory Testing

- Error guessing: Predict likely defects using experience.
- Exploratory testing: Learn, design and execute tests simultaneously.

### 3. Checklist-Based vs Exploratory Testing

- Checklist-based: Follow predefined checks.
- Exploratory: Adapt testing based on learning and observations.

### 4. Statement Coverage vs Branch Coverage

- Statement coverage: Were the executable statements executed?
- Branch coverage: Were the decision outcomes exercised?

---

# 9. Practice Questions — Test Techniques Overview

**20 original exam-oriented questions**

These are practice questions, not official ISTQB questions or verified past-paper questions.

## Q1. Purpose of Test Techniques

What is the primary purpose of test techniques?

A. To eliminate the need for test execution.

B. To support systematic test analysis and test design.

C. To guarantee that all defects are identified.

D. To replace the test process.

**Correct Answer: B**

**Explanation:** Test techniques support the identification of test conditions, coverage items, test data and test cases in a systematic manner.

---

## Q2. Black-Box Testing

A tester derives test cases using business requirements without examining the application's source code.

Which technique category is being used?

A. White-box

B. Experience-based

C. Black-box

D. Static analysis

**Correct Answer: C**

**Explanation:** Black-box testing is based on specified behaviour without reference to internal structure.

---

## Q3. Implementation Independence

A development team changes the internal implementation of a payment service from Java to Kotlin.

The expected API behaviour remains unchanged.

Which statement is MOST accurate?

A. All black-box test cases must be redesigned.

B. Existing black-box test cases may remain useful.

C. White-box testing is no longer possible.

D. All test cases must be discarded.

**Correct Answer: B**

**Explanation:** Black-box test cases are independent of internal implementation, provided the required behaviour remains unchanged.

---

## Q4. White-Box Testing

A tester examines source code and designs tests to execute all decision outcomes.

Which technique category is being used?

A. Black-box

B. White-box

C. Experience-based

D. Checklist-based

**Correct Answer: B**

**Explanation:** White-box techniques are based on the internal structure and processing of the test object.

---

## Q5. Experience-Based Testing

An experienced tester predicts that a shopping cart may fail when a user adds and removes the same product repeatedly.

Which technique is being applied?

A. Branch testing

B. Equivalence partitioning

C. Error guessing

D. Decision table testing

**Correct Answer: C**

**Explanation:** Error guessing uses the tester's experience to anticipate likely defects.

---

## Q6. Exploratory Testing

A tester starts testing a new mobile application without fully predefined test cases. While testing, the tester learns the application behaviour and designs additional tests.

Which technique is being used?

A. Exploratory testing

B. Statement testing

C. Decision table testing

D. Boundary value analysis

**Correct Answer: A**

**Explanation:** Exploratory testing combines learning, test design and test execution.

---

## Q7. Checklist-Based Testing

A QA team maintains a list of common checks for every API endpoint, including status codes, response structure and authentication.

Which technique is being used?

A. Error guessing

B. Checklist-based testing

C. State transition testing

D. Branch testing

**Correct Answer: B**

**Explanation:** Checklist-based testing uses predefined items to guide testing.

---

## Q8. Test Technique Classification

Which of the following is a black-box test technique?

A. Statement testing

B. Branch testing

C. Boundary value analysis

D. Error guessing

**Correct Answer: C**

**Explanation:** Boundary value analysis is a specification-based or black-box technique.

---

## Q9. Identifying White-Box Techniques

Which pair contains only white-box techniques?

A. Equivalence partitioning and boundary value analysis.

B. Statement testing and branch testing.

C. Error guessing and exploratory testing.

D. Decision table testing and state transition testing.

**Correct Answer: B**

**Explanation:** Statement testing and branch testing are structure-based techniques.

---

## Q10. Identifying Experience-Based Techniques

Which option contains only experience-based techniques?

A. Error guessing, exploratory testing and checklist-based testing.

B. Statement testing, branch testing and error guessing.

C. Equivalence partitioning, boundary value analysis and decision table testing.

D. State transition testing, statement testing and exploratory testing.

**Correct Answer: A**

**Explanation:** All three techniques rely on tester knowledge and experience.

---

## Q11. Requirement-Based Testing

A tester receives a requirement stating that an account can be locked after five consecutive unsuccessful login attempts.

The tester derives test cases without examining the source code.

Which category is MOST appropriate?

A. White-box

B. Black-box

C. Experience-based

D. Static analysis

**Correct Answer: B**

**Explanation:** The test cases are derived from the specified behaviour.

---

## Q12. Code Coverage

A tester wants to determine whether every executable statement in a program has been executed at least once.

Which technique should be used?

A. Branch testing

B. Statement testing

C. Decision table testing

D. Exploratory testing

**Correct Answer: B**

**Explanation:** Statement testing measures the execution of executable statements.

---

## Q13. Branch Coverage

A tester wants to verify both TRUE and FALSE outcomes of an IF condition.

Which technique is MOST appropriate?

A. Statement testing

B. Branch testing

C. Equivalence partitioning

D. Error guessing

**Correct Answer: B**

**Explanation:** Branch testing checks whether the decision outcomes have been exercised.

---

## Q14. Complementary Techniques

Why are experience-based techniques considered complementary to black-box and white-box techniques?

A. They eliminate the need for specifications.

B. They guarantee complete test coverage.

C. They can identify defects that other techniques may miss.

D. They require no tester involvement.

**Correct Answer: C**

**Explanation:** Experience-based techniques leverage human knowledge and intuition to identify additional potential defects.

---

## Q15. Test Analysis

A tester identifies that a password field must support passwords between 8 and 16 characters.

The tester identifies the valid and invalid input conditions.

Which activity is being performed?

A. Test execution

B. Test analysis

C. Test closure

D. Test monitoring

**Correct Answer: B**

**Explanation:** Test analysis identifies what needs to be tested, including test conditions and coverage items.

---

## Q16. Test Design

After identifying the password length conditions, the tester decides which specific values to use and derives test cases.

Which activity is being performed?

A. Test analysis

B. Test design

C. Test execution

D. Test closure

**Correct Answer: B**

**Explanation:** Test design determines how to test the identified conditions and derives test cases and test data.

---

## Q17. Choosing a Technique

A tester wants to test how an application behaves when it moves between logged-out, logged-in and locked states.

Which black-box technique is MOST suitable?

A. Statement testing

B. State transition testing

C. Error guessing

D. Branch testing

**Correct Answer: B**

**Explanation:** State transition testing examines how the system behaves when moving between states in response to events.

---

## Q18. Choosing a Technique

A tester needs to verify different combinations of business conditions and corresponding actions.

Which black-box technique is MOST suitable?

A. Decision table testing

B. Statement testing

C. Exploratory testing

D. Checklist-based testing

**Correct Answer: A**

**Explanation:** Decision table testing is useful when system behaviour depends on combinations of conditions.

---

## Q19. Choosing a Technique

A tester needs to identify defects around the minimum and maximum permitted values of an input field.

Which black-box technique is MOST suitable?

A. Error guessing

B. Boundary value analysis

C. Branch testing

D. Statement testing

**Correct Answer: B**

**Explanation:** Boundary value analysis focuses on values at and around the boundaries of equivalence partitions.

---

## Q20. Scenario — Multiple Techniques

A tester performs the following activities:

1. Derives test cases from API requirements.
2. Examines source code to identify unexecuted branches.
3. Uses previous experience to predict session-handling defects.

Which sequence correctly identifies the techniques?

A. Black-box, White-box, Experience-based.

B. White-box, Black-box, Experience-based.

C. Experience-based, White-box, Black-box.

D. Black-box, Experience-based, White-box.

**Correct Answer: A**

**Explanation:**

- Activity 1: Black-box — based on API requirements.
- Activity 2: White-box — based on internal code structure.
- Activity 3: Experience-based — based on tester experience.

---

# 10. Answer Key — Quick Revision

| Question | Answer | Concept |
|---|---|---|
| 1 | B | Purpose of test techniques |
| 2 | C | Black-box |
| 3 | B | Implementation independence |
| 4 | B | White-box |
| 5 | C | Error guessing |
| 6 | A | Exploratory testing |
| 7 | B | Checklist-based testing |
| 8 | C | Black-box techniques |
| 9 | B | White-box techniques |
| 10 | A | Experience-based techniques |
| 11 | B | Requirement-based testing |
| 12 | B | Statement testing |
| 13 | B | Branch testing |
| 14 | C | Complementary techniques |
| 15 | B | Test analysis |
| 16 | B | Test design |
| 17 | B | State transition testing |
| 18 | A | Decision table testing |
| 19 | B | Boundary value analysis |
| 20 | A | Technique classification |

---

# 11. One-Page Revision Sheet

## Three Categories

| Category | Meaning | Techniques |
|---|---|---|
| Black-box | Specification-based | Equivalence Partitioning, Boundary Value Analysis, State Transition, Decision Table |
| White-box | Structure-based | Statement Testing, Branch Testing |
| Experience-based | Tester knowledge and experience | Error Guessing, Exploratory Testing, Checklist-Based Testing |

## Remember These Definitions

- **Black-box:** Tests specified behaviour without considering internal structure.
- **White-box:** Tests internal structure and processing.
- **Experience-based:** Uses tester knowledge and experience to derive tests.
- **Error guessing:** Predicts likely defects.
- **Exploratory testing:** Learning, test design and execution happen together.
- **Checklist-based testing:** Uses a predefined list of checks.
- **Statement testing:** Measures executable statement coverage.
- **Branch testing:** Measures decision outcome coverage.

## Most Important Exam Statements

1. Test techniques support test analysis and test design.
2. Test analysis answers *what to test*.
3. Test design answers *how to test*.
4. Black-box test cases are independent of internal implementation.
5. White-box test cases depend on internal structure.
6. Experience-based techniques depend heavily on tester skills.
7. Experience-based techniques complement black-box and white-box techniques.
8. Test techniques help derive a relatively small but sufficient set of test cases.

---

# 12. Self-Assessment Checklist

Before moving to the next topic, make sure you can:

- [ ] Explain the purpose of test techniques.
- [ ] Differentiate test analysis and test design.
- [ ] Explain black-box testing with examples.
- [ ] Explain white-box testing with examples.
- [ ] Explain experience-based testing with examples.
- [ ] Classify all nine techniques mentioned in the slides.
- [ ] Differentiate error guessing, exploratory and checklist-based testing.
- [ ] Differentiate statement and branch testing.
- [ ] Explain why the three categories complement each other.
- [ ] Identify the correct technique from a practical scenario.

