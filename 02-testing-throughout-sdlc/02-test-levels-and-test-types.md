# Chapter 2.2 — Test Levels and Test Types

## 1. Learning Objectives

By the end of this topic, you should be able to:

- Explain the different test levels.
- Differentiate between different test types.
- Understand confirmation testing and regression testing.
- Identify the appropriate test level or test type from a scenario.

---

# 2. Test Levels

## 2.1 What are Test Levels?

**Definition:**

Test levels are groups of test activities that are organized and managed together.

Each test level represents an instance of the test process performed in relation to software at a particular stage of development.

Testing can be performed on:

- Individual components
- Integrated components
- Complete systems
- Systems of systems

### Important Characteristics

1. Each test level has specific objectives.
2. Each test level is associated with different test objects.
3. Test levels are related to other SDLC activities.
4. Each level has its own entry and exit criteria.
5. Test levels may overlap in time, particularly in iterative and incremental development.
6. Different test levels help identify different categories of defects.

### Test Levels in Sequence

1. Component Testing
2. Component Integration Testing
3. System Testing
4. System Integration Testing
5. Acceptance Testing

**Remember:** Test levels describe WHERE or AT WHAT SCOPE testing is performed.

---

# 3. Component Testing

## 3.1 Definition

Component testing, also known as unit testing, focuses on testing individual components in isolation.

A component can be:

- A function
- A method
- A class
- A module
- A small software unit

### Key Characteristics

1. Tests individual components independently.
2. Usually performed by developers.
3. Commonly performed in the development environment.
4. Often uses test harnesses and unit testing frameworks.
5. Typically uses a white-box testing approach.
6. Helps identify defects within individual components before integration.

### Example

Consider an e-commerce application with the following components:

- LoginService
- CartService
- PaymentService
- OrderService

Testing the `calculateTotal()` method of CartService independently is component testing.

The test verifies whether the method calculates the cart total correctly without involving the complete application.

### SDET Example

Using JUnit:

```java
@Test
void shouldCalculateCartTotal() {
    CartService cartService = new CartService();

    double total = cartService.calculateTotal(100, 2);

    assertEquals(200, total);
}
````

Here:

- Only the CartService functionality is tested.
- Other application components are not required.
- The test focuses on the component's internal behavior.

### Important Terms

| Term                | Meaning                                                      |
| ------------------- | ------------------------------------------------------------ |
| Unit Testing        | Testing individual units or components                       |
| Test Harness        | Provides the environment and support needed to execute tests |
| Unit Test Framework | Framework used to write and execute unit tests               |
| White-box Testing   | Testing based on internal structure                          |

### Exam Trap

Component testing is NOT primarily concerned with:

- Communication between multiple components.
- Complete application workflows.
- Interaction with external systems.

These belong to integration or higher test levels.

# 4. Component Integration Testing

## 4.1 Definition

Component integration testing focuses on testing the interfaces and interactions between integrated components.

It verifies whether individual components communicate and work correctly together.

It is also known as unit integration testing.

### Key Characteristics

1. Focuses on interfaces between components.
2. Checks data exchange between components.
3. Verifies communication and interaction.
4. Can identify defects in component interfaces.
5. Depends on the integration strategy being followed.

### Example

Consider an e-commerce application:

CartService → OrderService → PaymentService

Suppose CartService sends the order amount to OrderService.

Component integration testing verifies:

- Whether CartService sends the correct amount.
- Whether OrderService receives the correct data.
- Whether the components communicate correctly.
- Whether the expected response is returned.

### Integration Strategies

Common integration approaches include:

| Strategy  | Explanation                                                                     |
| --------- | ------------------------------------------------------------------------------- |
| Big Bang  | All components are integrated together before testing                           |
| Top-Down  | Higher-level components are integrated and tested before lower-level components |
| Bottom-Up | Lower-level components are integrated and tested before higher-level components |

Note: These are integration strategies. Do not confuse them with test levels.

### Exam Trap

- Component testing → Individual component.
- Component integration testing → Interfaces between components.
- System testing → Complete system.
- System integration testing → Interfaces between systems.

The word "integration" alone does not tell you the test level. Identify WHAT is being integrated.

# 5. System Testing

## 5.1 Definition

System testing focuses on the overall behavior and capabilities of an entire system or product.

It verifies whether the complete integrated system satisfies its specified requirements.

### Key Characteristics

1. Tests the complete system.
2. Evaluates overall system behavior.
3. Includes functional and non-functional testing.
4. Often includes end-to-end business workflows.
5. Usually relates to system specifications.
6. May be performed by an independent test team.
7. Can identify defects arising from incomplete or incorrect system requirements.

### Example

Consider an e-commerce application.

A system test may validate the complete purchase workflow:

1. User logs in.
2. Searches for a product.
3. Adds the product to the cart.
4. Applies a discount coupon.
5. Completes payment.
6. Receives an order confirmation.

The complete application is tested against its requirements.

### Non-Functional Testing at System Level

Some quality characteristics are best evaluated on a complete system in a representative environment.

Examples:

- Performance testing
- Usability testing
- Reliability testing
- Security testing

For example, testing whether the complete e-commerce application can handle 10,000 concurrent users is system-level performance testing.

### Exam Trap

System testing is not the same as system integration testing.

- System testing → Overall behavior of the complete system.
- System integration testing → Interfaces between the system under test and other systems or external services.

# 6. System Integration Testing

## 6.1 Definition

System integration testing focuses on testing the interfaces between the system under test and other systems or external services.

It verifies whether the system communicates correctly with external dependencies.

### Key Characteristics

1. Focuses on interactions between different systems.
2. Tests interfaces and data exchange.
3. Requires suitable test environments.
4. The environment should preferably resemble the operational environment.
5. May involve software-to-software, software-to-hardware or hardware-to-hardware interactions.

### Example

Consider an e-commerce application integrated with:

- Payment Gateway
- Inventory Management System
- Shipping Provider
- Notification Service

System integration testing verifies:

- Whether payment requests reach the payment gateway.
- Whether payment responses are processed correctly.
- Whether inventory is updated after an order.
- Whether shipping information is sent correctly.
- Whether notification services receive the required data.

### Real SDET Example

Suppose your application integrates with an external payment gateway.

You send:

```
{
  "orderId": "ORD101",
  "amount": 2500,
  "currency": "INR"
}
```

You verify:

- Correct request payload.
- Correct authentication.
- Expected HTTP response.
- Correct response mapping.
- Error handling when the external service is unavailable.

This is system integration testing because the focus is on communication between separate systems.

### Exam Trap

| Scenario                                                      | Correct Test Level            |
| ------------------------------------------------------------- | ----------------------------- |
| Testing PaymentService independently                          | Component Testing             |
| Testing CartService and OrderService interaction              | Component Integration Testing |
| Testing the complete shopping application                     | System Testing                |
| Testing shopping application with an external payment gateway | System Integration Testing    |

# 7. Acceptance Testing

## 7.1 Definition

Acceptance testing focuses on validation and demonstrating readiness for deployment.

It checks whether the system fulfils the business needs and expectations of the intended users and other relevant stakeholders.

### Key Characteristics

1. Focuses on business requirements.
2. Evaluates whether the system is fit for intended use.
3. Supports decisions about deployment or acceptance.
4. Ideally performed by intended users or relevant stakeholders.
5. Can be performed at different points in the SDLC.

### Example

An e-commerce company develops a new order management system.

Business stakeholders verify:

- Orders can be placed successfully.
- Discounts follow business rules.
- Refunds are processed according to company policy.
- Reports meet business expectations.

If the system meets the agreed acceptance criteria, stakeholders may accept it.

## 7.2 Main Forms of Acceptance Testing

### 1. User Acceptance Testing (UAT)

Performed by intended users or their representatives to determine whether the system meets business needs.

Example:

Bank employees validate whether a banking application supports their actual daily operations.

### 2. Operational Acceptance Testing (OAT)

Evaluates whether the system is ready for operation and can be managed effectively in its operational environment.

It may include:

- Backup and restoration.
- Recovery procedures.
- Installation and uninstallation.
- Operational monitoring.
- User and access management.
- Maintenance procedures.

Example:

The operations team verifies whether a banking application can be backed up and restored successfully.

### 3. Contractual Acceptance Testing

Verifies whether the system meets acceptance criteria specified in a contract.

Example:

A vendor develops software for a client. The client verifies whether all contractually agreed features and performance criteria have been delivered.

### 4. Regulatory Acceptance Testing

Verifies whether the system complies with relevant laws, regulations and standards.

Example:

A financial application is checked against applicable regulatory requirements.

## 7.3 Alpha and Beta Testing

### Alpha Testing

- Performed at the developer's site.
- Conducted by potential users, customers or an independent test team.
- Takes place before beta testing.
- Helps identify defects before wider external exposure.

### Beta Testing

- Performed by potential or existing users at their own locations or in their environment.
- Takes place outside the developer's site.
- Helps obtain feedback under real-world conditions.
- Can help identify issues that were not detected during alpha testing.

### Alpha vs Beta Testing

| Parameter    | Alpha Testing                           | Beta Testing                   |
| ------------ | --------------------------------------- | ------------------------------ |
| Location     | Developer's site                        | User's environment             |
| Participants | Potential users, customers or test team | Potential or existing users    |
| Environment  | Controlled environment                  | Real-world or user environment |
| Purpose      | Identify issues before external release | Obtain real-world feedback     |
| Sequence     | Before beta                             | After alpha                    |

### Exam Trap

- Alpha → Developer's site.
- Beta → User's environment.
- UAT → Business/user acceptance.
- OAT → Operational readiness.
- Contractual → Contract requirements.
- Regulatory → Legal/regulatory compliance.

Do not assume that all acceptance testing is UAT.

# 8. Test Types

## 8.1 Definition

Test types are groups of test activities related to specific quality characteristics.

Most test types can be performed at every test level, although their focus may differ depending on the level.

Remember:

- Test levels → WHERE or at what scope testing is performed.
- Test types → WHAT quality aspect is being tested.

The four major test types covered here are:

1. Functional Testing
2. Non-Functional Testing
3. Black-Box Testing
4. White-Box Testing

# 9. Functional Testing

## 9.1 Definition

Functional testing evaluates whether a system performs the functions it is expected to perform.

It focuses on WHAT the system does.

It checks the system's behavior against functional requirements or specifications.

### Examples

For an e-commerce application:

- User should be able to log in.
- User should be able to add products to the cart.
- User should be able to apply a valid coupon.
- User should be able to complete payment.
- User should receive an order confirmation.

### Real SDET Example

Testing a login API:

```
POST /api/login
```

Request:

```
{
  "username": "user123",
  "password": "password123"
}
```

Expected behavior:

- Valid credentials should return a successful response.
- Invalid credentials should return an appropriate error.
- Missing mandatory fields should be handled correctly.

These are functional tests because they validate the functionality of the login feature.

# 10. Non-Functional Testing

## 10.1 Definition

Non-functional testing evaluates how well a system performs its functions.

It focuses on HOW the system works and evaluates its quality characteristics.

### Examples

| Test Type               | What It Evaluates                                      |
| ----------------------- | ------------------------------------------------------ |
| Performance Testing     | Response time, throughput and resource usage           |
| Load Testing            | System behavior under expected workload                |
| Stress Testing          | System behavior beyond normal operating capacity       |
| Usability Testing       | Ease of use and user experience                        |
| Reliability Testing     | Ability to operate consistently over time              |
| Security Testing        | Protection against security threats                    |
| Maintainability Testing | Ease of modifying and maintaining the system           |
| Portability Testing     | Ease of transferring the system to another environment |

### Practical Examples

Performance Testing:

Does the application respond within 2 seconds when 5,000 users access it?

Load Testing:

Can the application handle its expected workload of 5,000 concurrent users?

Stress Testing:

What happens when the application receives 20,000 concurrent requests, exceeding its expected capacity?

Usability Testing:

Can a first-time user complete a purchase without confusion?

Reliability Testing:

Can the application operate continuously without frequent failures?

Security Testing:

Can an unauthorized user access another user's account?

### Functional vs Non-Functional Testing

| Functional Testing                | Non-Functional Testing                           |
| --------------------------------- | ------------------------------------------------ |
| Focuses on WHAT the system does   | Focuses on HOW well the system works             |
| Validates functional requirements | Evaluates quality characteristics                |
| Checks business functionality     | Checks performance, usability, reliability, etc. |
| Example: Login works              | Example: Login responds within 2 seconds         |

### Important Exam Point

Functional and non-functional testing can be performed at different test levels.

For example:

- Component-level functional testing.
- System-level functional testing.
- System-level performance testing.
- System-level usability testing.

Do not associate a test type exclusively with one test level.

# 11. Black-Box Testing

## 11.1 Definition

Black-box testing is specification-based testing that derives test cases from documentation external to the test object.

It evaluates the system's behavior without requiring knowledge of its internal structure.

### Key Characteristics

1. Based on specifications and requirements.
2. Focuses on inputs and expected outputs.
3. Does not require knowledge of internal implementation.
4. Can be performed by testers and developers.
5. Evaluates whether the system behaves according to its specification.

### Example

Suppose a login application accepts:

- Valid username and password.
- Invalid username and password.

A tester validates the expected response without examining the source code.

### Common Black-Box Techniques

- Equivalence Partitioning.
- Boundary Value Analysis.
- Decision Table Testing.
- State Transition Testing.

These techniques are covered in more detail in Chapter 4.

# 12. White-Box Testing

## 12.1 Definition

White-box testing is structure-based testing that derives tests from the system's internal structure or implementation.

It evaluates the internal workings of the system.

### Key Characteristics

1. Based on internal structure.
2. Uses knowledge of source code, architecture or workflows.
3. Focuses on structural coverage.
4. Commonly performed by developers, but testers can also perform it.
5. Helps identify defects in internal logic and implementation.

### Example

Consider the following code:

```
public String validateAge(int age) {

    if (age >= 18) {
        return "Eligible";
    } else {
        return "Not Eligible";
    }
}
```

A white-box test may ensure that both branches are executed:

- `age = 20` → Eligible.
- `age = 15` → Not Eligible.

The objective is to achieve branch coverage.

### Common White-Box Techniques

- Statement Testing.
- Branch Testing.

These techniques are covered in detail in Chapter 4.

### Black-Box vs White-Box Testing

| Parameter      | Black-Box                          | White-Box                                      |
| -------------- | ---------------------------------- | ---------------------------------------------- |
| Basis          | Specification                      | Internal structure                             |
| Focus          | External behavior                  | Internal implementation                        |
| Code knowledge | Not required                       | Required                                       |
| Test design    | Requirements and expected behavior | Code, logic and structure                      |
| Example        | Validate login functionality       | Validate execution of both login code branches |

### Important Exam Trap

White-box testing is NOT restricted to component testing.

Black-box testing is NOT restricted to system testing.

Both approaches can be applied at different test levels, depending on the test objective and test basis.

# 13. Confirmation Testing (Retesting)

## 13.1 Definition

Confirmation testing verifies that an original defect has been successfully fixed.

It is also known as retesting.

### Why Is Confirmation Testing Required?

Suppose a tester identifies a defect:

- User enters valid credentials.
- Application displays an error instead of logging in.

The developer fixes the defect.

The tester executes the previously failed test again to verify that the defect has been fixed.

This is confirmation testing.

### Key Characteristics

1. Confirms that the original defect has been fixed.
2. Re-executes previously failed test cases.
3. May include additional tests covering changes made during the fix.
4. Focuses on the specific defect that was reported.
5. Can be performed at any test level where the defect was identified.

### Example

Original defect:

\- Login fails when the password contains special characters.

Developer fixes the issue.

Confirmation testing:

- Execute the same test case again.
- Verify that login now succeeds with special characters.

### Important Point

Depending on the risk, confirmation testing may include:

- Re-executing all test cases that previously failed because of the defect.
- Adding new tests to cover changes made to fix the defect.

When resources are limited, confirmation testing may be restricted to reproducing the original failure and verifying that it no longer occurs.

# 14. Regression Testing

## 14.1 Definition

Regression testing verifies that no adverse consequences have been introduced by a change.

These changes may include:

- Defect fixes.
- New features.
- Enhancements.
- Configuration changes.
- Changes to existing functionality.

### Why Is Regression Testing Required?

A change in one component may affect:

1. The same component.
2. Other components in the same system.
3. Connected systems.
4. The test environment.

### Example

An e-commerce application has a defect in its coupon calculation.

The developer fixes the coupon calculation logic.

Confirmation testing:

\- Checks whether the coupon calculation defect has been fixed.

Regression testing:

- Checks whether checkout still works.
- Checks whether cart totals remain correct.
- Checks whether tax calculations are unaffected.
- Checks whether payment processing still works.

### Key Characteristics

1. Checks for unintended side effects of changes.
2. Can cover the changed component and other affected components.
3. May include connected systems and the environment.
4. Is performed after changes.
5. Is a strong candidate for test automation.
6. Should be considered early in the project.
7. Can be performed at different test levels.

### Impact Analysis

Before performing regression testing, impact analysis can help identify which areas may be affected by a change.

This helps optimize the scope of regression testing.

Example:

A change to the payment calculation service may affect:

- Cart total.
- Order summary.
- Payment amount.
- Invoice generation.
- Refund calculation.

Impact analysis helps determine which areas require regression testing.

### Why Is Regression Testing a Strong Candidate for Automation?

- Regression suites are executed repeatedly.
- The number of regression test cases may increase with every iteration or release.
- Automation reduces repetitive manual effort.
- Automated tests can provide faster feedback.
- Regression tests can be integrated into CI/CD pipelines.

# 15. Confirmation Testing vs Regression Testing

This is one of the MOST IMPORTANT distinctions in this chapter.

| Parameter     | Confirmation Testing                                         | Regression Testing                                     |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| Also known as | Retesting                                                    | Regression                                             |
| Objective     | Verify that a defect is fixed                                | Verify that changes have not caused side effects       |
| Focus         | Original defect                                              | Existing functionality potentially affected by changes |
| Test cases    | Previously failed tests and additional defect-specific tests | Relevant existing test cases                           |
| Scope         | Usually narrow and specific                                  | May be broad                                           |
| Example       | Verify that login defect is fixed                            | Verify that login changes did not break password reset |

### Easy Memory Trick

Confirmation = Did the FIX work?

Regression = Did the FIX break something ELSE?

### Practical Scenario

A developer fixes a defect in the payment module.

- Rechecking the failed payment test case → Confirmation Testing.
- Checking whether order creation, invoice generation and refunds still work → Regression Testing.

### Important Exam Traps

1. Confirmation testing is not the same as regression testing.
2. Regression testing is not limited to the modified component.
3. Confirmation testing does not necessarily require executing the entire regression suite.
4. Regression testing can be performed after a defect fix or any other change.
5. Both can be performed at any test level where the relevant changes or defects occur.

# 16. Test Levels vs Test Types vs Test Techniques

These three terms are frequently confused in the examination.

| Concept        | Meaning                                              | Example                 |
| -------------- | ---------------------------------------------------- | ----------------------- |
| Test Level     | Scope or stage at which testing is performed         | System Testing          |
| Test Type      | Quality characteristic or testing objective          | Performance Testing     |
| Test Technique | Method used to derive test conditions and test cases | Boundary Value Analysis |

### Example

Suppose you are testing an online banking application.

- Test Level: System Testing.
- Test Type: Functional Testing.
- Test Technique: Equivalence Partitioning.

Another example:

- Test Level: System Testing.
- Test Type: Non-Functional Testing.
- Test Technique: A suitable performance test design approach.

Remember:

Level = Where?

Type = What aspect?

Technique = How do we design the tests?

# 17. Complete Test Level Comparison

| Test Level                    | Main Focus                                  | Example                                                   |
| ----------------------------- | ------------------------------------------- | --------------------------------------------------------- |
| Component Testing             | Individual component                        | Testing calculateInterest()                               |
| Component Integration Testing | Interfaces between components               | Testing AccountService and TransactionService interaction |
| System Testing                | Complete system                             | Testing the complete banking application                  |
| System Integration Testing    | Interfaces between systems                  | Testing banking application with external payment service |
| Acceptance Testing            | Business needs and readiness for deployment | Bank employees validating business workflows              |

### Quick Identification

- One method or class → Component Testing.
- Two or more components communicating → Component Integration Testing.
- Complete application → System Testing.
- Application communicating with external systems → System Integration Testing.
- Business/user approval → Acceptance Testing.

# 18. Exam Traps and Important Distinctions

| Statement                                                        | Correct Understanding |
| ---------------------------------------------------------------- | --------------------- |
| Unit testing is another name for component testing               | Correct               |
| Component integration testing focuses on component interfaces    | Correct               |
| System testing focuses on the complete system                    | Correct               |
| System integration testing focuses on external system interfaces | Correct               |
| Acceptance testing validates business needs                      | Correct               |
| Functional testing checks WHAT the system does                   | Correct               |
| Non-functional testing checks HOW WELL the system works          | Correct               |
| Black-box testing requires source code knowledge                 | Incorrect             |
| White-box testing is based on internal structure                 | Correct               |
| Confirmation testing checks whether a defect was fixed           | Correct               |
| Regression testing checks unintended side effects                | Correct               |
| Regression testing is only performed after defect fixes          | Incorrect             |
| All test types can be performed only at system level             | Incorrect             |
| Alpha testing takes place at the developer's site                | Correct               |
| Beta testing takes place in the user's environment               | Correct               |
| UAT and OAT are the same                                         | Incorrect             |

# 19. High-Value Revision Table

| Term                          | One-Line Revision                                   |
| ----------------------------- | --------------------------------------------------- |
| Component Testing             | Testing individual components in isolation          |
| Component Integration Testing | Testing interactions between components             |
| System Testing                | Testing the complete system                         |
| System Integration Testing    | Testing interfaces with external systems            |
| Acceptance Testing            | Validating business needs and readiness             |
| UAT                           | Validation by intended users                        |
| OAT                           | Validation of operational readiness                 |
| Contractual Testing           | Verifying contractual acceptance criteria           |
| Regulatory Testing            | Verifying regulatory compliance                     |
| Alpha Testing                 | Testing at developer's site                         |
| Beta Testing                  | Testing in user's environment                       |
| Functional Testing            | WHAT the system does                                |
| Non-Functional Testing        | HOW WELL the system works                           |
| Black-Box Testing             | Specification-based testing                         |
| White-Box Testing             | Structure-based testing                             |
| Confirmation Testing          | Verifying that the defect is fixed                  |
| Regression Testing            | Verifying that changes have not caused side effects |

# 20. Practice MCQs — Foundational (12 Questions)

## Q1. Which test level focuses on testing individual software components in isolation?

A. System Testing\
B. Component Testing\
C. Acceptance Testing\
D. System Integration Testing

## Q2. What is the primary objective of component integration testing?

A. Validate business requirements\
B. Test individual components independently\
C. Test interfaces and interactions between components\
D. Test the complete application

## Q3. Which test level focuses on the overall behavior and capabilities of an entire system?

A. Component Testing\
B. Component Integration Testing\
C. System Testing\
D. System Integration Testing

## Q4. Testing an application integrated with an external payment gateway primarily belongs to which test level?

A. Component Testing\
B. System Integration Testing\
C. Acceptance Testing\
D. Component Integration Testing

## Q5. Which type of acceptance testing evaluates whether a system can be operated and maintained effectively?

A. User Acceptance Testing\
B. Operational Acceptance Testing\
C. Contractual Acceptance Testing\
D. Regulatory Acceptance Testing

## Q6. Which testing is typically performed at the developer's site before beta testing?

A. Beta Testing\
B. Alpha Testing\
C. UAT\
D. OAT

## Q7. Functional testing primarily focuses on:

A. How efficiently the system works\
B. What the system does\
C. Internal code structure only\
D. Hardware compatibility only

## Q8. Which of the following is a non-functional test?

A. Verify that a user can log in\
B. Verify that a user can add products to a cart\
C. Verify that the application responds within two seconds\
D. Verify that an order can be placed

## Q9. Which testing approach derives tests from the internal structure of the software?

A. Black-box Testing\
B. White-box Testing\
C. Acceptance Testing\
D. Functional Testing

## Q10. Which testing approach derives tests from specifications without requiring knowledge of internal implementation?

A. White-box Testing\
B. Black-box Testing\
C. Component Integration Testing\
D. Performance Testing

## Q11. What is the main objective of confirmation testing?

A. Identify new defects in unrelated modules\
B. Verify that a reported defect has been fixed\
C. Validate the complete application\
D. Verify system performance

## Q12. What is the main objective of regression testing?

A. Confirm that a defect has been fixed\
B. Verify that changes have not caused unintended side effects\
C. Validate only new functionality\
D. Test only the modified source code

# 21. Practice MCQs — Scenario-Based (20 Questions)

## Q13.

A developer writes a test for a method that calculates the discount amount. The method is tested independently without involving other modules.

Which test level is being performed?

A. Component Integration Testing\
B. Component Testing\
C. System Testing\
D. Acceptance Testing

## Q14.

An application has separate modules for customer registration and customer profile management. A tester verifies whether customer data is correctly transferred between these modules.

Which test level is most appropriate?

A. Component Testing\
B. Component Integration Testing\
C. System Testing\
D. Acceptance Testing

## Q15.

A tester validates the complete banking application, including account creation, fund transfer, transaction history and statement generation.

Which test level is this?

A. Component Testing\
B. Component Integration Testing\
C. System Testing\
D. System Integration Testing

## Q16.

A banking application communicates with an external credit bureau. The testing team verifies whether requests and responses are exchanged correctly between the two systems.

Which test level is being performed?

A. Component Testing\
B. System Testing\
C. System Integration Testing\
D. Acceptance Testing

## Q17.

A group of bank employees validates whether a newly developed banking application supports their daily business operations before it is accepted.

Which testing is this?

A. Component Testing\
B. User Acceptance Testing\
C. Regression Testing\
D. Component Integration Testing

## Q18.

An operations team verifies backup, restoration, recovery and monitoring procedures before a production release.

Which testing is being performed?

A. UAT\
B. OAT\
C. Alpha Testing\
D. Beta Testing

## Q19.

A software vendor develops a solution for a client. The client checks whether the delivered solution meets the acceptance conditions specified in their contract.

Which testing is this?

A. Regulatory Acceptance Testing\
B. Contractual Acceptance Testing\
C. Operational Acceptance Testing\
D. Component Testing

## Q20.

A financial application is evaluated to ensure that it meets applicable regulatory requirements.

Which testing is most appropriate?

A. UAT\
B. OAT\
C. Regulatory Acceptance Testing\
D. Alpha Testing

## Q21.

A software product is tested by potential customers at the developer's premises before it is released for wider external testing.

Which testing is being performed?

A. Beta Testing\
B. Alpha Testing\
C. UAT\
D. OAT

## Q22.

A company releases a pre-release version of its application to selected users who test it in their own environments and provide feedback.

Which testing is this?

A. Alpha Testing\
B. Beta Testing\
C. Component Testing\
D. System Integration Testing

## Q23.

A tester verifies that a user can successfully reset a password using a registered email address.

Which test type is being performed?

A. Non-Functional Testing\
B. Functional Testing\
C. White-box Testing\
D. Performance Testing

## Q24.

A testing team evaluates whether an application can handle 8,000 concurrent users while maintaining acceptable response times.

Which test type is most appropriate?

A. Functional Testing\
B. Non-Functional Testing\
C. Component Testing\
D. Acceptance Testing

## Q25.

A tester validates an application's behavior using requirements and expected results without looking at the source code.

Which approach is being used?

A. White-box Testing\
B. Black-box Testing\
C. Component Testing\
D. Static Analysis

## Q26.

A developer examines the source code and designs test cases to ensure that every decision branch is executed.

Which approach is being used?

A. Black-box Testing\
B. White-box Testing\
C. Acceptance Testing\
D. System Integration Testing

## Q27.

A defect is reported because the application incorrectly calculates tax. After the developer fixes it, the tester executes the previously failed test case to verify the fix.

Which testing is this?

A. Regression Testing\
B. Confirmation Testing\
C. System Testing\
D. Acceptance Testing

## Q28.

A developer fixes a defect in the payment module. The tester then checks whether invoice generation, order processing and refunds continue to work correctly.

Which testing is being performed?

A. Confirmation Testing\
B. Regression Testing\
C. Component Testing\
D. Alpha Testing

## Q29.

A developer changes a shared authentication library. The tester checks whether login, password reset and session management are still working.

Which testing is this?

A. Confirmation Testing only\
B. Regression Testing\
C. Acceptance Testing\
D. Alpha Testing

## Q30.

A tester verifies that the original defect is fixed and then executes other relevant test cases to ensure that the fix has not affected existing functionality.

Which combination is being performed?

A. Component and System Testing\
B. Confirmation and Regression Testing\
C. Alpha and Beta Testing\
D. Functional and Acceptance Testing

## Q31.

A tester validates the functionality of an application and also checks its response time and usability.

Which statement is correct?

A. Functional and non-functional testing cannot be performed together\
B. Functional testing can only be performed at component level\
C. Functional and non-functional testing can both be performed at different test levels\
D. Non-functional testing can only be performed during acceptance testing

## Q32.

A tester is checking whether an application correctly handles invalid input values based on the specified requirements. The tester has no access to the source code.

Which statement is correct?

A. It is white-box testing because input validation is involved\
B. It is black-box testing because test cases are derived from specifications\
C. It is component integration testing because inputs are involved\
D. It is regression testing because invalid values are tested

# 22. Answer Key — Foundational Questions

| Question | Answer | Explanation                                                         |
| -------- | ------ | ------------------------------------------------------------------- |
| Q1       | B      | Component testing checks individual components in isolation.        |
| Q2       | C      | Component integration testing focuses on component interfaces.      |
| Q3       | C      | System testing evaluates the complete system.                       |
| Q4       | B      | External payment gateway integration is system integration testing. |
| Q5       | B      | OAT evaluates operational readiness.                                |
| Q6       | B      | Alpha testing is performed at the developer's site.                 |
| Q7       | B      | Functional testing evaluates WHAT the system does.                  |
| Q8       | C      | Response time is a performance quality characteristic.              |
| Q9       | B      | White-box testing is structure-based.                               |
| Q10      | B      | Black-box testing is specification-based.                           |
| Q11      | B      | Confirmation testing verifies that the defect is fixed.             |
| Q12      | B      | Regression testing checks for unintended side effects.              |

# 23. Answer Key — Scenario-Based Questions

| Question | Answer | Explanation                                                      |
| -------- | ------ | ---------------------------------------------------------------- |
| Q13      | B      | A single method tested independently is component testing.       |
| Q14      | B      | The focus is on interaction between two components.              |
| Q15      | C      | The complete banking application is being tested.                |
| Q16      | C      | The focus is on communication between separate systems.          |
| Q17      | B      | Intended business users are validating business needs.           |
| Q18      | B      | Backup, recovery and monitoring are operational concerns.        |
| Q19      | B      | The acceptance criteria are contractually defined.               |
| Q20      | C      | The objective is to verify regulatory compliance.                |
| Q21      | B      | Alpha testing takes place at the developer's site.               |
| Q22      | B      | Beta testing involves users testing in their own environments.   |
| Q23      | B      | Password reset is a system function.                             |
| Q24      | B      | Concurrent users and response time are performance concerns.     |
| Q25      | B      | Tests are based on specifications, not source code.              |
| Q26      | B      | Branch execution is a white-box testing objective.               |
| Q27      | B      | The previously failed test is executed to verify the fix.        |
| Q28      | B      | Other related functionality is checked for side effects.         |
| Q29      | B      | A shared component change may affect multiple existing features. |
| Q30      | B      | The tester verifies the fix and checks for side effects.         |
| Q31      | C      | Both test types can be applied at different test levels.         |
| Q32      | B      | The test is derived from external requirements.                  |

# 24. Final Revision Checklist

Before moving to the next topic, ensure you can:

- Explain all five test levels.
- Differentiate component testing and component integration testing.
- Differentiate system testing and system integration testing.
- Explain all major forms of acceptance testing.
- Differentiate alpha and beta testing.
- Explain functional and non-functional testing.
- Differentiate black-box and white-box testing.
- Explain confirmation testing with an example.
- Explain regression testing with an example.
- Differentiate confirmation testing and regression testing.
- Identify test levels and types from real-world scenarios.

## 25. Last-Minute Memory Map

| If the question mentions...        | Think of...                    |
| ---------------------------------- | ------------------------------ |
| Individual method, class or module | Component Testing              |
| Interaction between components     | Component Integration Testing  |
| Complete application               | System Testing                 |
| External API or third-party system | System Integration Testing     |
| Business approval                  | Acceptance Testing             |
| Backup, recovery, monitoring       | OAT                            |
| Contractual obligations            | Contractual Acceptance Testing |
| Regulatory compliance              | Regulatory Acceptance Testing  |
| Developer's premises               | Alpha Testing                  |
| User's environment                 | Beta Testing                   |
| WHAT the system does               | Functional Testing             |
| HOW WELL the system works          | Non-Functional Testing         |
| External specification             | Black-Box Testing              |
| Internal code structure            | White-Box Testing              |
| Verify the fix                     | Confirmation Testing           |
| Check for side effects             | Regression Testing             |

Source note: These practice questions are original questions created for revision. They are not reproduced official ISTQB examination questions or verified past-paper questions.



## Important corrections to remember from your slides

A few distinctions are particularly important for avoiding wrong answers in the exam:

1. **Component integration vs system integration:** The former tests interactions between components; the latter tests interfaces between separate systems.
2. **White-box vs black-box:** These are testing approaches, not test levels. Neither is restricted to a particular test level.
3. **Functional vs non-functional:** These are test types. Both can be applied at different test levels.
4. **Confirmation vs regression:** Confirmation checks whether the fix worked; regression checks whether the change caused side effects.
5. **Acceptance testing:** UAT is only one form. OAT, contractual and regulatory acceptance testing are also important.

**My recommendation:** Don't move ahead until you can solve the 20 scenario-based questions without looking at the notes. These distinctions are much easier to remember through scenarios than through definitions.
