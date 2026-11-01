# 4.2 Black-Box Test Techniques
**ISTQB CTFL v4.0.1 — Chapter 4: Test Analysis and Design**

**Scope:** Equivalence Partitioning, Boundary Value Analysis, Decision Table Testing and State Transition Testing.

---

# 1. Learning Objectives

| Learning Objective | K-Level | What You Must Know |
|---|---|---|
| FL-4.2.1 | K3 | Use Equivalence Partitioning to derive test cases |
| FL-4.2.2 | K3 | Use Boundary Value Analysis to derive test cases |
| FL-4.2.3 | K3 | Use Decision Table Testing to derive test cases |
| FL-4.2.4 | K3 | Use State Transition Testing to derive test cases |

**Important:** All four techniques are black-box (specification-based) test techniques.

K3 means you should be able to apply the technique, not merely recall its definition.

---

# 2. Equivalence Partitioning (EP)

## 2.1 Definition

Equivalence Partitioning is a black-box test technique in which input data is divided into groups called **equivalence partitions or equivalence classes**.

The values within a partition are expected to be processed in the same way by the system.

Therefore, testing one representative value from each partition is generally sufficient to provide coverage of that partition.

### Why Do We Use EP?

Suppose an application accepts an age between 18 and 60.

Testing every possible age would be unnecessary.

Instead, we divide the inputs into groups:

- Age below 18.
- Age between 18 and 60.
- Age above 60.

We select representative values from these partitions.

This reduces the number of test cases while maintaining systematic test coverage.

## 2.2 Types of Equivalence Partitions

There are two types:

1. Valid equivalence partitions.
2. Invalid equivalence partitions.

### A. Valid Equivalence Partition

A valid equivalence partition contains values that the system is expected to accept.

Example:

An application accepts ages from 18 to 60, inclusive.

Valid partition:

`18–60`

Representative test value: `30`

### B. Invalid Equivalence Partition

An invalid equivalence partition contains values that the system is expected to reject.

For the same age requirement:

- Values below 18.
- Values above 60.

Representative test values:

- `17`
- `61`

## 2.3 Example: Integer Field Accepting Values Between 1 and 15

**Requirement:** An integer field shall contain values between and including 1 and 15.

Identify the equivalence partitions:

| Partition | Input Range | Classification | Representative Value |
|---|---|---|---:|
| EP1 | Less than 1 | Invalid | 0 |
| EP2 | 1–15 | Valid | 8 |
| EP3 | Greater than 15 | Invalid | 16 |

<Diagram in words>

`Invalid (<1) | Valid (1–15) | Invalid (>15)`

### Minimum Number of Test Cases

There are three equivalence partitions.

One representative value from each partition:

1. Test Case 1: 0
2. Test Case 2: 8
3. Test Case 3: 16

**Answer: 3 test cases.**

### Exam Trap

Do not confuse the number of possible input values with the number of equivalence partitions.

For the range 1–15, there are 15 valid integer values, but only one valid equivalence partition.

## 2.4 Example: Identifying Correct Equivalence Classes

Requirement:

An integer field accepts values from 1 to 15, inclusive.

Which collection represents the correct equivalence partitions?

A. Less than 1, 1 through 15, more than 15.

B. Negative numbers, 1 through 15, above 15.

C. Less than 1, 1 through 14, more than 15.

D. Less than 0, 1 through 14, 15 and more than 15.

**Correct Answer: A**

Explanation:

The correct partitions must cover the entire input domain without gaps or overlaps:

- Invalid: x < 1
- Valid: 1 ≤ x ≤ 15
- Invalid: x > 15

Option B does not correctly classify values between 0 and 1 if non-integer values are possible. The requirement specifies an integer field, but the partition definition should still represent the entire invalid lower range.

Option C excludes 15 from the valid partition.

Option D incorrectly separates 15 from the other valid values.

## 2.5 Example: Tax Calculation System

Consider a tax calculation system with these rules:

- First £4,000: Tax-free.
- Next £1,500: Taxed at 10%.
- Next £28,000: Taxed at 22%.
- Any further amount: Taxed at 40%.

For the purpose of this example, assume the input is a positive whole-pound salary amount.

### Step 1: Identify the Partitions

| Partition | Salary Range | Tax Treatment |
|---|---|---|
| EP1 | £1–£4,000 | Tax-free |
| EP2 | £4,001–£5,500 | 10% |
| EP3 | £5,501–£33,500 | 22% |
| EP4 | Above £33,500 | 40% |

### Step 2: Select Representative Values

| Partition | Representative Value |
|---|---:|
| EP1 | £2,000 |
| EP2 | £5,000 |
| EP3 | £20,000 |
| EP4 | £40,000 |

### Practice Question

Which group of numbers belongs to the same equivalence partition?

A. £4,800; £14,000; £28,000

B. £5,200; £5,500; £28,000

C. £28,001; £32,000; £35,000

D. £5,800; £28,000; £32,000

**Correct Answer: D**

Explanation:

All three values in option D belong to EP3:

`£5,501–£33,500`

- £5,800 → 22%
- £28,000 → 22%
- £32,000 → 22%

They are processed using the same tax rate.

**Important:** EPs are defined by expected system behaviour, not merely by whether values look numerically similar.

## 2.6 EP with Multiple Input Conditions

This is an important examination concept.

When a test case contains multiple input parameters, you should consider the equivalence partitions of each input parameter.

Where possible, one test case can cover one partition from each input parameter.

The minimum number of test cases is not necessarily the total number of partitions across all parameters.

### Example: Apartment Search Application

A simplified apartment search form has two criteria:

**Input 1: Floor**

- Ground floor.
- First floor.
- Second floor or higher.

**Input 2: Garden Type**

- No garden.
- Small garden.
- Large garden.

Business rule:

Only ground-floor apartments have gardens.

The application does not allow combinations that violate this rule.

### Step 1: Identify the Partitions

| Input | Equivalence Partition |
|---|---|
| Floor | Ground floor |
| Floor | First floor |
| Floor | Second floor or higher |
| Garden | No garden |
| Garden | Small garden |
| Garden | Large garden |

### Step 2: Identify Valid Combinations

| Test Case | Floor | Garden Type | Validity |
|---|---|---|---|
| TC01 | Ground floor | No garden | Valid |
| TC02 | Ground floor | Small garden | Valid |
| TC03 | Ground floor | Large garden | Valid |
| TC04 | First floor | No garden | Valid |
| TC05 | Second floor or higher | No garden | Valid |

### Step 3: Determine Minimum Test Cases

We must cover:

- All three floor partitions.
- All three garden partitions.

The three ground-floor test cases cover all three garden partitions.

However, we still need to cover:

- First floor.
- Second floor or higher.

Therefore:

**Minimum test cases = 5**

### Exam Trap

Do not simply add the number of partitions:

3 floor partitions + 3 garden partitions = 6.

That is incorrect because one test case can cover one partition from each input parameter simultaneously.

Also, do not create invalid combinations when the system's validation rules prohibit them.

## 2.7 Example: Flight Booking Application

Consider an airline booking application with these restrictions:

1. Only airline staff can book flights.
2. Flights can be booked only on weekdays (Monday–Friday).
3. Booking is allowed only between 9 AM and 5 PM.

Each test case contains inputs for all three conditions.

### Step 1: Identify the Equivalence Partitions

| Input | Valid Partition | Invalid Partition |
|---|---|---|
| User | Airline staff | Non-staff |
| Day | Weekday | Weekend |
| Time | 9 AM–5 PM | Before 9 AM or after 5 PM |

### Step 2: Cover All Partitions

We need to exercise both partitions for every input.

Example test cases:

| Test Case | User | Day | Time |
|---|---|---|---|
| TC01 | Staff | Monday | 10 AM |
| TC02 | Non-staff | Saturday | 7 PM |

Coverage:

- Staff: TC01
- Non-staff: TC02
- Weekday: TC01
- Weekend: TC02
- Valid time: TC01
- Invalid time: TC02

**Minimum test cases = 2**, assuming these representative combinations are supported by the specification and the goal is to cover every partition of every input.

### Important Clarification

EP coverage is measured for each identified input partition.

A test case can cover multiple partitions simultaneously, but it must use a valid, meaningful combination of inputs.

---

# 3. Boundary Value Analysis (BVA)

## 3.1 Definition

Boundary Value Analysis is a black-box test technique in which test cases are designed around the boundaries of equivalence partitions.

Defects frequently occur near boundaries because developers may incorrectly implement:

- Less than versus less than or equal to.
- Greater than versus greater than or equal to.
- Minimum and maximum limits.
- Off-by-one conditions.

BVA focuses on these boundary areas.

### Why Is BVA Important?

Suppose a field accepts ages between 18 and 30.

A developer accidentally writes:

```java
if (age > 18 && age < 30)
```

Instead of:

```java
if (age >= 18 && age <= 30)
```

The values 18 and 30 will be incorrectly rejected.

Testing only an ordinary value such as 25 will not identify this defect.

BVA helps detect such issues.

## 3.2 Boundary Terminology

For a valid input range:

`18–30`

| Term | Meaning | Value |
|---|---|---:|
| LB | Lower Boundary | 18 |
| RB | Upper Boundary | 30 |
| LB-1 | Value immediately below lower boundary | 17 |
| LB+1 | Value immediately above lower boundary | 19 |
| RB-1 | Value immediately below upper boundary | 29 |
| RB+1 | Value immediately above upper boundary | 31 |

## 3.3 Types of BVA

There are two important variants:

1. Two-point Boundary Value Analysis.
2. Three-point Boundary Value Analysis.

## 3.4 Two-Point BVA (2-Point BVA)

Two-point BVA selects two values around each boundary:

- The boundary value.
- The immediately adjacent value on the other side of the boundary.

For a valid range from 18 to 30:

### Lower Boundary

- 17: Invalid.
- 18: Valid.

### Upper Boundary

- 30: Valid.
- 31: Invalid.

Therefore, the test values are:

`17, 18, 30, 31`

### Formula

For two boundaries:

`LB-1, LB, RB, RB+1`

### Diagram

`Invalid | 17 | 18 ... 30 | 31 | Invalid`

### Number of Test Values

For one valid range with two boundaries:

**2-point BVA = 4 values**

## 3.5 Three-Point BVA (3-Point BVA)

Three-point BVA selects three values around each boundary:

- The value immediately below the boundary.
- The boundary value.
- The value immediately above the boundary.

For the valid range 18–30:

### Lower Boundary

- 17: Invalid.
- 18: Valid.
- 19: Valid.

### Upper Boundary

- 29: Valid.
- 30: Valid.
- 31: Invalid.

Therefore, the test values are:

`17, 18, 19, 29, 30, 31`

### Formula

`LB-1, LB, LB+1`

`RB-1, RB, RB+1`

### Number of Test Values

For one valid range with two boundaries:

**3-point BVA = 6 values**

## 3.6 Comparison: 2-Point vs 3-Point BVA

| Basis | 2-Point BVA | 3-Point BVA |
|---|---|---|
| Values per boundary | 2 | 3 |
| Lower boundary | LB-1, LB | LB-1, LB, LB+1 |
| Upper boundary | RB, RB+1 | RB-1, RB, RB+1 |
| Values for range 18–30 | 17, 18, 30, 31 | 17, 18, 19, 29, 30, 31 |
| Coverage | Boundary and adjacent value across each boundary | Boundary and both adjacent values |
| Relative thoroughness | Lower | Higher |

**Exam Trap:** Do not confuse 2-point and 3-point BVA.

- 2-point: Two values around each boundary.
- 3-point: Three values around each boundary.

## 3.7 Example: Age Field

Requirement:

A text field accepts ages between 18 and 30, inclusive.

Question:

Using three-point BVA, what is the minimum number of test cases required for maximum boundary coverage?

A. 2

B. 6

C. 1

D. 4

**Correct Answer: B — 6**

Calculation:

Lower boundary = 18

- 17
- 18
- 19

Upper boundary = 30

- 29
- 30
- 31

Total = 6 test cases.

## 3.8 Example: Order Quantity

Requirement:

- Minimum quantity to place an order = 5.
- Additional 10% discount applies for orders of 100 or more.

Identify the partitions:

| Partition | Range | Expected Behaviour |
|---|---|---|
| EP1 | 1–4 | Order not allowed |
| EP2 | 5–99 | Order allowed without discount |
| EP3 | 100 and above | Order allowed with 10% discount |

### Apply 2-Point BVA

First boundary: 5

- 4: Invalid.
- 5: Valid.

Second boundary: 100

- 99: Valid.
- 100: Valid.

Therefore:

`4, 5, 99, 100`

### Question

Which option contains the valid collection of 2-point boundary values?

A. 3, 4, 99, 100

B. 4, 5, 100, 101

C. 4, 5, 99, 100

D. 3, 4, 99, 100

**Correct Answer: C**

Explanation:

- 4: Immediately below the minimum.
- 5: Minimum valid quantity.
- 99: Immediately below the discount threshold.
- 100: Discount threshold.

## 3.9 Combining EP and BVA

This is a common examination area.

EP identifies representative values from equivalence partitions.

BVA focuses on boundary values.

When both techniques are applied, a test suite may include:

- Invalid partition representative.
- Valid partition representative.
- Valid boundary values.
- Invalid boundary values.

### Example: Age Between 18 and 30

Valid partition:

`18–30`

Invalid partitions:

- `≤17`
- `≥31`

Using EP, we may choose:

- 10: Invalid representative.
- 25: Valid representative.
- 40: Invalid representative.

Using 2-point BVA:

- 17
- 18
- 30
- 31

A combined test set can therefore be:

`10, 17, 18, 25, 30, 31, 40`

However, avoid unnecessary duplication.

For example, 17 already represents the lower invalid boundary, so it may also provide coverage of the lower invalid partition.

A compact set could be:

`17, 18, 25, 30, 31`

This covers:

- Lower invalid partition.
- Valid partition.
- Upper invalid partition.
- Both valid boundaries.
- Both adjacent invalid values.

### Question From the Slides

A text field accepts ages between 18 and 30, inclusive.

Using EP and 2-point BVA, which option contains both valid boundary values and a valid equivalence value?

A. 17, 18, 20

B. 18, 30, 25

C. 18, 30, 31

D. 19, 20, 31

**Correct Answer: B**

Explanation:

- 18: Valid lower boundary.
- 30: Valid upper boundary.
- 25: Representative value from the valid partition.

Option B includes both valid boundary values and a valid EP representative.

---

# 4. Decision Table Testing

## 4.1 Definition

Decision Table Testing is a black-box test technique used when system behaviour depends on combinations of different conditions.

It captures the logical relationships between:

- Input conditions.
- Combinations of conditions.
- Expected actions or outcomes.

These relationships are represented in a tabular format.

### Why Do We Use Decision Table Testing?

Some requirements contain multiple conditions that influence the final system behaviour.

For example, an insurance premium may depend on:

- Customer age.
- Insurance category.
- Customer membership.
- Type of policy.

Testing these conditions independently may not be sufficient.

Decision tables help systematically identify combinations and their corresponding expected results.

## 4.2 Structure of a Decision Table

A decision table generally consists of four sections:

1. Conditions.
2. Condition alternatives.
3. Actions.
4. Action entries.

### Example

Consider a login system:

- Username must be valid.
- Password must be valid.
- If both are valid, allow login.
- Otherwise, reject login.

| Conditions / Rules | Rule 1 | Rule 2 | Rule 3 | Rule 4 |
|---|---|---|---|---|
| Username valid? | Yes | Yes | No | No |
| Password valid? | Yes | No | Yes | No |
| **Actions** | | | | |
| Allow login | Yes | No | No | No |
| Reject login | No | Yes | Yes | Yes |

Each column represents a rule, or a combination of condition outcomes.

Each rule can be used to derive a test case.

## 4.3 Number of Combinations

For N independent binary conditions:

`Number of combinations = 2^N`

Where:

N = Number of conditions.

| Number of Conditions | Combinations |
|---:|---:|
| 1 | 2 |
| 2 | 4 |
| 3 | 8 |
| 4 | 16 |
| 5 | 32 |
| 6 | 64 |

### Example

For two binary conditions:

`2² = 4 combinations`

For three binary conditions:

`2³ = 8 combinations`

**Important:** This is the theoretical number of combinations when each condition has two possible outcomes.

If conditions have more than two alternatives, the total number of combinations is the product of the number of alternatives for each condition.

For example:

- Condition 1 has 2 alternatives.
- Condition 2 has 3 alternatives.

Total combinations:

`2 × 3 = 6`

## 4.4 Decision Table Example: Hotel Upgrade

Consider a hotel offering room upgrades based on:

1. Whether the customer is a Citibank card member.
2. Whether the customer has a Silver or Platinum room.

Rules:

| Conditions / Rules | Rule 1 | Rule 2 | Rule 3 | Rule 4 |
|---|---|---|---|---|
| Citibank card member | Yes | Yes | No | No |
| Room type | Silver | Platinum | Silver | Platinum |
| **Actions** | | | | |
| Upgrade to Gold | Yes | No | No | No |
| Upgrade to Silver | N/A | Yes | N/A | No |

### Question

What is the expected result for:

- User X: Citibank card member with a Silver room.
- User Y: Non-Citibank member with a Platinum room.

For User X:

- Card member = Yes.
- Room type = Silver.
- Matches Rule 1.
- Upgrade to Gold.

For User Y:

- Card member = No.
- Room type = Platinum.
- Matches Rule 4.
- No upgrade.

**Correct Answer: D — User X gets a Gold upgrade; User Y gets no upgrade.**

## 4.5 Decision Table Example: Insurance Premium

Consider the following decision table:

| Conditions / Rules | Rule 1 | Rule 2 | Rule 3 | Rule 4 |
|---|---|---|---|---|
| Age | Below 21 | 21–29 | 30–50 | Above 50 |
| Insurance Class | A | A or B | B, C or D | C or D |
| **Actions** | | | | |
| Premium | £100 | £90 | £70 | £70 |
| Excess | £2,500 | £2,500 | £500 | £1,000 |

### Question

Which test case and expected result are valid?

A. 23-year-old, insurance class A, premium £90, excess £2,500.

B. 51-year-old, insurance class C, premium £100, excess £500.

C. 31-year-old, insurance class B, premium £70, excess £2,500.

D. 43-year-old, insurance class C, premium £100, excess £1,000.

**Correct Answer: A**

Explanation:

For option A:

- Age = 23 → Rule 2.
- Insurance class = A → Allowed under Rule 2.
- Premium = £90.
- Excess = £2,500.

The expected results match the decision table.

Why others are incorrect:

- B: Age 51 and class C match Rule 4, not Rule 1.
- C: Age 31 and class B match Rule 3, where excess is £500.
- D: Age 43 and class C match Rule 3, where premium is £70 and excess is £500.

## 4.6 Rules and Test Cases

Each column in a decision table represents a rule.

A rule is a particular combination of condition values and its associated actions.

For complete decision table coverage, each feasible rule should be exercised at least once.

### Important Terms

| Term | Meaning |
|---|---|
| Condition | An input or logical factor affecting system behaviour |
| Condition alternative | A possible value of a condition |
| Rule | A combination of condition alternatives |
| Action | The expected system behaviour |
| Rule coverage | Percentage of feasible rules exercised by test cases |

### Formula

`Decision Table Coverage = (Number of Rules Tested / Total Feasible Rules) × 100`

## 4.7 Don't-Care Values and Infeasible Combinations

A decision table may contain combinations that do not affect an outcome or cannot occur.

**Don't-care value (-):**

A condition value is irrelevant for a particular rule.

Example:

If an account is already locked, the password validity may not affect the expected action.

**Infeasible combination:**

A combination of conditions that cannot occur according to the requirements.

For example, a system might specify that a user cannot simultaneously be a guest and an authenticated administrator.

Do not blindly create tests for impossible combinations.

## 4.8 Common Exam Traps

1. A decision table is suitable when behaviour depends on combinations of conditions.
2. Each column represents a rule.
3. Each row generally represents a condition or action.
4. For N binary conditions, the theoretical number of combinations is 2^N.
5. Not every theoretical combination must necessarily become a test case if some are infeasible.
6. Decision table testing is a black-box technique.
7. It is particularly useful for business rules and complex logical combinations.

---

# 5. State Transition Testing

## 5.1 Definition

State Transition Testing is a black-box test technique used when the system's behaviour depends on its current state and the events or inputs that cause it to change state.

It focuses on:

- States.
- Events.
- Transitions.
- Actions.
- Resulting states.

### Why Do We Use State Transition Testing?

Many applications behave differently depending on their current state.

For example:

- A user can log in only when logged out.
- An account can become locked after repeated failed login attempts.
- An order moves from Created to Confirmed to Shipped.
- A payment moves from Pending to Successful or Failed.

Testing only individual inputs is insufficient when behaviour depends on the sequence of events.

## 5.2 Important Terminology

| Term | Meaning |
|---|---|
| State | A condition or situation in which a system exists |
| Event | An occurrence that triggers a possible state change |
| Transition | Movement from one state to another |
| Initial state | The state in which the system begins |
| Final state | The state reached after a transition |
| Valid transition | A transition permitted by the specification |
| Invalid transition | A transition not permitted by the specification |

## 5.3 State Transition Diagram (STD)

A State Transition Diagram visually represents states and the transitions between them.

A typical diagram uses:

- Nodes or boxes to represent states.
- Directed arrows to represent transitions.
- Labels on arrows to represent events or actions.

### Example: Three-State System

Consider a system with three states:

- S1
- S2
- S3

Transitions:

- A: S1 → S2
- B: S2 → S3
- C: S3 → S2
- D: S2 → S1

The diagram represents the permitted transitions.

A transition that is absent from the specified diagram can be considered invalid, unless the specification defines it elsewhere.

## 5.4 State Transition Table

A state transition table represents transitions in tabular form.

Example:

| Current State | Event | Next State |
|---|---|---|
| S1 | A | S2 |
| S2 | B | S3 |
| S3 | C | S2 |
| S2 | D | S1 |

The table provides a structured representation of the state transition behaviour.

## 5.5 Example: Water State Transition

Consider three states of water:

- ICE
- WATER
- VAPOUR

Transitions:

- A: ICE → WATER (melting)
- B: WATER → VAPOUR (vaporisation)
- C: VAPOUR → WATER (condensation)
- D: WATER → ICE (freezing)

### State Transition Diagram

```text
ICE  --A--> WATER --B--> VAPOUR
ICE  <--D-- WATER <--C-- VAPOUR
```

### Deriving Test Cases

| Test Case | Starting State | Transition | Final State |
|---|---|---|---|
| TC01 | ICE | A | WATER |
| TC02 | WATER | D | ICE |
| TC03 | WATER | B | VAPOUR |
| TC04 | VAPOUR | C | WATER |

Each test case exercises one valid transition.

## 5.6 Valid and Invalid Transitions

Consider a switch with three states:

- OFF
- ON
- FAULT

The diagram specifies:

- OFF → ON
- ON → OFF
- ON → FAULT
- FAULT → FAULT

Question:

Which transition is invalid?

A. OFF to ON

B. ON to OFF

C. FAULT to ON

D. ON to FAULT

**Correct Answer: C — FAULT to ON**

Explanation:

The diagram does not specify a transition from FAULT to ON.

The other three transitions are explicitly represented.

**Exam Trap:** A transition that looks logically possible is not automatically valid. Always follow the transitions specified in the diagram or table.

## 5.7 State Transition Sequences

A test case can cover a sequence of transitions rather than just one transition.

Consider the following state transition diagram:

- A: S0 → S1
- B: S1 → S2
- C: S2 → S0
- D: S1 → S0

Required state sequence:

`S1 → S0 → S1 → S2 → S0`

Identify the transitions:

1. S1 → S0 = D
2. S0 → S1 = A
3. S1 → S2 = B
4. S2 → S0 = C

Therefore, the required transition sequence is:

`D, A, B, C`

**Correct Answer: A — D, A, B, C**

### Exam Technique

When a question provides a state sequence:

1. Identify the starting state.
2. Read the next state.
3. Find the arrow connecting those two states.
4. Record its transition label.
5. Repeat until the entire sequence is covered.

Do not confuse the state labels with the transition labels.

## 5.8 State Transition Coverage

State transition testing can use different coverage objectives.

### A. State Coverage

Checks whether all specified states have been visited.

Formula:

`State Coverage = (States Visited / Total Specified States) × 100`

Example:

If a system has four states and tests visit all four:

State Coverage = 4/4 × 100 = 100%

### B. Valid Transition Coverage

Checks whether all specified valid transitions have been exercised.

Formula:

`Valid Transition Coverage = (Valid Transitions Exercised / Total Specified Valid Transitions) × 100`

Example:

If a diagram has five valid transitions and test cases exercise all five:

Coverage = 5/5 × 100 = 100%

### C. Transition Sequence Coverage

Checks whether the required sequences of transitions have been exercised.

For example:

`Logged Out → Logged In → Session Expired → Logged Out`

A test may need to exercise the complete sequence rather than isolated transitions.

**Important:** State coverage does not guarantee transition coverage.

A test suite can visit every state without exercising every valid transition.

## 5.9 State Transition Testing in Real Applications

### Example 1: Login Application

States:

- Logged Out.
- Logged In.
- Account Locked.

Possible transitions:

| Current State | Event | Next State |
|---|---|---|
| Logged Out | Valid credentials | Logged In |
| Logged Out | Repeated invalid credentials | Account Locked |
| Logged In | Logout | Logged Out |
| Account Locked | Valid credentials | Depends on unlock policy |

The final transition must follow the actual requirement. Do not assume that entering valid credentials automatically unlocks an account.

### Example 2: E-commerce Order

States:

- Created.
- Confirmed.
- Shipped.
- Delivered.
- Cancelled.

Possible transitions:

| Current State | Event | Next State |
|---|---|---|
| Created | Payment successful | Confirmed |
| Confirmed | Dispatch order | Shipped |
| Shipped | Delivery successful | Delivered |
| Created | Cancel order | Cancelled |

A tester should also verify prohibited transitions.

For example, an order that is already delivered should not normally move back to Created.

### Example 3: Payment Application

States:

- Initiated.
- Pending.
- Successful.
- Failed.

Possible transitions:

| Current State | Event | Next State |
|---|---|---|
| Initiated | Payment request sent | Pending |
| Pending | Bank approves | Successful |
| Pending | Bank declines | Failed |

Testers should verify the valid state changes and ensure that prohibited state changes are handled correctly.

---

# 6. Comparison of All Four Black-Box Techniques

| Technique | Main Focus | Best Used When | Example |
|---|---|---|---|
| Equivalence Partitioning | Groups of similar inputs | Inputs can be divided into classes | Age validation |
| Boundary Value Analysis | Values around boundaries | Defects are likely near limits | Minimum/maximum age |
| Decision Table Testing | Combinations of conditions | Multiple conditions determine an action | Insurance premium |
| State Transition Testing | States and transitions | Behaviour depends on current state and event sequence | Login/account locking |

## Quick Memory Trick

- EP → Divide inputs into groups.
- BVA → Test around boundaries.
- Decision Table → Test combinations of conditions.
- State Transition → Test movement between states.

---

# 7. Important Exam Traps

| Statement | Correct Understanding |
|---|---|
| EP divides input data into equivalence partitions. | True |
| All values in an equivalence partition are expected to behave the same way. | True |
| EP always requires one test for every possible input value. | False |
| EP includes valid and invalid partitions. | True |
| One test case can cover partitions from multiple input parameters. | True |
| BVA focuses on boundaries of equivalence partitions. | True |
| BVA is a white-box technique. | False |
| 2-point BVA uses two values around each boundary. | True |
| 3-point BVA uses three values around each boundary. | True |
| Decision tables represent combinations of conditions and actions. | True |
| Every binary decision table with three conditions has 8 theoretical combinations. | True |
| Every theoretical decision table combination must always be tested. | False |
| Each decision table column represents a rule. | True |
| State transition testing focuses on states and transitions. | True |
| A state transition diagram represents specified transitions. | True |
| State coverage guarantees transition coverage. | False |
| A transition not specified in the model should automatically be considered valid. | False |
| State transition testing is useful for workflows. | True |

---

# 8. Practice Questions — Equivalence Partitioning

**Original exam-oriented practice questions. These are not official ISTQB questions or verified past-paper questions.**

## Q1. Basic Equivalence Partitioning

An application accepts values between 10 and 50, inclusive.

How many equivalence partitions are present if values below and above the range are also considered?

A. 1

B. 2

C. 3

D. 4

**Correct Answer: C**

Explanation:

- Below 10: Invalid.
- 10–50: Valid.
- Above 50: Invalid.

Total = 3 partitions.

---

## Q2. Representative Values

A field accepts integers between 1 and 100.

Which set provides one representative value from each equivalence partition?

A. 1, 50, 100

B. 0, 50, 101

C. 1, 100

D. 0, 1, 100

**Correct Answer: B**

Explanation:

The three partitions are:

- Below 1.
- 1–100.
- Above 100.

Representatives: 0, 50, 101.

---

## Q3. Same Equivalence Partition

A system accepts a salary between ₹20,000 and ₹50,000.

Which set belongs to the same valid equivalence partition?

A. ₹10,000, ₹30,000, ₹60,000

B. ₹21,000, ₹35,000, ₹49,000

C. ₹19,999, ₹30,000, ₹50,001

D. ₹20,000, ₹50,000, ₹50,001

**Correct Answer: B**

Explanation:

All values in option B belong to the valid partition.

---

## Q4. Multiple Inputs

A form has two independent inputs:

- Age: Below 18, 18–60, above 60.
- Membership: Basic, Premium.

Assuming every combination is valid, what is the minimum number of tests required to cover every partition of both inputs?

A. 3

B. 4

C. 5

D. 6

**Correct Answer: A**

Explanation:

There are three age partitions and two membership partitions.

A single test can cover one age partition and one membership partition.

Three tests can cover all three age partitions and both membership partitions.

Example:

| Test | Age | Membership |
|---|---|---|
| TC01 | Below 18 | Basic |
| TC02 | 30 | Premium |
| TC03 | Above 60 | Basic |

---

## Q5. EP with Constraints

An apartment search form supports:

- Floor: Ground, First, Second or higher.
- Garden: None, Small, Large.

Only ground-floor apartments can have gardens.

What is the minimum number of tests to cover all floor and garden partitions using valid combinations?

A. 3

B. 4

C. 5

D. 6

**Correct Answer: C**

Explanation:

Three ground-floor tests cover all garden partitions.

Two additional tests cover first floor and second floor or higher with no garden.

Total = 5.

---

# 9. Practice Questions — Boundary Value Analysis

## Q6. Basic 2-Point BVA

An input accepts integers between 10 and 20, inclusive.

Which set represents 2-point BVA?

A. 9, 10, 20, 21

B. 10, 11, 19, 20

C. 9, 10, 11, 19, 20, 21

D. 10, 20

**Correct Answer: A**

Explanation:

- Lower boundary: 9 and 10.
- Upper boundary: 20 and 21.

---

## Q7. Basic 3-Point BVA

An application accepts values from 50 to 100, inclusive.

Which set represents 3-point BVA?

A. 49, 50, 100, 101

B. 49, 50, 51, 99, 100, 101

C. 50, 51, 99, 100

D. 48, 49, 50, 100, 101, 102

**Correct Answer: B**

Explanation:

Three values are selected around each boundary.

---

## Q8. Number of Test Cases

An integer field accepts values between 18 and 30.

How many test values are required for 3-point BVA?

A. 2

B. 4

C. 6

D. 8

**Correct Answer: C**

Explanation:

Three values around the lower boundary and three around the upper boundary.

Total = 6.

---

## Q9. Minimum Quantity

An order requires a minimum quantity of 5.

Which values represent the lower boundary using 2-point BVA?

A. 3 and 4

B. 4 and 5

C. 5 and 6

D. 4, 5 and 6

**Correct Answer: B**

Explanation:

- 4: Immediately below the boundary.
- 5: Boundary value.

---

## Q10. Discount Boundary

An application offers a 10% discount for quantities of 100 or more.

Which pair represents the upper threshold using 2-point BVA?

A. 98 and 99

B. 99 and 100

C. 100 and 101

D. 98, 99 and 100

**Correct Answer: B**

Explanation:

The discount boundary is 100.

The two values are 99 and 100.

---

## Q11. Combining EP and BVA

An application accepts ages from 18 to 30, inclusive.

Which option contains both valid boundary values and one valid equivalence representative?

A. 17, 18, 20

B. 18, 30, 25

C. 18, 30, 31

D. 19, 20, 31

**Correct Answer: B**

Explanation:

- 18: Valid lower boundary.
- 30: Valid upper boundary.
- 25: Valid partition representative.

---

## Q12. Identifying a Boundary Defect

An application accepts numbers from 1 to 10.

A developer implements:

```java
if (value > 1 && value < 10) {
    return true;
}
```

Which values are most likely to expose the defect?

A. 5 and 6

B. 2 and 9

C. 1 and 10

D. 4 and 7

**Correct Answer: C**

Explanation:

The implementation incorrectly excludes both valid boundary values.

The correct implementation should be:

```java
if (value >= 1 && value <= 10) {
    return true;
}
```

---

# 10. Practice Questions — Decision Table Testing

## Q13. Number of Combinations

A decision table has four independent binary conditions.

How many theoretical combinations are possible?

A. 4

B. 8

C. 16

D. 32

**Correct Answer: C**

Explanation:

`2⁴ = 16`

---

## Q14. Two Conditions

A system has two binary conditions:

- Valid username?
- Valid password?

How many theoretical rules are possible?

A. 2

B. 3

C. 4

D. 8

**Correct Answer: C**

Explanation:

`2² = 4`

---

## Q15. Decision Table Structure

In a decision table, each column generally represents:

A. A test environment.

B. A rule.

C. A test execution report.

D. A defect.

**Correct Answer: B**

Explanation:

Each column represents a combination of condition alternatives and the corresponding actions.

---

## Q16. Choosing the Technique

A banking application approves a loan based on:

- Credit score.
- Employment status.
- Existing debt.

Which technique is MOST suitable for systematically testing combinations of these conditions?

A. Boundary Value Analysis

B. Decision Table Testing

C. State Transition Testing

D. Statement Testing

**Correct Answer: B**

Explanation:

The expected action depends on combinations of multiple conditions.

---

## Q17. Decision Table Scenario

A system grants access when:

- User is active.
- User has valid credentials.

What should happen when the user is active but credentials are invalid?

A. Grant access.

B. Reject access.

C. Lock the database.

D. Ignore the credentials.

**Correct Answer: B**

Explanation:

Both conditions must be true for access to be granted.

---

# 11. Practice Questions — State Transition Testing

## Q18. State Transition Diagram

Which component represents a state in a typical state transition diagram?

A. Directed arrow.

B. Node or state box.

C. Test execution report.

D. Boundary line.

**Correct Answer: B**

Explanation:

Nodes or boxes represent states. Directed arrows represent transitions.

---

## Q19. Invalid Transition

A switch supports:

- OFF → ON.
- ON → OFF.
- ON → FAULT.
- FAULT → FAULT.

Which transition is invalid?

A. OFF → ON

B. ON → OFF

C. FAULT → ON

D. ON → FAULT

**Correct Answer: C**

Explanation:

FAULT → ON is not specified in the state transition model.

---

## Q20. Transition Sequence

A system has these transitions:

- A: S0 → S1
- B: S1 → S2
- C: S2 → S0
- D: S1 → S0

Which sequence covers:

`S1 → S0 → S1 → S2 → S0`

A. D, A, B, C

B. A, B, C, D

C. D, B, A, C

D. A, D, B, C

**Correct Answer: A**

Explanation:

- S1 → S0 = D
- S0 → S1 = A
- S1 → S2 = B
- S2 → S0 = C

---

## Q21. State Coverage

A system has five specified states.

A test suite visits all five states but does not exercise every valid transition.

Which statement is correct?

A. Both state and transition coverage are 100%.

B. State coverage is 100%, but transition coverage may be less than 100%.

C. Transition coverage is 100%, but state coverage is less than 100%.

D. Neither coverage can be calculated.

**Correct Answer: B**

Explanation:

Visiting every state does not guarantee that every transition has been exercised.

---

## Q22. Choosing State Transition Testing

A user account can be:

- Active.
- Suspended.
- Locked.

The application responds differently to login attempts depending on the current account status.

Which technique is MOST suitable?

A. Equivalence Partitioning

B. Boundary Value Analysis

C. State Transition Testing

D. Decision Table Testing

**Correct Answer: C**

Explanation:

The behaviour depends on the current state and the event.

---

## Q23. State Transition Table

What does a state transition table primarily represent?

A. Input ranges and their equivalence classes.

B. Current state, event and resulting state.

C. Source code statements and branches.

D. Business conditions and their combinations only.

**Correct Answer: B**

Explanation:

A state transition table maps a current state and an event to the resulting state.

---

# 12. Advanced Scenario-Based Questions

These questions combine multiple concepts and are intended to test application rather than memorisation.

## Q24. EP vs BVA

A system accepts a quantity from 10 to 100, inclusive.

A tester selects 10, 50 and 100.

Which statement is MOST accurate?

A. The tester has applied 2-point BVA.

B. The tester has selected values from the valid equivalence partition.

C. The tester has achieved 3-point BVA.

D. The tester has covered all valid and invalid partitions.

**Correct Answer: B**

Explanation:

All three values are inside the valid partition.

The set does not include invalid values immediately outside the boundaries.

---

## Q25. EP with Multiple Inputs

A registration form contains:

- Age: Below 18, 18–60, Above 60.
- Account type: Personal, Business.
- Country: India, Other countries.

Assuming every combination is valid, what is the minimum number of tests required to cover every partition of each input?

A. 3

B. 4

C. 6

D. 12

**Correct Answer: A**

Explanation:

There are three age partitions, two account-type partitions and two country partitions.

Each test can cover one partition from each input.

Three tests can cover all three age partitions and both partitions of the other inputs.

---

## Q26. Boundary Analysis

A system accepts marks between 35 and 100, inclusive.

Using 3-point BVA, which values should be selected?

A. 34, 35, 36, 99, 100, 101

B. 35, 36, 99, 100

C. 34, 35, 100, 101

D. 33, 34, 35, 100, 101, 102

**Correct Answer: A**

Explanation:

Three values around each boundary:

- Lower: 34, 35, 36.
- Upper: 99, 100, 101.

---

## Q27. Decision Table Application

An application grants a discount when:

- Customer is a premium member.
- Purchase amount is at least ₹5,000.

How many theoretical combinations are possible?

A. 2

B. 3

C. 4

D. 8

**Correct Answer: C**

Explanation:

Two binary conditions:

`2² = 4`

---

## Q28. State Transition Scenario

A payment application has the following states:

- Initiated.
- Pending.
- Successful.
- Failed.

A payment is initiated and then approved by the bank.

Which transition sequence is correct?

A. Initiated → Successful

B. Initiated → Pending → Successful

C. Pending → Initiated → Successful

D. Failed → Pending → Successful

**Correct Answer: B**

Explanation:

The payment first enters Pending after initiation. Bank approval then moves it to Successful.

---

## Q29. Choosing Between Techniques

A tester wants to validate an API field that accepts values between 1 and 100 and also wants to verify values around the minimum and maximum.

Which combination is MOST suitable?

A. Decision Table and State Transition Testing.

B. Equivalence Partitioning and Boundary Value Analysis.

C. White-box and Experience-based Testing.

D. Exploratory and Checklist-based Testing.

**Correct Answer: B**

Explanation:

EP identifies valid and invalid groups. BVA focuses on values around their boundaries.

---

## Q30. Combined Testing Scenario

An online shopping application has:

- Membership status: Regular or Premium.
- Cart value: Below ₹5,000 or at least ₹5,000.
- Order status: Created, Confirmed or Cancelled.

The discount depends on membership and cart value, while order behaviour depends on order status.

Which combination of techniques is MOST appropriate?

A. EP only.

B. BVA only.

C. Decision Table Testing and State Transition Testing, supplemented by EP/BVA for input values.

D. Statement Testing only.

**Correct Answer: C**

Explanation:

- Decision Table Testing: Membership and cart value determine discount eligibility.
- State Transition Testing: Order behaviour depends on order status and transitions.
- EP/BVA: Useful for partitioning and testing cart-value boundaries.

---

# 13. Answer Key — Quick Revision

| Q | Answer | Concept |
|---|---|---|
| 1 | C | Number of EPs |
| 2 | B | Representative values |
| 3 | B | Same equivalence partition |
| 4 | A | Multiple input partitions |
| 5 | C | EP with constraints |
| 6 | A | 2-point BVA |
| 7 | B | 3-point BVA |
| 8 | C | Number of 3-point tests |
| 9 | B | Lower boundary |
| 10 | B | Discount boundary |
| 11 | B | EP + BVA |
| 12 | C | Boundary defect |
| 13 | C | Decision table combinations |
| 14 | C | Two binary conditions |
| 15 | B | Decision table rules |
| 16 | B | Multiple conditions |
| 17 | B | Decision table outcome |
| 18 | B | State representation |
| 19 | C | Invalid transition |
| 20 | A | Transition sequence |
| 21 | B | State vs transition coverage |
| 22 | C | State-dependent behaviour |
| 23 | B | State transition table |
| 24 | B | EP representative values |
| 25 | A | Multiple-input EP |
| 26 | A | 3-point BVA |
| 27 | C | Decision table combinations |
| 28 | B | Payment state sequence |
| 29 | B | EP + BVA |
| 30 | C | Combining techniques |

---

# 14. One-Page Revision Sheet

## Equivalence Partitioning

- Divides input data into equivalence classes.
- Values within a partition are expected to behave similarly.
- Includes valid and invalid partitions.
- Select representative values from each partition.
- One test can cover partitions from multiple input parameters.

**Example:**

Valid age = 18–30.

Partitions:

- Below 18.
- 18–30.
- Above 30.

## Boundary Value Analysis

- Focuses on boundaries of equivalence partitions.
- Useful for detecting off-by-one defects.
- 2-point BVA tests two values around each boundary.
- 3-point BVA tests three values around each boundary.

For range 18–30:

**2-point:** `17, 18, 30, 31`

**3-point:** `17, 18, 19, 29, 30, 31`

## Decision Table Testing

- Tests combinations of conditions.
- Represents conditions and actions in tabular form.
- Each column represents a rule.
- For N binary conditions: `2^N` theoretical combinations.
- Useful for complex business rules.

## State Transition Testing

- Tests states and transitions.
- Uses state transition diagrams and tables.
- Valid transitions are specified by the system model.
- Invalid transitions are not permitted by the specification.
- State coverage does not guarantee transition coverage.

---

# 15. Commonly Confused Concepts

| Confusion | Correct Difference |
|---|---|
| EP vs BVA | EP tests representative values from groups; BVA tests around boundaries. |
| 2-point vs 3-point BVA | Two vs three values around each boundary. |
| EP vs Decision Table | EP groups similar input values; decision tables test combinations of conditions. |
| Decision Table vs State Transition | Decision tables focus on logical combinations; state transition focuses on state changes. |
| State Coverage vs Transition Coverage | Visiting all states does not guarantee exercising all transitions. |
| Valid vs Invalid Partition | Valid values are accepted; invalid values are rejected. |
| State vs Transition | State is a condition; transition is movement between states. |

---

# 16. Self-Assessment Checklist

Before moving to the next chapter, make sure you can:

### Equivalence Partitioning
- [ ] Explain valid and invalid equivalence partitions.
- [ ] Identify partitions from a requirement.
- [ ] Select representative values.
- [ ] Calculate minimum test cases for multiple inputs.
- [ ] Handle constraints between input parameters.

### Boundary Value Analysis
- [ ] Identify lower and upper boundaries.
- [ ] Calculate 2-point BVA values.
- [ ] Calculate 3-point BVA values.
- [ ] Differentiate valid and invalid boundary values.
- [ ] Solve combined EP and BVA questions.

### Decision Table Testing
- [ ] Identify conditions and actions.
- [ ] Construct a decision table.
- [ ] Calculate 2^N combinations for binary conditions.
- [ ] Identify the correct rule for a scenario.
- [ ] Recognise infeasible and don't-care combinations.

### State Transition Testing
- [ ] Identify states and transitions.
- [ ] Read a state transition diagram.
- [ ] Construct a state transition table.
- [ ] Identify invalid transitions.
- [ ] Derive a transition sequence from a state sequence.
- [ ] Differentiate state coverage and transition coverage.

---

# 17. Final Exam Strategy

| Question Pattern | What to Do |
|---|---|
| Identify equivalence classes | Divide the entire input domain into valid and invalid partitions. |
| Minimum EP test cases | Cover every partition, combining inputs where valid. |
| 2-point BVA | Select LB-1, LB, RB, RB+1. |
| 3-point BVA | Select LB-1, LB, LB+1, RB-1, RB, RB+1. |
| Decision table combinations | Calculate 2^N for N binary conditions. |
| Decision table scenario | Match all condition values to the correct rule. |
| Invalid state transition | Look for a transition not permitted by the model. |
| Transition sequence | Follow the state sequence and record each arrow label. |
| Coverage question | Distinguish states, transitions and transition sequences. |

**Recommended approach:** Practise numerical EP/BVA questions until you can solve them quickly. For decision tables and state transitions, draw the table or diagram before selecting the answer.

---
