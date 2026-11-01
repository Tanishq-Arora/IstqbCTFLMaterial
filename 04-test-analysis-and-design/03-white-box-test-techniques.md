
# 4.3 White-Box Test Techniques

## 1. What is White-Box Testing?

**White-box testing** is a test technique based on the internal structure or implementation of the test object.

It involves designing tests using knowledge of the internal code, logic, architecture or structure of the software.

It is also known as:
- Structural testing
- Clear-box testing
- Glass-box testing

### Example

A tester examines the source code of a Java method and designs test cases to execute every statement and every decision outcome.

### Key Characteristics

- Tests are derived from the internal structure of the software.
- Code structure, statements and branches guide test design.
- Coverage measurements provide objective information about what has been tested.
- It can reveal defects even when specifications are incomplete or outdated.

### White-Box Techniques Covered in CTFL

The two primary code-related white-box techniques covered in this section are:

1. Statement Testing
2. Branch Testing

More rigorous white-box techniques may be used in safety-critical, mission-critical or high-integrity environments to achieve more thorough code coverage.

---

# 2. Statement Testing

## 2.1 What is Statement Testing?

**Statement testing** is a white-box test technique in which test cases are designed to execute statements in the code.

The objective is to achieve the required statement coverage.

A statement is an instruction in the source code that can be executed.

### Example

Consider the following Java code:

```java
public void checkAge(int age) {

    System.out.println("Checking age");

    if (age >= 18) {
        System.out.println("Eligible");
    }

    System.out.println("Check completed");
}
```

Consider these test cases:

| Test Case | Input | Statements Executed |
|---|---:|---|
| TC01 | age = 20 | All executable statements |
| TC02 | age = 15 | Statements except "Eligible" |

When `age = 20`, all executable statements are executed.

Therefore, statement coverage is 100%.

When `age = 15`, the statement inside the IF block is not executed.

## 2.2 Statement Coverage

**Statement coverage** is the percentage of executable statements that have been executed by a test suite.

### Formula

Statement Coverage = (Number of executable statements executed / Total number of executable statements) × 100

### Example

Suppose a program contains:

- Total executable statements = 10
- Statements executed = 8

Statement Coverage = (8 / 10) × 100 = 80%

**Answer: 80% Statement Coverage**

### Important Points

- 100% statement coverage means every executable statement has been executed at least once.
- It does not guarantee that every decision outcome has been tested.
- It does not guarantee that all defects have been detected.
- It does not guarantee that the software meets all requirements.

---

# 3. Branch Testing

## 3.1 What is Branch Testing?

**Branch testing** is a white-box test technique in which test cases are designed to execute branches in the code.

A branch represents a possible transfer of control from one point in the code to another.

For a simple IF-ELSE decision, there are two possible outcomes:

1. True branch
2. False branch

The objective is to achieve the required branch coverage.

## 3.2 Example: A > B

Consider the following pseudocode:

```text
Read A
Read B

IF A > B THEN
    Print "A is Bigger"
ELSE
    Print "B is Bigger"
END IF
```

There are two possible outcomes:

**Branch 1: TRUE**

Input:
- A = 20
- B = 10

Condition: A > B = TRUE

Output: A is Bigger

**Branch 2: FALSE**

Input:
- A = 10
- B = 20

Condition: A > B = FALSE

Output: B is Bigger

To achieve 100% branch coverage, both outcomes must be executed.

| Test Case | A | B | Outcome |
|---|---:|---:|---|
| TC01 | 20 | 10 | TRUE |
| TC02 | 10 | 20 | FALSE |

## 3.3 Branch Coverage

**Branch coverage** is the percentage of branches that have been executed by a test suite.

### Formula

Branch Coverage = (Number of branches executed / Total number of branches) × 100

### Example

Suppose a program contains:

- Total branches = 8
- Branches executed = 6

Branch Coverage = (6 / 8) × 100 = 75%

**Answer: 75% Branch Coverage**

### Important Points

- 100% branch coverage means every branch has been executed at least once.
- Branch testing is stronger than statement testing.
- 100% branch coverage guarantees 100% statement coverage.
- 100% statement coverage does not guarantee 100% branch coverage.

---

# 4. Statement Testing vs Branch Testing

This is one of the most important comparisons in this topic.

| Parameter | Statement Testing | Branch Testing |
|---|---|---|
| Focus | Executable statements | Branches / control-flow outcomes |
| Objective | Execute every statement | Execute every branch |
| Coverage metric | Statement coverage | Branch coverage |
| Strength | Lower | Higher |
| 100% coverage guarantees | All executable statements executed | All branches and executable statements covered |
| Defect-free software guaranteed? | No | No |

## 4.1 Why is Branch Testing Stronger?

Consider:

```java
public void check(int a) {

    System.out.println("Start");

    if (a > 10) {
        System.out.println("Greater");
    }

    System.out.println("End");
}
```

### Test Case 1

Input: `a = 20`

Execution:

- Start executes.
- Condition `a > 10` evaluates to TRUE.
- Greater executes.
- End executes.

Every executable statement has been executed.

Therefore:

- Statement Coverage = 100%
- Branch Coverage = 50%

The FALSE branch has not been tested.

### Test Case 2

Input: `a = 5`

Execution:

- Start executes.
- Condition `a > 10` evaluates to FALSE.
- Greater is skipped.
- End executes.

Now both decision outcomes have been exercised.

Therefore:

- Statement Coverage = 100%
- Branch Coverage = 100%

**Exam Takeaway:**

100% statement coverage can be achieved without testing every decision outcome.

---

# 5. Nested Decisions

Nested decisions contain one decision inside another decision.

Consider the following pseudocode from the study slides:

```text
Read A

IF A > 0 THEN
    IF A = 21 THEN
        Print "Key"
    ENDIF
ENDIF
```

There are two decisions:

1. A > 0
2. A = 21

Each decision has two possible outcomes.

| Decision | Possible Outcomes |
|---|---|
| A > 0 | TRUE / FALSE |
| A = 21 | TRUE / FALSE |

### Test Cases

| Test Case | Input A | First Decision | Second Decision |
|---|---:|---|---|
| TC01 | -5 | FALSE | Not evaluated |
| TC02 | 10 | TRUE | FALSE |
| TC03 | 21 | TRUE | TRUE |

### Why are three test cases required to exercise all outcomes?

- TC01 exercises the FALSE outcome of the outer decision.
- TC02 exercises the TRUE outcome of the outer decision and FALSE outcome of the inner decision.
- TC03 exercises the TRUE outcome of both decisions.

**Important:** The inner decision cannot be evaluated when the outer decision is FALSE.

This is an important concept in nested decision testing.

---

# 6. Understanding Paths

A **path** is a sequence of executable statements or branches from the starting point to the ending point of a program or code fragment.

Consider:

```text
IF A > B THEN
    Print "A is Bigger"
ELSE
    Print "B is Bigger"
END IF
```

There are two possible execution paths:

**Path 1:**

Start → A > B (TRUE) → Print A is Bigger → End

**Path 2:**

Start → A > B (FALSE) → Print B is Bigger → End

### Important Distinction

| Coverage Type | What It Measures |
|---|---|
| Statement Coverage | Executable statements |
| Branch Coverage | Branches / decision outcomes |
| Path Coverage | Complete execution paths |

Do not confuse branch coverage with path coverage.

The CTFL section covered here focuses on statement and branch testing. The path illustrations in the slides help explain program control flow.

---

# 7. Relationship Between Statement and Branch Coverage

This is one of the most important facts for the examination.

**100% Branch Coverage guarantees 100% Statement Coverage, but not vice versa.**

| Statement Coverage | Branch Coverage | Possible? |
|---:|---:|---|
| 100% | 100% | Yes |
| 100% | Less than 100% | Yes |
| Less than 100% | 100% | No |
| Less than 100% | Less than 100% | Yes |

### Remember

- Branch testing is stronger than statement testing.
- 100% branch coverage implies 100% statement coverage.
- 100% statement coverage does not imply 100% branch coverage.
- Neither coverage metric guarantees defect-free software.

---

# 8. The Value of White-Box Testing

White-box testing has several strengths and limitations.

## 8.1 Advantages

### 1. Implementation-Based Defect Detection

The internal implementation is considered during testing.

This facilitates defect detection even when the software specification is vague, outdated or incomplete.

### 2. Objective Coverage Measurement

White-box coverage metrics provide an objective measurement of the coverage achieved by tests.

### 3. Identification of Additional Tests

Coverage results help identify untested statements or branches.

Additional tests can then be designed to increase coverage.

### 4. Static Testing Support

White-box techniques can also be used in static testing.

Examples include:

- Code reviews
- Dry runs of code
- Reviewing pseudocode
- Examining control-flow logic

They are particularly useful when code is not yet ready for execution.

### 5. Improved Confidence

White-box coverage measurements provide information about the extent to which the implementation has been tested.

Increasing coverage can improve confidence in the code.

## 8.2 Limitations

### 1. Missing Requirements May Not Be Detected

If the software does not implement one or more requirements, white-box testing may not detect the resulting defects of omission.

Example:

Requirement: The application must allow users to reset their passwords.

However, the developer never implements the password-reset feature.

White-box testing of the existing implementation may achieve 100% statement coverage, but it cannot execute code that does not exist.

Black-box testing against the requirement can expose the missing functionality.

### 2. Coverage Does Not Guarantee Defect-Free Software

Even 100% statement or branch coverage does not prove that the software is correct.

### 3. Does Not Replace Black-Box Testing

Structural testing alone cannot establish that all expected functionality and requirements have been implemented correctly.

### 4. Requires Knowledge of Internal Structure

Testers need sufficient knowledge of the internal code or structure to design effective white-box tests.

---

# 9. White-Box Testing vs Black-Box Testing

| Parameter | White-Box Testing | Black-Box Testing |
|---|---|---|
| Basis | Internal structure | External behaviour |
| Knowledge required | Internal implementation knowledge | Requirements and expected behaviour |
| Test design | Code, statements, branches and structure | Inputs, outputs and specifications |
| Coverage | Code coverage can be measured | Does not directly measure actual code coverage |
| Example | Statement testing | Equivalence partitioning |
| Main limitation | May miss unimplemented requirements | Cannot directly measure internal code coverage |

**Exam Trap:**

Performing only black-box testing does not provide a measure of actual code coverage.

---

# 10. Exam Traps – Must Remember

| Statement | Correct Answer |
|---|---|
| 100% statement coverage guarantees 100% branch coverage. | FALSE |
| 100% branch coverage guarantees 100% statement coverage. | TRUE |
| Branch testing is stronger than statement testing. | TRUE |
| 100% statement coverage means the software is defect-free. | FALSE |
| White-box testing considers internal implementation. | TRUE |
| White-box testing can always identify missing requirements. | FALSE |
| White-box techniques can support static testing. | TRUE |
| Black-box testing alone provides a measure of actual code coverage. | FALSE |
| Statement coverage measures executed statements. | TRUE |
| Branch coverage measures executed branches. | TRUE |
| 100% branch coverage guarantees all possible execution paths have been tested. | FALSE |
| 100% coverage guarantees that all defects have been detected. | FALSE |

---

# 11. Practice MCQs

These are original practice questions based on the concepts in the uploaded slides. They are not verbatim official ISTQB questions.

## A. Conceptual Questions

### Q1. Which of the following is a white-box test technique?

A. Equivalence Partitioning  
B. Boundary Value Analysis  
C. Statement Testing  
D. Decision Table Testing

### Q2. What is the primary objective of statement testing?

A. Execute all possible paths  
B. Execute all executable statements  
C. Execute all requirements  
D. Test all input combinations

### Q3. Which coverage metric measures the proportion of executable statements exercised?

A. Branch Coverage  
B. Statement Coverage  
C. Requirement Coverage  
D. Path Coverage

### Q4. Which statement about branch coverage is correct?

A. It is weaker than statement coverage.  
B. It guarantees defect-free software.  
C. 100% branch coverage guarantees 100% statement coverage.  
D. 100% statement coverage guarantees 100% branch coverage.

### Q5. What is a major limitation of white-box testing?

A. It cannot measure code coverage.  
B. It cannot execute code.  
C. It may not identify missing functionality that has not been implemented.  
D. It only works with user interfaces.

### Q6. A tester executes every statement in a program but does not exercise every outcome of a decision. Which coverage is achieved?

A. 100% statement coverage, less than 100% branch coverage  
B. 100% branch coverage, less than 100% statement coverage  
C. 100% path coverage  
D. 0% statement coverage

## B. Scenario-Based Questions

### Q7.

A program contains 20 executable statements. A test suite executes 15 of them.

What is the statement coverage?

A. 50%  
B. 65%  
C. 75%  
D. 80%

### Q8.

A decision has two outcomes. The test suite exercises only the TRUE outcome.

What is the branch coverage for this decision?

A. 0%  
B. 25%  
C. 50%  
D. 100%

### Q9.

A test suite achieves 100% branch coverage. Which conclusion can be drawn?

A. All defects have been detected.  
B. All executable statements have been executed.  
C. All requirements have been validated.  
D. All possible execution paths have been tested.

### Q10.

A developer implements an application but forgets to implement the logout functionality. The implemented code achieves 100% statement coverage.

What is the most likely explanation?

A. Statement coverage guarantees that all requirements are implemented.  
B. White-box testing may not detect the missing functionality.  
C. The test suite must have 100% path coverage.  
D. Branch coverage is always zero.

### Q11.

A tester reviews source code that is not yet executable and examines its control flow.

Which statement is correct?

A. White-box techniques can only be used during dynamic testing.  
B. White-box techniques can also support static testing.  
C. Static testing requires executing every statement.  
D. This is exclusively black-box testing.

### Q12.

A program has 12 branches. A test suite executes 9 branches.

What is the branch coverage?

A. 60%  
B. 70%  
C. 75%  
D. 90%

---

# 12. Answer Key with Explanations

| Question | Correct Answer | Explanation |
|---|---|---|
| Q1 | C | Statement testing is a white-box technique. |
| Q2 | B | Its objective is to execute all executable statements. |
| Q3 | B | Statement coverage measures the proportion of executable statements exercised. |
| Q4 | C | Branch coverage is stronger and 100% branch coverage guarantees 100% statement coverage. |
| Q5 | C | Missing functionality may not be detected when the corresponding code does not exist. |
| Q6 | A | All statements can execute while one decision outcome remains untested. |
| Q7 | C | 15 / 20 × 100 = 75%. |
| Q8 | C | One of two outcomes has been exercised: 1 / 2 × 100 = 50%. |
| Q9 | B | 100% branch coverage guarantees execution of all executable statements, but not all paths or defect detection. |
| Q10 | B | Code coverage cannot establish that unimplemented requirements exist. |
| Q11 | B | White-box techniques can support static examination of code and control flow. |
| Q12 | C | 9 / 12 × 100 = 75%. |

---

# 13. Quick Revision Sheet

| Topic | Remember |
|---|---|
| White-box testing | Based on internal structure |
| Statement testing | Execute executable statements |
| Statement coverage | Executed statements / Total executable statements × 100 |
| Branch testing | Exercise branches / control-flow outcomes |
| Branch coverage | Executed branches / Total branches × 100 |
| Stronger technique | Branch testing |
| 100% statement coverage | Does not guarantee 100% branch coverage |
| 100% branch coverage | Guarantees 100% statement coverage |
| Main limitation | May miss unimplemented requirements |
| Static testing | White-box techniques can support it |

---

# 14. Self-Assessment Checklist

- [ ] I can explain white-box testing.
- [ ] I understand statement testing and statement coverage.
- [ ] I can calculate statement coverage.
- [ ] I understand branch testing and branch coverage.
- [ ] I can calculate branch coverage.
- [ ] I understand why branch testing is stronger.
- [ ] I can solve nested decision examples.
- [ ] I understand the limitations of white-box testing.
- [ ] I can distinguish statement, branch and path coverage.
- [ ] I can explain the value of white-box testing.

## Final Exam Memory Points

1. Statement testing focuses on executable statements.
2. Branch testing focuses on branches or control-flow outcomes.
3. 100% branch coverage guarantees 100% statement coverage.
4. 100% statement coverage does not guarantee 100% branch coverage.
5. Neither coverage metric guarantees defect-free software.
6. White-box testing can identify defects in implemented code even when specifications are incomplete.
7. White-box testing may not detect missing functionality that has not been implemented.
8. White-box techniques can support static testing.
9. Black-box testing alone does not provide a measure of actual code coverage.
