# DBMS Notes
# Lossy vs Lossless Decomposition 


---

# Table of Contents

1. Introduction
2. What is Decomposition?
3. Why Do We Need Decomposition?
4. Everyday Life Analogy
5. Good Decomposition vs Bad Decomposition
6. What is Lossless Decomposition?
7. What is Lossy Decomposition?
8. Step-by-Step Examples
9. Comparison Table
10. Memory Tricks
11. Important Exam Points

---

# Introduction

One of the most important topics in **Normalization** is **Decomposition**.

Almost every university, GATE, NIELIT, and IBPS SO exam asks questions on:

- Lossless Decomposition
- Lossy Decomposition
- Functional Dependency
- Normal Forms

Students usually memorize definitions but fail to understand **why decomposition is needed**.

Once you understand the idea, you will never forget it.

---

# Imagine This...

Suppose you maintain one large table.

| StudentID | StudentName | Course | Faculty | FacultyRoom |
|-----------|-------------|---------|----------|-------------|
|101|Rahul|DBMS|Sharma|A101|
|102|Amit|OS|Verma|B202|
|103|Rahul|Java|Sharma|A101|

Looks okay?

Now imagine 50,000 students.

Problems arise:

- Duplicate faculty names
- Duplicate rooms
- Updating room everywhere
- Wasted storage
- More chances of mistakes

This is why we normalize.

---

# What is Decomposition?

## Definition

Decomposition means

> Breaking one large relation (table) into two or more smaller relations without losing important information.

Think of it as:

```
Large Table

↓

Smaller Tables
```

Example

Instead of

Student

|Roll|Name|Department|Department Head|

Create

Student

|Roll|Name|Department|

Department

|Department|Department Head|

Same information.

Less repetition.

Cleaner database.

---

# Simple Definition for Exams

> Decomposition is the process of dividing a relation into smaller relations to reduce redundancy and improve database design.

---

# Why Do We Need Decomposition?

Suppose this table exists.

Employee

|EmpID|EmpName|Department|Department Phone|

|101|Amit|IT|1111|

|102|Rahul|IT|1111|

|103|Riya|HR|2222|

Notice

Department Phone repeats.

If IT phone changes

1111

to

9999

You must update EVERY IT employee.

If you forget one row

Database becomes inconsistent.

This is called

**Update Anomaly**

---

Similarly

Deletion anomaly

Insert anomaly

also happen.

To remove these problems

we decompose tables.

---

# Everyday Analogy

Imagine your school notebook.

Instead of writing

Rahul
Class 10
School ABC
Principal Mr Sharma

100 times

You write

Student Notebook

|Student|Class|

School Notebook

|School|Principal|

Cleaner

Smaller

No repetition

Exactly same idea.

---

# Decomposition Should Preserve Information

Breaking a table is good.

But...

Breaking incorrectly is dangerous.

Suppose

Original Table

|Student|Course|

Rahul DBMS

Amit Java

Now divide into

Table1

|Student|

Rahul

Amit

Table2

|Course|

DBMS

Java

Can we reconstruct original table?

No.

Because

Rahul may study Java.

Amit may study DBMS.

We don't know.

Information is lost.

This is bad decomposition.

---

# Two Types of Decomposition

```
             Decomposition

              /          \

     Lossless           Lossy
```

---

# What is Lossless Decomposition?

## Simple Definition

Lossless means

**No information is lost after decomposition.**

We can always reconstruct the original table exactly.

No extra rows.

No missing rows.

Exactly same table.

---

Think

Original Table

↓

Split

↓

Join Again

↓

Original Table Back

Exactly Same

---

Formula

```
Original Table

↓

Decompose

↓

Join

↓

Original Table
```

If this happens

Lossless Decomposition

---

# Simple Example

Original Table

Employee

|EmpID|Name|Department|

101 Amit IT

102 Rahul HR

Split into

Employee

|EmpID|Name|

101 Amit

102 Rahul

Department

|EmpID|Department|

101 IT

102 HR

Now Join

EmpID matches

Result

|EmpID|Name|Department|

101 Amit IT

102 Rahul HR

Exactly same.

Nothing lost.

Hence

Lossless.

---

# Why is it Called Lossless?

Because

Nothing is lost.

```
Original Information

↓

Split

↓

Join

↓

Everything Returned
```

---

# Properties of Lossless Decomposition

✔ Original table recovered

✔ No fake rows

✔ No information loss

✔ Preferred in normalization

✔ Database remains correct

---

# Example 2

Original Relation

Student

|Roll|Name|Branch|

1 Rahul CS

2 Amit IT

Split

StudentInfo

|Roll|Name|

1 Rahul

2 Amit

BranchInfo

|Roll|Branch|

1 CS

2 IT

Join using Roll

Result

Exactly original.

Lossless.

---

# What is Lossy Decomposition?

Now suppose

Original Table

|Student|Course|

Rahul DBMS

Amit Java

Split

Students

Rahul

Amit

Courses

DBMS

Java

Join

Every student combines with every course.

Result

Rahul DBMS

Rahul Java

Amit DBMS

Amit Java

Original had only

Rahul DBMS

Amit Java

Now

Extra rows appeared.

Information changed.

This is

Lossy Decomposition.

---

# Simple Definition

Lossy decomposition means

Information cannot be recovered exactly after decomposition.

Extra tuples appear

or

Some original tuples disappear.

---

# Why is Lossy Dangerous?

Because database becomes wrong.

Example

Original

Rahul studies DBMS

Amit studies Java

After joining

Database says

Rahul studies Java

which is false.

---

# Properties of Lossy Decomposition

❌ Information lost

❌ Extra tuples generated

❌ Wrong answers

❌ Incorrect query results

❌ Never preferred

---

# Visual Understanding

Lossless

```
Original

ABC

↓

Split

↓

Join

↓

ABC
```

Lossy

```
Original

ABC

↓

Split

↓

Join

↓

ABCDXYZ
```

Extra information generated.

Wrong.

---

# Real-Life Analogy

Imagine cutting a photograph.

Suppose photo has

Mother

Father

Child

You cut into two halves carefully.

Later

Join.

Complete photo returns.

Lossless.

---

Now

Suppose

Pieces get mixed with another photo.

After joining

Mother

Father

Unknown Child

Wrong photo.

Lossy.

---

# Restaurant Analogy

Original Bill

|Table|Customer|Food|

1 Rahul Pizza

2 Amit Burger

Split

Customer Table

Rahul

Amit

Food Table

Pizza

Burger

Join

Now

Rahul Pizza

Rahul Burger

Amit Pizza

Amit Burger

Restaurant records become wrong.

Lossy.

---

# Train Reservation Analogy

Original

Passenger

Seat

Rahul S1

Amit S2

Split

Passengers

Rahul

Amit

Seats

S1

S2

Join

Rahul S2

Amit S1

Wrong reservation.

Lossy decomposition.

---

# School Example

Original

|Roll|Subject|

1 Math

2 Science

Split

Roll Table

1

2

Subject Table

Math

Science

Join

1 Math

1 Science

2 Math

2 Science

Wrong.

Lossy.

---

# Comparison

|Feature|Lossless|Lossy|
|--------|---------|------|
|Information Lost?|No|Yes|
|Original Table Recover?|Yes|No|
|Extra Tuples?|No|Yes|
|Preferred?|Yes|No|
|Normalization?|Used|Avoided|
|Database Correct?|Yes|No|

---

# Easy Memory Trick

Remember

```
LossLESS

LESS Loss

No Information Lost
```

---

Remember

```
LossY

WHY?

Why did information disappear?
```

---

# Another Memory Trick

Imagine

Glass of Water

Pour into two glasses.

Pour back.

Still same quantity.

Lossless.

---

Now

One glass leaks.

Pour back.

Water missing.

Lossy.

---

# Golden Rule

Whenever you decompose a relation, ask only one question:

> **Can I reconstruct the original table exactly by joining the decomposed tables?**

- **Yes → Lossless**
- **No → Lossy**

This single question solves most conceptual exam questions.

---

# Important Points for Exams

### Lossless

- No information loss
- Original relation recovered exactly
- No spurious (fake) tuples
- Always desirable
- Used during normalization

---

### Lossy

- Information lost
- Original relation cannot be recovered exactly
- Generates spurious tuples
- Gives incorrect query results
- Avoided in good database design

---

# Common Exam Mistakes

❌ Thinking "more tables = better"

Not always. The decomposition must also be **lossless**.

---

❌ Thinking "joining always returns the original table"

Wrong.

Joining incorrectly decomposed tables may create **extra rows**.

---

❌ Confusing redundancy with lossless

A table may have redundancy, but decomposition is considered successful only if it is **lossless**.

---

# One-Line Revision

- **Decomposition** → Breaking a large table into smaller tables.
- **Lossless Decomposition** → Original table is recovered exactly after joining.
- **Lossy Decomposition** → Original table cannot be recovered exactly; fake or missing rows occur.
- **Lossless = Good Database Design**
- **Lossy = Bad Database Design**

---

# Quick Revision Box

✅ Decomposition = Divide large relation.

✅ Lossless = No information loss.

✅ Lossy = Information loss.

✅ Lossless generates **no spurious tuples**.

✅ Lossy may generate **spurious tuples**.

✅ Normalization aims for **lossless decomposition**.

---

# DBMS Notes
# Lossy vs Lossless Decomposition (Part 2)
## Functional Dependency • Keys • Lossless Conditions • Chase Test • Exam Tricks
### Topper Notes | Simplest Language | IBPS SO IT Officer | GATE | University

---

# Table of Contents

1. Quick Revision
2. Functional Dependency (FD)
3. Why FD is Important in Decomposition
4. Super Key
5. Candidate Key
6. Primary Key
7. Prime vs Non-Prime Attribute
8. Why Keys Decide Lossless or Lossy
9. Condition for Lossless Decomposition
10. Shortcut Rule
11. Mathematical Rule
12. How to Identify Lossless in 30 Seconds
13. Chase Test (Step by Step)
14. Solved Examples
15. Exam Tricks
16. Common Mistakes
17. Revision Sheet

---

# Quick Revision

Part 1 taught us:

- Decomposition means breaking a large table into smaller tables.
- Lossless means no information is lost.
- Lossy means information is lost or extra tuples (spurious tuples) appear.

Now the biggest question is:

> **How do we know whether a decomposition is lossless or lossy?**

For that, we need **Functional Dependency (FD)** and **Keys**.

---

# Functional Dependency (FD)

## Simple Definition

A Functional Dependency tells us:

> One attribute uniquely determines another attribute.

Notation:

```
A → B
```

Read as:

```
A determines B
```

or

```
Knowing A, we can always find B.
```

---

## Example 1

Student Table

| Roll | Name |
|------|------|
|101|Rahul|
|102|Amit|
|103|Priya|

Every Roll Number belongs to exactly one student.

So,

```
Roll → Name
```

Correct.

---

## Example 2

Employee Table

|EmpID|Department|
|-----|----------|
|1|IT|
|2|HR|

```
EmpID → Department
```

Correct.

---

## Wrong Functional Dependency

Can we say

```
Department → EmpID
```

No.

Why?

IT department has many employees.

One department cannot determine exactly one employee.

So this FD is incorrect.

---

# Easy Trick

Ask yourself:

> If I know the value on the left, can I always predict exactly one value on the right?

If YES

It is a Functional Dependency.

---

# Why Functional Dependency Matters

Lossless decomposition depends on Functional Dependencies.

Without FD,

you cannot determine whether decomposition is good or bad.

Think of FD as the **rules of the database**.

---

# Super Key

## Definition

A Super Key is any set of attributes that uniquely identifies every row.

It may contain extra attributes.

---

Example

Student

|Roll|Name|Phone|

```
Roll
```

uniquely identifies every student.

So,

```
Roll
```

is a Super Key.

But

```
Roll + Name
```

also uniquely identifies every student.

Still a Super Key.

```
Roll + Name + Phone
```

also works.

Still a Super Key.

---

# Memory Trick

Super Key

```
Unique
+

May contain extra attributes
```

---

# Candidate Key

Candidate Key means

> Minimum Super Key.

No unnecessary attributes.

---

Example

```
Roll
```

is enough.

So

Candidate Key = Roll

But

```
Roll + Name
```

contains an extra attribute.

So

NOT Candidate Key.

---

# Memory Trick

Candidate Key

```
Unique

AND

Minimum
```

---

# Primary Key

One Candidate Key selected by the database designer becomes

Primary Key.

---

Example

Candidate Keys

```
Email

EmployeeID
```

Suppose database chooses EmployeeID.

Then

Primary Key = EmployeeID

---

# Prime Attribute

Attribute that belongs to at least one Candidate Key.

---

Example

Candidate Key

```
Roll
```

Prime Attribute

```
Roll
```

---

# Non-Prime Attribute

Attribute not present in any Candidate Key.

Example

```
Roll

Name

Department
```

Candidate Key

Roll

Prime

Roll

Non-prime

Name

Department

---

# Why Keys Matter?

Suppose

Original Relation

```
R(A,B,C)
```

FD

```
A → B
```

Decompose

```
R1(A,B)

R2(A,C)
```

Notice

Common Attribute

```
A
```

A determines B.

A is a key in R1.

Therefore

Lossless.

---

# Biggest Rule of Lossless Decomposition

Suppose

```
R

↓

R1

R2
```

Common attributes are

```
R1 ∩ R2
```

If the common attribute can determine all attributes of at least one table,

then decomposition is

**Lossless**

---

# Mathematical Rule

For decomposition

```
R → R1,R2
```

Lossless if

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

This is the most important formula.

Memorize it.

---

# Simple Language Version

Look at the common column.

Ask

Can this common column identify one complete table?

If YES

Lossless.

If NO

Lossy.

---

# Shortcut Rule

Suppose

```
Student(Roll,Name,Department)
```

Split

```
StudentInfo(Roll,Name)

DepartmentInfo(Roll,Department)
```

Common Attribute

```
Roll
```

Roll identifies StudentInfo completely.

Hence

Lossless.

---

# Another Example

Original

```
R(A,B,C)
```

FD

```
A → B

A → C
```

Split

```
R1(A,B)

R2(A,C)
```

Common

```
A
```

A identifies R1

A identifies R2

Therefore

Lossless.

---

# Counter Example

Original

```
R(A,B,C)
```

Split

```
R1(A,B)

R2(B,C)
```

FD

```
A → B
```

Common Attribute

```
B
```

Can B identify R1?

No.

Can B identify R2?

No.

Therefore

Lossy.

---

# 30-Second Identification Trick

STEP 1

Find common attributes.

STEP 2

Check Functional Dependency.

STEP 3

Ask

Can common attribute determine all columns of one table?

YES

Lossless

NO

Lossy

---

# Visual Trick

```
      R1

A B

      ∩

A

      ∩

A C

      R2
```

Common Attribute

A

A determines R1

Lossless

---

# Chase Test

One of the favorite GATE questions.

Don't worry.

Let's learn from scratch.

---

# What is Chase Test?

A systematic method to verify whether decomposition is

Lossless

or

Lossy.

---

# When to Use Chase Test?

Use when

- Multiple Functional Dependencies
- Confusing decomposition
- Competitive exams
- GATE
- University theory papers

---

# Chase Test Steps

Suppose

```
R(A,B,C)
```

Decompose

```
R1(A,B)

R2(A,C)
```

FD

```
A → B

A → C
```

---

## Step 1

Create table

|Relation|A|B|C|
|---------|--|--|--|
|R1|a1|b1|c2|
|R2|a1|b2|c1|

Same attributes

same symbols

Missing attributes

different symbols

---

## Step 2

Apply Functional Dependencies.

FD

```
A → B
```

Since A is same

Make B same.

---

FD

```
A → C
```

Make C same.

---

Result

Everything becomes identical.

Hence

Lossless.

---

# Easy Way to Remember Chase Test

```
Same Left Side

↓

Make Right Side Same
```

Repeat until

No further change.

---

If one complete row becomes identical

Lossless.

Otherwise

Lossy.

---

# Solved Example 1

Relation

```
R(A,B,C)
```

FD

```
A → B

B → C
```

Split

```
R1(A,B)

R2(B,C)
```

Common

```
B
```

Can

```
B → R1 ?
```

No.

Need A also.

Can

```
B → R2 ?
```

Yes

Because

```
B → C
```

So B determines

(B,C)

Hence

Lossless.

---

# Solved Example 2

```
R(A,B,C)
```

FD

```
A → B
```

Split

```
R1(A,C)

R2(B,C)
```

Common

```
C
```

Can C determine R1?

No.

Can C determine R2?

No.

Lossy.

---

# Solved Example 3

Relation

```
Employee(EmpID,Name,Department)
```

FD

```
EmpID → Name

EmpID → Department
```

Split

Employee

```
(EmpID,Name)
```

Department

```
(EmpID,Department)
```

Common

EmpID

EmpID determines both tables.

Lossless.

---

# Solved Example 4

Original

```
(Student,Course)
```

Split

```
Student

Course
```

Common Attribute

None.

Immediately

Lossy.

---

# Super Shortcut

No Common Attribute

↓

Always Lossy

because natural join becomes Cartesian Product.

This is a favorite MCQ.

---

# Important Exam Tricks

## Trick 1

Common Attribute is Candidate Key

↓

Always Lossless

---

## Trick 2

No Common Attribute

↓

Lossy

---

## Trick 3

Intersection should determine one complete relation.

---

## Trick 4

Extra tuples after Join

↓

Lossy

---

## Trick 5

Exact original relation after Join

↓

Lossless

---

# Common Mistakes

❌ Thinking every decomposition is good.

Wrong.

Only Lossless decomposition is desirable.

---

❌ Looking only at number of tables.

Wrong.

Need Functional Dependency.

---

❌ Ignoring common attributes.

Intersection is the first thing to check.

---

❌ Confusing Candidate Key with Super Key.

Candidate Key

=

Minimum Super Key.

---

# Memory Hacks

## FD

```
Left Side

knows

Right Side
```

---

## Candidate Key

```
Minimum

Unique
```

---

## Super Key

```
Unique

May contain extras
```

---

## Lossless Formula

```
Common Attribute

↓

Must determine one complete table.
```

---

# Golden Formula (Most Important)

For

```
R → R1,R2
```

Lossless iff

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

Remember this formula for **IBPS SO**, **GATE**, **University exams**, and **interviews**.

---

# Quick Revision Sheet

✅ Functional Dependency means one attribute determines another.

✅ Super Key uniquely identifies tuples.

✅ Candidate Key is the minimum Super Key.

✅ Primary Key is a selected Candidate Key.

✅ Lossless decomposition requires the common attributes to determine at least one decomposed relation completely.

✅ If there is **no common attribute**, the decomposition is generally **Lossy**.

✅ Chase Test is a systematic method to verify lossless decomposition.

---

# DBMS Notes
# Lossy vs Lossless Decomposition (Part 3)
## Solved Problems | Exam Tricks | GATE | IBPS SO | University | Placement

---

# Table of Contents

1. How Questions are Asked in Exams
2. Step-by-Step Solving Strategy
3. Shortcut Algorithm
4. Solved Problems (Basic to Advanced)
5. University Questions
6. GATE-Level Questions
7. IBPS SO Style Questions
8. Common Mistakes
9. Practice Questions (Without Solutions)
10. Topper Revision Sheet

---

# How Questions are Asked in Exams

Generally, examiners ask questions in one of the following ways:

### Type 1

Is the following decomposition Lossless or Lossy?

---

### Type 2

Prove whether the decomposition is Lossless using Functional Dependency.

---

### Type 3

Use Chase Test to verify decomposition.

---

### Type 4

Which of the following decompositions is Lossless?

(MCQ)

---

### Type 5

Which decomposition generates spurious tuples?

(MCQ)

---

# Universal Solving Strategy

Whenever you see a decomposition problem, follow these five steps.

```
STEP 1

Find Common Attributes

↓

STEP 2

Write Functional Dependencies

↓

STEP 3

Check

(Common Attribute)

↓

Determines R1 ?

OR

Determines R2 ?

↓

YES

Lossless

↓

NO

Lossy
```

---

# 10-Second Shortcut

Always remember

```
Common Attribute

↓

Must become

Key

of

At least one decomposed table.
```

If yes

Lossless

Else

Lossy

---

# Problem 1

Relation

```
R(A,B,C)
```

FD

```
A → B

A → C
```

Decompose into

```
R1(A,B)

R2(A,C)
```

---

## Step 1

Common Attribute

```
A
```

---

## Step 2

Can A determine R1?

```
A → B

Yes

A already contains A

Therefore

A determines

(A,B)
```

Yes.

---

## Final Answer

Lossless

---

# Problem 2

Relation

```
R(A,B,C)
```

FD

```
A → B
```

Decompose

```
R1(A,C)

R2(B,C)
```

---

Common Attribute

```
C
```

Can C determine R1?

No

Can C determine R2?

No

---

Answer

Lossy

---

# Problem 3

Relation

```
R(A,B,C,D)
```

FD

```
A → B

A → C

A → D
```

Split

```
R1(A,B)

R2(A,C,D)
```

---

Common Attribute

```
A
```

Can A determine R1?

Yes

Hence

Lossless

---

# Problem 4

Relation

```
R(Student,Course)
```

Split

```
Student

Course
```

---

Common Attribute

None

Immediately

Lossy

---

### Why?

Join becomes

Cartesian Product

Every student combines with every course.

Extra tuples appear.

---

# Problem 5

Relation

```
Employee(EmpID,Name,Department)
```

FD

```
EmpID → Name

EmpID → Department
```

Split

```
Employee(EmpID,Name)

Department(EmpID,Department)
```

---

Common Attribute

EmpID

EmpID determines both relations.

Answer

Lossless

---

# Problem 6

Relation

```
R(A,B,C,D)
```

FD

```
AB → C

AB → D
```

Split

```
R1(A,B,C)

R2(A,B,D)
```

---

Common Attribute

```
AB
```

AB determines R1

Therefore

Lossless

---

# Problem 7

Relation

```
R(A,B,C,D)
```

FD

```
A → B
```

Split

```
R1(A,C)

R2(B,D)
```

---

Common Attribute

None

Answer

Lossy

---

# Problem 8

Relation

```
R(A,B,C)
```

FD

```
B → C
```

Split

```
R1(A,B)

R2(B,C)
```

---

Common Attribute

```
B
```

Can B determine R2?

Yes

Because

```
B → C
```

So

B determines

(B,C)

Answer

Lossless

---

# Problem 9

Relation

```
R(A,B,C,D)
```

FD

```
C → D
```

Split

```
R1(A,B,C)

R2(C,D)
```

---

Common Attribute

```
C
```

Can C determine R2?

Yes

Answer

Lossless

---

# Problem 10

Relation

```
R(A,B,C,D)
```

FD

```
A → B
```

Split

```
R1(A,C)

R2(C,D)
```

---

Common Attribute

```
C
```

Can C determine R1?

No

Can C determine R2?

No

Answer

Lossy

---

# Problem 11

Relation

```
R(A,B,C,D)
```

FD

```
A → B

B → C

C → D
```

Split

```
R1(A,B)

R2(B,C,D)
```

---

Common Attribute

```
B
```

Can B determine R2?

Yes

```
B → C

C → D

Therefore

B → D
```

Hence

B determines

(B,C,D)

Lossless

---

# Problem 12

Relation

```
R(A,B,C)
```

FD

```
AB → C
```

Split

```
R1(A,B)

R2(B,C)
```

---

Common Attribute

```
B
```

Does

```
B → C
```

No

Need A also.

Lossy

---

# Problem 13

Relation

```
R(A,B,C,D)
```

FD

```
A → B

C → D
```

Split

```
R1(A,B)

R2(C,D)
```

Common Attribute

None

Lossy

---

# Problem 14

Relation

```
R(A,B,C,D)
```

FD

```
A → BC
```

Split

```
R1(A,B)

R2(A,C,D)
```

Common

A

Can A determine R1?

Yes

Lossless

---

# Problem 15

Relation

```
R(A,B,C)
```

FD

None

Split

```
R1(A,B)

R2(B,C)
```

---

Common

B

But no FD.

Cannot determine either relation.

Lossy

---

# University Style Question

Question

```
Given

R(A,B,C,D)

FD

A→B

B→C

C→D

Check whether

R1(A,B)

R2(B,C,D)

is Lossless.
```

---

Solution

Common Attribute

```
B
```

Now

```
B→C

C→D

Therefore

B→CD
```

Hence

```
B→BCD
```

Common attribute determines complete R2.

Therefore

Lossless.

---

# GATE Style Question

Relation

```
R(A,B,C,D,E)
```

FD

```
A→B

B→C

C→D

D→E
```

Split

```
R1(A,B,C)

R2(C,D,E)
```

---

Common

```
C
```

Can C determine R2?

```
C→D

D→E

Therefore

C→DE
```

Hence

```
C→CDE
```

Lossless

---

# Another GATE Question

Relation

```
R(A,B,C)
```

FD

```
A→B
```

Split

```
R1(A,C)

R2(B,C)
```

Common

```
C
```

No FD from C.

Lossy

---

# IBPS SO Pattern Question

Employee

```
(EmpID,Name,Dept)
```

FD

```
EmpID→Name

EmpID→Dept
```

Split

```
Employee(EmpID,Name)

Department(EmpID,Dept)
```

Answer

Lossless

---

# Interview Question 1

Can Lossless Decomposition still have redundancy?

Answer

Yes.

Lossless only guarantees

"No information loss."

It does not automatically remove all redundancy.

---

# Interview Question 2

Can Lossy Decomposition produce extra tuples?

Yes.

These extra tuples are called

**Spurious Tuples**

---

# Interview Question 3

Which decomposition is always preferred?

Lossless

---

# Interview Question 4

Why is Lossy decomposition avoided?

Because

- Wrong data
- Incorrect joins
- Incorrect reports
- Wrong query results

---

# Most Common Mistakes

## Mistake 1

Ignoring Common Attribute.

Always find intersection first.

---

## Mistake 2

Checking wrong FD.

Only check whether

Common Attribute

determines

Entire Relation.

---

## Mistake 3

Thinking

More tables

means

Better normalization.

Wrong.

---

## Mistake 4

Using Cartesian Product instead of Natural Join.

Lossless always uses

Natural Join.

---

## Mistake 5

Not considering transitive dependencies.

Example

```
B→C

C→D

Therefore

B→D
```

Competitive exams often test this.

---

# Practice Questions (Without Solutions)

---

## Question 1

```
R(A,B,C)

FD

A→B

Split

R1(A,B)

R2(A,C)
```

Lossless or Lossy?

---

## Question 2

```
R(A,B,C)

FD

A→B

Split

R1(A,C)

R2(B,C)
```

---

## Question 3

```
R(A,B,C,D)

FD

B→C

Split

R1(A,B)

R2(B,C,D)
```

---

## Question 4

```
R(A,B,C,D)

FD

AB→C

Split

R1(A,B,C)

R2(B,D)
```

---

## Question 5

```
R(A,B,C,D)

FD

A→BCD

Split

R1(A,B)

R2(A,C,D)
```

---

## Question 6

```
R(A,B,C)

No FD

Split

R1(A,B)

R2(B,C)
```

---

## Question 7

```
R(A,B,C,D)

FD

C→D

Split

R1(A,B,C)

R2(C,D)
```

---

## Question 8

```
R(A,B,C,D)

FD

A→B

B→C

Split

R1(A,B)

R2(B,C)
```

---

## Question 9

```
R(Student,Course)

Split

Student

Course
```

---

## Question 10

```
R(EmpID,Name,Dept)

FD

EmpID→Name

EmpID→Dept

Split

(EmpID,Name)

(EmpID,Dept)
```

---

# Expected Answers

|Question|Answer|
|----------|------|
|1|Lossless|
|2|Lossy|
|3|Lossy|
|4|Lossy|
|5|Lossless|
|6|Lossy|
|7|Lossless|
|8|Lossless|
|9|Lossy|
|10|Lossless|

---

# Topper Revision Sheet

## Always Follow This Algorithm

```
Find Common Attribute

↓

Apply Functional Dependency

↓

Can Common Attribute determine

Entire R1

OR

Entire R2 ?

↓

YES

Lossless

↓

NO

Lossy
```

---

# Golden Rules

✅ Lossless decomposition preserves all information.

✅ Lossy decomposition introduces spurious tuples or loses information.

✅ If there is **no common attribute**, the decomposition is **always Lossy**.

✅ If the **intersection is a key of at least one decomposed relation**, the decomposition is **Lossless**.

✅ Natural Join is used to reconstruct the original relation.

✅ Cartesian Product usually indicates a bad decomposition.

---

# Formula Sheet

## Lossless Condition

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

---

## Shortcut

```
Intersection

↓

Key of one table

↓

Lossless
```

---

## Red Flag

```
No Common Attribute

↓

Lossy
```

---
# DBMS Notes
# Lossy vs Lossless Decomposition (Part 4)
## 75+ MCQs | PYQs | Interview Questions | Cheat Sheet | One-Liners | Revision Notes
### Topper Notes | IBPS SO IT Officer | GATE | NIELIT | University | Placements

---

# Table of Contents

1. Basic MCQs
2. Intermediate MCQs
3. Advanced MCQs
4. Previous Year Pattern Questions
5. Assertion & Reason Questions
6. Fill in the Blanks
7. One-Liners
8. Interview Questions
9. Cheat Sheet
10. Complete Revision Sheet

---

# Section 1 : Basic MCQs

## MCQ 1

Decomposition means

A. Combining tables

B. Splitting relation into smaller relations

C. Deleting tuples

D. Creating indexes

✅ Answer

**B**

---

## MCQ 2

Which decomposition is preferred?

A. Lossy

B. Lossless

C. Random

D. Partial

✅ Answer

**B**

---

## MCQ 3

Lossless decomposition preserves

A. Indexes

B. Data only

C. All information

D. Keys only

✅ Answer

**C**

---

## MCQ 4

Lossy decomposition may generate

A. Candidate Keys

B. Primary Keys

C. Spurious Tuples

D. Foreign Keys

✅ Answer

**C**

---

## MCQ 5

Normalization aims to achieve

A. Lossy decomposition

B. Lossless decomposition

C. Duplicate records

D. Bigger tables

✅ Answer

**B**

---

## MCQ 6

Information loss occurs in

A. BCNF

B. Lossless

C. Lossy

D. Primary Key

✅ Answer

**C**

---

## MCQ 7

Lossless decomposition is verified using

A. Bubble Sort

B. Functional Dependency

C. Queue

D. Stack

✅ Answer

**B**

---

## MCQ 8

Which join reconstructs the original relation?

A. Cartesian Product

B. Natural Join

C. Left Join

D. Right Join

✅ Answer

**B**

---

## MCQ 9

Which decomposition avoids spurious tuples?

A. Lossy

B. Lossless

C. Random

D. Partial

✅ Answer

**B**

---

## MCQ 10

A decomposition producing incorrect rows is

A. Lossless

B. Dependency Preserving

C. Lossy

D. Normalized

✅ Answer

**C**

---

# Section 2 : Intermediate MCQs

## MCQ 11

The condition for lossless decomposition is

A.

```
R1 ∪ R2
```

B.

```
R1 − R2
```

C.

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

D.

None

✅ Answer

**C**

---

## MCQ 12

Which attribute is checked first while solving decomposition problems?

A. Candidate Key

B. Primary Key

C. Common Attribute

D. Foreign Key

✅ Answer

**C**

---

## MCQ 13

A decomposition without any common attribute is generally

A. Lossless

B. Lossy

C. BCNF

D. 3NF

✅ Answer

**B**

---

## MCQ 14

Spurious tuples appear due to

A. Good normalization

B. Lossy decomposition

C. Candidate Key

D. Foreign Key

✅ Answer

**B**

---

## MCQ 15

Functional Dependency is written as

A.

```
A=B
```

B.

```
A↔B
```

C.

```
A→B
```

D.

```
A+B
```

✅ Answer

**C**

---

## MCQ 16

A Candidate Key is

A. Largest Super Key

B. Minimum Super Key

C. Any Attribute

D. Composite Key

✅ Answer

**B**

---

## MCQ 17

Which key may contain extra attributes?

A. Candidate Key

B. Primary Key

C. Super Key

D. Foreign Key

✅ Answer

**C**

---

## MCQ 18

Which key is selected from Candidate Keys?

A. Foreign Key

B. Composite Key

C. Primary Key

D. Alternate Key

✅ Answer

**C**

---

## MCQ 19

Which decomposition gives the exact original table after joining?

A. Lossless

B. Lossy

C. Random

D. Weak

✅ Answer

**A**

---

## MCQ 20

Extra tuples generated after join are called

A. Prime Tuples

B. Candidate Tuples

C. Spurious Tuples

D. Composite Tuples

✅ Answer

**C**

---

# Section 3 : Advanced MCQs

## MCQ 21

Given

```
R(A,B,C)

FD

A→B

A→C
```

Decomposition

```
(A,B)

(A,C)
```

Answer

A. Lossless

B. Lossy

C. Cannot Determine

D. None

✅ Answer

**A**

---

## MCQ 22

Given

```
R(A,B,C)

FD

A→B
```

Split

```
(A,C)

(B,C)
```

Answer

A. Lossless

B. Lossy

C. BCNF

D. 3NF

✅ Answer

**B**

---

## MCQ 23

```
R(A,B,C,D)

FD

B→C
```

Split

```
(A,B)

(B,C,D)
```

Answer

A. Lossless

B. Lossy

C. BCNF

D. None

✅ Answer

**A**

---

## MCQ 24

If the common attribute is a key for one relation, decomposition is

A. Lossy

B. Lossless

C. Random

D. Impossible

✅ Answer

**B**

---

## MCQ 25

Lossless decomposition guarantees

A. More tables

B. Exact reconstruction

C. Smaller memory

D. Faster CPU

✅ Answer

**B**

---

# Section 4 : Previous Year Pattern Questions

## PYQ 1

Which of the following is NOT true?

A. Lossless preserves information

B. Lossy may generate spurious tuples

C. Lossless produces extra tuples

D. Functional Dependency helps verify decomposition

✅ Answer

**C**

---

## PYQ 2

Normalization aims to

A. Increase redundancy

B. Remove redundancy

C. Increase anomalies

D. Increase duplication

✅ Answer

**B**

---

## PYQ 3

The Chase Test is used for

A. Sorting

B. Searching

C. Verifying Lossless Decomposition

D. Encryption

✅ Answer

**C**

---

## PYQ 4

Natural Join is used to

A. Delete tuples

B. Recover relation

C. Insert tuples

D. Create indexes

✅ Answer

**B**

---

## PYQ 5

Which is undesirable?

A. Candidate Key

B. Functional Dependency

C. Lossy Decomposition

D. BCNF

✅ Answer

**C**

---

# Section 5 : Assertion & Reason

## Question 1

Assertion

Lossless decomposition preserves information.

Reason

Joining decomposed tables reconstructs the original relation exactly.

A. Both True, Reason explains Assertion

B. Both True, Reason incorrect

C. Assertion True, Reason False

D. Both False

✅ Answer

**A**

---

## Question 2

Assertion

Lossy decomposition is preferred.

Reason

It removes all redundancy.

✅ Answer

**D**

---

## Question 3

Assertion

Spurious tuples occur in Lossy decomposition.

Reason

Incorrect joins create extra tuples.

✅ Answer

**A**

---

## Question 4

Assertion

Functional Dependencies help determine lossless decomposition.

Reason

They identify relationships among attributes.

✅ Answer

**A**

---

## Question 5

Assertion

Natural Join is used to reconstruct decomposed relations.

Reason

Cartesian Product always gives the original relation.

✅ Answer

**C**

---

# Section 6 : Fill in the Blanks

1.

Lossless decomposition causes **__________** information loss.

✅ No

---

2.

Lossy decomposition creates **__________ tuples**.

✅ Spurious

---

3.

A Functional Dependency is represented by **__________**.

✅ →

---

4.

The minimum Super Key is called **__________**.

✅ Candidate Key

---

5.

Normalization aims for **__________ decomposition**.

✅ Lossless

---

6.

The common attribute should determine at least **__________ relation**.

✅ One

---

7.

The Chase Test verifies **__________ decomposition**.

✅ Lossless

---

8.

Natural Join reconstructs the **__________ relation**.

✅ Original

---

9.

Extra rows generated after joining are called **__________ tuples**.

✅ Spurious

---

10.

No common attribute generally leads to **__________ decomposition**.

✅ Lossy

---

# Section 7 : One-Liners

- Decomposition divides one relation into smaller relations.
- Lossless decomposition preserves all information.
- Lossy decomposition loses information or creates spurious tuples.
- Functional Dependencies determine relationships among attributes.
- Candidate Key is the minimum Super Key.
- Primary Key is a chosen Candidate Key.
- Super Key may contain unnecessary attributes.
- Natural Join reconstructs decomposed relations.
- Cartesian Product usually indicates a bad decomposition.
- Normalization prefers Lossless decomposition.

---

# Section 8 : Frequently Asked Interview Questions

## Q1. What is decomposition?

Breaking a relation into smaller relations to reduce redundancy while preserving information.

---

## Q2. Difference between Lossless and Lossy decomposition?

|Lossless|Lossy|
|---------|------|
|No information loss|Information lost|
|No spurious tuples|Spurious tuples appear|
|Preferred|Avoided|

---

## Q3. What are spurious tuples?

Extra tuples generated after joining incorrectly decomposed relations.

---

## Q4. Why is Lossless decomposition important?

Because it guarantees correct reconstruction of the original relation.

---

## Q5. What is the role of Functional Dependency?

It helps determine whether a decomposition is Lossless or Lossy.

---

## Q6. What is the Chase Test?

A systematic algorithm to verify Lossless decomposition.

---

## Q7. Which join is used after decomposition?

Natural Join.

---

## Q8. Can Lossless decomposition still have redundancy?

Yes. Lossless only ensures no information loss; redundancy may still exist until proper normalization.

---

## Q9. Is every normalized table automatically Lossless?

Good normalization algorithms aim to ensure Lossless decomposition.

---

## Q10. What is the biggest shortcut for exams?

Check whether the **common attribute is a key of at least one decomposed relation**.

---

# Section 9 : Ultimate Cheat Sheet

## Formula

```
Lossless

(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

---

## 5-Step Shortcut

```
Find Common Attribute

↓

Find FD

↓

Common Attribute

↓

Key of one table?

↓

YES

Lossless

↓

NO

Lossy
```

---

## Memory Trick

```
LossLESS

LESS Loss

No Information Lost
```

---

```
LossY

WHY?

Why is information missing?
```

---

## Red Flags

🚨 No common attribute

→ Lossy

---

🚨 Extra tuples after join

→ Lossy

---

🚨 Exact original relation recovered

→ Lossless

---

# Section 10 : Complete Topic Summary

## Lossless Decomposition

✔ No information loss

✔ Original relation recovered

✔ No spurious tuples

✔ Preferred in normalization

✔ Correct query results

✔ Verified using Functional Dependencies

✔ Natural Join reconstructs original relation

---

## Lossy Decomposition

✘ Information loss

✘ Incorrect reconstruction

✘ Spurious tuples

✘ Incorrect query results

✘ Avoided in database design

---

# 10 Golden Rules (Must Remember)

1. Decomposition means splitting a relation into smaller relations.

2. Lossless decomposition preserves all information.

3. Lossy decomposition loses information or creates spurious tuples.

4. Normalization always aims for Lossless decomposition.

5. Functional Dependencies are essential for checking decomposition.

6. Check the **common attribute (intersection)** first.

7. If the common attribute determines **one complete relation**, the decomposition is Lossless.

8. No common attribute generally means Lossy decomposition.

9. Natural Join is used to reconstruct the original relation.

10. The Chase Test is the standard algorithm to verify Lossless decomposition.

---

# Last-Minute Revision (30 Seconds Before Exam)

✅ Decomposition = Divide table.

✅ Lossless = Join returns the **exact** original table.

✅ Lossy = Join creates **extra or missing** rows.

✅ Spurious Tuples = Fake rows created after join.

✅ Candidate Key = Minimum Super Key.

✅ Super Key = Unique identifier (may have extra attributes).

✅ Functional Dependency = `A → B`.

✅ Lossless Formula:

```
(R1 ∩ R2) → R1

OR

(R1 ∩ R2) → R2
```

✅ No Common Attribute = Usually Lossy.

✅ Common Attribute is a Key = Lossless.

---

