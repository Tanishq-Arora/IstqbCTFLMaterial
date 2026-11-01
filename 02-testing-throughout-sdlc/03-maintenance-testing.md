# 2.3 Maintenance Testing
**ISTQB CTFL v4.0.1 — Chapter 2: Testing Throughout the SDLC**

**Scope:** Maintenance testing, reasons for maintenance testing, maintenance triggers, impact analysis and factors influencing the scope of maintenance testing.

---

## Learning Objective

| LO Code | Learning Objective | K-Level |
|---|---|---|
| FL-2.3.1 | Summarize maintenance testing and its triggers. | K2 |

**Source basis:** These notes follow the maintenance-testing slide images you supplied. Additional explanations and practice questions are included for exam preparation.

---

# 1. What is Maintenance Testing?

**Maintenance testing** is testing performed on an existing software system after it has been deployed, to evaluate changes made to the system or its environment and to ensure that the existing functionality continues to work correctly.

Maintenance testing is required whenever an existing system is modified, migrated, upgraded or retired.

### Why is Maintenance Testing Required?

Software systems undergo changes throughout their operational life.

Examples include:

- Adding new features.
- Fixing defects.
- Improving performance.
- Adapting software to a new operating system.
- Migrating to a new database.
- Upgrading infrastructure.
- Retiring an application.

These changes can introduce new defects or adversely affect existing functionality.

Therefore, maintenance testing typically includes:

1. Testing the changes made to the system.
2. Checking for possible regressions in unchanged parts of the system.

### Practical Example – Banking Application

Consider an existing banking application.

A new feature is introduced that allows customers to schedule recurring payments.

Testing should cover:

- Whether recurring payments can be scheduled successfully.
- Whether the payment frequency is correctly applied.
- Whether the payment executes on the scheduled date.
- Whether existing one-time payments continue to work.
- Whether account balances and transaction histories remain correct.

The first group verifies the new functionality. The second group checks for regression.

---

# 2. Categories of Maintenance

Maintenance can be classified into different categories.

| Maintenance Category | Meaning | Example |
|---|---|---|
| Corrective | Fixing defects identified in the existing system. | Fixing a payment failure bug. |
| Adaptive | Modifying software to accommodate changes in the environment. | Updating an application to support a new operating system. |
| Perfective | Improving performance, maintainability or other characteristics. | Optimizing database queries to improve response time. |
| Preventive | Modifying software to reduce the possibility of future problems. | Refactoring complex code to improve maintainability. |

### Understanding Each Category

**1. Corrective Maintenance**

Performed to correct defects in an existing system.

Example:
- A customer cannot complete a payment because of a calculation defect.
- Developers fix the calculation.
- Testers perform confirmation testing and regression testing.

**2. Adaptive Maintenance**

Performed to adapt software to changes in its operational environment.

Example:
- An application is migrated from one database platform to another.
- Testers validate compatibility and data migration.

**3. Perfective Maintenance**

Performed to improve the system or enhance its performance and maintainability.

Example:
- Optimizing an API that takes five seconds to respond.
- Improving an existing user interface.

**4. Preventive Maintenance**

Performed to prevent potential future problems.

Example:
- Refactoring complex code.
- Removing obsolete dependencies.
- Improving code structure to reduce future maintenance risks.

---

# 3. Planned and Unplanned Maintenance Releases

Maintenance can involve both planned and unplanned releases or deployments.

| Type | Meaning | Example |
|---|---|---|
| Planned Maintenance | Changes scheduled as part of a planned release or deployment. | A monthly release containing new features and improvements. |
| Unplanned Maintenance | Changes deployed urgently, often as hot fixes. | An emergency production fix for a critical payment defect. |

### Hot Fix

A **hot fix** is an urgent software change released to address a critical issue, usually without waiting for the normal release cycle.

Example:

A production application stops processing payments.

The development team prepares an urgent fix and deploys it immediately.

Testing should verify:

- The original issue has been resolved.
- The fix has not introduced new defects.
- Critical existing functionality remains operational.

**Exam Point:** A hot fix is an example of unplanned maintenance.

---

# 4. Impact Analysis in Maintenance Testing

**Impact analysis** is performed to identify the potential consequences of a proposed change in other areas of the system.

It helps the team decide:

- Whether a change should be implemented.
- Which components may be affected.
- Which interfaces may be impacted.
- Which existing test cases should be executed.
- How much regression testing is required.

### Why is Impact Analysis Important?

A change in one component can affect other components or connected systems.

Example:

An application changes its authentication mechanism from password-based authentication to OAuth.

Potentially affected areas:

- Login functionality.
- API authorization.
- Session management.
- Token refresh.
- Mobile application authentication.
- Third-party integrations.

Impact analysis helps identify the scope of required testing.

### Impact Analysis Workflow

1. Understand the proposed change.
2. Identify the components and interfaces affected.
3. Identify dependent systems and integrations.
4. Assess the associated risks.
5. Determine the required confirmation and regression testing.
6. Prioritize the test execution.

**Exam Trap:** Impact analysis helps determine the scope of regression testing. It does not itself confirm that the change works correctly.

---

# 5. Testing Changes in a Production System

Testing changes to a system in production includes two important activities:

1. Evaluating the success of the implementation of the change.
2. Checking for possible regressions in parts of the system that remain unchanged.

Usually, most of the existing system remains unchanged when a modification is introduced.

Therefore, maintenance testing must consider both the changed and unchanged parts of the system.

### Practical Example – E-commerce Application

An e-commerce platform introduces a new discount calculation mechanism.

**Testing the changed functionality:**

- Verify discount calculations.
- Verify coupon validation.
- Verify the final payable amount.

**Testing unchanged functionality:**

- Verify payment processing.
- Verify order creation.
- Verify inventory updates.
- Verify refund processing.

A change in discount calculation could unintentionally affect the final payment amount or order processing.

---

# 6. Scope of Maintenance Testing

The scope of maintenance testing typically depends on three factors:

| Factor | Explanation | Example |
|---|---|---|
| Degree of risk of the change | Higher-risk changes generally require broader and deeper testing. | Changes to payment processing require extensive testing. |
| Size of the existing system | Larger systems may have more dependencies and interactions to consider. | A banking platform with multiple integrated services. |
| Size of the change | Larger changes may affect more components and require broader testing. | Replacing an entire authentication module rather than changing a single validation rule. |

### Important Exam Point

The scope of maintenance testing is influenced by:

- Risk associated with the change.
- Size of the existing system.
- Size of the change.

Do not confuse these factors with the triggers for maintenance testing.

---

# 7. Triggers for Maintenance Testing

The triggers for maintenance and maintenance testing can be classified into three main categories:

1. Modifications.
2. Upgrades or migrations of the operational environment.
3. Retirement of a system.

## 7.1 Modifications

Modifications include:

- Planned enhancements.
- Corrective changes.
- Hot fixes.

Examples:

**Planned Enhancement**

A banking application introduces a new feature that allows customers to download account statements in PDF format.

**Corrective Change**

A defect causing incorrect tax calculations is fixed.

**Hot Fix**

A critical production issue is fixed through an emergency deployment.

In all these situations, maintenance testing is required.

## 7.2 Upgrades or Migrations of the Operational Environment

An operational environment may be upgraded or migrated from one platform to another.

This can require testing of:

- The new operational environment.
- The changed software.
- Data conversion.
- Compatibility with the new platform.

### Example – Database Migration

An organization migrates its application database from Oracle to PostgreSQL.

Testing may include:

- Database connectivity.
- Data migration accuracy.
- Data integrity.
- Query compatibility.
- Application functionality.
- Performance in the new environment.

### Example – Operating System Upgrade

A mobile application is updated to support a newer Android version.

Testing should verify:

- Application compatibility.
- Installation and upgrade behavior.
- Device permissions.
- Notifications.
- Existing functionality.

**Important:** Environment migration may require testing both the new environment and the changed software.

## 7.3 Retirement of a System

Maintenance testing may also be required when an application reaches the end of its life.

When a system is retired, testing may include:

- Data archiving.
- Data retention.
- Data restoration.
- Data retrieval procedures.

### Example – Application Retirement

An organization retires an old payroll application but must retain employee payroll records for several years.

Testing may be required to verify:

- Whether data is archived correctly.
- Whether archived records can be retrieved.
- Whether data remains complete and accurate.
- Whether restoration procedures work when required.

**Exam Trap:** Retirement does not mean testing is unnecessary. Data archiving, restoration and retrieval may still require testing.

---

# 8. Maintenance Testing – Complete Summary Table

| Trigger | What Happens? | Testing Focus |
|---|---|---|
| Modifications | Planned enhancements, corrective changes or hot fixes. | Test changed functionality and check for regressions. |
| Upgrades or migrations | Changes to the operational environment or migration to another platform. | Test the new environment, changed software and data conversion. |
| Retirement | Application reaches the end of its life. | Test data archiving, restoration and retrieval procedures. |

---

# 9. Maintenance Testing vs Development Testing

| Basis | Development Testing | Maintenance Testing |
|---|---|---|
| Purpose | Tests software during its development. | Tests changes to an existing system and their impact. |
| Timing | During development. | After deployment, when changes or retirement activities occur. |
| Main Focus | Verifying newly developed software. | Testing modifications and checking for regressions. |
| Triggers | Development activities and new functionality. | Modifications, environment upgrades/migrations and retirement. |
| Regression Testing | May be performed when changes are introduced. | Particularly important because existing functionality must continue to work. |

---

# 10. SDET Practical Scenarios

### Scenario 1 – Production Hot Fix

A payment application has a production defect. Developers release a hot fix.

As an SDET, you should:

1. Understand the defect and the fix.
2. Execute confirmation testing for the original issue.
3. Identify potentially affected components.
4. Execute appropriate regression tests.
5. Verify critical payment workflows.

### Scenario 2 – Database Migration

An application migrates from MySQL to PostgreSQL.

Testing should cover:

- Database connectivity.
- Data conversion.
- Data integrity.
- SQL compatibility.
- Application functionality.
- Performance.
- Existing integrations.

This is maintenance testing triggered by an operational environment migration.

### Scenario 3 – Application Retirement

An organization retires an old HR application but must preserve employee records.

Testing should verify:

- Data archiving.
- Data retention.
- Retrieval of archived records.
- Restoration procedures.

This is maintenance testing triggered by system retirement.

### Scenario 4 – Feature Enhancement

An e-commerce application introduces a new coupon feature.

Testing should cover:

- New coupon functionality.
- Coupon validation.
- Discount calculations.
- Existing checkout functionality.
- Payment processing.
- Order creation.

This is maintenance testing triggered by a modification.

---

# 11. Exam Traps and Important Points

1. Maintenance testing is performed on an existing system after deployment.
2. Maintenance testing is not limited to defect fixes.
3. Planned enhancements are maintenance triggers.
4. Corrective changes and hot fixes are maintenance triggers.
5. Upgrades and migrations of operational environments are maintenance triggers.
6. Retirement of a system is also a maintenance trigger.
7. Maintenance testing includes testing the change and checking for regressions.
8. Impact analysis identifies the potential consequences of a change.
9. Impact analysis helps determine the scope of regression testing.
10. The scope depends on risk of change, size of the existing system and size of the change.
11. Environment migration may require data conversion testing.
12. System retirement may require testing of archiving, restoration and retrieval procedures.
13. Hot fixes are examples of unplanned maintenance releases.
14. Maintenance testing is not restricted to production bug fixes.
15. Changes in the environment can trigger maintenance testing even when the application functionality itself has not changed significantly.

---

# 12. Quick Revision Table

| Term | Key Point |
|---|---|
| Maintenance Testing | Testing an existing system after changes or maintenance activities. |
| Corrective Maintenance | Fixing defects. |
| Adaptive Maintenance | Adapting software to environmental changes. |
| Perfective Maintenance | Improving performance or maintainability. |
| Preventive Maintenance | Preventing potential future problems. |
| Hot Fix | Urgent, usually unplanned production fix. |
| Impact Analysis | Identifying potential consequences of a change. |
| Planned Enhancement | A planned modification to an existing system. |
| Environment Migration | Moving to another platform or environment. |
| Retirement | End-of-life activities for an application. |
| Data Archiving | Storing data for long-term retention. |
| Data Retrieval | Accessing archived data when required. |
| Scope of Maintenance Testing | Depends on risk, existing system size and change size. |

---

# 13. Practice Questions

**Note:** These are original practice questions, not official ISTQB questions or verified past examination questions.

## Section A – Core Concept MCQs

### Q1. What is the primary purpose of maintenance testing?

A. To test software only before its first release.

B. To test changes to an existing system and check for possible regressions.

C. To replace all development testing.

D. To test only newly developed applications.

### Q2. Which of the following is a maintenance testing trigger?

A. Modifications to an existing system.

B. Upgrades or migrations of the operational environment.

C. Retirement of a system.

D. All of the above.

### Q3. Which of the following is an example of corrective maintenance?

A. Moving an application to a new operating system.

B. Fixing a defect in payment processing.

C. Archiving an application before retirement.

D. Improving code readability to prevent future problems.

### Q4. Which maintenance category involves adapting software to changes in its operational environment?

A. Corrective.

B. Adaptive.

C. Perfective.

D. Preventive.

### Q5. What is the purpose of impact analysis?

A. To execute all regression tests.

B. To identify the potential consequences of a change in other areas of the system.

C. To confirm that the software is defect-free.

D. To replace maintenance testing.

### Q6. Which of the following is an example of unplanned maintenance?

A. A scheduled monthly release.

B. A planned feature enhancement.

C. An emergency production hot fix.

D. A planned database upgrade.

### Q7. Which factor influences the scope of maintenance testing?

A. Risk of the change.

B. Size of the existing system.

C. Size of the change.

D. All of the above.

### Q8. What should be tested when an operational environment is migrated?

A. Only the changed software.

B. Only the new environment.

C. The new environment, changed software and potentially data conversion.

D. Only the user interface.

### Q9. Which of the following may require testing when an application is retired?

A. Data archiving.

B. Data restoration.

C. Data retrieval.

D. All of the above.

### Q10. Which statement about maintenance testing is correct?

A. It is required only for corrective changes.

B. It can be triggered by modifications, environment changes and retirement.

C. It is unnecessary when the application is already in production.

D. It only tests new functionality.

### Q11. What is a hot fix?

A. A planned feature enhancement.

B. An urgent software change, usually released outside the normal release cycle.

C. A database migration.

D. A data archiving procedure.

### Q12. What is the primary focus of adaptive maintenance?

A. Fixing existing functional defects.

B. Adapting software to changes in its operational environment.

C. Improving code readability only.

D. Retiring the application.

### Q13. What is the purpose of regression testing during maintenance?

A. To confirm only that the original defect has been fixed.

B. To ensure that a change has not adversely affected existing functionality.

C. To test only newly introduced features.

D. To validate the retirement of a system.

### Q14. Which statement about impact analysis is correct?

A. It identifies which parts of the system could be affected by a change.

B. It guarantees that no regression defects will occur.

C. It is performed only after deployment.

D. It replaces confirmation testing.

### Q15. Which of the following is NOT one of the three maintenance testing triggers described in this module?

A. Modifications.

B. Upgrades or migrations of the operational environment.

C. Retirement.

D. Initial development of a completely new system.

---

## Section B – Implementation-Oriented and Scenario-Based MCQs

### Q16. Production Hot Fix

A production payment application experiences a critical defect. The development team releases an urgent fix outside the planned release schedule.

What type of maintenance trigger is this?

A. Planned enhancement.

B. Hot fix.

C. System retirement.

D. Environment migration.

### Q17. Database Migration

An organization migrates its application database from Oracle to PostgreSQL.

Which testing activities are particularly relevant?

A. Only UI testing.

B. Data conversion, database compatibility and application testing.

C. Only unit testing.

D. Only acceptance testing.

### Q18. Impact Analysis

A developer changes a shared authentication component used by five different applications.

What should the test team do first to determine the scope of regression testing?

A. Execute every test case without analyzing the change.

B. Perform impact analysis to identify affected applications and dependencies.

C. Test only the authentication screen.

D. Skip regression testing because the component was already tested.

### Q19. Application Retirement

An organization retires an old payroll system but must preserve employee records for seven years.

Which testing activity is most relevant?

A. Load testing of the retired application.

B. Testing data archiving, retrieval and restoration procedures.

C. Testing new feature development.

D. Testing UI responsiveness.

### Q20. Planned Enhancement

An e-commerce application introduces a new loyalty-points feature.

Which activity is most appropriate?

A. Test only the loyalty-points feature.

B. Test the new feature and perform appropriate regression testing on existing functionality.

C. Skip regression testing because the feature is new.

D. Test only the database.

### Q21. Operational Environment Upgrade

A company upgrades the operating system on which its application runs.

Which statement is most accurate?

A. Maintenance testing is unnecessary because application code has not changed.

B. Testing should evaluate compatibility with the new operational environment.

C. Only source-code review is required.

D. Only acceptance testing is required.

### Q22. Change Risk

A small change is made to a critical payment calculation module.

Although the code change is small, the business risk is high.

How should the testing team approach the scope of maintenance testing?

A. Perform minimal testing because the change is small.

B. Consider the high risk and perform appropriate testing.

C. Skip regression testing.

D. Test only the modified line of code.

### Q23. Regression Scope

A change is made to a shared API used by multiple microservices.

Which factor should influence the regression testing scope?

A. Only the number of changed lines.

B. The potential impact on dependent services and interfaces.

C. Only the developer who made the change.

D. Only the deployment date.

### Q24. Preventive Maintenance

A development team refactors complex code to reduce the likelihood of future defects.

Which maintenance category does this represent?

A. Corrective.

B. Adaptive.

C. Perfective.

D. Preventive.

### Q25. Perfective Maintenance

A company optimizes database queries to improve application response time and maintainability.

Which maintenance category is most appropriate?

A. Corrective.

B. Adaptive.

C. Perfective.

D. Retirement.

### Q26. Data Conversion

During a migration, data from an old application is transferred into a new application.

Which testing activity is especially important?

A. Data conversion and data integrity testing.

B. Only UI testing.

C. Only performance testing.

D. Only unit testing.

### Q27. Maintenance Testing Scope

A minor change is made to a very large system with many dependencies.

Which factors should be considered when deciding the scope of maintenance testing?

A. Only the size of the code change.

B. Risk of the change, size of the existing system and size of the change.

C. Only the number of developers.

D. Only the time available for testing.

### Q28. Confirmation vs Regression

A defect in a login feature is fixed.

The tester:

1. Re-executes the previously failing login test.
2. Tests other affected features to ensure the change has not introduced new problems.

Which statement is correct?

A. Both activities are confirmation testing.

B. The first is confirmation testing; the second is regression testing.

C. The first is regression testing; the second is confirmation testing.

D. Both activities are maintenance planning.

### Q29. Unchanged Functionality

A new discount feature is introduced in an e-commerce application. Existing checkout and payment features are not modified directly.

Why should they still be tested?

A. Because maintenance testing must only test unchanged components.

B. Because changes can adversely affect unchanged parts of the system.

C. Because unchanged components always contain defects.

D. Because regression testing is mandatory for every single line of code.

### Q30. Multiple Maintenance Triggers

An organization performs the following activities:

1. Fixes a production defect.
2. Migrates its database platform.
3. Retires an old application and archives its data.

Which statement is correct?

A. Only activity 1 requires maintenance testing.

B. Activities 1 and 2 require maintenance testing.

C. All three activities can trigger maintenance testing.

D. None of the activities require maintenance testing.

---

# 14. Answer Key – Section A

| Question | Answer | Concept |
|---|---|---|
| Q1 | B | Maintenance testing purpose |
| Q2 | D | Maintenance triggers |
| Q3 | B | Corrective maintenance |
| Q4 | B | Adaptive maintenance |
| Q5 | B | Impact analysis |
| Q6 | C | Hot fix |
| Q7 | D | Maintenance testing scope |
| Q8 | C | Environment migration |
| Q9 | D | System retirement |
| Q10 | B | Maintenance testing triggers |
| Q11 | B | Hot fix |
| Q12 | B | Adaptive maintenance |
| Q13 | B | Regression testing |
| Q14 | A | Impact analysis |
| Q15 | D | Maintenance testing triggers |

## Section A – Explanations

**Q1 – B:** Maintenance testing evaluates changes to an existing system and checks whether existing functionality has been affected.

**Q2 – D:** Modifications, environment upgrades or migrations and system retirement are all maintenance testing triggers.

**Q3 – B:** Corrective maintenance involves fixing defects in existing software.

**Q4 – B:** Adaptive maintenance modifies software to accommodate environmental changes.

**Q5 – B:** Impact analysis identifies potential consequences of a change in other areas of the system.

**Q6 – C:** An emergency hot fix is an example of unplanned maintenance.

**Q7 – D:** The scope depends on the risk of the change, size of the existing system and size of the change.

**Q8 – C:** Migration may require testing the new environment, changed software and data conversion.

**Q9 – D:** Retirement can require testing archiving, restoration and retrieval procedures.

**Q10 – B:** All three categories are maintenance testing triggers.

**Q11 – B:** A hot fix is an urgent change, usually released outside the normal release cycle.

**Q12 – B:** Adaptive maintenance addresses changes in the operational environment.

**Q13 – B:** Regression testing checks that changes have not caused adverse effects in existing functionality.

**Q14 – A:** Impact analysis helps identify potentially affected areas and determine the testing scope.

**Q15 – D:** Initial development of a completely new system is not one of the three maintenance triggers described here.

---

# 15. Answer Key – Section B

| Question | Answer | Concept |
|---|---|---|
| Q16 | B | Hot fix |
| Q17 | B | Database migration |
| Q18 | B | Impact analysis |
| Q19 | B | System retirement |
| Q20 | B | Enhancement and regression |
| Q21 | B | Environment upgrade |
| Q22 | B | Risk-based maintenance testing |
| Q23 | B | Dependencies and impact |
| Q24 | D | Preventive maintenance |
| Q25 | C | Perfective maintenance |
| Q26 | A | Data conversion |
| Q27 | B | Scope of maintenance testing |
| Q28 | B | Confirmation vs regression |
| Q29 | B | Regression testing |
| Q30 | C | Maintenance triggers |

## Section B – Detailed Explanations

**Q16 – B:** A critical production fix released urgently outside the normal release schedule is a hot fix.

**Q17 – B:** Database migration requires checking data conversion, data integrity, compatibility and application behavior.

**Q18 – B:** Impact analysis identifies affected applications, dependencies and interfaces before the team determines the regression scope.

**Q19 – B:** Retirement may require testing data archiving, retrieval and restoration procedures.

**Q20 – B:** The new loyalty-points feature requires testing, but existing checkout and payment functionality should also be checked for regressions.

**Q21 – B:** An operating system upgrade changes the operational environment and can trigger maintenance testing even if application code is unchanged.

**Q22 – B:** A small code change can have high business risk. Testing scope should consider risk rather than code size alone.

**Q23 – B:** Shared APIs can affect multiple dependent services. Their potential impact should guide regression testing.

**Q24 – D:** Refactoring to reduce the possibility of future problems is preventive maintenance.

**Q25 – C:** Improving performance and maintainability is perfective maintenance.

**Q26 – A:** Data conversion and data integrity are important when migrating data between applications or platforms.

**Q27 – B:** All three factors influence the scope of maintenance testing.

**Q28 – B:** Repeating the previously failing test verifies the fix (confirmation testing). Testing other affected functionality checks for regressions.

**Q29 – B:** A change can affect components that were not directly modified. Regression testing helps detect such adverse consequences.

**Q30 – C:** Defect fixes, environment migrations and system retirement can all trigger maintenance testing.

---

# 16. Last-Minute Revision Checklist

Before moving to the next chapter, ensure that you can:

- [ ] Define maintenance testing.
- [ ] Explain why maintenance testing is required.
- [ ] Differentiate corrective, adaptive, perfective and preventive maintenance.
- [ ] Explain planned and unplanned maintenance.
- [ ] Define a hot fix.
- [ ] Explain impact analysis and its purpose.
- [ ] Explain why unchanged functionality must also be tested.
- [ ] Identify the three maintenance testing triggers.
- [ ] Explain testing requirements during environment upgrades and migrations.
- [ ] Explain why retirement requires testing.
- [ ] Identify the three factors influencing maintenance testing scope.
- [ ] Differentiate confirmation testing and regression testing.

---

# 17. Self-Assessment

| Score | Assessment |
|---|---|
| 27–30 | Excellent – Strong understanding |
| 24–26 | Good – Revise incorrect concepts |
| 20–23 | Average – Revisit scenario-based questions |
| 15–19 | Needs improvement – Revise the module |
| Below 15 | Re-study the module before proceeding |

**High-priority exam areas:**

1. Three maintenance testing triggers.
2. Impact analysis.
3. Scope of maintenance testing.
4. Corrective, adaptive, perfective and preventive maintenance.
5. Data archiving and migration.
6. Confirmation testing vs regression testing.
