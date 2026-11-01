# 2.1 — Impact of SDLC on Testing

**ISTQB CTFL v4.0.1 | Chapter 2: Testing Throughout the Software Development Life Cycle**

## 1. Learning Objectives

After studying this topic, you should be able to:

- Explain how the selected Software Development Life Cycle (SDLC) affects testing.
- Understand the relationship between development activities and test activities.
- Explain how sequential, iterative, and incremental development models influence testing.
- Understand how testing is integrated into Agile, TDD, ATDD, BDD, and DevOps practices.
- Explain good testing practices, shift-left testing, and retrospectives.

---

## 2. What Is the Software Development Life Cycle (SDLC)?

A **Software Development Life Cycle (SDLC) model** is an abstract, high-level representation of the software development process.

It defines how different development phases and activities relate to one another, both:

- **Logically:** The dependencies between activities.
- **Chronologically:** The order and timing in which activities occur.

### Examples of SDLC models

| Category | Examples | General characteristic |
|---|---|---|
| Sequential | Waterfall, V-model | Phases are performed largely in a defined sequence. |
| Iterative | Spiral, prototyping | Work is repeated and refined through iterations. |
| Incremental | Unified Process, incremental delivery | The product is built and delivered in smaller parts. |
| Iterative and incremental | Many Agile approaches | The product evolves through repeated cycles and successive increments. |

**Exam trap:** Iterative and incremental are related but different concepts.

- **Iterative:** Refine and improve an existing solution through repeated cycles.
- **Incremental:** Add new functionality in successive pieces.
- A development approach can be both iterative and incremental.

### Practical example

Consider an e-commerce application.

- Sequential approach: Requirements and design are completed before implementation and later testing phases.
- Iterative approach: The checkout design is repeatedly refined using feedback.
- Incremental approach: Product browsing is delivered first, followed by cart functionality and then payment functionality.

The chosen approach affects when testers participate, what they test, and how frequently they provide feedback.

---

## 3. How Does the SDLC Affect Testing?

Testing must be adapted to the selected SDLC to be effective.

The SDLC influences five important areas:

| Area | How the SDLC influences it |
|---|---|
| Scope and timing | Determines when testing activities occur and which test levels and types are performed. |
| Test documentation | Influences the level of detail and formality of test documentation. |
| Test techniques and approach | Influences which techniques and testing approaches are suitable. |
| Test automation | Influences the extent and type of automation needed. |
| Tester roles and responsibilities | Influences when testers participate and how they collaborate with other team members. |

### Example

A team delivering software every two weeks needs frequent feedback and repeatable regression testing.

The team may therefore prioritize automated regression tests, lightweight documentation, and early tester involvement.

A safety-critical project may require more formal documentation, additional independent testing, and specific regulatory evidence.

**Remember:** The SDLC does not eliminate the need for testing. It changes how testing is planned, organized, and performed.

---

## 4. Testing in Sequential Development Models

In sequential development models, activities generally proceed through defined phases.

Examples include the Waterfall model and the V-model.

### How testing works

- Testers may participate early through requirements reviews, test analysis, and test design.
- Executable code is usually available in later phases.
- Dynamic testing often cannot begin until executable software or components are available.
- Testing activities are planned around the relevant development phases.

### Example

A banking project follows a sequential process.

1. Requirements are documented.
2. Testers review requirements and identify ambiguities.
3. Architecture and design are prepared.
4. Developers implement the software.
5. Testers execute dynamic tests when the relevant software becomes available.

Even though execution occurs later, **testing-related activities can begin early**.

### V-model connection

The V-model emphasizes relationships between development stages and corresponding test levels.

| Development activity | Corresponding test level |
|---|---|
| Business or user requirements | Acceptance testing |
| System requirements | System testing |
| Architecture or high-level design | System integration testing |
| Detailed design | Component testing |

The exact mapping can vary according to the V-model representation used.

**Exam trap:** Do not assume that testing begins only after coding. Reviews and test analysis can start while requirements and designs are being produced.

---

## 5. Testing in Iterative and Incremental Development Models

In iterative and incremental models, the product is developed or refined through repeated cycles.

Each iteration may produce a working prototype or product increment.

### Impact on testing

- Both static and dynamic testing may occur during iterations.
- Testing can take place at different test levels.
- Frequent delivery requires fast feedback.
- Changes to existing functionality increase the importance of regression testing.
- Test automation can help teams test frequently and efficiently.

### Example

A mobile banking application is developed in increments.

- Iteration 1: Login and authentication.
- Iteration 2: Account balance and transaction history.
- Iteration 3: Money transfers.
- Iteration 4: Beneficiary management.

Each increment needs appropriate testing. When money-transfer functionality is introduced, regression tests should also check that login, account balance, and transaction history still work.

### Why is regression testing important here?

Each new increment can affect existing functionality.

Without regression testing, a feature that worked in an earlier iteration may break after a new change.

**Exam trap:** Incremental delivery does not mean testing only the new feature. Existing functionality must also be considered.

---

## 6. Testing in Agile Development

Agile development assumes that requirements and priorities may change throughout the project.

Testing is integrated into ongoing development rather than being treated solely as a final phase.

### Common characteristics

- Frequent feedback.
- Close collaboration between testers, developers, and business stakeholders.
- Lightweight documentation where appropriate.
- Extensive use of automation for repeatable regression checks.
- Early testing and continuous improvement.
- Regular adaptation of the testing approach as requirements change.

Agile teams may use experience-based testing techniques for exploratory testing and other activities, alongside formal test design techniques when appropriate.

### Example

During a sprint, the product owner changes the acceptance criteria for a checkout feature.

The tester collaborates with the product owner and developers to clarify the new criteria, update tests, execute relevant checks, and assess regression risks.

### Agile testing does not mean:

- No documentation.
- No test planning.
- No structured testing techniques.
- Everything must be automated.
- Testing can be skipped because releases are frequent.

**Exam trap:** Agile favors adaptable documentation, not the complete absence of documentation.

---

## 7. Good Testing Practices Independent of the SDLC

Some testing practices are valuable regardless of which SDLC model is selected.

### Practice 1: Every development activity has a corresponding test activity

Testing should address work products produced throughout development, not just executable code.

Examples:

- Requirements → Requirements reviews.
- Architecture → Architecture reviews.
- Source code → Static analysis and dynamic testing.
- User stories → Acceptance criteria reviews and acceptance tests.

This supports quality control across development activities.

### Practice 2: Different test levels have different objectives

Each test level should have its own purpose.

For example:

- Component testing focuses on individual components.
- Integration testing focuses on interactions between components or systems.
- System testing evaluates the behavior of the complete system.
- Acceptance testing evaluates whether the system meets relevant acceptance needs.

Distinct objectives help avoid unnecessary duplication while providing appropriate coverage.

### Practice 3: Test analysis and design begin early

For a given test level, test analysis and design should begin during the corresponding development phase.

This supports early testing and helps identify defects before they become more expensive to fix.

### Practice 4: Review work products as soon as drafts are available

Testers can review draft requirements, user stories, and designs before implementation.

This helps identify ambiguities, missing information, and inconsistencies early.

### Practical example

A requirement states:

> The application must respond quickly.

A tester may ask what "quickly" means, which operations are covered, and under what workload.

Clarifying these details before implementation reduces the risk of unclear expectations later.

---

## 8. Testing as a Driver for Software Development

In some development approaches, tests are defined before the relevant code is written. The tests help guide development.

Three important approaches are TDD, ATDD, and BDD.

### 8.1 Test-Driven Development (TDD)

**Definition:** Test-Driven Development uses tests to guide coding.

Typical cycle:

1. Write a test that initially fails.
2. Write the minimum code needed to make the test pass.
3. Refactor the code and tests while keeping the tests passing.

This is commonly summarized as **Red → Green → Refactor**.

Example: A developer writes a unit test for a method that calculates a discount before implementing the method itself.

### 8.2 Acceptance Test-Driven Development (ATDD)

**Definition:** Acceptance Test-Driven Development derives tests from acceptance criteria, usually through collaboration between relevant stakeholders.

Typical approach:

1. Discuss and clarify acceptance criteria.
2. Define acceptance tests before implementing the relevant functionality.
3. Develop the feature to satisfy those tests.
4. Execute the tests to evaluate whether the acceptance criteria are met.

Example: Before developing a refund feature, the tester, developer, and business representative agree on acceptance tests for eligible refunds, expired orders, and invalid requests.

### 8.3 Behavior-Driven Development (BDD)

**Definition:** Behavior-Driven Development expresses expected behavior in a form that is understandable to business and technical stakeholders.

A common format is **Given–When–Then**.

- **Given:** The initial context.
- **When:** The action or event.
- **Then:** The expected outcome.

Example:

```gherkin
Scenario: Successful login
  Given the user has a valid account
  When the user enters valid credentials
  Then the user should access the dashboard
```

BDD scenarios can be connected to automation so that executable tests run against the application.

### TDD vs ATDD vs BDD

| Approach | Main focus | Typical emphasis |
|---|---|---|
| TDD | Code and tests | Tests guide implementation, often at component level. |
| ATDD | Acceptance criteria | Tests are derived collaboratively from acceptance criteria. |
| BDD | Expected behavior | Behavior is described in a shared, understandable language. |

**Exam trap:** All three can support early testing and iterative development, but they emphasize different things.

---

## 9. DevOps and Testing

**DevOps** is an organizational and cultural approach that brings development—including testing—and operations together to achieve shared goals.

It encourages collaboration, rapid feedback, automation, and integrated delivery processes.

### Important DevOps practices

- Team autonomy and shared responsibility.
- Continuous Integration (CI).
- Continuous Delivery or Deployment (CD).
- Integrated toolchains.
- Automated testing and feedback.
- Stable and repeatable test environments.

### How DevOps benefits testing

| Benefit | Explanation |
|---|---|
| Faster feedback | Teams learn quickly whether a change has introduced problems. |
| Shift-left testing | Automated component tests and static analysis can run early in the delivery process. |
| Stable test environments | Automated pipelines can create or maintain repeatable environments. |
| Less repetitive manual work | Automated checks reduce the need to repeat the same routine tests manually. |
| More regression coverage | Automated regression suites can run frequently. |
| Better non-functional quality visibility | Performance and reliability checks can be incorporated into the pipeline where appropriate. |

### DevOps challenges

- The delivery pipeline must be designed and established.
- CI/CD tools need to be introduced, configured, and maintained.
- Automation requires time, skills, and resources.
- Automated tests themselves require maintenance.
- Unstable tests or environments can reduce confidence in pipeline results.

### CI vs CD

- **Continuous Integration (CI):** Frequently integrate code changes and run automated checks to provide fast feedback.
- **Continuous Delivery:** Keep software in a releasable state through an automated delivery process; production release may still require approval.
- **Continuous Deployment:** Automatically release qualifying changes to production without a separate manual release decision.

**Exam trap:** Continuous Delivery and Continuous Deployment are related, but they are not identical.

---

## 10. The Shift-Left Approach

**Definition:** Shift-left means performing testing activities earlier in the SDLC rather than postponing them until later stages.

The aim is to identify defects early, when they are generally less expensive and easier to address.

### Examples of shift-left testing

1. Review requirements from a testing perspective.
2. Write test cases before the corresponding code is implemented.
3. Use TDD, ATDD, or BDD where appropriate.
4. Run static analysis before or alongside dynamic testing.
5. Execute automated component tests during CI.
6. Begin suitable non-functional testing at component level where feasible.

### Example

A requirement incorrectly states that a user can withdraw any amount without a daily limit.

If this ambiguity is discovered during a requirements review, the team can clarify it before development.

If discovered after implementation and release, correction may require changes to code, tests, documentation, and production behavior.

### Advantages

- Earlier defect detection.
- Faster feedback.
- Reduced rework later.
- Better clarification of requirements.
- Potential savings in time and cost over the full lifecycle.

### Challenges

- Additional effort or training may be needed earlier.
- Teams need suitable tools and skills.
- Stakeholders must support and participate in the approach.
- Earlier testing cannot replace appropriate testing at later levels.

**Exam trap:** Shift-left does not mean eliminating system testing or acceptance testing. It means starting appropriate testing activities earlier.

---

## 11. Retrospectives and Process Improvement

A **retrospective** is a meeting held to review how work was performed and identify improvements.

Retrospectives may take place:

- At the end of an iteration.
- At a release milestone.
- At the end of a project.
- Whenever the team considers them useful.

### Who participates?

Depending on the context, participants may include:

- Testers.
- Developers.
- Architects.
- Product owners.
- Business analysts.
- Other relevant team members.

### Three key retrospective questions

1. What went well and should be retained?
2. What did not go well and should be improved?
3. How can improvements and successful practices be incorporated into future work?

### Example

A team discovers that regression testing repeatedly starts late because the test environment is unavailable.

During the retrospective, the team agrees to automate environment provisioning and assign an owner to monitor environment readiness.

The improvement should then be tracked and reviewed to confirm that it is implemented and effective.

### Benefits of retrospectives

- Improved test effectiveness and efficiency.
- Better quality of testware.
- Team learning and stronger collaboration.
- Improvements to requirements and other test basis documents.
- Better cooperation between development and testing.

Retrospective outcomes should be recorded appropriately, often as part of test completion reporting, and agreed improvements should be followed up.

**Exam trap:** A retrospective is not merely a meeting to assign blame. Its purpose is learning and continuous improvement.

---

# 12. Exam Traps — Quick Revision

| Statement | Correct understanding |
|---|---|
| Testing starts after coding. | Incorrect. Reviews and test analysis can start earlier. |
| Sequential models prevent early testing. | Incorrect. Static testing and test preparation can occur early. |
| Incremental development requires testing only new functionality. | Incorrect. Regression testing is also important. |
| Agile means no documentation. | Incorrect. Documentation is adapted to context. |
| Automation eliminates manual testing. | Incorrect. Exploratory and other manual testing can still be valuable. |
| Shift-left means skipping later testing. | Incorrect. It means starting suitable testing earlier. |
| TDD, ATDD, and BDD are identical. | Incorrect. They have different emphases. |
| Continuous Delivery always means automatic production deployment. | Incorrect. That describes Continuous Deployment more closely. |
| Retrospectives are only for testers. | Incorrect. They can involve the whole relevant team. |
| A retrospective is useful only at project end. | Incorrect. It can happen after iterations or releases as well. |

---

# 13. Practice Questions — Chapter 2.1

**Instructions:** Select one correct answer for each question. These are original practice questions, not official ISTQB exam questions.

## Foundational Questions

### Q1. What does an SDLC model describe?

A. Only the coding standards used by developers.

B. How development phases and activities relate logically and chronologically.

C. Only the testing activities performed after deployment.

D. Only the responsibilities of the project manager.

### Q2. Which is an example of a sequential development model?

A. Waterfall.

B. Prototyping.

C. An iterative Agile approach.

D. Continuous Deployment.

### Q3. Which area is influenced by the chosen SDLC?

A. Timing of test activities.

B. Level of test documentation.

C. Choice of test techniques and automation.

D. All of the above.

### Q4. Which statement about testing in sequential models is correct?

A. Testers cannot participate until coding is complete.

B. Test analysis and reviews can begin before executable code is available.

C. Static testing is prohibited.

D. Regression testing is never required.

### Q5. Why is regression testing important in iterative and incremental development?

A. Because each new increment can adversely affect existing functionality.

B. Because acceptance testing is unnecessary.

C. Because new functionality never introduces defects.

D. Because static testing cannot be performed.

### Q6. Which is a good testing practice independent of the SDLC?

A. Perform all testing after deployment.

B. Eliminate test documentation.

C. Ensure development activities have corresponding test activities.

D. Use only automated testing.

### Q7. What is the main idea behind shift-left testing?

A. Move all testing to the end of the lifecycle.

B. Start appropriate testing activities earlier in the lifecycle.

C. Replace testing with code reviews.

D. Perform only component testing.

### Q8. Which approach typically uses Given–When–Then scenarios?

A. TDD.

B. ATDD only.

C. BDD.

D. Waterfall.

### Q9. Which approach most directly uses tests to guide coding through a Red–Green–Refactor cycle?

A. TDD.

B. BDD.

C. Continuous Delivery.

D. Retrospective.

### Q10. What is the primary purpose of a retrospective?

A. To prove that the product contains no defects.

B. To identify lessons and improvements for future work.

C. To replace test completion reporting.

D. To assign all defects to individual testers.

### Q11. Which statement best describes DevOps?

A. A testing technique used only for component testing.

B. A process in which testing is separated from development and operations.

C. An organizational and cultural approach promoting collaboration between development and operations.

D. A replacement for all SDLC models.

### Q12. Which statement correctly distinguishes Continuous Delivery from Continuous Deployment?

A. Continuous Delivery always requires manual testing; Continuous Deployment never uses testing.

B. Continuous Delivery keeps software releasable, while Continuous Deployment automatically releases qualifying changes to production.

C. Continuous Deployment is a type of requirements review.

D. They are completely unrelated concepts.

## Scenario-Based Questions

### Q13. A team follows a sequential SDLC. During requirements analysis, a tester identifies that a business rule has two possible interpretations.

What is the best action?

A. Wait until system testing to report it.

B. Clarify the ambiguity through an early requirements review.

C. Ignore it because executable code is unavailable.

D. Create an automated UI test immediately without clarifying the rule.

### Q14. A team delivers new features every two weeks. After adding a payment feature, the login functionality stops working.

Which testing practice would help identify this type of unintended consequence?

A. Retrospective only.

B. Confirmation testing only.

C. Regression testing.

D. Requirements elicitation only.

### Q15. Before implementing a new discount calculation, a developer writes a failing unit test and then implements code to make it pass.

Which approach is being used?

A. ATDD.

B. TDD.

C. BDD.

D. Continuous Delivery.

### Q16. A tester, developer, and product owner jointly define acceptance tests before a refund feature is implemented.

Which approach does this most closely represent?

A. ATDD.

B. TDD exclusively.

C. Retrospective.

D. Continuous Deployment.

### Q17. A team writes business-readable scenarios using Given–When–Then and connects them to automated executable checks.

Which approach is most directly demonstrated?

A. Waterfall.

B. BDD.

C. Defect clustering.

D. Test completion.

### Q18. A CI pipeline runs automated component tests and static analysis whenever code is submitted to the repository.

Which concepts does this best illustrate?

A. Shift-left testing and DevOps practices.

B. Exhaustive testing.

C. Testing only after deployment.

D. The absence-of-errors fallacy.

### Q19. A manager claims that adopting Agile means the team no longer needs test documentation.

What is the best response?

A. Correct, Agile prohibits test documentation.

B. Correct, because automated tests replace all documentation.

C. Incorrect, because Agile adapts documentation to the context rather than eliminating it entirely.

D. Incorrect, because Agile requires every test to have a lengthy formal document.

### Q20. A team discovers that its regression suite takes too long to execute after every increment.

Which response is most appropriate?

A. Stop regression testing.

B. Consider suitable test automation and optimize the regression approach based on risk and feedback needs.

C. Test only the latest feature.

D. Wait until the end of the project to test existing functionality.

### Q21. During a retrospective, the team discovers recurring delays caused by unavailable test environments.

What should happen next?

A. Blame the team member who reported the issue.

B. Ignore the problem because the iteration has ended.

C. Agree on an actionable improvement, assign appropriate responsibility, and follow up.

D. Replace all testing with production monitoring.

### Q22. A project has regulatory requirements for detailed evidence, while another project uses lightweight documentation and frequent releases.

What does this illustrate?

A. The same documentation level is mandatory for every SDLC and project.

B. The SDLC and project context influence the required documentation and testing approach.

C. Regulatory projects cannot use automation.

D. Agile projects do not require quality control.

### Q23. A team performs reviews of requirements, static analysis of source code, and dynamic tests of the executable application.

What does this demonstrate?

A. Testing activities can address different work products throughout the SDLC.

B. Dynamic testing makes static testing unnecessary.

C. Testing is restricted to the implementation phase.

D. Only source code can be tested.

### Q24. An organization automates its deployment pipeline but rarely maintains its automated tests. Many tests become unreliable and fail intermittently.

What is the most appropriate conclusion?

A. Automation requires no maintenance once introduced.

B. DevOps removes the need for reliable test environments.

C. Test automation requires ongoing maintenance and reliable supporting processes.

D. The team should permanently disable all automated tests.

### Q25. A team moves requirements reviews and test design earlier, but continues performing system and acceptance testing later.

Which statement is correct?

A. The team is not using shift-left because all testing must occur before coding.

B. The team is using shift-left without eliminating later testing activities.

C. The team must stop regression testing.

D. The team has adopted TDD automatically.

### Q26. A team repeatedly discusses problems during retrospectives but never implements the agreed actions.

What is the main weakness?

A. Retrospectives are useful only for technical teams.

B. Retrospectives should happen only after deployment.

C. Improvement actions need to be implemented and followed up for continuous improvement to occur.

D. Retrospectives should focus only on defects in production.

### Q27. A team produces a working increment at the end of every iteration and obtains feedback before planning the next increment.

Which development characteristic is most clearly demonstrated?

A. Iterative and incremental development.

B. Strictly sequential development with no feedback.

C. Continuous Deployment only.

D. Static testing only.

### Q28. A team performs performance checks on individual components earlier than it traditionally would, where suitable tools and environments are available.

Which approach does this illustrate?

A. Shift-left testing.

B. Testing only at the system level.

C. The absence-of-errors fallacy.

D. Retrospective planning only.

### Q29. Which statement about TDD, ATDD, and BDD is most accurate?

A. All three have exactly the same purpose and level of focus.

B. TDD focuses on tests guiding coding, ATDD on acceptance criteria, and BDD on describing expected behavior collaboratively.

C. BDD is a sequential SDLC model.

D. ATDD means that acceptance testing is performed only after deployment.

### Q30. A team wants to release software frequently but needs confidence that existing features continue to work.

Which combination is most suitable?

A. Frequent releases without regression tests.

B. Lightweight documentation, fast feedback, and suitable automated regression testing.

C. Testing only at the end of the project.

D. Retrospectives without executing tests.

---

# 14. Answer Key

| Question | Answer | Tested concept |
|---|---|---|
| Q1 | B | SDLC definition |
| Q2 | A | Sequential models |
| Q3 | D | SDLC impact |
| Q4 | B | Early testing in sequential models |
| Q5 | A | Regression testing |
| Q6 | C | Good testing practices |
| Q7 | B | Shift-left |
| Q8 | C | BDD |
| Q9 | A | TDD |
| Q10 | B | Retrospectives |
| Q11 | C | DevOps |
| Q12 | B | Continuous Delivery vs Deployment |
| Q13 | B | Early requirements review |
| Q14 | C | Regression testing |
| Q15 | B | TDD |
| Q16 | A | ATDD |
| Q17 | B | BDD |
| Q18 | A | CI and shift-left |
| Q19 | C | Agile documentation |
| Q20 | B | Regression optimization and automation |
| Q21 | C | Retrospective follow-up |
| Q22 | B | Context-dependent documentation |
| Q23 | A | Testing throughout the SDLC |
| Q24 | C | Automation maintenance |
| Q25 | B | Shift-left without removing later tests |
| Q26 | C | Continuous improvement |
| Q27 | A | Iterative and incremental development |
| Q28 | A | Shift-left non-functional testing |
| Q29 | B | TDD vs ATDD vs BDD |
| Q30 | B | Frequent delivery and regression testing |

---

# 15. Explanations for Scenario Questions

- **Q13:** Early reviews can uncover ambiguity before it becomes an implementation defect.
- **Q14:** Regression testing checks whether a change has adversely affected existing functionality.
- **Q15:** TDD uses a failing test to guide implementation, followed by refactoring.
- **Q16:** ATDD derives acceptance tests collaboratively from acceptance criteria.
- **Q17:** BDD describes expected behavior in a form stakeholders can understand, commonly Given–When–Then.
- **Q18:** Running static analysis and component tests in CI gives early feedback and supports shift-left.
- **Q19:** Agile documentation should be appropriate to the context; it is not prohibited.
- **Q20:** Automation can make frequent regression testing more efficient, but test selection and maintenance remain important.
- **Q21:** Retrospectives should result in actionable improvements that are followed up.
- **Q22:** Documentation and testing practices depend on the SDLC, project needs, and constraints such as regulation.
- **Q23:** Testing can evaluate requirements, designs, code, and executable software through suitable activities.
- **Q24:** Automation must be maintained. Unreliable tests can reduce confidence in the pipeline.
- **Q25:** Shift-left brings suitable testing activities earlier; it does not eliminate testing at later levels.
- **Q26:** Discussion alone does not produce continuous improvement. Agreed changes must be implemented and reviewed.
- **Q27:** Iterative development uses repeated cycles; incremental development adds functionality in successive parts.
- **Q28:** Performing suitable testing earlier than usual is an example of shift-left.
- **Q29:** TDD, ATDD, and BDD all use tests to guide development, but their primary focus differs.
- **Q30:** Frequent delivery benefits from fast feedback and appropriate automated regression checks.

---

# 16. Final Revision Checklist

- [ ] I can define an SDLC model.
- [ ] I can distinguish sequential, iterative, and incremental development.
- [ ] I know the five main ways the SDLC affects testing.
- [ ] I understand how testing fits into sequential development.
- [ ] I understand why iterative and incremental models need fast feedback and regression testing.
- [ ] I know good testing practices that apply across SDLC models.
- [ ] I can distinguish TDD, ATDD, and BDD.
- [ ] I understand DevOps, CI, Continuous Delivery, and Continuous Deployment.
- [ ] I can explain shift-left testing and give examples.
- [ ] I understand retrospectives and the importance of following up improvement actions.
- [ ] I can apply these concepts to scenario-based questions.

## One-Minute Recall

**SDLC impact:** Scope and timing, documentation, techniques and approach, automation, tester roles.

**Good practices:** Test every relevant work product, use distinct objectives for test levels, begin test analysis early, review drafts early.

**TDD:** Tests guide coding.

**ATDD:** Tests come from acceptance criteria.

**BDD:** Expected behavior is described collaboratively, often with Given–When–Then.

**DevOps:** Collaboration, automation, CI/CD, and fast feedback.

**Shift-left:** Test earlier, not instead of testing later.

**Retrospective:** Learn, improve, implement, and follow up.