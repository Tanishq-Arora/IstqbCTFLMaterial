2.3 Maintenance Testing
1. Learning Objectives
   By the end of this topic, you should be able to:
- Explain what maintenance testing is and why it is needed.
- Identify the common triggers for maintenance testing.
- Understand the different categories of maintenance.
- Explain the role of impact analysis.
- Identify factors that influence the scope of maintenance testing.
- Differentiate testing of a change from regression testing of the
  unchanged parts of a system.
2. What is Maintenance Testing?
   Definition: Maintenance testing is testing performed on an existing
   software system after it has been delivered and put into operation, when
   changes are made to it or when it is being retired.

Maintenance testing may be required because of:
- Modifications to the software.
- Changes in the operational environment.
- Retirement of the system.
  The purpose is to evaluate the success of the changes and to check that
  the changes have not caused unintended effects in parts of the system
  that remain unchanged.
  Example
  A banking application is already live in production.

A new feature is introduced to support international fund transfers.

The testing team must:
1. Test the new international transfer functionality.
2. Verify that the existing domestic transfer functionality still
   works.
3. Check whether other affected features, such as transaction history
   and account balance updates, continue to work correctly.
   This is maintenance testing.

Remember: Maintenance testing is performed on an existing system,
not only during initial development.
3. Categories of Maintenance
   Maintenance can be performed for different reasons. The important
   categories include:
   3.1 Corrective Maintenance
   Performed to correct defects discovered after the software has been
   delivered.

Example: A production application calculates tax incorrectly. A
hotfix is released to correct the calculation.
3.2 Adaptive Maintenance
Performed to adapt the software to changes in its operational
environment.

Example: - Migrating an application to a new operating system. -
Updating an application to work with a new database version. - Adapting
software to a new browser or platform.
3.3 Perfective Maintenance
Performed to improve performance, maintainability, or other aspects of
the software.

Example: - Optimizing a slow database query. - Improving application
response time. - Refactoring code to make future maintenance easier.
3.4 Preventive Maintenance
Performed to reduce the likelihood of future problems and improve the
maintainability or reliability of the system.

Example: Refactoring a fragile module or updating an outdated
dependency before it causes production failures.
Category                Main purpose            Example
Corrective              Fix an existing defect  Hotfix for incorrect
tax calculation

Adaptive                Adapt to environment    Migration to a new
changes                 operating system

Perfective              Improve performance or  Optimize a slow query
maintainability         
Preventive              Reduce future risk or   Refactor fragile code
avoid potential
problems
Exam trap: Read the reason for the change carefully. - Fixing an
existing defect → Corrective. - Adapting to a changed environment →
Adaptive. - Improving performance or maintainability → Perfective. -
Reducing the likelihood of future problems → Preventive.
4. Triggers for Maintenance Testing
   Maintenance and maintenance testing may be triggered by three major
   situations.
   4.1 Modifications
   Modifications may include:
- Planned enhancements (release-based changes).
- Corrective changes.
- Hot fixes.
  Example: A company adds a new payment method to its existing
  application. Testing is required for the new functionality and for
  possible side effects on existing payment methods.
  4.2 Upgrades or Migrations of the Operational Environment
  Changes to the operational environment may include moving from one
  platform to another.

This may require:
- Testing the changed software in the new environment.
- Testing compatibility with the new environment.
- Testing data conversion when data from another application is
  migrated into the maintained system.
  Example: An application is migrated from an on-premises database to
  a cloud database. Testing must cover the migrated application, the new
  environment, and the correctness of converted data.
  4.3 Retirement
  Maintenance testing may also be required when an application reaches the
  end of its life and is retired.

This may require:
- Testing data archiving.
- Checking that long-term data-retention requirements are met.
- Testing restoration procedures.
- Testing retrieval procedures to ensure archived data can be accessed
  when required.
  Example: A company retires an old payroll application but must
  retain employee salary records for a legally required retention period.
  The team tests whether records are archived and can be retrieved when
  needed.
  Quick comparison of triggers
  Trigger                 What causes it?         Example
  Modification            A change or fix to the  New feature or hotfix
  existing software

  Upgrade / Migration     A change in the         New OS, platform,
  operational environment database, or data
  or movement of data     conversion
  Retirement              The system reaches end  Archiving and
  of life                 retrieving historical
  records
  Exam trap: Retirement does not mean that no testing is needed. Data
  archiving, restoration, and retrieval may still need to be tested.
5. What Does Maintenance Testing Cover?
   Maintenance testing generally includes two important aspects:
   5.1 Testing the Change
   Evaluate whether the modification has been implemented successfully.

Examples: - Does the new feature work? - Has the reported defect been
fixed? - Does the application work in the upgraded environment? - Has
data been converted correctly?
5.2 Testing for Regression
Check for possible regressions in parts of the system that remain
unchanged.

A change may affect other parts of the application even when those parts
were not directly modified.

Example: A change to the payment calculation module may
unintentionally affect: - Order totals. - Invoices. - Refund
calculations. - Transaction reports.

Therefore, maintenance testing includes testing the change as well as
checking for unintended consequences in unchanged areas.

Important distinction:
- Testing the changed functionality checks whether the change works.
- Regression testing checks whether the change has adversely affected
  existing functionality.
6. Impact Analysis
   Definition: Impact analysis is performed before a change is made to
   help determine whether the change should be implemented, based on its
   potential consequences in other areas of the system.

It helps identify which parts of the system may be affected by a
proposed change.
Why is impact analysis important?
1. Identifies areas that may be affected by a change.
2. Helps estimate the scope of testing.
3. Helps identify potential risks.
4. Supports decisions about whether a change should be made.
5. Helps select relevant regression tests.
   Example
   A team plans to modify a shared authentication service.

Impact analysis may identify these dependent areas:
- Login.
- Password reset.
- Session management.
- Multi-factor authentication.
- API authentication.
  The test team can use this information to plan appropriate testing.

Exam trap: Impact analysis is not itself the execution of regression
tests. It is an analysis activity used to understand possible
consequences and guide decisions and test scope.
7. Factors That Determine the Scope of Maintenance Testing
   The scope of maintenance testing typically depends on three factors:
   7.1 Degree of Risk of the Change
   A high-risk change may require more extensive testing.

Example: Changing the payment processing logic is likely to require
broader testing than changing the text on a help page.
7.2 Size of the Existing System
A larger system may have more components, dependencies, and interactions
that could be affected.

Example: A change to a shared service in a large banking platform
may require testing several dependent modules.
7.3 Size of the Change
A larger change may affect more functionality and require a wider test
scope.

Example: Replacing an entire authentication module is likely to
require more testing than correcting a small label.
Factor                              What to consider
Risk of the change                  How serious are the possible
consequences?

Size of the existing system         How large and interconnected is the
system?
Size of the change                  How much functionality or code is
being changed?
Memory aid: Maintenance test scope = Risk + Existing system size +
Change size.

Exam trap: Do not confuse the size of the existing system with the
size of the change. They are separate factors.
8. Planned Releases vs Unplanned Releases
   Maintenance can involve both planned and unplanned releases or
   deployments.
   Planned release / deployment        Unplanned release / deployment
   Scheduled and prepared in advance   Usually performed urgently

Often includes planned enhancements Often includes urgent corrective
changes
Example: Scheduled feature release  Example: Production hotfix
A hotfix is an example of an unplanned release or deployment used to
address an urgent issue.

Important: Both planned and unplanned maintenance changes require
appropriate testing.
9. Maintenance Testing vs Development Testing
   Development testing                 Maintenance testing
   Performed while the software is     Performed on an existing system
   being developed                     after delivery

Tests newly developed software and  Tests changes to an operational or
components                          existing system

Focuses on verifying the system     Focuses on validating changes and
during development                  checking for regressions
Example: Testing a newly developed  Example: Testing a production login
login module                        module after a security fix
10. Maintenance Testing --- End-to-End Example
    Consider a live e-commerce application.

The organization makes the following changes:
1. Adds a new payment gateway.
2. Migrates the application to a new cloud platform.
3. Retires an old order management module.
   The maintenance testing activities may include:
   Change                              Testing required
   New payment gateway                 Test the new integration and check
   existing payment methods for
   regressions

Cloud migration                     Test compatibility, application
behavior, and data migration
Retirement of old module            Test data archiving, restoration,
and retrieval
This example demonstrates that maintenance testing is not limited to
fixing defects. It also applies to enhancements, environment changes,
migrations, and retirement.
11. Exam Traps and Important Distinctions
    Statement                           Correct understanding
    Maintenance testing is performed on Correct
    an existing system

Maintenance testing is required     Incorrect
only for defect fixes

Planned enhancements can trigger    Correct
maintenance testing

Hotfixes can trigger maintenance    Correct
testing

Environment upgrades or migrations  Correct
can trigger maintenance testing

Retirement can require testing      Correct

Data archiving and retrieval may    Correct
need testing during retirement

Maintenance testing checks only the Incorrect
changed functionality

Regression testing may be needed    Correct
for unchanged parts of the system

Impact analysis can help decide     Correct
whether a change should be made

Impact analysis identifies possible Correct
consequences in other areas         
The scope depends on risk, existing Correct
system size, and change size
12. High-Value Revision Table
    Term                                One-line revision
    Maintenance Testing                 Testing an existing system after
    changes or during retirement

Corrective Maintenance              Fixing defects

Adaptive Maintenance                Adapting to environment changes

Perfective Maintenance              Improving performance or
maintainability

Preventive Maintenance              Reducing future problems or risks

Modification                        Planned enhancement, corrective
change, or hotfix

Upgrade / Migration                 Change in operational environment
or movement of data

Retirement                          End-of-life activities, including
data archiving

Impact Analysis                     Assessing possible consequences of
a change

Regression Testing                  Checking for adverse effects in
unchanged areas
Maintenance Test Scope              Influenced by risk, existing system
size, and change size
13. Practice MCQs --- Foundational (10 Questions)
    Q1. What is the primary context in which maintenance testing is performed?
    A. Before requirements are documented
    B. On an existing system after delivery when changes are made or the
    system is retired
    C. Only during component development
    D. Only before the first production release
    Q2. Which of the following is a trigger for maintenance testing?
    A. Only new software development
    B. Modifications to an existing system
    C. Only creation of test cases
    D. Only unit testing
    Q3. Which maintenance category involves fixing defects discovered after delivery?
    A. Adaptive
    B. Perfective
    C. Corrective
    D. Preventive
    Q4. Updating an application to work with a new operating system is an example of:
    A. Corrective maintenance
    B. Adaptive maintenance
    C. Retirement
    D. User acceptance testing
    Q5. Improving application performance by optimizing database queries is an example of:
    A. Perfective maintenance
    B. Corrective maintenance
    C. Retirement
    D. System integration testing
    Q6. Which of the following is an example of a maintenance testing trigger related to retirement?
    A. Adding a new feature
    B. Fixing a production defect
    C. Testing data archiving and retrieval
    D. Migrating to a new operating system
    Q7. What is the purpose of impact analysis?
    A. To execute all regression tests
    B. To identify possible consequences of a change in other areas of the
    system
    C. To confirm that a defect has been fixed
    D. To replace maintenance testing
    Q8. Which of the following is NOT one of the stated factors affecting the scope of maintenance testing?
    A. Degree of risk of the change
    B. Size of the existing system
    C. Size of the change
    D. Number of developers assigned to the project
    Q9. Maintenance testing after a software change should include:
    A. Only testing the changed functionality
    B. Only testing unchanged functionality
    C. Testing the change and checking for possible regressions
    D. Only performance testing
    Q10. Which type of release is commonly associated with an urgent production correction?
    A. Planned feature release
    B. Hotfix
    C. Retirement release only
    D. Beta release
14. Practice MCQs --- Scenario-Based (15 Questions)
    Q11.
    A production application calculates interest incorrectly. The
    development team releases an urgent fix to correct the calculation.

Which maintenance category best describes this change?

A. Adaptive
B. Corrective
C. Perfective
D. Preventive
Q12.
A company moves its application from an older operating system to a
newer platform. The team tests compatibility with the new environment.

Which maintenance category is most relevant?

A. Corrective
B. Adaptive
C. Perfective
D. Preventive
Q13.
A development team optimizes database queries to improve application
response time.

Which maintenance category is most appropriate?

A. Corrective
B. Adaptive
C. Perfective
D. Retirement
Q14.
A team refactors a fragile module to reduce the likelihood of future
failures, even though no current defect has been reported.

Which maintenance category is most appropriate?

A. Corrective
B. Adaptive
C. Perfective
D. Preventive
Q15.
An organization introduces a new feature in an application that has been
running in production for two years.

Which testing activity is required?

A. Only initial development testing
B. Maintenance testing
C. Only static testing
D. No testing because the application is already live
Q16.
A company migrates customer records from an old application into a
system being maintained. The team checks whether the converted data is
correct.

Which maintenance trigger is involved?

A. Retirement only
B. Upgrade or migration
C. Corrective change
D. Planned enhancement only
Q17.
A company is retiring an old application but must preserve its records.
The team checks whether archived records can be restored and retrieved.

Which maintenance trigger is involved?

A. Modification
B. Upgrade
C. Retirement
D. Perfective maintenance
Q18.
Before modifying a shared payment service, a tester identifies that the
service is used by checkout, refunds, and subscription renewals.

Which activity is being performed?

A. Confirmation testing
B. Impact analysis
C. Acceptance testing
D. Alpha testing
Q19.
A change is made to the discount calculation. The tester verifies that
the new discount rule works correctly.

What is the primary focus of this testing?

A. Testing the change
B. Testing system retirement
C. Testing only the operational environment
D. Testing data archiving
Q20.
After a change to the discount calculation, the tester checks whether
existing tax calculation and invoice generation still work correctly.

What is the primary purpose of this testing?

A. Confirmation testing only
B. Regression testing
C. Alpha testing
D. Regulatory acceptance testing
Q21.
A minor change is proposed in a very large and highly interconnected
application. The team decides to assess the risk before deciding the
test scope.

Which statement is correct?

A. Only the size of the code change matters
B. Only the number of testers matters
C. Risk, existing system size, and change size can influence maintenance
test scope
D. Maintenance testing scope is always fixed
Q22.
A team releases a planned enhancement in a scheduled release. The team
tests the new feature and checks unchanged functionality for
regressions.

Which statement is correct?

A. Maintenance testing applies only to unplanned hotfixes
B. Planned enhancements can trigger maintenance testing
C. Regression testing is unnecessary for planned releases
D. Maintenance testing applies only during retirement
Q23.
A production issue requires an urgent deployment outside the planned
release schedule.

Which term best describes this type of deployment?

A. Hotfix
B. Beta release
C. Alpha release
D. Retirement
Q24.
An application is migrated to a new platform. The team tests the
modified application in the new environment and also checks that
existing functionality remains correct.

Which statement best describes the testing?

A. Only component testing is required
B. Maintenance testing includes testing the change and checking for
regressions
C. Only acceptance testing is required
D. Regression testing is not relevant to migrations
Q25.
A system is being retired. The organization must retain historical
records for several years and ensure that the records can be accessed
when required.

Which testing is especially relevant?

A. Data archiving and retrieval testing
B. Only load testing
C. Only component integration testing
D. Only alpha testing
15. Answer Key --- Foundational Questions
    Question                Answer                  Explanation
    Q1                      B                       Maintenance testing
    concerns an existing
    system after delivery
    when it changes or is
    retired.

Q2                      B                       Modifications are a
major trigger for
maintenance testing.

Q3                      C                       Corrective maintenance
fixes defects.

Q4                      B                       Adapting to a new
operating environment
is adaptive
maintenance.

Q5                      A                       Improving performance
is perfective
maintenance.

Q6                      C                       Retirement may require
testing archiving and
retrieval procedures.

Q7                      B                       Impact analysis
identifies possible
consequences of a
change.

Q8                      D                       The stated factors are
risk, existing system
size, and change size.

Q9                      C                       Maintenance testing
checks the change and
possible regressions.
Q10                     B                       A hotfix is an urgent
correction.
16. Answer Key --- Scenario-Based Questions
    Question                Answer                  Explanation
    Q11                     B                       The change corrects a
    defect in production.

Q12                     B                       The software is being
adapted to a changed
environment.

Q13                     C                       Query optimization
improves performance.

Q14                     D                       The refactoring aims to
reduce future problems.

Q15                     B                       Changes to an existing
production system
trigger maintenance
testing.

Q16                     B                       Data conversion during
migration is part of an
upgrade/migration
trigger.

Q17                     C                       The application is
being retired and
archived data must
remain accessible.

Q18                     B                       The tester identifies
areas potentially
affected by a proposed
change.

Q19                     A                       The tester is checking
whether the new change
works.

Q20                     B                       The tester checks
unchanged functionality
for side effects.

Q21                     C                       All three stated
factors can influence
test scope.

Q22                     B                       Planned enhancements
can trigger maintenance
testing.

Q23                     A                       An urgent production
deployment is commonly
a hotfix.

Q24                     B                       Maintenance testing
includes testing the
change and checking for
regressions.
Q25                     A                       Retirement can require
archiving, restoration,
and retrieval testing.
17. Final Revision Checklist
- [ ] Explain maintenance testing in your own words.
- [ ] Identify the four categories of maintenance.
- [ ] Differentiate corrective, adaptive, perfective, and preventive
  maintenance.
- [ ] Identify modifications, upgrades/migrations, and retirement as
  maintenance triggers.
- [ ] Explain why a hotfix requires testing.
- [ ] Explain why data conversion may need testing during migration.
- [ ] Explain why archiving and retrieval need testing during
  retirement.
- [ ] Explain impact analysis and when it is performed.
- [ ] Identify the three factors that influence maintenance testing
  scope.
- [ ] Explain why maintenance testing includes testing the change and
  regression testing.
18. Last-Minute Memory Map
    If the question mentions...                Think of...
    Fixing a production defect                 Corrective maintenance
    Adapting to a new OS/platform              Adaptive maintenance
    Improving performance or maintainability   Perfective maintenance
    Reducing future problems                   Preventive maintenance
    Planned enhancement or hotfix              Modification trigger
    New platform or data conversion            Upgrade / migration trigger
    End of life, archive, restore, retrieve    Retirement trigger
    Assessing consequences before a change     Impact analysis
    Testing the new or modified behavior       Testing the change
    Checking unchanged functionality           Regression testing
    Risk, system size, change size             Maintenance testing scope
    Source note: These notes are based primarily on the screenshots
    provided. Explanatory examples and practice questions are added for
    learning; the MCQs are original revision questions, not official ISTQB
    examination questions or verified past-paper questions.