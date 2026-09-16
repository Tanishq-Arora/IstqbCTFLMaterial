# What is Testing?

## Definition

**Software testing is a set of activities to discover defects and evaluate the quality of software artifacts.**

The software artifacts being tested are known as **test objects**.

> **Exam Keyword:** Testing = discovering defects + evaluating quality.

---

## Testing Is More Than Test Execution

A common misconception is:

> **Testing = executing the software and checking the results.**

This is incorrect.

**Test execution is only one part of testing.**

Testing can include activities such as:

* Test planning
* Test analysis
* Test design
* Test implementation
* Test execution
* Evaluation of test results
* Reporting
* Monitoring and control

Therefore:

> **Testing is a broader activity than simply running test cases.**

### Exam Perspective

If a question states:

> "Testing consists only of executing tests."

**Answer: False.**

Testing includes activities that take place **before, during, and after test execution**.

---

# Testing Is Not Limited to the Final Software

Another common misconception is:

> **Testing focuses entirely on verifying the executable software.**

Testing can be performed on different **software work products**, including:

* Requirements
* User stories
* Designs
* Code
* Other software artifacts

The artifact being tested is referred to as the **test object**.

### Exam Trap

> "Only executable software can be tested."

❌ **Incorrect**

Requirements, designs, user stories, code, and other work products can also be evaluated.

---

# Static and Dynamic Testing

Testing can be broadly classified into:

## Static Testing

Static testing evaluates a work product **without executing the software**.

Examples include:

* Reviews
* Inspections
* Static analysis

Static testing can directly identify defects in work products.

```text
Work Product
     ↓
Static Testing
     ↓
Defect Identified
```

---

## Dynamic Testing

Dynamic testing involves **executing the test object**.

During dynamic testing, tests can trigger failures.

```text
Test Execution
      ↓
Failure Observed
      ↓
Investigate
      ↓
Defect Identified
```

### Exam Trap

> "Testing always requires execution of the software."

❌ **False**

Static testing does not require software execution.

---

# Testing Is Not Only a Technical Activity

Testing is not purely a technical activity.

It also needs to be:

* Planned
* Managed
* Estimated
* Monitored
* Controlled

Therefore, testing contains both **technical** and **management** aspects.

### Technical Activities

Examples:

* Test analysis
* Test design
* Test implementation
* Test execution
* Evaluation of results

### Management Activities

Examples:

* Test planning
* Test estimation
* Test monitoring
* Test control
* Test reporting

### Exam Perspective

> "Testing is purely a technical activity performed by testers."

❌ **Incorrect**

Testing also requires appropriate planning, management, estimation, monitoring, and control.

---

# Test Objectives

The typical objectives of testing include:

## 1. Evaluating Work Products

Testing evaluates software work products such as:

* Requirements
* User stories
* Designs
* Code

### Exam Point

Testing is **not restricted to executable software**.

---

## 2. Triggering Failures and Finding Defects

Testing aims to:

* Trigger failures during dynamic testing
* Find defects in test objects
* Provide information about the quality of the test object

Static and dynamic testing approach defects differently.

```text
Static Testing
     ↓
Defect can be identified directly

Dynamic Testing
     ↓
Execute software
     ↓
Failure
     ↓
Defect may be identified
```

---

## 3. Ensuring Required Coverage

Testing aims to achieve the required level of **coverage** of the test object.

Coverage can provide information about how much of a particular aspect has been exercised by testing.

Examples include:

* Requirement coverage
* Code coverage
* Test condition coverage
* Risk coverage

### Exam Trap

> "Required coverage means testing every possible input and scenario."

❌ Not necessarily.

**Exhaustive testing is generally impossible.**

---

## 4. Reducing the Risk of Inadequate Software Quality

Testing helps reduce the risk associated with inadequate software quality.

Testing provides information about:

* Defects
* Quality
* Coverage
* Risks
* Remaining uncertainty

This information can support decisions about the software.

---

## 5. Verifying Specified Requirements

Testing can verify whether specified requirements have been fulfilled.

### Example

```text
Requirement:
Users must be able to reset their password.

Test:
Perform password reset.

Expected Result:
Password is successfully reset.
```

The test provides evidence about whether the specified requirement has been fulfilled.

---

## 6. Verifying Contractual, Legal, and Regulatory Requirements

Testing can verify whether the test object complies with:

* Contractual requirements
* Legal requirements
* Regulatory requirements

This can be particularly important for software operating in regulated environments.

---

## 7. Providing Information to Stakeholders

Testing provides information that allows stakeholders to make **informed decisions**.

Testing can provide information about:

* Current quality
* Defects
* Coverage
* Risks
* Test progress
* Remaining uncertainty

### Important

Testing is therefore not simply about producing:

```text
PASS / FAIL
```

It also provides useful information for decision-making.

---

## 8. Building Confidence in Quality

Testing can increase stakeholders' confidence in the quality of the test object.

However:

> **Testing cannot prove that the software is completely defect-free.**

Testing provides evidence and can reduce uncertainty and risk, but it cannot guarantee the absence of defects.

---

## 9. Validating Stakeholder Expectations

Testing can validate whether the test object:

* Is complete
* Works as expected by stakeholders
* Meets stakeholder needs and expectations

This relates to the concept of **validation**.

---

# Verification vs Validation

A useful distinction for exam purposes:

## Verification

> **Are we building the product correctly according to specified requirements?**

Focus:

* Specified requirements
* Specifications
* Work products
* Correct implementation

---

## Validation

> **Are we building the right product that meets stakeholder needs and expectations?**

Focus:

* Stakeholder needs
* Expectations
* Intended use
* Suitability

### Easy Memory Trick

```text
VERIFICATION
"Did we build it correctly?"

VALIDATION
"Did we build the right thing?"
```

---

# Testing and Debugging

**Testing and debugging are separate activities.**

They have different purposes.

---

## Testing

Testing is concerned with:

* Evaluating work products
* Finding defects
* Triggering failures
* Evaluating quality
* Providing information about risks and quality

---

## Debugging

Debugging is concerned with:

* Finding the cause of a failure
* Analyzing the cause
* Removing or fixing the cause

### Easy Way to Remember

```text
TESTING
"Something is wrong."
       ↓
DEBUGGING
"Why is it wrong?"
       ↓
FIX
"Remove the cause."
```

---

# Dynamic Testing and Debugging

When dynamic testing triggers a failure, debugging is used to investigate the failure.

The typical debugging process is:

```text
Failure
   ↓
Reproduction
   ↓
Diagnosis
   ↓
Fixing the Cause
```

---

## 1. Reproduction

The failure is reproduced to confirm and investigate the observed behavior.

---

## 2. Diagnosis

The cause of the failure is investigated.

The goal is to identify the underlying **defect/root cause**.

---

## 3. Fixing

The identified cause is corrected or removed.

---

# Static Testing and Debugging

Static testing works differently.

Static testing can **directly identify defects** in a work product because it does not execute the software.

Therefore, when static testing identifies a defect:

```text
Static Testing
      ↓
Defect Identified
      ↓
Remove / Correct Defect
```

There is no need to reproduce a failure because:

* The software was not executed.
* Static testing directly identified the defect.
* No failure was triggered by the static test.

---

# Error, Defect, and Failure

These terms are important for understanding the relationship between testing and debugging.

## Error

A **human action** that produces an incorrect result.

Example:

> A developer misunderstands a requirement.

---

## Defect

A **flaw in a work product** that can cause the software to fail to perform as expected.

Example:

> The developer implements the password validation incorrectly.

---

## Failure

An event in which the software does not perform a required function within specified limits.

Example:

> The application accepts a password that should have been rejected.

---

## Relationship

A common relationship is:

```text
Human Error
     ↓
Defect
     ↓
Failure
```

### Important Exam Point

A defect **may cause** a failure when the software is executed.

Not every defect necessarily causes a failure in every situation.

---

# Testing vs Debugging

| Aspect              | Testing                              | Debugging                                                                          |
| ------------------- | ------------------------------------ | ---------------------------------------------------------------------------------- |
| Primary purpose     | Find defects / trigger failures      | Find and remove causes                                                             |
| Can be static?      | Yes                                  | Debugging after static defect identification does not require failure reproduction |
| Executes software?  | Dynamic testing does                 | Not the defining characteristic                                                    |
| Finds failure?      | Dynamic testing can trigger failures | Investigates the failure                                                           |
| Root cause analysis | Not its primary purpose              | Yes                                                                                |
| Fixes defect?       | No                                   | Yes                                                                                |
| Main question       | "Is there a problem?"                | "Why is there a problem?"                                                          |

---

# Static vs Dynamic Testing

| Static Testing                       | Dynamic Testing                   |
| ------------------------------------ | --------------------------------- |
| Does not execute software            | Executes software                 |
| Can directly identify defects        | Can trigger failures              |
| Applied to work products             | Applied through execution         |
| Examples: reviews, static analysis   | Examples: functional/system tests |
| No failure is triggered by execution | Failures can be observed          |

---

# Testing vs Debugging Flow

## Dynamic Testing

```text
Test Case
    ↓
Execute Software
    ↓
Failure
    ↓
Debugging
    ↓
Reproduce
    ↓
Diagnose
    ↓
Fix
```

## Static Testing

```text
Work Product
    ↓
Static Testing
    ↓
Defect Identified
    ↓
Correct / Remove Defect
```

---

# Exam Traps

## Trap 1 — Testing = Execution

> "Testing is the execution of software and checking actual results against expected results."

❌ **Incorrect**

Execution is only one part of testing.

---

## Trap 2 — Only Software Can Be Tested

> "Requirements cannot be tested because they are not executable."

❌ **Incorrect**

Requirements and other work products can be evaluated through testing activities such as static testing.

---

## Trap 3 — Testing Always Requires Execution

> "Testing always involves executing the test object."

❌ **Incorrect**

Static testing does not require execution.

---

## Trap 4 — Static Testing Causes Failures

> "Static testing triggers failures."

❌ **Incorrect**

Static testing does not execute the software, so it does not trigger execution failures.

---

## Trap 5 — Testing and Debugging Are the Same

> "Debugging is another name for testing."

❌ **Incorrect**

They are **separate activities**.

---

## Trap 6 — Testers Fix Defects

> "The primary purpose of testing is to fix defects."

❌ **Incorrect**

Testing finds defects/provides information.

Debugging investigates and removes the causes of failures/defects.

---

## Trap 7 — Testing Proves No Defects Exist

> "If all tests pass, the software has no defects."

❌ **Incorrect**

Testing cannot prove the complete absence of defects.

---

## Trap 8 — Testing Is Purely Technical

> "Testing only involves technical test execution activities."

❌ **Incorrect**

Testing also requires planning, management, estimation, monitoring, and control.

---

# Quick Revision

| Question                                          | Answer                                                                             |
| ------------------------------------------------- | ---------------------------------------------------------------------------------- |
| What is testing?                                  | A set of activities to discover defects and evaluate quality of software artifacts |
| What is a test object?                            | A software artifact being tested                                                   |
| Is testing only execution?                        | No                                                                                 |
| Can requirements be tested?                       | Yes                                                                                |
| Can testing be static?                            | Yes                                                                                |
| Does static testing execute software?             | No                                                                                 |
| Can dynamic testing trigger failures?             | Yes                                                                                |
| What is debugging?                                | Finding, analyzing, and removing the causes of failures/defects                    |
| What happens after a dynamic failure?             | Debugging may reproduce, diagnose, and fix the cause                               |
| Does static testing require failure reproduction? | No                                                                                 |
| Can testing prove absence of defects?             | No                                                                                 |
| Is testing purely technical?                      | No                                                                                 |
| What does verification ask?                       | Are we building the product correctly?                                             |
| What does validation ask?                         | Are we building the right product?                                                 |

---

# 🧠 One-Minute Memory Map

```text
                         TESTING
                            │
             ┌──────────────┴──────────────┐
             │                             │
          STATIC                        DYNAMIC
             │                             │
      No execution                    Execution
             │                             │
      Find defects                    Failure
             │                             │
             │                             ↓
             │                         DEBUGGING
             │                             │
             │                    ┌────────┼────────┐
             │                    │        │        │
             │               Reproduce  Diagnose   Fix
             │
             └─────────────────────────────┐
                                           │
                                  TEST OBJECTIVES
                                           │
        ┌──────────────────────────────────┼────────────────────────┐
        ↓                                  ↓                        ↓
 Evaluate work products              Find defects              Ensure coverage
        ↓                                  ↓                        ↓
 Verify requirements                Reduce risks             Build confidence
        ↓                                  ↓                        ↓
 Verify legal/contractual       Provide stakeholder       Validate stakeholder
 requirements                     information                 expectations
```

---

# 🎯 Exam Priority

| Topic                                   | Priority     |
| --------------------------------------- | ------------ |
| Definition of Testing                   | 🔴 Must Know |
| Testing vs Test Execution               | 🔴 Must Know |
| Test Object                             | 🔴 Must Know |
| Static vs Dynamic Testing               | 🔴 Must Know |
| Test Objectives                         | 🔴 Must Know |
| Testing vs Debugging                    | 🔴 Must Know |
| Dynamic Testing → Failure → Debugging   | 🔴 Must Know |
| Debugging Process                       | 🔴 Must Know |
| Error → Defect → Failure                | 🔴 Must Know |
| Verification vs Validation              | 🟠 Important |
| Testing is not purely technical         | 🟠 Important |
| Testing cannot prove absence of defects | 🔴 Must Know |

---

# Final Exam Takeaways

Remember these **10 statements**:

1. **Testing is broader than test execution.**
2. **A test object is the software artifact being tested.**
3. **Testing can be static or dynamic.**
4. **Static testing does not execute the software.**
5. **Dynamic testing can trigger failures.**
6. **Testing and debugging are separate activities.**
7. **Testing identifies defects/failures; debugging investigates and removes their causes.**
8. **Testing cannot prove the absence of defects.**
9. **Testing supports risk reduction, confidence, and stakeholder decision-making.**
10. **Testing requires both technical activities and appropriate planning, management, estimation, monitoring, and control.**
